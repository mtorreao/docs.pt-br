---
title: Implantar um aplicativo .NET para Apache Spark no Amazon EMR Spark
description: Descubra como implantar um aplicativo do .NET para Apache Spark no Amazon EMR Spark.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: dd1cfdf12266b55d9dbc0210479b89ba68c59a38
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688066"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="69b46-103">Implantar um aplicativo .NET para Apache Spark no Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="69b46-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="69b46-104">Este tutorial ensina a implantar um aplicativo do .NET para Apache Spark no Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="69b46-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="69b46-105">O [Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) é uma plataforma de cluster gerenciada que simplifica a execução de estruturas de Big Data na AWS.</span><span class="sxs-lookup"><span data-stu-id="69b46-105">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

<span data-ttu-id="69b46-106">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="69b46-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="69b46-107">Preparar o Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="69b46-107">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="69b46-108">Publicar seu aplicativo Spark .NET</span><span class="sxs-lookup"><span data-stu-id="69b46-108">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="69b46-109">Implantar seu aplicativo no Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="69b46-109">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="69b46-110">Executar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="69b46-110">Run your app</span></span>

> [!Note]
> <span data-ttu-id="69b46-111">O AWS EMR Spark é baseado em Linux.</span><span class="sxs-lookup"><span data-stu-id="69b46-111">AWS EMR Spark is Linux-based.</span></span> <span data-ttu-id="69b46-112">Portanto, se você estiver interessado em implantar seu aplicativo no AWS EMR Spark, verifique se seu aplicativo é .NET Standard compatível e se você usa o compilador .NET Core para compilar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="69b46-112">Therefore, if you are interested in deploying your app to AWS EMR Spark, make sure your app is .NET Standard compatible and that you use .NET Core compiler to compile your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69b46-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="69b46-113">Prerequisites</span></span>

<span data-ttu-id="69b46-114">Antes de começar, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="69b46-114">Before you start, do the following:</span></span>

* <span data-ttu-id="69b46-115">Baixe a [CLI da AWS](https://aws.amazon.com/cli/).</span><span class="sxs-lookup"><span data-stu-id="69b46-115">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="69b46-116">Baixe o [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) para seu computador local.</span><span class="sxs-lookup"><span data-stu-id="69b46-116">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="69b46-117">Esse é um script auxiliar que você usa posteriormente para copiar arquivos dependentes do .NET para Apache Spark para os nós de trabalho do cluster do Spark.</span><span class="sxs-lookup"><span data-stu-id="69b46-117">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="69b46-118">Preparar dependências de trabalho</span><span class="sxs-lookup"><span data-stu-id="69b46-118">Prepare worker dependencies</span></span>

<span data-ttu-id="69b46-119">O **Microsoft.Spark.Worker** é um componente de back-end que reside nos nós de trabalho individuais do seu cluster do Spark.</span><span class="sxs-lookup"><span data-stu-id="69b46-119">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="69b46-120">Quando você deseja executar uma UDF em C# (função definida pelo usuário), o Spark precisa entender como iniciar o .NET CLR para executar o UDF.</span><span class="sxs-lookup"><span data-stu-id="69b46-120">When you want to execute a C# UDF (User-Defined Function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="69b46-121">O **Microsoft.Spark.Worker** fornece uma coleção de classes para o Spark que habilitam essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="69b46-121">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="69b46-122">Selecione uma versão do netcoreapp do Linux do [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) para ser implantada em seu cluster.</span><span class="sxs-lookup"><span data-stu-id="69b46-122">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="69b46-123">Por exemplo, se você quiser `.NET for Apache Spark v1.0.0` usar `netcoreapp3.1` o, você baixará [Microsoft. Spark. Worker. netcoreapp 3.1. Linux-x64-1.0.0. tar. gz](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="69b46-123">For example, if you want `.NET for Apache Spark v1.0.0` using `netcoreapp3.1`, you'd download [Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span></span>

2. <span data-ttu-id="69b46-124">Carregue `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) para um sistema de arquivos distribuído (por exemplo, S3) ao qual seu cluster tem acesso.</span><span class="sxs-lookup"><span data-stu-id="69b46-124">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="69b46-125">Preparar seu aplicativo .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="69b46-125">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="69b46-126">Siga o tutorial de [Introdução](get-started.md) para compilar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="69b46-126">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="69b46-127">Publique seu aplicativo .NET do Spark como independente.</span><span class="sxs-lookup"><span data-stu-id="69b46-127">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="69b46-128">Execute o comando a seguir no Linux.</span><span class="sxs-lookup"><span data-stu-id="69b46-128">Run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp3.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="69b46-129">Produza `<your app>.zip` para os arquivos publicados.</span><span class="sxs-lookup"><span data-stu-id="69b46-129">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="69b46-130">Execute o comando a seguir no Linux usando `zip`.</span><span class="sxs-lookup"><span data-stu-id="69b46-130">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="69b46-131">Carregue os seguintes itens para um sistema de arquivos distribuído (por exemplo, S3) ao qual seu cluster tem acesso:</span><span class="sxs-lookup"><span data-stu-id="69b46-131">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="69b46-132">`microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`: Esse jar é incluído como parte do pacote NuGet do [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) e é colocado no diretório de saída da compilação do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="69b46-132">`microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="69b46-133">Arquivos (como arquivos de dependência ou dados comuns acessíveis a cada trabalho) ou assemblies (como DLLs que contêm suas funções definidas pelo usuário ou bibliotecas das quais seu aplicativo depende) serão colocados no diretório de trabalho de cada executor.</span><span class="sxs-lookup"><span data-stu-id="69b46-133">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="69b46-134">Implantar no Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="69b46-134">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="69b46-135">O [Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) é uma plataforma de cluster gerenciada que simplifica a execução de estruturas de Big Data na AWS.</span><span class="sxs-lookup"><span data-stu-id="69b46-135">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE]
> <span data-ttu-id="69b46-136">O Amazon EMR Spark é baseado em Linux.</span><span class="sxs-lookup"><span data-stu-id="69b46-136">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="69b46-137">Portanto, se você estiver interessado em implantar seu aplicativo no Amazon EMR Spark, verifique se seu aplicativo é compatível com o .Net Standard e se você usa o [compilador do .NET Core](https://dotnet.microsoft.com/download) para compilar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="69b46-137">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="69b46-138">Implantar o Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="69b46-138">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="69b46-139">Esta etapa só é necessária na criação do cluster.</span><span class="sxs-lookup"><span data-stu-id="69b46-139">This step is only required at cluster creation.</span></span>

<span data-ttu-id="69b46-140">Execute `install-worker.sh` durante a criação do cluster usando [Ações de Inicialização](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span><span class="sxs-lookup"><span data-stu-id="69b46-140">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="69b46-141">Execute o seguinte comando no Linux usando a CLI da AWS.</span><span class="sxs-lookup"><span data-stu-id="69b46-141">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr create-cluster \
--name "Test cluster" \
--release-label emr-5.23.0 \
--use-default-roles \
--ec2-attributes KeyName=myKey \
--applications Name=Spark \
--instance-count 3 \
--instance-type m1.medium \
--bootstrap-actions Path=s3://mybucket/<some dir>/install-worker.sh,Name="Install Microsoft.Spark.Worker",Args=["aws","s3://mybucket/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz","/usr/local/bin"]
```

## <a name="run-your-app"></a><span data-ttu-id="69b46-142">Executar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="69b46-142">Run your app</span></span>

<span data-ttu-id="69b46-143">Há duas maneiras de executar seu aplicativo no Amazon EMR Spark: spark-submit e Etapas do Amazon EMR.</span><span class="sxs-lookup"><span data-stu-id="69b46-143">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="69b46-144">Usar spark-submit</span><span class="sxs-lookup"><span data-stu-id="69b46-144">Use spark-submit</span></span>

<span data-ttu-id="69b46-145">Você pode usar o comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabalhos do .NET para Apache Spark para o Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="69b46-145">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="69b46-146">`ssh` em um dos nós no cluster.</span><span class="sxs-lookup"><span data-stu-id="69b46-146">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="69b46-147">Execute `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="69b46-147">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="69b46-148">Usar as etapas do Amazon EMR</span><span class="sxs-lookup"><span data-stu-id="69b46-148">Use Amazon EMR Steps</span></span>

<span data-ttu-id="69b46-149">As [Etapas do Amazon EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) podem ser usadas para enviar trabalhos para a estrutura do Spark instalada no cluster EMR.</span><span class="sxs-lookup"><span data-stu-id="69b46-149">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="69b46-150">Execute o seguinte comando no Linux usando a CLI da AWS.</span><span class="sxs-lookup"><span data-stu-id="69b46-150">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="69b46-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="69b46-151">Next steps</span></span>

<span data-ttu-id="69b46-152">Neste tutorial, você implantou seu aplicativo .NET para Apache Spark para o Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="69b46-152">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="69b46-153">Para exemplos de projetos do .NET para Apache Spark, continue no GitHub.</span><span class="sxs-lookup"><span data-stu-id="69b46-153">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="69b46-154">Exemplos do .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="69b46-154">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
