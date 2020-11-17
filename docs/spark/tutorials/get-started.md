---
title: Introdução ao .NET para Apache Spark
description: Descubra como executar um .NET para Apache Spark aplicativo usando o .NET Core no Windows, no macOS e no Ubuntu.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 16ccc8f40f290c4bc10f03d1f4d1b296b17f6b11
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687812"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="491b7-103">Tutorial: introdução ao .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="491b7-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="491b7-104">Este tutorial ensina como executar um .NET para Apache Spark aplicativo usando o .NET Core no Windows, no macOS e no Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="491b7-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, macOS, and Ubuntu.</span></span>

<span data-ttu-id="491b7-105">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="491b7-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="491b7-106">Prepare seu ambiente para .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="491b7-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="491b7-107">Escreva seu primeiro .NET para Apache Spark aplicativo</span><span class="sxs-lookup"><span data-stu-id="491b7-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="491b7-108">Crie e execute seu .NET para Apache Spark aplicativo</span><span class="sxs-lookup"><span data-stu-id="491b7-108">Build and run your .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="491b7-109">Prepare o seu ambiente</span><span class="sxs-lookup"><span data-stu-id="491b7-109">Prepare your environment</span></span>

<span data-ttu-id="491b7-110">Antes de começar a escrever seu aplicativo, você precisa configurar algumas dependências de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="491b7-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="491b7-111">Se você puder executar `dotnet` `java` o,, `spark-shell` no ambiente de linha de comando, seu ambiente já estará preparado e você poderá pular para a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="491b7-111">If you can run `dotnet`, `java`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="491b7-112">Se você não puder executar um ou todos os comandos, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="491b7-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="491b7-113">1. instalar o .NET</span><span class="sxs-lookup"><span data-stu-id="491b7-113">1. Install .NET</span></span>

<span data-ttu-id="491b7-114">Para começar a criar aplicativos .NET, você precisa baixar e instalar o SDK do .NET (Software Development Kit).</span><span class="sxs-lookup"><span data-stu-id="491b7-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="491b7-115">Baixe e instale o [SDK do .NET Core](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="491b7-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="491b7-116">A instalação do SDK adiciona a cadeia de ferramentas `dotnet` a seu caminho.</span><span class="sxs-lookup"><span data-stu-id="491b7-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="491b7-117">Depois de instalar o SDK do .NET Core, abra um novo prompt de comando ou terminal e execute `dotnet` .</span><span class="sxs-lookup"><span data-stu-id="491b7-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="491b7-118">Se o comando executar e imprimir as informações sobre como usar dotnet, o poderá passar para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="491b7-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="491b7-119">Se você receber um `'dotnet' is not recognized as an internal or external command` erro, verifique se você abriu um **novo** prompt de comando ou terminal antes de executar o comando.</span><span class="sxs-lookup"><span data-stu-id="491b7-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="491b7-120">2. instalar o Java</span><span class="sxs-lookup"><span data-stu-id="491b7-120">2. Install Java</span></span>

<span data-ttu-id="491b7-121">Instale o [Java 8,1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) para Windows e MacOS, ou [OpenJDK 8](https://openjdk.java.net/install/) para Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="491b7-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and macOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="491b7-122">Selecione a versão apropriada para seu sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="491b7-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="491b7-123">Por exemplo, selecione **jdk-8u201-windows-x64.exe** para um computador x64 do Windows (como mostrado abaixo) ou **JDK-8u231-MacOSX-x64. dmg** para MacOS.</span><span class="sxs-lookup"><span data-stu-id="491b7-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for macOS.</span></span> <span data-ttu-id="491b7-124">Em seguida, use o comando `java` para verificar a instalação.</span><span class="sxs-lookup"><span data-stu-id="491b7-124">Then, use the command `java` to verify the installation.</span></span>

![Download do Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="491b7-126">3. instalar o software de compactação</span><span class="sxs-lookup"><span data-stu-id="491b7-126">3. Install compression software</span></span>

<span data-ttu-id="491b7-127">Apache Spark é baixado como um arquivo. tgz compactado.</span><span class="sxs-lookup"><span data-stu-id="491b7-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="491b7-128">Use um programa de extração, como [7-zip](https://www.7-zip.org/) ou [WinZip](https://www.winzip.com/), para extrair o arquivo.</span><span class="sxs-lookup"><span data-stu-id="491b7-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="491b7-129">4. instalar o Apache Spark</span><span class="sxs-lookup"><span data-stu-id="491b7-129">4. Install Apache Spark</span></span>

<span data-ttu-id="491b7-130">[Baixe e instale o Apache Spark](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="491b7-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="491b7-131">Você precisará selecionar a partir da versão 2,3. \* ou 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 ou 3.0.1 (.NET para Apache Spark não é compatível com outras versões do Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="491b7-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0, or 3.0.1 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="491b7-132">Os comandos usados nas etapas a seguir pressupõem que você tenha [baixado e instalado Apache Spark 3.0.1](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="491b7-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 3.0.1](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="491b7-133">Se você quiser usar uma versão diferente, substitua o **3.0.1** pelo número de versão apropriado.</span><span class="sxs-lookup"><span data-stu-id="491b7-133">If you wish to use a different version, replace **3.0.1** with the appropriate version number.</span></span> <span data-ttu-id="491b7-134">Em seguida, extraia o arquivo **. tar** e os arquivos de Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="491b7-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="491b7-135">Para extrair o arquivo **. tar** aninhado:</span><span class="sxs-lookup"><span data-stu-id="491b7-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="491b7-136">Localize o arquivo **Spark-3.0.1-bin-Hadoop 2.7. tgz** que você baixou.</span><span class="sxs-lookup"><span data-stu-id="491b7-136">Locate the **spark-3.0.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="491b7-137">Clique com o botão direito do mouse no arquivo e selecione **7-zip-> extrair aqui**.</span><span class="sxs-lookup"><span data-stu-id="491b7-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="491b7-138">o **Spark-3.0.1-bin-Hadoop 2.7. tar** é criado junto com o arquivo **. tgz** que você baixou.</span><span class="sxs-lookup"><span data-stu-id="491b7-138">**spark-3.0.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="491b7-139">Para extrair os arquivos de Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="491b7-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="491b7-140">Clique com o botão direito do mouse em **Spark-3.0.1-bin-Hadoop 2.7. tar** e selecione **7-zip-> extrair arquivos...**</span><span class="sxs-lookup"><span data-stu-id="491b7-140">Right-click on **spark-3.0.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="491b7-141">Insira **C:\bin** no campo **extrair para** .</span><span class="sxs-lookup"><span data-stu-id="491b7-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="491b7-142">Desmarque a caixa de seleção abaixo do campo **extrair para** .</span><span class="sxs-lookup"><span data-stu-id="491b7-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="491b7-143">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="491b7-143">Select **OK**.</span></span>
* <span data-ttu-id="491b7-144">Os arquivos de Apache Spark são extraídos para C:\bin\spark-3.0.1-bin-hadoop2.7</span><span class="sxs-lookup"><span data-stu-id="491b7-144">The Apache Spark files are extracted to C:\bin\spark-3.0.1-bin-hadoop2.7</span></span>\

![Instalar Spark](./media/spark-extract-with-7-zip.png)

<span data-ttu-id="491b7-146">Execute os comandos a seguir para definir as variáveis de ambiente usadas para localizar Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="491b7-146">Run the following commands to set the environment variables used to locate Apache Spark.</span></span> <span data-ttu-id="491b7-147">No Windows, certifique-se de executar o prompt de comando no modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="491b7-147">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="491b7-148">Windows</span><span class="sxs-lookup"><span data-stu-id="491b7-148">Windows</span></span>](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin"
```

#### <a name="maclinux"></a>[<span data-ttu-id="491b7-149">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="491b7-149">Mac/Linux</span></span>](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-3.0.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

<span data-ttu-id="491b7-150">Depois de instalar tudo e definir suas variáveis de ambiente, abra um **novo** prompt de comando ou terminal e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="491b7-150">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

```text
spark-submit --version
```

<span data-ttu-id="491b7-151">Se o comando executar e imprimir as informações de versão, você poderá passar para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="491b7-151">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="491b7-152">Se você receber um `'spark-submit' is not recognized as an internal or external command` erro, certifique-se de ter aberto um **novo** prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="491b7-152">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="491b7-153">5. instalar o .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="491b7-153">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="491b7-154">Baixe a versão [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) do .net para Apache Spark github.</span><span class="sxs-lookup"><span data-stu-id="491b7-154">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="491b7-155">Por exemplo, se você estiver em um computador Windows e planeja usar o .NET Core, [Baixe a versão Windows x64 netcoreapp 3.1](https://github.com/dotnet/spark/releases).</span><span class="sxs-lookup"><span data-stu-id="491b7-155">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases).</span></span>

<span data-ttu-id="491b7-156">Para extrair o Microsoft. Spark. Worker:</span><span class="sxs-lookup"><span data-stu-id="491b7-156">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="491b7-157">Localize o arquivo de **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip** que você baixou.</span><span class="sxs-lookup"><span data-stu-id="491b7-157">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="491b7-158">Clique com o botão direito do mouse e selecione **7-zip-> extrair arquivos...**.</span><span class="sxs-lookup"><span data-stu-id="491b7-158">Right-click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="491b7-159">Insira **C:\bin** no campo **extrair para** .</span><span class="sxs-lookup"><span data-stu-id="491b7-159">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="491b7-160">Desmarque a caixa de seleção abaixo do campo **extrair para** .</span><span class="sxs-lookup"><span data-stu-id="491b7-160">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="491b7-161">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="491b7-161">Select **OK**.</span></span>

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="491b7-162">6. instalar o WinUtils (somente Windows)</span><span class="sxs-lookup"><span data-stu-id="491b7-162">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="491b7-163">O .NET para Apache Spark requer que o WinUtils seja instalado junto com Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="491b7-163">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="491b7-164">[Baixar winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="491b7-164">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="491b7-165">Em seguida, copie WinUtils para **C:\bin\spark-3.0.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="491b7-165">Then, copy WinUtils into **C:\bin\spark-3.0.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="491b7-166">Se você estiver usando uma versão diferente do Hadoop, que é anotada no final do nome da pasta de instalação do Spark, [Selecione a versão do WinUtils](https://github.com/steveloughran/winutils) que é compatível com sua versão do Hadoop.</span><span class="sxs-lookup"><span data-stu-id="491b7-166">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="491b7-167">7. definir DOTNET_WORKER_DIR e verificar dependências</span><span class="sxs-lookup"><span data-stu-id="491b7-167">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="491b7-168">Execute um dos comandos a seguir para definir a `DOTNET_WORKER_DIR` variável de ambiente, que é usada pelos aplicativos .net para localizar o .net para Apache Spark binários de trabalho.</span><span class="sxs-lookup"><span data-stu-id="491b7-168">Run one of the following commands to set the `DOTNET_WORKER_DIR` environment variable, which is used by .NET apps to locate .NET for Apache Spark worker binaries.</span></span> <span data-ttu-id="491b7-169">Certifique-se de substituir `<PATH-DOTNET_WORKER_DIR>` pelo diretório onde você baixou e extraiu o `Microsoft.Spark.Worker` .</span><span class="sxs-lookup"><span data-stu-id="491b7-169">Make sure to replace `<PATH-DOTNET_WORKER_DIR>` with the directory where you downloaded and extracted the `Microsoft.Spark.Worker`.</span></span> <span data-ttu-id="491b7-170">No Windows, certifique-se de executar o prompt de comando no modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="491b7-170">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="491b7-171">Windows</span><span class="sxs-lookup"><span data-stu-id="491b7-171">Windows</span></span>](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[<span data-ttu-id="491b7-172">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="491b7-172">Mac/Linux</span></span>](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

<span data-ttu-id="491b7-173">Por fim, verifique se você pode executar `dotnet` , `java` , `spark-shell` na linha de comando antes de passar para a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="491b7-173">Finally, double-check that you can run `dotnet`, `java`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="491b7-174">Escrever um aplicativo .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="491b7-174">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="491b7-175">1. criar um aplicativo de console</span><span class="sxs-lookup"><span data-stu-id="491b7-175">1. Create a console app</span></span>

<span data-ttu-id="491b7-176">No prompt de comando ou terminal, execute os seguintes comandos para criar um novo aplicativo de console:</span><span class="sxs-lookup"><span data-stu-id="491b7-176">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

<span data-ttu-id="491b7-177">O `dotnet` comando cria um `new` aplicativo do tipo `console` para você.</span><span class="sxs-lookup"><span data-stu-id="491b7-177">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="491b7-178">O `-o` parâmetro cria um diretório chamado *MySparkApp* onde seu aplicativo é armazenado e o preenche com os arquivos necessários.</span><span class="sxs-lookup"><span data-stu-id="491b7-178">The `-o` parameter creates a directory named *MySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="491b7-179">O `cd MySparkApp` comando altera o diretório para o diretório do aplicativo que você criou.</span><span class="sxs-lookup"><span data-stu-id="491b7-179">The `cd MySparkApp` command changes the directory to the app directory you created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="491b7-180">2. instalar o pacote NuGet</span><span class="sxs-lookup"><span data-stu-id="491b7-180">2. Install NuGet package</span></span>

<span data-ttu-id="491b7-181">Para usar o .NET para Apache Spark em um aplicativo, instale o pacote Microsoft. Spark.</span><span class="sxs-lookup"><span data-stu-id="491b7-181">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="491b7-182">No prompt de comando ou terminal, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="491b7-182">In your command prompt or terminal, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> <span data-ttu-id="491b7-183">Este tutorial usa a versão mais recente do `Microsoft.Spark` pacote NuGet, a menos que especificado de outra forma.</span><span class="sxs-lookup"><span data-stu-id="491b7-183">This tutorial uses the latest version of the `Microsoft.Spark` NuGet package unless otherwise specified.</span></span>

### <a name="3-write-your-app"></a><span data-ttu-id="491b7-184">3. Escreva seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="491b7-184">3. Write your app</span></span>

<span data-ttu-id="491b7-185">Abra *Program.cs* no Visual Studio Code, ou em qualquer editor de texto, e substitua todo o código pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="491b7-185">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

<span data-ttu-id="491b7-186">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) é o ponto de entrada de aplicativos Apache Spark, que gerencia o contexto e as informações do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="491b7-186">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) is the entrypoint of Apache Spark applications, which manages the context and information of your application.</span></span> <span data-ttu-id="491b7-187">Usando o método [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) , os dados de texto do arquivo especificado pelo `filePath` são lidos em um [dataframe](xref:Microsoft.Spark.Sql.DataFrame).</span><span class="sxs-lookup"><span data-stu-id="491b7-187">Using the [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) method, the text data from the file specified by the `filePath` is read into a [DataFrame](xref:Microsoft.Spark.Sql.DataFrame).</span></span> <span data-ttu-id="491b7-188">Um dataframe é uma maneira de organizar dados em um conjunto de colunas nomeadas.</span><span class="sxs-lookup"><span data-stu-id="491b7-188">A DataFrame is a way of organizing data into a set of named columns.</span></span> <span data-ttu-id="491b7-189">Em seguida, uma série de transformações é aplicada para dividir as frases no arquivo, agrupar cada uma das palavras, contá-las e ordená-las em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="491b7-189">Then, a series of transformations is applied to split the sentences in the file, group each of the words, count them and order them in descending order.</span></span> <span data-ttu-id="491b7-190">O resultado dessas operações é armazenado em outro dataframe.</span><span class="sxs-lookup"><span data-stu-id="491b7-190">The result of these operations is stored in another DataFrame.</span></span> <span data-ttu-id="491b7-191">Observe que neste ponto, nenhuma operação ocorreu porque o .NET para Apache Spark avalia os dados lentamente.</span><span class="sxs-lookup"><span data-stu-id="491b7-191">Note that at this point, no operations have taken place because .NET for Apache Spark lazily evaluates the data.</span></span> <span data-ttu-id="491b7-192">Não é até que o método [show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) seja chamado para exibir o conteúdo do `words` dataframe transformado para o console que as operações definidas nas linhas acima executam.</span><span class="sxs-lookup"><span data-stu-id="491b7-192">It's not until the [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) method is called to display the contents of the `words` transformed DataFrame to the console that the operations defined in the lines above execute.</span></span> <span data-ttu-id="491b7-193">Depois que você não precisar mais da sessão do Spark, use o método [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) para interromper a sessão.</span><span class="sxs-lookup"><span data-stu-id="491b7-193">Once you no longer need the Spark session, use the [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) method to stop your session.</span></span>

### <a name="4-create-data-file"></a><span data-ttu-id="491b7-194">4. criar arquivo de dados</span><span class="sxs-lookup"><span data-stu-id="491b7-194">4. Create data file</span></span>

<span data-ttu-id="491b7-195">Seu aplicativo processa um arquivo que contém linhas de texto.</span><span class="sxs-lookup"><span data-stu-id="491b7-195">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="491b7-196">Crie um arquivo chamado *input.txt* arquivo no diretório *MySparkApp* , contendo o seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="491b7-196">Create a file called *input.txt* file in your *MySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

<span data-ttu-id="491b7-197">Salve as alterações e feche o arquivo.</span><span class="sxs-lookup"><span data-stu-id="491b7-197">Save the changes and close the file.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="491b7-198">Executar seu aplicativo .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="491b7-198">Run your .NET for Apache Spark app</span></span>

<span data-ttu-id="491b7-199">Execute o seguinte comando para compilar seu aplicativo:</span><span class="sxs-lookup"><span data-stu-id="491b7-199">Run the following command to build your application:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="491b7-200">Navegue até o diretório de saída da compilação e use o `spark-submit` comando para enviar seu aplicativo para execução em Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="491b7-200">Navigate to your build output directory and use the `spark-submit` command to submit your application to run on Apache Spark.</span></span> <span data-ttu-id="491b7-201">Certifique-se de substituir  `<version>` pela versão do seu trabalho do .net e `<path-of-input.txt>` pelo caminho de seu arquivo de *input.txt* está armazenado.</span><span class="sxs-lookup"><span data-stu-id="491b7-201">Make sure to replace  `<version>` with the version of your .NET worker and `<path-of-input.txt>` with the path of your *input.txt* file is stored.</span></span>

### <a name="windows"></a>[<span data-ttu-id="491b7-202">Windows</span><span class="sxs-lookup"><span data-stu-id="491b7-202">Windows</span></span>](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-3-0_2.12-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[<span data-ttu-id="491b7-203">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="491b7-203">Mac/Linux</span></span>](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-3-0_2.12-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> <span data-ttu-id="491b7-204">Esse comando pressupõe que você tenha baixado Apache Spark e adicionado-o à variável de ambiente PATH para poder usar `spark-submit` .</span><span class="sxs-lookup"><span data-stu-id="491b7-204">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="491b7-205">Caso contrário, você precisaria usar o caminho completo (por exemplo, *C:\bin\apache-spark\bin\spark-Submit* ou *~/Spark/bin/Spark-Submit*).</span><span class="sxs-lookup"><span data-stu-id="491b7-205">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

<span data-ttu-id="491b7-206">Quando seu aplicativo é executado, os dados de contagem de palavras do arquivo de *input.txt* são gravados no console do.</span><span class="sxs-lookup"><span data-stu-id="491b7-206">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

<span data-ttu-id="491b7-207">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="491b7-207">Congratulations!</span></span> <span data-ttu-id="491b7-208">Você criou e executou com êxito um aplicativo .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="491b7-208">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="491b7-209">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="491b7-209">Next steps</span></span>

<span data-ttu-id="491b7-210">Neste tutorial, você aprendeu a:</span><span class="sxs-lookup"><span data-stu-id="491b7-210">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="491b7-211">Prepare seu ambiente para .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="491b7-211">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="491b7-212">Escreva seu primeiro .NET para Apache Spark aplicativo</span><span class="sxs-lookup"><span data-stu-id="491b7-212">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="491b7-213">Crie e execute seu .NET para Apache Spark aplicativo</span><span class="sxs-lookup"><span data-stu-id="491b7-213">Build and run your .NET for Apache Spark application</span></span>

<span data-ttu-id="491b7-214">Para ver um vídeo explicando as etapas acima, confira a [série de vídeos .net para Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span><span class="sxs-lookup"><span data-stu-id="491b7-214">To see a video explaining the steps above, check out the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="491b7-215">Confira a página de recursos para saber mais.</span><span class="sxs-lookup"><span data-stu-id="491b7-215">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="491b7-216">Recursos do .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="491b7-216">.NET for Apache Spark Resources</span></span>](../resources/index.md)
