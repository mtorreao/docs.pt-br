---
title: 'Tutorial: detectar anomalias em chamadas telefônicas'
description: Saiba como criar um aplicativo de detecção de anomalias para dados de série temporal. Este tutorial cria um aplicativo de console .NET Core usando C# no Visual Studio 2019.
ms.date: 12/04/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 3451a44f8fa7ae85625687b7d52f120c411df1b6
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97634047"
---
# <a name="tutorial-detect-anomalies-in-time-series-with-mlnet"></a><span data-ttu-id="58670-104">Tutorial: detectar anomalias na série temporal com ML.NET</span><span class="sxs-lookup"><span data-stu-id="58670-104">Tutorial: Detect anomalies in time series with ML.NET</span></span>

<span data-ttu-id="58670-105">Saiba como criar um aplicativo de detecção de anomalias para dados de série temporal.</span><span class="sxs-lookup"><span data-stu-id="58670-105">Learn how to build an anomaly detection application for time series data.</span></span> <span data-ttu-id="58670-106">Este tutorial cria um aplicativo de console .NET Core usando C# no Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="58670-106">This tutorial creates a .NET Core console application using C# in Visual Studio 2019.</span></span>

<span data-ttu-id="58670-107">Neste tutorial, você aprenderá como:</span><span class="sxs-lookup"><span data-stu-id="58670-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="58670-108">Carregar os dados</span><span class="sxs-lookup"><span data-stu-id="58670-108">Load the data</span></span>
> * <span data-ttu-id="58670-109">Detectar período para uma série temporal</span><span class="sxs-lookup"><span data-stu-id="58670-109">Detect period for a time series</span></span>
> * <span data-ttu-id="58670-110">Detectar anomalias para uma série de tempo periódico</span><span class="sxs-lookup"><span data-stu-id="58670-110">Detect anomaly for a periodical time series</span></span>

<span data-ttu-id="58670-111">Você pode encontrar o código-fonte para este tutorial no repositório [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="58670-111">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="58670-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="58670-112">Prerequisites</span></span>

* <span data-ttu-id="58670-113">[Visual Studio 2019 versão 16.7.8 ou posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) com a carga de trabalho "desenvolvimento de plataforma cruzada do .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="58670-113">[Visual Studio 2019 version 16.7.8 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="58670-114">O conjunto de phone-calls.csv</span><span class="sxs-lookup"><span data-stu-id="58670-114">The phone-calls.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrCnnDetection/Data/phone-calls.csv)

## <a name="create-a-console-application"></a><span data-ttu-id="58670-115">Criar um aplicativo de console</span><span class="sxs-lookup"><span data-stu-id="58670-115">Create a console application</span></span>

1. <span data-ttu-id="58670-116">Crie um **aplicativo de console do .NET Core em C#** chamado "ProductSalesAnomalyDetection".</span><span class="sxs-lookup"><span data-stu-id="58670-116">Create a **C# .NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="58670-117">Crie um diretório chamado *dados* em seu projeto para salvar os arquivos do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="58670-117">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="58670-118">Instalar o **Pacote NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="58670-118">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="58670-119">No Gerenciador de Soluções, clique com o botão direito do mouse no seu projeto e selecione **Gerenciar Pacotes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="58670-119">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="58670-120">Escolha "nuget.org" como a origem do pacote, selecione a guia procurar, procure **Microsoft.ml** e selecione o botão **instalar** .</span><span class="sxs-lookup"><span data-stu-id="58670-120">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="58670-121">Selecione o botão **OK** na caixa de diálogo **Visualizar Alterações** e selecione o botão **Aceito** na caixa de diálogo **Aceitação da Licença**, se concordar com o termos de licença para os pacotes listados.</span><span class="sxs-lookup"><span data-stu-id="58670-121">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="58670-122">Repita essas etapas para **Microsoft. ml. timeseries**.</span><span class="sxs-lookup"><span data-stu-id="58670-122">Repeat these steps for **Microsoft.ML.TimeSeries**.</span></span>

4. <span data-ttu-id="58670-123">Adicione as seguintes instruções `using` à parte superior do arquivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="58670-123">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="58670-124">Baixar seus dados</span><span class="sxs-lookup"><span data-stu-id="58670-124">Download your data</span></span>

1. <span data-ttu-id="58670-125">Baixe o conjunto de dados e salve-o na pasta *Data* criada anteriormente:</span><span class="sxs-lookup"><span data-stu-id="58670-125">Download the dataset and save it to the *Data* folder you previously created:</span></span>

    <span data-ttu-id="58670-126">Clique com o botão direito do mouse em [*phone-calls.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrCnnDetection/Data/phone-calls.csv) e selecione "Salvar link (ou destino) como..."</span><span class="sxs-lookup"><span data-stu-id="58670-126">Right click on [*phone-calls.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrCnnDetection/Data/phone-calls.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="58670-127">Salve o arquivo \*.csv na pasta *Data* ou, depois de salvá-lo em outro lugar, mova o arquivo \*.csv para a pasta *Data*.</span><span class="sxs-lookup"><span data-stu-id="58670-127">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="58670-128">No Gerenciador de Soluções, clique com o botão direito do mouse no arquivo \*.csv e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="58670-128">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="58670-129">Em **avançado**, altere o valor de **copiar para diretório de saída** para **copiar se mais recente**.</span><span class="sxs-lookup"><span data-stu-id="58670-129">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="58670-130">A tabela a seguir é uma visualização de dados do seu arquivo \*.csv:</span><span class="sxs-lookup"><span data-stu-id="58670-130">The following table is a data preview from your \*.csv file:</span></span>

| <span data-ttu-id="58670-131">timestamp</span><span class="sxs-lookup"><span data-stu-id="58670-131">timestamp</span></span>  | <span data-ttu-id="58670-132">value</span><span class="sxs-lookup"><span data-stu-id="58670-132">value</span></span> |
|--------|--------------|
| <span data-ttu-id="58670-133">2018/9/3</span><span class="sxs-lookup"><span data-stu-id="58670-133">2018/9/3</span></span>  | <span data-ttu-id="58670-134">36,69670857</span><span class="sxs-lookup"><span data-stu-id="58670-134">36.69670857</span></span>  |
| <span data-ttu-id="58670-135">2018/9/4</span><span class="sxs-lookup"><span data-stu-id="58670-135">2018/9/4</span></span>  | <span data-ttu-id="58670-136">35,74160571</span><span class="sxs-lookup"><span data-stu-id="58670-136">35.74160571</span></span>  |
| <span data-ttu-id="58670-137">.....</span><span class="sxs-lookup"><span data-stu-id="58670-137">.....</span></span>  | <span data-ttu-id="58670-138">.....</span><span class="sxs-lookup"><span data-stu-id="58670-138">.....</span></span>  |
| <span data-ttu-id="58670-139">2018/10/3</span><span class="sxs-lookup"><span data-stu-id="58670-139">2018/10/3</span></span>  | <span data-ttu-id="58670-140">34,49893429</span><span class="sxs-lookup"><span data-stu-id="58670-140">34.49893429</span></span>  |
| <span data-ttu-id="58670-141">...</span><span class="sxs-lookup"><span data-stu-id="58670-141">...</span></span>    | <span data-ttu-id="58670-142">....</span><span class="sxs-lookup"><span data-stu-id="58670-142">....</span></span>   |

<span data-ttu-id="58670-143">Esse arquivo representa uma série temporal.</span><span class="sxs-lookup"><span data-stu-id="58670-143">This file represents a time-series.</span></span> <span data-ttu-id="58670-144">Cada linha no arquivo é um ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="58670-144">Each row in the file is a data point.</span></span> <span data-ttu-id="58670-145">Cada ponto de dados tem dois atributos, `timestamp` ou seja, e `value` , para representar o número de chamadas telefônicas a cada dia.</span><span class="sxs-lookup"><span data-stu-id="58670-145">Each data point has two attributes, namely, `timestamp` and `value`, to represent the number of phone calls at each day.</span></span> <span data-ttu-id="58670-146">O número de chamadas telefônicas é transformado em diferenciação.</span><span class="sxs-lookup"><span data-stu-id="58670-146">The number of phone calls is transformed to de-sensitivity.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="58670-147">Criar classes e definir demarcadores</span><span class="sxs-lookup"><span data-stu-id="58670-147">Create classes and define paths</span></span>

<span data-ttu-id="58670-148">Em seguida, defina suas estruturas de dados de classe de entrada e de previsão.</span><span class="sxs-lookup"><span data-stu-id="58670-148">Next, define your input and prediction class data structures.</span></span>

<span data-ttu-id="58670-149">Adicione uma nova classe ao seu projeto:</span><span class="sxs-lookup"><span data-stu-id="58670-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="58670-150">No **Gerenciador de Soluções**, clique com o botão direito do mouse no projeto e, em seguida, selecione **Adicionar > Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="58670-150">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="58670-151">Na **caixa de diálogo Adicionar novo item**, selecione **classe** e altere o campo **nome** para *PhoneCallsData.cs*.</span><span class="sxs-lookup"><span data-stu-id="58670-151">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *PhoneCallsData.cs*.</span></span> <span data-ttu-id="58670-152">Em seguida, selecione o botão **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="58670-152">Then, select the **Add** button.</span></span>

   <span data-ttu-id="58670-153">O arquivo *PhoneCallsData.cs* é aberto no editor de código.</span><span class="sxs-lookup"><span data-stu-id="58670-153">The *PhoneCallsData.cs* file opens in the code editor.</span></span>

3. <span data-ttu-id="58670-154">Adicione a seguinte `using` instrução à parte superior de *PhoneCallsData.cs*:</span><span class="sxs-lookup"><span data-stu-id="58670-154">Add the following `using` statement to the top of *PhoneCallsData.cs*:</span></span>

   ```csharp
   using Microsoft.ML.Data;
   ```

4. <span data-ttu-id="58670-155">Remova a definição de classe existente e adicione o código a seguir, que tem duas classes `PhoneCallsData` e `PhoneCallsPrediction` , ao arquivo *PhoneCallsData.cs* :</span><span class="sxs-lookup"><span data-stu-id="58670-155">Remove the existing class definition and add the following code, which has two classes `PhoneCallsData` and `PhoneCallsPrediction`, to the *PhoneCallsData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](./snippets/phone-calls-anomaly-detection/csharp/PhoneCallsData.cs#DeclareTypes "Declare data record types")]

    <span data-ttu-id="58670-156">`PhoneCallsData` especifica uma classe de dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="58670-156">`PhoneCallsData` specifies an input data class.</span></span> <span data-ttu-id="58670-157">O atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) especifica quais colunas (por índice de coluna) no conjunto de dados devem ser carregadas.</span><span class="sxs-lookup"><span data-stu-id="58670-157">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="58670-158">Ele tem dois atributos `timestamp` e `value` correspondem aos mesmos atributos no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="58670-158">It has two attributes `timestamp` and `value` that correspond to the same attributes in the data file.</span></span>

    <span data-ttu-id="58670-159">`PhoneCallsPrediction` especifica a classe de dados de previsão.</span><span class="sxs-lookup"><span data-stu-id="58670-159">`PhoneCallsPrediction` specifies the prediction data class.</span></span> <span data-ttu-id="58670-160">Para o detector SR-CNN, a previsão depende do [modo de detecção](xref:Microsoft.ML.TimeSeries.SrCnnDetectMode) especificado.</span><span class="sxs-lookup"><span data-stu-id="58670-160">For SR-CNN detector, the prediction depends on the [detect mode](xref:Microsoft.ML.TimeSeries.SrCnnDetectMode) specified.</span></span> <span data-ttu-id="58670-161">Neste exemplo, selecionamos o `AnomalyAndMargin` modo.</span><span class="sxs-lookup"><span data-stu-id="58670-161">In this sample, we select the `AnomalyAndMargin` mode.</span></span> <span data-ttu-id="58670-162">A saída contém sete colunas.</span><span class="sxs-lookup"><span data-stu-id="58670-162">The output contains seven columns.</span></span> <span data-ttu-id="58670-163">Na maioria dos casos,,, `IsAnomaly` `ExpectedValue` `UpperBoundary` e `LowerBoundary` são informais o suficiente.</span><span class="sxs-lookup"><span data-stu-id="58670-163">In most cases, `IsAnomaly`, `ExpectedValue`, `UpperBoundary`, and `LowerBoundary` are informative enough.</span></span> <span data-ttu-id="58670-164">Eles informam se um ponto é uma anomalia, o valor esperado do ponto e a região de limite inferior/superior do ponto.</span><span class="sxs-lookup"><span data-stu-id="58670-164">They tell you if a point is an anomaly, the expected value of the point and the lower / upper boundary region of the point.</span></span>

5. <span data-ttu-id="58670-165">Adicione o seguinte código à linha à direita acima do `Main` método para especificar o caminho para o arquivo de dados:</span><span class="sxs-lookup"><span data-stu-id="58670-165">Add the following code to the line right above the `Main` method to specify the path to your data file:</span></span>

    [!code-csharp[Declare global variables](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a><span data-ttu-id="58670-166">Inicializar variáveis em Main</span><span class="sxs-lookup"><span data-stu-id="58670-166">Initialize variables in Main</span></span>

1. <span data-ttu-id="58670-167">Substitua a linha `Console.WriteLine("Hello World!")` no método `Main` pelo seguinte código para declarar e inicializar a variável `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="58670-167">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

    [!code-csharp[CreateMLContext](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    <span data-ttu-id="58670-168">A [classe MLContext](xref:Microsoft.ML.MLContext) é um ponto de partida para todas as operações do ML.NET e a inicialização do `mlContext` cria um ambiente do ML.NET que pode ser compartilhado entre os objetos de fluxo de trabalho da criação de modelo.</span><span class="sxs-lookup"><span data-stu-id="58670-168">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="58670-169">Ele é semelhante, conceitualmente, a `DBContext` no Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="58670-169">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="load-the-data"></a><span data-ttu-id="58670-170">Carregar os dados</span><span class="sxs-lookup"><span data-stu-id="58670-170">Load the data</span></span>

<span data-ttu-id="58670-171">Os dados do ML.NET são representados como uma [classe IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="58670-171">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="58670-172">`IDataView` é uma maneira flexível e eficiente de descrever dados tabulares (numéricos e texto).</span><span class="sxs-lookup"><span data-stu-id="58670-172">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="58670-173">Os dados podem ser carregados de um arquivo de texto ou de outras fontes (por exemplo, banco de dados SQL ou arquivos de log) para um objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="58670-173">Data can be loaded from a text file or from other sources (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="58670-174">Adicione o seguinte código como a próxima linha do método `Main`:</span><span class="sxs-lookup"><span data-stu-id="58670-174">Add the following code as the next line of the `Main` method:</span></span>

    [!code-csharp[LoadData](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="58670-175">O [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define o esquema de dados e lê o arquivo.</span><span class="sxs-lookup"><span data-stu-id="58670-175">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="58670-176">Ele usa as variáveis de caminho de dados e retorna uma `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="58670-176">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="time-series-anomaly-detection"></a><span data-ttu-id="58670-177">Detecção de anomalias de série temporal</span><span class="sxs-lookup"><span data-stu-id="58670-177">Time series anomaly detection</span></span>

<span data-ttu-id="58670-178">Detecção de anomalias de série temporal é o processo de detectar exceções de dados de série temporal; pontos em uma determinada série temporal de entrada em que o comportamento não é o esperado, ou "estranho".</span><span class="sxs-lookup"><span data-stu-id="58670-178">Time series anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span> <span data-ttu-id="58670-179">Essas anomalias normalmente são indicativas de alguns eventos de interesse no domínio problemático: um ataque cibernético em contas de usuário, queda de energia, disparo de RPS em um servidor, vazamento de memória, etc.</span><span class="sxs-lookup"><span data-stu-id="58670-179">These anomalies are typically indicative of some events of interest in the problem domain: a cyber-attack on user accounts, power outage, bursting RPS on a server, memory leak, etc.</span></span>

<span data-ttu-id="58670-180">Para localizar anomalias na série temporal, você deve primeiro determinar o período da série.</span><span class="sxs-lookup"><span data-stu-id="58670-180">To find anomaly on time series, you should first determine the period of the series.</span></span> <span data-ttu-id="58670-181">Em seguida, a série temporal pode ser decomposta em vários componentes como `Y = T + S + R` , onde `Y` é a série original, `T` é o componente de tendência, `S` é o componente sazonal e `R` é o componente residual da série.</span><span class="sxs-lookup"><span data-stu-id="58670-181">Then, the time series can be decomposed into several components as `Y = T + S + R`, where `Y` is the original series, `T` is the trend component, `S` is the seasonal component, and `R` is the residual component of the series.</span></span> <span data-ttu-id="58670-182">Essa etapa é chamada de [decomposição](https://en.wikipedia.org/wiki/Decomposition_of_time_series).</span><span class="sxs-lookup"><span data-stu-id="58670-182">This step is called [decomposition](https://en.wikipedia.org/wiki/Decomposition_of_time_series).</span></span> <span data-ttu-id="58670-183">Por fim, a detecção é executada no componente residual para localizar as anomalias.</span><span class="sxs-lookup"><span data-stu-id="58670-183">Finally, detection is performed on the residual component to find the anomalies.</span></span> <span data-ttu-id="58670-184">No ML.NET, o algoritmo SR-CNN é um algoritmo avançado e romance baseado em Spectral residuais (SR) e rede neural (CNN) para detectar anomalias na série temporal.</span><span class="sxs-lookup"><span data-stu-id="58670-184">In ML.NET, The SR-CNN algorithm is an advanced and novel algorithm that is based on Spectral Residual (SR) and Convolutional Neural Network(CNN) to detect anomaly on time-series.</span></span> <span data-ttu-id="58670-185">Para obter mais informações sobre esse algoritmo, consulte [serviço de detecção de anomalias de série temporal na Microsoft](https://arxiv.org/pdf/1906.03821.pdf).</span><span class="sxs-lookup"><span data-stu-id="58670-185">For more information on this algorithm, see [Time-Series Anomaly Detection Service at Microsoft](https://arxiv.org/pdf/1906.03821.pdf).</span></span>

<span data-ttu-id="58670-186">Neste tutorial, você verá que esses procedimentos podem ser concluídos usando duas funções.</span><span class="sxs-lookup"><span data-stu-id="58670-186">In this tutorial, you will see that these procedures can be completed using two functions.</span></span>

## <a name="detect-period"></a><span data-ttu-id="58670-187">Período de detecção</span><span class="sxs-lookup"><span data-stu-id="58670-187">Detect Period</span></span>

<span data-ttu-id="58670-188">Na primeira etapa, invocamos a `DetectSeasonality` função para determinar o período da série.</span><span class="sxs-lookup"><span data-stu-id="58670-188">In the first step, we invoke the `DetectSeasonality` function to determine the period of the series.</span></span>

### <a name="create-the-detectperiod-method"></a><span data-ttu-id="58670-189">Criar o método DetectPeriod</span><span class="sxs-lookup"><span data-stu-id="58670-189">Create the DetectPeriod method</span></span>

1. <span data-ttu-id="58670-190">Crie o `DetectPeriod` método, logo abaixo do `Main` método, usando o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="58670-190">Create the `DetectPeriod` method, just below the `Main` method, using the following code:</span></span>

    ```csharp
    static void DetectPeriod(MLContext mlContext, IDataView phoneCalls)
    {

    }
    ```

2. <span data-ttu-id="58670-191">Use a <xref:Microsoft.ML.TimeSeriesCatalog.DetectSeasonality%2A> função para detectar o período.</span><span class="sxs-lookup"><span data-stu-id="58670-191">Use the <xref:Microsoft.ML.TimeSeriesCatalog.DetectSeasonality%2A> function to detect period.</span></span> <span data-ttu-id="58670-192">Adicione-o ao método `DetectPeriod` com o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="58670-192">Add it to the `DetectPeriod` method with the following code:</span></span>

    [!code-csharp[DetectSeasonality](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectSeasonality)]

3. <span data-ttu-id="58670-193">Exiba o valor do período adicionando o seguinte como a próxima linha de código no `DetectPeriod` método:</span><span class="sxs-lookup"><span data-stu-id="58670-193">Display the period value by adding the following as the next line of code in the `DetectPeriod` method:</span></span>

    [!code-csharp[DisplayPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayPeriod)]

4. <span data-ttu-id="58670-194">Adicione a seguinte chamada ao `DetectPeriod` método no `Main` método:</span><span class="sxs-lookup"><span data-stu-id="58670-194">Add the following call to the `DetectPeriod` method in the `Main` method:</span></span>

    [!code-csharp[CallDetectPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectPeriod)]

### <a name="period-detection-results"></a><span data-ttu-id="58670-195">Resultados da detecção de período</span><span class="sxs-lookup"><span data-stu-id="58670-195">Period detection results</span></span>

<span data-ttu-id="58670-196">Execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="58670-196">Run the application.</span></span> <span data-ttu-id="58670-197">Seus resultados devem ser semelhantes aos seguintes.</span><span class="sxs-lookup"><span data-stu-id="58670-197">Your results should be similar to the following.</span></span>

```console
Period of the series is: 7.
```

## <a name="detect-anomaly"></a><span data-ttu-id="58670-198">Detectar anomalias</span><span class="sxs-lookup"><span data-stu-id="58670-198">Detect Anomaly</span></span>

<span data-ttu-id="58670-199">Nesta etapa, você usa o <xref:Microsoft.ML.TimeSeriesCatalog.DetectEntireAnomalyBySrCnn%2A> método para localizar anomalias.</span><span class="sxs-lookup"><span data-stu-id="58670-199">In this step, you use the <xref:Microsoft.ML.TimeSeriesCatalog.DetectEntireAnomalyBySrCnn%2A> method to find anomalies.</span></span>

### <a name="create-the-detectanomaly-method"></a><span data-ttu-id="58670-200">Criar o método DetectAnomaly</span><span class="sxs-lookup"><span data-stu-id="58670-200">Create the DetectAnomaly method</span></span>

1. <span data-ttu-id="58670-201">Crie o `DetectAnomaly` método, logo abaixo do `DetectPeriod` método, usando o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="58670-201">Create the `DetectAnomaly` method, just below the `DetectPeriod` method, using the following code:</span></span>

    ```csharp
    static void DetectAnomaly(MLContext mlContext, IDataView phoneCalls, int period)
    {

    }
    ```

2. <span data-ttu-id="58670-202">Configure <xref:Microsoft.ML.TimeSeries.SrCnnEntireAnomalyDetectorOptions> no `DetectAnomaly` método com o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="58670-202">Set up <xref:Microsoft.ML.TimeSeries.SrCnnEntireAnomalyDetectorOptions> in the `DetectAnomaly` method with the following code:</span></span>

    [!code-csharp[SetupSrCnnParameters](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#SetupSrCnnParameters)]

3. <span data-ttu-id="58670-203">Detecte anomalias pelo algoritmo SR-CNN adicionando a seguinte linha de código ao `DetectAnomaly` método:</span><span class="sxs-lookup"><span data-stu-id="58670-203">Detect anomaly by SR-CNN algorithm by adding the following line of code in the `DetectAnomaly` method:</span></span>

    [!code-csharp[DetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectAnomaly)]

4. <span data-ttu-id="58670-204">Converta a exibição de dados de saída em um tipo fortemente tipado `IEnumerable` para facilitar a exibição usando o [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) método com o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="58670-204">Convert the output data view into a strongly typed `IEnumerable` for easier display using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

    [!code-csharp[CreateEnumerableForResult](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateEnumerableForResult)]

5. <span data-ttu-id="58670-205">Crie um cabeçalho de exibição com o código a seguir como a próxima linha no método `DetectAnomaly`:</span><span class="sxs-lookup"><span data-stu-id="58670-205">Create a display header with the following code as the next line in the `DetectAnomaly` method:</span></span>

    [!code-csharp[DisplayHeader](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayHeader)]

    <span data-ttu-id="58670-206">Você exibirá as informações a seguir nos resultados da detecção de ponto de alteração:</span><span class="sxs-lookup"><span data-stu-id="58670-206">You'll display the following information in your change point detection results:</span></span>

    * <span data-ttu-id="58670-207">`Index` é o índice de cada ponto.</span><span class="sxs-lookup"><span data-stu-id="58670-207">`Index` is the index of each point.</span></span>
    * <span data-ttu-id="58670-208">`Anomaly` é o indicador de se cada ponto é detectado como anomalia.</span><span class="sxs-lookup"><span data-stu-id="58670-208">`Anomaly` is the indicator of whether each point is detected as anomaly.</span></span>
    * <span data-ttu-id="58670-209">`ExpectedValue` é o valor estimado de cada ponto.</span><span class="sxs-lookup"><span data-stu-id="58670-209">`ExpectedValue` is the estimated value of each point.</span></span>
    * <span data-ttu-id="58670-210">`LowerBoundary` é o menor valor que cada ponto pode ser não ser anormal.</span><span class="sxs-lookup"><span data-stu-id="58670-210">`LowerBoundary` is the lowest value each point can be to be not anomaly.</span></span>
    * <span data-ttu-id="58670-211">`UpperBoundary` é o maior valor que cada ponto pode ser não ser anormal.</span><span class="sxs-lookup"><span data-stu-id="58670-211">`UpperBoundary` is the highest value each point can be to be not anomaly.</span></span>

6. <span data-ttu-id="58670-212">Itere por meio do `predictions` `IEnumerable` e exiba os resultados com o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="58670-212">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

    [!code-csharp[DisplayAnomalyDetectionResults](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayAnomalyDetectionResults)]

7. <span data-ttu-id="58670-213">Adicione a seguinte chamada ao `DetectAnomaly` método no `Main` método:</span><span class="sxs-lookup"><span data-stu-id="58670-213">Add the following call to the `DetectAnomaly` method in the `Main` method:</span></span>

    [!code-csharp[CallDetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectAnomaly)]

## <a name="anomaly-detection-results"></a><span data-ttu-id="58670-214">Resultados da detecção de anomalias</span><span class="sxs-lookup"><span data-stu-id="58670-214">Anomaly detection results</span></span>

<span data-ttu-id="58670-215">Execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="58670-215">Run the application.</span></span> <span data-ttu-id="58670-216">Seus resultados devem ser semelhantes aos seguintes.</span><span class="sxs-lookup"><span data-stu-id="58670-216">Your results should be similar to the following.</span></span> <span data-ttu-id="58670-217">Durante o processamento, as mensagens são exibidas.</span><span class="sxs-lookup"><span data-stu-id="58670-217">During processing, messages are displayed.</span></span> <span data-ttu-id="58670-218">Você pode ver avisos ou mensagens de processamento.</span><span class="sxs-lookup"><span data-stu-id="58670-218">You may see warnings or processing messages.</span></span> <span data-ttu-id="58670-219">Algumas mensagens foram removidas dos resultados a seguir para fins de clareza.</span><span class="sxs-lookup"><span data-stu-id="58670-219">Some messages have been removed from the following results for clarity.</span></span>

```console
Detect period of the series
Period of the series is: 7.
Detect anomaly points in the series
Index   Data    Anomaly AnomalyScore    Mag     ExpectedValue   BoundaryUnit    UpperBoundary   LowerBoundary
0,0,36.841787256739266,41.14206982401966,32.541504689458876
1,0,35.67303618137362,39.97331874865401,31.372753614093227
2,0,34.710132999891826,39.029491313022824,30.390774686760828
3,0,33.44765248883495,37.786086547816545,29.10921842985335
4,0,28.937110922276364,33.25646923540736,24.61775260914537
5,0,5.143895892785781,9.444178460066171,0.843613325505391
6,0,5.163325228419392,9.463607795699783,0.8630426611390014
7,0,36.76414836240396,41.06443092968435,32.46386579512357
8,0,35.77908590657007,40.07936847385046,31.478803339289676
9,0,34.547259536635245,38.847542103915636,30.246976969354854
10,0,33.55193524820608,37.871293561337076,29.23257693507508
11,0,29.091800129624648,33.392082696905035,24.79151756234426
12,0,5.154836630338823,9.455119197619213,0.8545540630584334
13,0,5.234332502492464,9.534615069772855,0.934049935212073
14,0,36.54992549471526,40.85020806199565,32.24964292743487
15,0,35.79526470980883,40.095547277089224,31.494982142528443
16,0,34.34099013096804,38.64127269824843,30.040707563687647
17,0,33.61201516582131,37.9122977331017,29.31173259854092
18,0,29.223563320561812,33.5238458878422,24.923280753281425
19,0,5.170512168851533,9.470794736131923,0.8702296015711433
20,0,5.2614938889462834,9.561776456226674,0.9612113216658926
21,0,36.37103858487317,40.67132115215356,32.07075601759278
22,0,35.813544599026855,40.113827166307246,31.513262031746464
23,0,34.05600492733225,38.356287494612644,29.755722360051863
24,0,33.65828319077884,37.95856575805923,29.358000623498448
25,0,29.381125690882463,33.681408258162854,25.080843123602072
26,0,5.261543539820418,9.561826107100808,0.9612609725400283
27,0,5.4873712582971805,9.787653825577571,1.1870886910167897
28,1,36.504694001629254,40.804976568909645,32.20441143434886  <-- alert is on, detected anomaly
...
```

<span data-ttu-id="58670-220">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="58670-220">Congratulations!</span></span> <span data-ttu-id="58670-221">Agora você criou com êxito modelos de aprendizado de máquina para detectar períodos e anomalias em uma série temporal.</span><span class="sxs-lookup"><span data-stu-id="58670-221">You've now successfully built machine learning models for detecting period and anomaly on a periodical series.</span></span>

<span data-ttu-id="58670-222">Você pode encontrar o código-fonte para este tutorial no repositório [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="58670-222">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection) repository.</span></span>

<span data-ttu-id="58670-223">Neste tutorial, você aprendeu a:</span><span class="sxs-lookup"><span data-stu-id="58670-223">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="58670-224">Carregar os dados</span><span class="sxs-lookup"><span data-stu-id="58670-224">Load the data</span></span>
> * <span data-ttu-id="58670-225">Detectar período nos dados de série temporal</span><span class="sxs-lookup"><span data-stu-id="58670-225">Detect period on the time series data</span></span>
> * <span data-ttu-id="58670-226">Detectar anomalias nos dados de série temporal</span><span class="sxs-lookup"><span data-stu-id="58670-226">Detect anomaly on the time series data</span></span>

## <a name="next-steps"></a><span data-ttu-id="58670-227">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="58670-227">Next steps</span></span>

<span data-ttu-id="58670-228">Confira o repositório do GitHub de exemplos de Machine Learning para explorar um exemplo de Detecção de Anomalias de Consumo de Energia.</span><span class="sxs-lookup"><span data-stu-id="58670-228">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="58670-229">dotnet/machinelearning-samples GitHub repository</span><span class="sxs-lookup"><span data-stu-id="58670-229">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)
