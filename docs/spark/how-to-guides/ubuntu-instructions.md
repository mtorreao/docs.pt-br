---
title: Compilar um aplicativo .NET para Apache Spark no Ubuntu
description: Saiba como criar seu .NET para Apache Spark aplicativo no Ubuntu
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 77daad7298c41d21054db9174f30a8d1ed12648d
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687786"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-ubuntu"></a><span data-ttu-id="f2907-103">Saiba como criar seu .NET para Apache Spark aplicativo no Ubuntu</span><span class="sxs-lookup"><span data-stu-id="f2907-103">Learn how to build your .NET for Apache Spark application on Ubuntu</span></span>

<span data-ttu-id="f2907-104">Este artigo ensina como criar seu .NET para aplicativos Apache Spark no Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="f2907-104">This article teaches you how to build your .NET for Apache Spark applications on Ubuntu.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f2907-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f2907-105">Prerequisites</span></span>

<span data-ttu-id="f2907-106">Se você já tiver todos os pré-requisitos a seguir, pule para as etapas de [compilação](#build) .</span><span class="sxs-lookup"><span data-stu-id="f2907-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

1. <span data-ttu-id="f2907-107">Baixar e instalar o **[SDK do .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)** -a instalação do SDK adiciona o `dotnet` ferramentas ao seu caminho.</span><span class="sxs-lookup"><span data-stu-id="f2907-107">Download and install **[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)** - installing the SDK adds the `dotnet` toolchain to your path.</span></span>  <span data-ttu-id="f2907-108">Há suporte para o .NET Core 2,1, 2,2 e 3,1.</span><span class="sxs-lookup"><span data-stu-id="f2907-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>

2. <span data-ttu-id="f2907-109">Instale o **[OpenJDK 8](https://openjdk.java.net/install/)**.</span><span class="sxs-lookup"><span data-stu-id="f2907-109">Install **[OpenJDK 8](https://openjdk.java.net/install/)**.</span></span>

   - <span data-ttu-id="f2907-110">Você pode usar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f2907-110">You can use the following command:</span></span>

   ```bash
   sudo apt install openjdk-8-jdk
   ```

   * <span data-ttu-id="f2907-111">Verifique se você pode executar a `java` partir de sua linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f2907-111">Verify you are able to run `java` from your command-line.</span></span>

      <span data-ttu-id="f2907-112">Saída de exemplo de versão Java:</span><span class="sxs-lookup"><span data-stu-id="f2907-112">Sample java -version output:</span></span>

      ```bash
      openjdk version "1.8.0_191"
      OpenJDK Runtime Environment (build 1.8.0_191-8u191-b12-2ubuntu0.18.04.1-b12)
      OpenJDK 64-Bit Server VM (build 25.191-b12, mixed mode)
      ```

   * <span data-ttu-id="f2907-113">Se você já tiver várias versões do OpenJDK instaladas e quiser selecionar o OpenJDK 8, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f2907-113">If you already have multiple OpenJDK versions installed and want to select OpenJDK 8, use the following command:</span></span>

      ```bash
      sudo update-alternatives --config java
      ```

3. <span data-ttu-id="f2907-114">Instale o **[Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi)**.</span><span class="sxs-lookup"><span data-stu-id="f2907-114">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>

   * <span data-ttu-id="f2907-115">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f2907-115">Run the following command:</span></span>

      ```bash
      mkdir -p ~/bin/maven
      cd ~/bin/maven
      wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
      tar -xvzf apache-maven-3.6.0-bin.tar.gz
      ln -s apache-maven-3.6.0 current
      export M2_HOME=~/bin/maven/current
      export PATH=${M2_HOME}/bin:${PATH}
      source ~/.bashrc
      ```

       <span data-ttu-id="f2907-116">Observe que essas variáveis de ambiente serão perdidas quando você fechar o terminal.</span><span class="sxs-lookup"><span data-stu-id="f2907-116">Note that these environment variables will be lost when you close your terminal.</span></span> <span data-ttu-id="f2907-117">Se você quiser que as alterações sejam permanentes, adicione as `export` linhas ao `~/.bashrc` arquivo.</span><span class="sxs-lookup"><span data-stu-id="f2907-117">If you want the changes to be permanent, add the `export` lines to your `~/.bashrc` file.</span></span>

   * <span data-ttu-id="f2907-118">Verifique se você pode executar a `mvn` partir de sua linha de comando</span><span class="sxs-lookup"><span data-stu-id="f2907-118">Verify you are able to run `mvn` from your command-line</span></span>

       <span data-ttu-id="f2907-119">Exemplo de saída MVN-Version:</span><span class="sxs-lookup"><span data-stu-id="f2907-119">Sample mvn -version output:</span></span>

       ```output
       Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T18:41:47Z)
       Maven home: ~/bin/apache-maven-3.6.0
       Java version: 1.8.0_191, vendor: Oracle Corporation, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
       Default locale: en, platform encoding: UTF-8
       OS name: "linux", version: "4.4.0-17763-microsoft", arch: "amd64", family: "unix"
       ```

4. <span data-ttu-id="f2907-120">Instale o **[Apache Spark 2.3 +](https://spark.apache.org/downloads.html)**.</span><span class="sxs-lookup"><span data-stu-id="f2907-120">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
<span data-ttu-id="f2907-121">Baixe [Apache Spark 2.3 +](https://spark.apache.org/downloads.html) e extraia-o em uma pasta local (por exemplo, `~/bin/spark-3.0.1-bin-hadoop2.7` ).</span><span class="sxs-lookup"><span data-stu-id="f2907-121">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (e.g., `~/bin/spark-3.0.1-bin-hadoop2.7`).</span></span> <span data-ttu-id="f2907-122">(As versões do Spark com suporte são 2,3. \*, 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 e 3.0.1)</span><span class="sxs-lookup"><span data-stu-id="f2907-122">(The supported spark versions are 2.3.\*, 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 and 3.0.1)</span></span>

   ```bash
   tar -xvzf /path/to/spark-3.0.1-bin-hadoop2.7.tgz -C ~/bin/spark-3.0.1-bin-hadoop2.7
   ```

   * <span data-ttu-id="f2907-123">Adicionar as [variáveis de ambiente](https://www.java.com/en/download/help/path.xml) necessárias `SPARK_HOME` (por exemplo, `~/bin/spark-3.0.1-bin-hadoop2.7/` ) e `PATH` (por exemplo, `$SPARK_HOME/bin:$PATH` )</span><span class="sxs-lookup"><span data-stu-id="f2907-123">Add the necessary [environment variables](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` (e.g., `~/bin/spark-3.0.1-bin-hadoop2.7/`) and `PATH` (e.g., `$SPARK_HOME/bin:$PATH`)</span></span>

      ```bash
      export SPARK_HOME=~/bin/spark-3.0.1-hadoop2.7
      export PATH="$SPARK_HOME/bin:$PATH"
      source ~/.bashrc
      ```

      <span data-ttu-id="f2907-124">Observe que essas variáveis de ambiente serão perdidas quando você fechar o terminal.</span><span class="sxs-lookup"><span data-stu-id="f2907-124">Note that these environment variables will be lost when you close your terminal.</span></span> <span data-ttu-id="f2907-125">Se você quiser que as alterações sejam permanentes, adicione as `export` linhas ao `~/.bashrc` arquivo.</span><span class="sxs-lookup"><span data-stu-id="f2907-125">If you want the changes to be permanent, add the `export` lines to your `~/.bashrc` file.</span></span>

   * <span data-ttu-id="f2907-126">Verifique se você pode executar a `spark-shell` partir de sua linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f2907-126">Verify you are able to run `spark-shell` from your command-line.</span></span>

      <span data-ttu-id="f2907-127">Exemplo de saída do console:</span><span class="sxs-lookup"><span data-stu-id="f2907-127">Sample console output:</span></span>

      ```
      Welcome to
            ____              __
           / __/__  ___ _____/ /__
          _\ \/ _ \/ _ `/ __/  '_/
         /___/ .__/\_,_/_/ /_/\_\   version 3.0.1
            /_/

      Using Scala version 2.12.10 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
      Type in expressions to have them evaluated.
      Type :help for more information.

      scala> sc
      res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
      ```

<span data-ttu-id="f2907-128">Verifique se você pode executar `dotnet` o,, `java` `mvn` , `spark-shell` de sua linha de comando antes de passar para a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="f2907-128">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command-line before you move to the next section.</span></span> <span data-ttu-id="f2907-129">Existe uma maneira melhor?</span><span class="sxs-lookup"><span data-stu-id="f2907-129">Feel there is a better way?</span></span> <span data-ttu-id="f2907-130">[Abra um problema](https://github.com/dotnet/spark/issues) e sinta-se à vontade para contribuir.</span><span class="sxs-lookup"><span data-stu-id="f2907-130">Please [open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

## <a name="build"></a><span data-ttu-id="f2907-131">Build</span><span class="sxs-lookup"><span data-stu-id="f2907-131">Build</span></span>

<span data-ttu-id="f2907-132">Para o restante deste guia, você precisará ter clonado o .NET para o repositório Apache Spark em seu computador, por exemplo, `~/dotnet.spark/` .</span><span class="sxs-lookup"><span data-stu-id="f2907-132">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine e.g., `~/dotnet.spark/`.</span></span>

```bash
git clone https://github.com/dotnet/spark.git ~/dotnet.spark
```

### <a name="build-net-for-spark-scala-extensions-layer"></a><span data-ttu-id="f2907-133">Compilar .NET para camada de extensões do Spark escalares</span><span class="sxs-lookup"><span data-stu-id="f2907-133">Build .NET for Spark Scala extensions layer</span></span>

<span data-ttu-id="f2907-134">Quando você envia um aplicativo .NET, o .NET for Apache Spark tem a lógica necessária escrita em escalares que informa Apache Spark como lidar com suas solicitações (por exemplo, solicitação para criar uma nova sessão do Spark, solicitação para transferir dados do lado do .NET para o lado da JVM, etc.).</span><span class="sxs-lookup"><span data-stu-id="f2907-134">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (e.g., request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="f2907-135">Essa lógica pode ser encontrada no [código-fonte escalar do .net para Apache Spark](https://github.com/dotnet/spark/tree/master/src/scala).</span><span class="sxs-lookup"><span data-stu-id="f2907-135">This logic can be found in the [.NET for Apache Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="f2907-136">A próxima etapa é criar o .NET para Apache Spark camada de extensão escalabilidade:</span><span class="sxs-lookup"><span data-stu-id="f2907-136">The next step is to build the .NET for Apache Spark Scala extension layer:</span></span>

```bash
cd src/scala
mvn clean package
```

<span data-ttu-id="f2907-137">Você deve ver os JARs criados para as versões do Spark com suporte:</span><span class="sxs-lookup"><span data-stu-id="f2907-137">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2-3\target\microsoft-spark-2-3_2.11-<spark-dotnet-version>.jar`
* `microsoft-spark-2-4\target\microsoft-spark-2-4_2.11-<spark-dotnet-version>.jar`
* `microsoft-spark-3-0\target\microsoft-spark-3-0_2.12-<spark-dotnet-version>.jar`

### <a name="build-net-sample-applications-using-net-core-cli"></a><span data-ttu-id="f2907-138">Crie aplicativos de exemplo .NET usando o CLI do .NET Core</span><span class="sxs-lookup"><span data-stu-id="f2907-138">Build .NET sample applications using .NET Core CLI</span></span>

<span data-ttu-id="f2907-139">Esta seção explica como criar os [aplicativos de exemplo](https://github.com/dotnet/spark/tree/master/examples) para .net para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="f2907-139">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="f2907-140">Essas etapas ajudarão a compreender o processo de criação geral de qualquer aplicativo .NET para Spark.</span><span class="sxs-lookup"><span data-stu-id="f2907-140">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

1. <span data-ttu-id="f2907-141">Crie o trabalho:</span><span class="sxs-lookup"><span data-stu-id="f2907-141">Build the worker:</span></span>

   ```dotnetcli
   cd ~/dotnet.spark/src/csharp/Microsoft.Spark.Worker/
   dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   ```

   <span data-ttu-id="f2907-142">Exemplo de saída do console:</span><span class="sxs-lookup"><span data-stu-id="f2907-142">Sample console output:</span></span>

   ```bash
   user@machine:/home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker$ dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

      Restore completed in 36.03 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker/Microsoft.Spark.Worker.csproj.
      Restore completed in 35.94 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.1/Microsoft.Spark.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/Microsoft.Spark.Worker.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/
   ```

2. <span data-ttu-id="f2907-143">Compile os exemplos:</span><span class="sxs-lookup"><span data-stu-id="f2907-143">Build the samples:</span></span>

   ```dotnetcli
   cd ~/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/
   dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   ```

   <span data-ttu-id="f2907-144">Exemplo de saída do console:</span><span class="sxs-lookup"><span data-stu-id="f2907-144">Sample console output:</span></span>

   ```bash
   user@machine:/home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples$ dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

      Restore completed in 37.11 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Restore completed in 281.63 ms for /home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/Microsoft.Spark.CSharp.Examples.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.1/Microsoft.Spark.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/Microsoft.Spark.CSharp.Examples.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/
   ```  

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="f2907-145">Executar o .NET para aplicativos de exemplo do Spark</span><span class="sxs-lookup"><span data-stu-id="f2907-145">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="f2907-146">Depois de criar os exemplos, você pode usar o `spark-submit` para enviar seus aplicativos .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2907-146">Once you build the samples, you can use `spark-submit` to submit your .NET Core apps.</span></span> <span data-ttu-id="f2907-147">Verifique se você seguiu a seção de [pré-requisitos](#prerequisites) e instalou o Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="f2907-147">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

1. <span data-ttu-id="f2907-148">Defina a `DOTNET_WORKER_DIR` `PATH` variável de ambiente ou para incluir o caminho em que o `Microsoft.Spark.Worker` binário foi gerado (por exemplo, `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish` ).</span><span class="sxs-lookup"><span data-stu-id="f2907-148">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (e.g., `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish`).</span></span>

   ```bash
   export DOTNET_WORKER_DIR=~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish
   ```

2. <span data-ttu-id="f2907-149">Abra um terminal e vá para o diretório em que o binário do aplicativo foi gerado (por exemplo, `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish` ).</span><span class="sxs-lookup"><span data-stu-id="f2907-149">Open a terminal and go to the directory where your app binary has been generated (e.g., `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish`).</span></span>

   ```bash
   cd ~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish
   ```

3. <span data-ttu-id="f2907-150">A execução do aplicativo segue a estrutura básica:</span><span class="sxs-lookup"><span data-stu-id="f2907-150">Running your app follows the basic structure:</span></span>

   ```bash
   spark-submit \
     [--jars <any-jars-your-app-is-dependent-on>] \
     --class org.apache.spark.deploy.dotnet.DotnetRunner \
     --master local \
     <path-to-microsoft-spark-jar> \
     <path-to-your-app-binary> <argument(s)-to-your-app>
   ```

   <span data-ttu-id="f2907-151">Aqui estão alguns exemplos que você pode executar:</span><span class="sxs-lookup"><span data-stu-id="f2907-151">Here are some examples you can run:</span></span>

   * <span data-ttu-id="f2907-152">**[Microsoft.Spark.Examples.Sql.Batch. Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="f2907-152">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Batch.Basic $SPARK_HOME/examples/src/main/resources/people.json
      ```

   * <span data-ttu-id="f2907-153">**[Microsoft. Spark. examples. Sql. streaming. StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="f2907-153">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredNetworkWordCount localhost 9999
      ```

   * <span data-ttu-id="f2907-154">**[Microsoft. Spark. examples. Sql. streaming. StructuredKafkaWordCount (com acesso ao Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="f2907-154">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
      ```

   * <span data-ttu-id="f2907-155">**[Microsoft. Spark. examples. Sql. streaming. StructuredKafkaWordCount (jars fornecidos)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="f2907-155">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --jars path/to/net.jpountz.lz4/lz4-1.3.0.jar,path/to/org.apache.kafka/kafka-clients-0.10.0.1.jar,path/to/org.apache.spark/spark-sql-kafka-0-10_2.11-2.3.2.jar,`path/to/org.slf4j/slf4j-api-1.7.6.jar,path/to/org.spark-project.spark/unused-1.0.0.jar,path/to/org.xerial.snappy/snappy-java-1.1.2.6.jar \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
       ```
