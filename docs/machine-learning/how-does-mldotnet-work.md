---
title: O que é ML.NET e como ele funciona?
description: O ML.NET oferece a capacidade de adicionar aprendizado de máquina a aplicativos .NET, em cenários online ou offline. Com essa funcionalidade, você pode fazer previsões automáticas usando os dados disponíveis para o aplicativo sem precisar estar conectado a uma rede para usar o ML.NET. Este artigo explica os conceitos básicos do aprendizado de máquina em ML.NET.
ms.date: 11/5/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: 2c44a83b4d45c95cbe45f125523207811f6368c2
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97634060"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a><span data-ttu-id="fb708-105">O que é ML.NET e como ele funciona?</span><span class="sxs-lookup"><span data-stu-id="fb708-105">What is ML.NET and how does it work?</span></span>

<span data-ttu-id="fb708-106">O ML.NET oferece a capacidade de adicionar aprendizado de máquina a aplicativos .NET, em cenários online ou offline.</span><span class="sxs-lookup"><span data-stu-id="fb708-106">ML.NET gives you the ability to add machine learning to .NET applications, in either online or offline scenarios.</span></span> <span data-ttu-id="fb708-107">Com essa funcionalidade, você pode fazer previsões automáticas usando os dados disponíveis ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fb708-107">With this capability, you can make automatic predictions using the data available to your application.</span></span> <span data-ttu-id="fb708-108">Os aplicativos de Machine Learning fazem uso de padrões nos dados para fazer previsões em vez de precisarem ser programados explicitamente.</span><span class="sxs-lookup"><span data-stu-id="fb708-108">Machine learning applications make use of patterns in the data to make predictions rather than needing to be explicitly programmed.</span></span>

<span data-ttu-id="fb708-109">Central para o ML.NET é um **modelo** de aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="fb708-109">Central to ML.NET is a machine learning **model**.</span></span> <span data-ttu-id="fb708-110">O modelo especifica as etapas necessárias para transformar os dados de entrada em uma previsão.</span><span class="sxs-lookup"><span data-stu-id="fb708-110">The model specifies the steps needed to transform your input data into a prediction.</span></span> <span data-ttu-id="fb708-111">Com o ML.NET, você pode treinar um modelo personalizado especificando um algoritmo ou pode importar modelos TensorFlow e ONNX pré-treinados.</span><span class="sxs-lookup"><span data-stu-id="fb708-111">With ML.NET, you can train a custom model by specifying an algorithm, or you can import pre-trained TensorFlow and ONNX models.</span></span>

<span data-ttu-id="fb708-112">Depois de ter um modelo, você pode adicioná-lo ao seu aplicativo para fazer as previsões.</span><span class="sxs-lookup"><span data-stu-id="fb708-112">Once you have a model, you can add it to your application to make the predictions.</span></span>

<span data-ttu-id="fb708-113">O ML.NET é executado no Windows, no Linux e no macOS usando o .NET Core ou o Windows usando .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fb708-113">ML.NET runs on Windows, Linux, and macOS using .NET Core, or Windows using .NET Framework.</span></span> <span data-ttu-id="fb708-114">Há suporte para 64 bits em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="fb708-114">64 bit is supported on all platforms.</span></span> <span data-ttu-id="fb708-115">Há suporte para 32 bits no Windows, exceto para a funcionalidade relacionada a TensorFlow, LightGBM e ONNX.</span><span class="sxs-lookup"><span data-stu-id="fb708-115">32 bit is supported on Windows, except for TensorFlow, LightGBM, and ONNX-related functionality.</span></span>

<span data-ttu-id="fb708-116">Exemplos do tipo de previsões que você pode fazer com ML.NET:</span><span class="sxs-lookup"><span data-stu-id="fb708-116">Examples of the type of predictions that you can make with ML.NET:</span></span>

|||
|-|-|
|<span data-ttu-id="fb708-117">Classificação/Categorização</span><span class="sxs-lookup"><span data-stu-id="fb708-117">Classification/Categorization</span></span>|<span data-ttu-id="fb708-118">Dividir automaticamente os comentários dos clientes em categorias positivas e negativas</span><span class="sxs-lookup"><span data-stu-id="fb708-118">Automatically divide customer feedback into positive and negative categories</span></span>|
|<span data-ttu-id="fb708-119">Regressão/Prever valores contínuos</span><span class="sxs-lookup"><span data-stu-id="fb708-119">Regression/Predict continuous values</span></span>|<span data-ttu-id="fb708-120">Prever o preço de residências com base em tamanho e localização</span><span class="sxs-lookup"><span data-stu-id="fb708-120">Predict the price of houses based on size and location</span></span>|
|<span data-ttu-id="fb708-121">Detecção de anomalias</span><span class="sxs-lookup"><span data-stu-id="fb708-121">Anomaly Detection</span></span>|<span data-ttu-id="fb708-122">Detectar transações bancárias fraudulentas</span><span class="sxs-lookup"><span data-stu-id="fb708-122">Detect fraudulent banking transactions</span></span> |
|<span data-ttu-id="fb708-123">Recomendações</span><span class="sxs-lookup"><span data-stu-id="fb708-123">Recommendations</span></span>|<span data-ttu-id="fb708-124">Sugerir produtos que compradores online talvez queiram comprar com base em suas compras anteriores</span><span class="sxs-lookup"><span data-stu-id="fb708-124">Suggest products that online shoppers may want to buy, based on their previous purchases</span></span>|
|<span data-ttu-id="fb708-125">Série temporal/dados sequenciais</span><span class="sxs-lookup"><span data-stu-id="fb708-125">Time series/sequential data</span></span>|<span data-ttu-id="fb708-126">Prever as vendas do clima/produto</span><span class="sxs-lookup"><span data-stu-id="fb708-126">Forecast the weather/product sales</span></span>|
|<span data-ttu-id="fb708-127">Classificação de imagens</span><span class="sxs-lookup"><span data-stu-id="fb708-127">Image classification</span></span>|<span data-ttu-id="fb708-128">Categorizar pathologies em imagens médicas</span><span class="sxs-lookup"><span data-stu-id="fb708-128">Categorize pathologies in medical images</span></span>|

## <a name="hello-mlnet-world"></a><span data-ttu-id="fb708-129">Olá, Mundo do ML.NET</span><span class="sxs-lookup"><span data-stu-id="fb708-129">Hello ML.NET World</span></span>

<span data-ttu-id="fb708-130">O código no snippet a seguir demonstra o aplicativo do ML.NET mais simples.</span><span class="sxs-lookup"><span data-stu-id="fb708-130">The code in the following snippet demonstrates the simplest ML.NET application.</span></span> <span data-ttu-id="fb708-131">Este exemplo cria um modelo de regressão linear para prever os preços de residências usando dados de tamanho e preço de residências.</span><span class="sxs-lookup"><span data-stu-id="fb708-131">This example constructs a linear regression model to predict house prices using house size and price data.</span></span>

 ```csharp
    using System;
    using Microsoft.ML;
    using Microsoft.ML.Data;

    class Program
    {
        public class HouseData
        {
            public float Size { get; set; }
            public float Price { get; set; }
        }

        public class Prediction
        {
            [ColumnName("Score")]
            public float Price { get; set; }
        }

        static void Main(string[] args)
        {
            MLContext mlContext = new MLContext();

            // 1. Import or create training data
            HouseData[] houseData = {
                new HouseData() { Size = 1.1F, Price = 1.2F },
                new HouseData() { Size = 1.9F, Price = 2.3F },
                new HouseData() { Size = 2.8F, Price = 3.0F },
                new HouseData() { Size = 3.4F, Price = 3.7F } };
            IDataView trainingData = mlContext.Data.LoadFromEnumerable(houseData);

            // 2. Specify data preparation and model training pipeline
            var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
                .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));

            // 3. Train model
            var model = pipeline.Fit(trainingData);

            // 4. Make a prediction
            var size = new HouseData() { Size = 2.5F };
            var price = mlContext.Model.CreatePredictionEngine<HouseData, Prediction>(model).Predict(size);

            Console.WriteLine($"Predicted price for size: {size.Size*1000} sq ft= {price.Price*100:C}k");

            // Predicted price for size: 2500 sq ft= $261.98k
        }
    }
```

## <a name="code-workflow"></a><span data-ttu-id="fb708-132">Fluxo de trabalho de código</span><span class="sxs-lookup"><span data-stu-id="fb708-132">Code workflow</span></span>

<span data-ttu-id="fb708-133">O diagrama a seguir representa a estrutura de código do aplicativo, bem como o processo iterativo de desenvolvimento do modelo:</span><span class="sxs-lookup"><span data-stu-id="fb708-133">The following diagram represents the application code structure, as well as the iterative process of model development:</span></span>

- <span data-ttu-id="fb708-134">Coletar e carregar dados de treinamento em um objeto **IDataView**</span><span class="sxs-lookup"><span data-stu-id="fb708-134">Collect and load training data into an **IDataView** object</span></span>
- <span data-ttu-id="fb708-135">Especifique um pipeline de operações para extrair recursos e aplicar um algoritmo de aprendizado de máquina</span><span class="sxs-lookup"><span data-stu-id="fb708-135">Specify a pipeline of operations to extract features and apply a machine learning algorithm</span></span>
- <span data-ttu-id="fb708-136">Treinar um modelo chamando **Fit()** no pipeline</span><span class="sxs-lookup"><span data-stu-id="fb708-136">Train a model by calling **Fit()** on the pipeline</span></span>
- <span data-ttu-id="fb708-137">Avaliar o modelo e iterar para melhorar</span><span class="sxs-lookup"><span data-stu-id="fb708-137">Evaluate the model and iterate to improve</span></span>
- <span data-ttu-id="fb708-138">Salvar o modelo em um formato binário para uso em um aplicativo</span><span class="sxs-lookup"><span data-stu-id="fb708-138">Save the model into binary format, for use in an application</span></span>
- <span data-ttu-id="fb708-139">Carregar o modelo de volta para um objeto **ITransformer**</span><span class="sxs-lookup"><span data-stu-id="fb708-139">Load the model back into an **ITransformer** object</span></span>
- <span data-ttu-id="fb708-140">Fazer previsões chamando **CreatePredictionEngine.Predict()**</span><span class="sxs-lookup"><span data-stu-id="fb708-140">Make predictions by calling **CreatePredictionEngine.Predict()**</span></span>

![Fluxo de desenvolvimento de aplicativo do ML.NET incluindo componentes para geração de dados, desenvolvimento de pipeline, treinamento do modelo, avaliação de modelo e uso do modelo](./media/mldotnet-annotated-workflow.png)

<span data-ttu-id="fb708-142">Vamos nos aprofundar um pouco mais nesses conceitos.</span><span class="sxs-lookup"><span data-stu-id="fb708-142">Let's dig a little deeper into those concepts.</span></span>

## <a name="machine-learning-model"></a><span data-ttu-id="fb708-143">Modelo de Machine Learning</span><span class="sxs-lookup"><span data-stu-id="fb708-143">Machine learning model</span></span>

<span data-ttu-id="fb708-144">Um modelo do ML.NET é um objeto que contém transformações para executar em seus dados de entrada para chegar na saída prevista.</span><span class="sxs-lookup"><span data-stu-id="fb708-144">An ML.NET model is an object that contains transformations to perform on your input data to arrive at the predicted output.</span></span>

### <a name="basic"></a><span data-ttu-id="fb708-145">Basic</span><span class="sxs-lookup"><span data-stu-id="fb708-145">Basic</span></span>

<span data-ttu-id="fb708-146">O modelo mais básico é regressão linear bidimensional, em que uma quantidade contínua é proporcional a outro, como no exemplo de preço de residência acima.</span><span class="sxs-lookup"><span data-stu-id="fb708-146">The most basic model is two-dimensional linear regression, where one continuous quantity is proportional to another, as in the house price example above.</span></span>

![Modelo de regressão linear com os parâmetros de peso e desvio](./media/linear-regression-model.svg)

<span data-ttu-id="fb708-148">O modelo é simplesmente: $Price = b + Size \* w$.</span><span class="sxs-lookup"><span data-stu-id="fb708-148">The model is simply: $Price = b + Size \* w$.</span></span> <span data-ttu-id="fb708-149">Os parâmetros $b$ e $w$ são estimados ajustando uma linha em um conjunto de pares (tamanho, preço).</span><span class="sxs-lookup"><span data-stu-id="fb708-149">The parameters $b$ and $w$ are estimated by fitting a line on a set of (size, price) pairs.</span></span> <span data-ttu-id="fb708-150">Os dados usados para localizar os parâmetros do modelo são chamados **dados de treinamento**.</span><span class="sxs-lookup"><span data-stu-id="fb708-150">The data used to find the parameters of the model is called **training data**.</span></span> <span data-ttu-id="fb708-151">As entradas de um modelo de machine learning são chamadas de **recursos**.</span><span class="sxs-lookup"><span data-stu-id="fb708-151">The inputs of a machine learning model are called **features**.</span></span> <span data-ttu-id="fb708-152">Neste exemplo, $Size$ é o único recurso.</span><span class="sxs-lookup"><span data-stu-id="fb708-152">In this example, $Size$ is the only feature.</span></span> <span data-ttu-id="fb708-153">Os valores de zero verdadeiro usados para treinar um modelo de machine learning são chamados de **rótulos**.</span><span class="sxs-lookup"><span data-stu-id="fb708-153">The ground-truth values used to train a machine learning model are called **labels**.</span></span> <span data-ttu-id="fb708-154">Aqui, os valores de $Price$ no conjunto de dados de treinamento são os rótulos.</span><span class="sxs-lookup"><span data-stu-id="fb708-154">Here, the $Price$ values in the training data set are the labels.</span></span>

### <a name="more-complex"></a><span data-ttu-id="fb708-155">Mais complexo</span><span class="sxs-lookup"><span data-stu-id="fb708-155">More complex</span></span>

<span data-ttu-id="fb708-156">Um modelo mais complexo classifica as transações financeiras em categorias usando a descrição de texto de transação.</span><span class="sxs-lookup"><span data-stu-id="fb708-156">A more complex model classifies financial transactions into categories using the transaction text description.</span></span>

<span data-ttu-id="fb708-157">Cada descrição de transação é dividida em um conjunto de recursos removendo caracteres e palavras redundantes e contando combinações de palavras e caracteres.</span><span class="sxs-lookup"><span data-stu-id="fb708-157">Each transaction description is broken down into a set of features by removing redundant words and characters, and counting word and character combinations.</span></span> <span data-ttu-id="fb708-158">O conjunto de recursos é usado para treinar um modelo linear com base no conjunto de categorias nos dados de treinamento.</span><span class="sxs-lookup"><span data-stu-id="fb708-158">The feature set is used to train a linear model based on the set of categories in the training data.</span></span> <span data-ttu-id="fb708-159">Quanto mais semelhante uma nova descrição é daquelas no conjunto de treinamento, mais provavelmente ela será atribuída à mesma categoria.</span><span class="sxs-lookup"><span data-stu-id="fb708-159">The more similar a new description is to the ones in the training set, the more likely it will be assigned to the same category.</span></span>

![Modelo de Classificação de Texto](./media/text-classification-model.svg)

<span data-ttu-id="fb708-161">Os modelos de preço de residência e o modelo de classificação de texto são modelos **lineares**.</span><span class="sxs-lookup"><span data-stu-id="fb708-161">Both the house price model and the text classification model are **linear** models.</span></span> <span data-ttu-id="fb708-162">Dependendo da natureza de seus dados e do problema que você está resolvendo, você também pode usar modelos de **árvore de decisão**, modelos **aditivos generalizados** e outros.</span><span class="sxs-lookup"><span data-stu-id="fb708-162">Depending on the nature of your data and the problem you are solving, you can also use **decision tree** models, **generalized additive** models, and others.</span></span> <span data-ttu-id="fb708-163">Você pode encontrar mais informações sobre os modelos em [Tarefas](./resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="fb708-163">You can find out more about the models in [Tasks](./resources/tasks.md).</span></span>

## <a name="data-preparation"></a><span data-ttu-id="fb708-164">Preparação de dados</span><span class="sxs-lookup"><span data-stu-id="fb708-164">Data preparation</span></span>

<span data-ttu-id="fb708-165">Na maioria dos casos, os dados que você tem disponíveis não são adequados para serem usados diretamente para treinar um modelo de machine learning.</span><span class="sxs-lookup"><span data-stu-id="fb708-165">In most cases, the data that you have available isn't suitable to be used directly to train a machine learning model.</span></span> <span data-ttu-id="fb708-166">Os dados brutos precisam ser preparados ou pré-processados antes que possam ser usados para localizar os parâmetros do modelo.</span><span class="sxs-lookup"><span data-stu-id="fb708-166">The raw data needs to be prepared, or pre-processed, before it can be used to find the parameters of your model.</span></span> <span data-ttu-id="fb708-167">Seus dados talvez precisem ser convertidos de valores de cadeia de caracteres em uma representação numérica.</span><span class="sxs-lookup"><span data-stu-id="fb708-167">Your data may need to be converted from string values to a numerical representation.</span></span> <span data-ttu-id="fb708-168">Você pode ter informações redundantes em seus dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="fb708-168">You might have redundant information in your input data.</span></span> <span data-ttu-id="fb708-169">Talvez você precise reduzir ou expandir as dimensões de seus dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="fb708-169">You may need to reduce or expand the dimensions of your input data.</span></span> <span data-ttu-id="fb708-170">Seus dados talvez precisem ser normalizados ou dimensionados.</span><span class="sxs-lookup"><span data-stu-id="fb708-170">Your data might need to be normalized or scaled.</span></span>

<span data-ttu-id="fb708-171">Os [tutoriais do ML.NET](./tutorials/index.md) ensinam a você sobre os diferentes pipelines de processamento de dados para texto, imagem, dados numéricos e de série temporal usados para tarefas de aprendizado de máquina específicas.</span><span class="sxs-lookup"><span data-stu-id="fb708-171">The [ML.NET tutorials](./tutorials/index.md) teach you about different data processing pipelines for text, image, numerical, and time-series data used for specific machine learning tasks.</span></span>

<span data-ttu-id="fb708-172">[Como preparar seus dados](./how-to-guides/prepare-data-ml-net.md) mostra como aplicar a preparação de dados com mais frequência.</span><span class="sxs-lookup"><span data-stu-id="fb708-172">[How to prepare your data](./how-to-guides/prepare-data-ml-net.md) shows you how to apply data preparation more generally.</span></span>

<span data-ttu-id="fb708-173">Você pode encontrar um apêndice de todas as [transformações disponíveis](./resources/transforms.md) na seção de recursos.</span><span class="sxs-lookup"><span data-stu-id="fb708-173">You can find an appendix of all of the [available transformations](./resources/transforms.md) in the resources section.</span></span>

## <a name="model-evaluation"></a><span data-ttu-id="fb708-174">Avaliação de modelos</span><span class="sxs-lookup"><span data-stu-id="fb708-174">Model evaluation</span></span>

<span data-ttu-id="fb708-175">Depois de treinar seu modelo, como você sabe o quão bem ele fará previsões futuras?</span><span class="sxs-lookup"><span data-stu-id="fb708-175">Once you have trained your model, how do you know how well it will make future predictions?</span></span> <span data-ttu-id="fb708-176">Com o do ML.NET, você pode avaliar seu modelo em relação a alguns novos dados de teste.</span><span class="sxs-lookup"><span data-stu-id="fb708-176">With ML.NET, you can evaluate your model against some new test data.</span></span>

<span data-ttu-id="fb708-177">Cada tipo de tarefa de aprendizado de máquina tem métricas usadas para avaliar a precisão e a exatidão do modelo em relação ao conjunto de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="fb708-177">Each type of machine learning task has metrics used to evaluate the accuracy and precision of the model against the test data set.</span></span>

<span data-ttu-id="fb708-178">Para nosso exemplo de preço de residência, usamos a tarefa **Regressão**.</span><span class="sxs-lookup"><span data-stu-id="fb708-178">For our house price example, we used the **Regression** task.</span></span> <span data-ttu-id="fb708-179">Para avaliar o modelo, adicione o seguinte código à amostra original.</span><span class="sxs-lookup"><span data-stu-id="fb708-179">To evaluate the model, add the following code to the original sample.</span></span>

```csharp
        HouseData[] testHouseData =
        {
            new HouseData() { Size = 1.1F, Price = 0.98F },
            new HouseData() { Size = 1.9F, Price = 2.1F },
            new HouseData() { Size = 2.8F, Price = 2.9F },
            new HouseData() { Size = 3.4F, Price = 3.6F }
        };

        var testHouseDataView = mlContext.Data.LoadFromEnumerable(testHouseData);
        var testPriceDataView = model.Transform(testHouseDataView);

        var metrics = mlContext.Regression.Evaluate(testPriceDataView, labelColumnName: "Price");

        Console.WriteLine($"R^2: {metrics.RSquared:0.##}");
        Console.WriteLine($"RMS error: {metrics.RootMeanSquaredError:0.##}");

        // R^2: 0.96
        // RMS error: 0.19
```

<span data-ttu-id="fb708-180">As métricas de avaliação dizem que o erro é mais ou menos baixo. Essa correlação entre a saída prevista e a saída do teste é alta.</span><span class="sxs-lookup"><span data-stu-id="fb708-180">The evaluation metrics tell you that the error is low-ish, and that correlation between the predicted output and the test output is high.</span></span> <span data-ttu-id="fb708-181">Isso foi fácil.</span><span class="sxs-lookup"><span data-stu-id="fb708-181">That was easy!</span></span> <span data-ttu-id="fb708-182">Em exemplos reais, é necessário mais ajuste para obter métricas de modelo válidas.</span><span class="sxs-lookup"><span data-stu-id="fb708-182">In real examples, it takes more tuning to achieve good model metrics.</span></span>

## <a name="mlnet-architecture"></a><span data-ttu-id="fb708-183">Arquitetura do ML.NET</span><span class="sxs-lookup"><span data-stu-id="fb708-183">ML.NET architecture</span></span>

<span data-ttu-id="fb708-184">Nesta seção, vamos repassar os padrões de arquitetura do ML.NET.</span><span class="sxs-lookup"><span data-stu-id="fb708-184">In this section, we go through the architectural patterns of ML.NET.</span></span> <span data-ttu-id="fb708-185">Se você for um desenvolvedor .NET experiente, alguns destes padrões serão familiares, enquanto outros serão menos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="fb708-185">If you are an experienced .NET developer, some of these patterns will be familiar to you, and some will be less familiar.</span></span> <span data-ttu-id="fb708-186">Mantenha o foco enquanto nos aprofundamos.</span><span class="sxs-lookup"><span data-stu-id="fb708-186">Hold tight, while we dive in!</span></span>

<span data-ttu-id="fb708-187">Um aplicativo do ML.NET começa com um objeto <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="fb708-187">An ML.NET application starts with an <xref:Microsoft.ML.MLContext> object.</span></span> <span data-ttu-id="fb708-188">Esse objeto singleton contém **catálogos**.</span><span class="sxs-lookup"><span data-stu-id="fb708-188">This singleton object contains **catalogs**.</span></span> <span data-ttu-id="fb708-189">Um catálogo é uma fábrica para carregar e salvar dados, componentes de operação de modelo, treinadores e transformações.</span><span class="sxs-lookup"><span data-stu-id="fb708-189">A catalog is a factory for data loading and saving, transforms, trainers, and model operation components.</span></span> <span data-ttu-id="fb708-190">Cada objeto de catálogo tem métodos para criar os diferentes tipos de componentes:</span><span class="sxs-lookup"><span data-stu-id="fb708-190">Each catalog object has methods to create the different types of components:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="fb708-191">Salvamento e carregamento de dados</span><span class="sxs-lookup"><span data-stu-id="fb708-191">Data loading and saving</span></span>||<xref:Microsoft.ML.DataOperationsCatalog>||
|<span data-ttu-id="fb708-192">Preparação de dados</span><span class="sxs-lookup"><span data-stu-id="fb708-192">Data preparation</span></span>||<xref:Microsoft.ML.TransformsCatalog>||
|<span data-ttu-id="fb708-193">Treinando algoritmos</span><span class="sxs-lookup"><span data-stu-id="fb708-193">Training algorithms</span></span>|<span data-ttu-id="fb708-194">Classificação binária</span><span class="sxs-lookup"><span data-stu-id="fb708-194">Binary classification</span></span>|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||<span data-ttu-id="fb708-195">Classificação multiclasse</span><span class="sxs-lookup"><span data-stu-id="fb708-195">Multiclass classification</span></span>|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||<span data-ttu-id="fb708-196">Detecção de anomalias</span><span class="sxs-lookup"><span data-stu-id="fb708-196">Anomaly detection</span></span>|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||<span data-ttu-id="fb708-197">Clustering</span><span class="sxs-lookup"><span data-stu-id="fb708-197">Clustering</span></span>|<xref:Microsoft.ML.ClusteringCatalog>||
||<span data-ttu-id="fb708-198">Previsão</span><span class="sxs-lookup"><span data-stu-id="fb708-198">Forecasting</span></span>|<xref:Microsoft.ML.ForecastingCatalog>||
||<span data-ttu-id="fb708-199">Classificação</span><span class="sxs-lookup"><span data-stu-id="fb708-199">Ranking</span></span>|<xref:Microsoft.ML.RankingCatalog>||
||<span data-ttu-id="fb708-200">Regressão</span><span class="sxs-lookup"><span data-stu-id="fb708-200">Regression</span></span>|<xref:Microsoft.ML.RegressionCatalog>||
||<span data-ttu-id="fb708-201">Recomendação</span><span class="sxs-lookup"><span data-stu-id="fb708-201">Recommendation</span></span>|<xref:Microsoft.ML.RecommendationCatalog>|<span data-ttu-id="fb708-202">adicionar o pacote NuGet `Microsoft.ML.Recommender`</span><span class="sxs-lookup"><span data-stu-id="fb708-202">add the `Microsoft.ML.Recommender` NuGet package</span></span>|
||<span data-ttu-id="fb708-203">TimeSeries</span><span class="sxs-lookup"><span data-stu-id="fb708-203">TimeSeries</span></span>|<xref:Microsoft.ML.TimeSeriesCatalog>|<span data-ttu-id="fb708-204">adicionar o pacote NuGet `Microsoft.ML.TimeSeries`</span><span class="sxs-lookup"><span data-stu-id="fb708-204">add the `Microsoft.ML.TimeSeries` NuGet package</span></span>|
|<span data-ttu-id="fb708-205">Uso do modelo</span><span class="sxs-lookup"><span data-stu-id="fb708-205">Model usage</span></span> ||<xref:Microsoft.ML.ModelOperationsCatalog>||

<span data-ttu-id="fb708-206">Você pode navegar para os métodos de criação em cada uma das categorias acima.</span><span class="sxs-lookup"><span data-stu-id="fb708-206">You can navigate to the creation methods in each of the above categories.</span></span> <span data-ttu-id="fb708-207">Usando o Visual Studio, os catálogos aparecem por meio do IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="fb708-207">Using Visual Studio, the catalogs show up via IntelliSense.</span></span>

   ![IntelliSense para Treinadores de Regressão](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a><span data-ttu-id="fb708-209">Criar o pipeline</span><span class="sxs-lookup"><span data-stu-id="fb708-209">Build the pipeline</span></span>

<span data-ttu-id="fb708-210">Dentro de cada catálogo está um conjunto de métodos de extensão.</span><span class="sxs-lookup"><span data-stu-id="fb708-210">Inside each catalog is a set of extension methods.</span></span> <span data-ttu-id="fb708-211">Vamos examinar como os métodos de extensão são usados para criar um pipeline de treinamento.</span><span class="sxs-lookup"><span data-stu-id="fb708-211">Let's look at how extension methods are used to create a training pipeline.</span></span>

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

<span data-ttu-id="fb708-212">No snippet, `Concatenate` e `Sdca` são ambos métodos no catálogo.</span><span class="sxs-lookup"><span data-stu-id="fb708-212">In the snippet, `Concatenate` and `Sdca` are both methods in the catalog.</span></span> <span data-ttu-id="fb708-213">Cada um deles criar um objeto [IEstimator](xref:Microsoft.ML.IEstimator%601) que é acrescentado ao pipeline.</span><span class="sxs-lookup"><span data-stu-id="fb708-213">They each create an [IEstimator](xref:Microsoft.ML.IEstimator%601) object that is appended to the pipeline.</span></span>

<span data-ttu-id="fb708-214">Neste ponto, os objetos são apenas criados.</span><span class="sxs-lookup"><span data-stu-id="fb708-214">At this point, the objects are created only.</span></span> <span data-ttu-id="fb708-215">Nenhuma execução aconteceu.</span><span class="sxs-lookup"><span data-stu-id="fb708-215">No execution has happened.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="fb708-216">Treinar o modelo</span><span class="sxs-lookup"><span data-stu-id="fb708-216">Train the model</span></span>

<span data-ttu-id="fb708-217">Quando os objetos no pipeline foram criados, os dados podem ser usados para treinar o modelo.</span><span class="sxs-lookup"><span data-stu-id="fb708-217">Once the objects in the pipeline have been created, data can be used to train the model.</span></span>

```csharp
    var model = pipeline.Fit(trainingData);
```

<span data-ttu-id="fb708-218">Chamar `Fit()` usa os dados de treinamento de entrada para estimar os parâmetros do modelo.</span><span class="sxs-lookup"><span data-stu-id="fb708-218">Calling `Fit()` uses the input training data to estimate the parameters of the model.</span></span> <span data-ttu-id="fb708-219">Isso é conhecido como treinamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="fb708-219">This is known as training the model.</span></span> <span data-ttu-id="fb708-220">Lembre-se de que o modelo de regressão linear acima tinha dois parâmetros de modelo: **desvio** e **peso**.</span><span class="sxs-lookup"><span data-stu-id="fb708-220">Remember, the linear regression model above had two model parameters: **bias** and **weight**.</span></span> <span data-ttu-id="fb708-221">Após a chamada `Fit()`, os valores dos parâmetros são conhecidos.</span><span class="sxs-lookup"><span data-stu-id="fb708-221">After the `Fit()` call, the values of the parameters are known.</span></span> <span data-ttu-id="fb708-222">A maioria dos modelos terá muito mais parâmetros que isso.</span><span class="sxs-lookup"><span data-stu-id="fb708-222">Most models will have many more parameters than this.</span></span>

<span data-ttu-id="fb708-223">Você pode aprender mais sobre o treinamento de modelo em [como treinar seu modelo](./how-to-guides/train-machine-learning-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="fb708-223">You can learn more about model training in [How to train your model](./how-to-guides/train-machine-learning-model-ml-net.md).</span></span>

<span data-ttu-id="fb708-224">O objeto de modelo resultante implementa a interface do <xref:Microsoft.ML.ITransformer>.</span><span class="sxs-lookup"><span data-stu-id="fb708-224">The resulting model object implements the <xref:Microsoft.ML.ITransformer> interface.</span></span> <span data-ttu-id="fb708-225">Ou seja, o modelo transforma dados de entrada em previsões.</span><span class="sxs-lookup"><span data-stu-id="fb708-225">That is, the model transforms input data into predictions.</span></span>

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a><span data-ttu-id="fb708-226">Usar o modelo</span><span class="sxs-lookup"><span data-stu-id="fb708-226">Use the model</span></span>

<span data-ttu-id="fb708-227">Você pode transformar dados de entrada em previsões em massa ou uma entrada por vez.</span><span class="sxs-lookup"><span data-stu-id="fb708-227">You can transform input data into predictions in bulk, or one input at a time.</span></span> <span data-ttu-id="fb708-228">No exemplo de preço de residência, fizemos ambos: em massa para fins de avaliar o modelo e um por vez para fazer uma nova previsão.</span><span class="sxs-lookup"><span data-stu-id="fb708-228">In the house price example, we did both: in bulk for the purpose of evaluating the model, and one at a time to make a new prediction.</span></span> <span data-ttu-id="fb708-229">Vamos examinar como fazer previsões únicas.</span><span class="sxs-lookup"><span data-stu-id="fb708-229">Let's look at making single predictions.</span></span>

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```

<span data-ttu-id="fb708-230">O método `CreatePredictionEngine()` usa uma classe de entrada e uma classe de saída.</span><span class="sxs-lookup"><span data-stu-id="fb708-230">The `CreatePredictionEngine()` method takes an input class and an output class.</span></span> <span data-ttu-id="fb708-231">Os nomes de campo e/ou atributos de código determinam os nomes das colunas de dados usadas durante a previsão e o treinamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="fb708-231">The field names and/or code attributes determine the names of the data columns used during model training and prediction.</span></span> <span data-ttu-id="fb708-232">Para obter mais informações, consulte [fazer previsões com um modelo treinado](how-to-guides/machine-learning-model-predictions-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="fb708-232">For more information, see [Make predictions with a trained model](how-to-guides/machine-learning-model-predictions-ml-net.md).</span></span>

### <a name="data-models-and-schema"></a><span data-ttu-id="fb708-233">Esquema e modelos de dados</span><span class="sxs-lookup"><span data-stu-id="fb708-233">Data models and schema</span></span>

<span data-ttu-id="fb708-234">No núcleo de um pipeline de aprendizado de máquina do ML.NET estão objetos [DataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="fb708-234">At the core of an ML.NET machine learning pipeline are [DataView](xref:Microsoft.ML.IDataView) objects.</span></span>

<span data-ttu-id="fb708-235">Cada transformação no pipeline tem um esquema de entrada (nomes, tipos e tamanhos de dados que a transformação espera ver em sua entrada); e um esquema de saída (nomes, tipos e tamanhos de dados que a transformação produz após a transformação).</span><span class="sxs-lookup"><span data-stu-id="fb708-235">Each transformation in the pipeline has an input schema (data names, types, and sizes that the transform expects to see on its input); and an output schema (data names, types, and sizes that the transform produces after the transformation).</span></span>

<span data-ttu-id="fb708-236">Se o esquema de saída de uma transformação no pipeline não corresponder ao esquema de entrada da transformação seguinte, o ML.NET gerará uma exceção.</span><span class="sxs-lookup"><span data-stu-id="fb708-236">If the output schema from one transform in the pipeline doesn't match the input schema of the next transform, ML.NET will throw an exception.</span></span>

<span data-ttu-id="fb708-237">Um objeto de exibição de dados tem colunas e linhas.</span><span class="sxs-lookup"><span data-stu-id="fb708-237">A data view object has columns and rows.</span></span> <span data-ttu-id="fb708-238">Cada coluna tem um nome, um tipo e um comprimento.</span><span class="sxs-lookup"><span data-stu-id="fb708-238">Each column has a name and a type and a length.</span></span> <span data-ttu-id="fb708-239">Por exemplo, as colunas de entrada no exemplo de preço da casa são **tamanho** e **preço**.</span><span class="sxs-lookup"><span data-stu-id="fb708-239">For example, the input columns in the house price example are **Size** and **Price**.</span></span> <span data-ttu-id="fb708-240">Eles são ambos os tipos e são quantidades escalares em vez de vetores.</span><span class="sxs-lookup"><span data-stu-id="fb708-240">They are both type and they are scalar quantities rather than vector ones.</span></span>

   ![Exemplo de Exibição de Dados do ML.NET com os dados de previsão de preço de residência](./media/ml-net-dataview.png)

<span data-ttu-id="fb708-242">Todos os algoritmos do ML.NET procuram por uma coluna de entrada que é um vetor.</span><span class="sxs-lookup"><span data-stu-id="fb708-242">All ML.NET algorithms look for an input column that is a vector.</span></span> <span data-ttu-id="fb708-243">Por padrão, essa coluna de vetor é chamada **Recursos**.</span><span class="sxs-lookup"><span data-stu-id="fb708-243">By default this vector column is called **Features**.</span></span> <span data-ttu-id="fb708-244">É por isso que estamos concatenados a coluna **Tamanho** em uma nova coluna chamada **Recursos** em nosso exemplo de preço de residência.</span><span class="sxs-lookup"><span data-stu-id="fb708-244">This is why we concatenated the **Size** column into a new column called **Features** in our house price example.</span></span>

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

<span data-ttu-id="fb708-245">Todos os algoritmos também criam novas colunas depois que executaram uma previsão.</span><span class="sxs-lookup"><span data-stu-id="fb708-245">All algorithms also create new columns after they have performed a prediction.</span></span> <span data-ttu-id="fb708-246">Os nomes fixos dessas novas colunas dependem do tipo de algoritmo de aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="fb708-246">The fixed names of these new columns depend on the type of machine learning algorithm.</span></span> <span data-ttu-id="fb708-247">Para a tarefa de regressão, uma das novas colunas é chamada **Pontuação**.</span><span class="sxs-lookup"><span data-stu-id="fb708-247">For the regression task, one of the new columns is called **Score**.</span></span> <span data-ttu-id="fb708-248">É por isso que atribuímos nossos dados de preço com esse nome.</span><span class="sxs-lookup"><span data-stu-id="fb708-248">This is why we attributed our price data with this name.</span></span>

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```

<span data-ttu-id="fb708-249">Você pode encontrar mais informações sobre colunas de saída das diferentes tarefas de aprendizado de máquina na guia [Tarefas de Aprendizado de Máquina](resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="fb708-249">You can find out more about output columns of different machine learning tasks in the [Machine Learning Tasks](resources/tasks.md) guide.</span></span>

<span data-ttu-id="fb708-250">Uma propriedade importante de objetos DataView é que eles são avaliados **lentamente**.</span><span class="sxs-lookup"><span data-stu-id="fb708-250">An important property of DataView objects is that they are evaluated **lazily**.</span></span> <span data-ttu-id="fb708-251">Exibições de dados só são carregadas e operadas durante o treinamento e a avaliação do modelo e a previsão de dados.</span><span class="sxs-lookup"><span data-stu-id="fb708-251">Data views are only loaded and operated on during model training and evaluation, and data prediction.</span></span> <span data-ttu-id="fb708-252">Enquanto você está escrevendo e testando seu aplicativo do ML.NET, pode usar o depurador do Visual Studio para dar uma espiada em qualquer objeto de exibição de dados chamando o método [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview%2A).</span><span class="sxs-lookup"><span data-stu-id="fb708-252">While you are writing and testing your ML.NET application, you can use the Visual Studio debugger to take a peek at any data view object by calling the [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview%2A) method.</span></span>

```csharp
    var debug = testPriceDataView.Preview();
```

<span data-ttu-id="fb708-253">Você pode assistir à variável `debug` no depurador e examinar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fb708-253">You can watch the `debug` variable in the debugger and examine its contents.</span></span> <span data-ttu-id="fb708-254">Não use o método Preview em código de produção, pois ele reduz significativamente o desempenho.</span><span class="sxs-lookup"><span data-stu-id="fb708-254">Do not use the Preview method in production code, as it significantly degrades performance.</span></span>

### <a name="model-deployment"></a><span data-ttu-id="fb708-255">Implantação de Modelo</span><span class="sxs-lookup"><span data-stu-id="fb708-255">Model Deployment</span></span>

<span data-ttu-id="fb708-256">Em aplicativos da vida real, seu código de avaliação e modelo de treinamento serão separados da sua previsão.</span><span class="sxs-lookup"><span data-stu-id="fb708-256">In real-life applications, your model training and evaluation code will be separate from your prediction.</span></span> <span data-ttu-id="fb708-257">Na verdade, essas duas atividades geralmente são executadas por equipes separadas.</span><span class="sxs-lookup"><span data-stu-id="fb708-257">In fact, these two activities are often performed by separate teams.</span></span> <span data-ttu-id="fb708-258">Sua equipe de desenvolvimento do modelo pode salvar o modelo para uso no aplicativo de previsão.</span><span class="sxs-lookup"><span data-stu-id="fb708-258">Your model development team can save the model for use in the prediction application.</span></span>

```csharp
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="next-steps"></a><span data-ttu-id="fb708-259">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="fb708-259">Next steps</span></span>

* <span data-ttu-id="fb708-260">Saiba como criar aplicativos usando tarefas de aprendizado de máquina diferentes com conjuntos de dados mais realistas nos [tutoriais](./tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="fb708-260">Learn how to build applications using different machine learning tasks with more realistic data sets in the [tutorials](./tutorials/index.md).</span></span>

* <span data-ttu-id="fb708-261">Saiba mais sobre tópicos específicos em mais detalhes nos [guias de instruções](./how-to-guides/index.md).</span><span class="sxs-lookup"><span data-stu-id="fb708-261">Learn about specific topics in more depth in the [How To Guides](./how-to-guides/index.md).</span></span>

* <span data-ttu-id="fb708-262">Se você estiver superando, poderá se aprofundar diretamente na [documentação de referência da API](../../api/index.md?view=ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="fb708-262">If you're super keen, you can dive straight into the [API Reference documentation](../../api/index.md?view=ml-dotnet).</span></span>
