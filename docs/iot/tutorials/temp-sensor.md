---
title: Ler condições ambientais com um sensor
description: Saiba como ler termperature, pressão barométrica e umidade com as bibliotecas IoT .NET.
author: camsoper
ms.author: casoper
ms.date: 11/14/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 1270e7629e9afc12b1d76d260d4b8b51428f1040
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96585647"
---
# <a name="read-environmental-conditions-from-a-sensor"></a><span data-ttu-id="d5ee2-103">Ler condições ambientais com um sensor</span><span class="sxs-lookup"><span data-stu-id="d5ee2-103">Read environmental conditions from a sensor</span></span>

<span data-ttu-id="d5ee2-104">Um dos cenários mais comuns para dispositivos IoT é a detecção de condições ambientais.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-104">One of the most common scenarios for IoT devices is detection of environmental conditions.</span></span> <span data-ttu-id="d5ee2-105">Uma variedade de sensores está disponível para monitorar a temperatura, a umidade, a pressão barométrica e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-105">A variety of sensors are available to monitor temperature, humidity, barometric pressure, and more.</span></span>

<span data-ttu-id="d5ee2-106">Neste tópico, você usará o .NET para ler as condições ambientais de um sensor.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-106">In this topic, you will use .NET to read environmental conditions from a sensor.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d5ee2-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d5ee2-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="d5ee2-108">[BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) <span class="docon docon-navigate-external x-hidden-focus"></span> análise de sensor de temperatura/pressão de umidade/barométrica</span><span class="sxs-lookup"><span data-stu-id="d5ee2-108">[BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) <span class="docon docon-navigate-external x-hidden-focus"></span> humidity/barometric pressure/temperature sensor breakout</span></span>
- <span data-ttu-id="d5ee2-109">Cabos de jumper</span><span class="sxs-lookup"><span data-stu-id="d5ee2-109">Jumper wires</span></span>
- <span data-ttu-id="d5ee2-110">Placa universal (opcional)</span><span class="sxs-lookup"><span data-stu-id="d5ee2-110">Breadboard (optional)</span></span>
- <span data-ttu-id="d5ee2-111">Painel de debates do Raspberry Pi GPIO (opcional)</span><span class="sxs-lookup"><span data-stu-id="d5ee2-111">Raspberry Pi GPIO breakout board (optional)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!IMPORTANT]
> <span data-ttu-id="d5ee2-112">Há muitos fabricantes de debates de BME280.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-112">There are many manufacturers of BME280 breakouts.</span></span> <span data-ttu-id="d5ee2-113">A maioria dos designs são semelhantes, e o fabricante não deve fazer nenhuma diferença na funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-113">Most designs are similar, and the manufacturer shouldn't make any difference to the functionality.</span></span> <span data-ttu-id="d5ee2-114">Este tutorial tenta considerar as variações.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-114">This tutorial attempts to account for variations.</span></span> <span data-ttu-id="d5ee2-115">Certifique-se de que sua análise de BME280 inclui uma interface de circuito de Inter-Integrated (I2C).</span><span class="sxs-lookup"><span data-stu-id="d5ee2-115">Ensure your BME280 breakout includes an Inter-Integrated Circuit (I2C) interface.</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="d5ee2-116">Preparar o hardware</span><span class="sxs-lookup"><span data-stu-id="d5ee2-116">Prepare the hardware</span></span>

<span data-ttu-id="d5ee2-117">Use os componentes de hardware para criar o circuito, conforme ilustrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="d5ee2-117">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-bmp280_i2c-thumb.png" alt-text="Um diagrama do Fritzing mostrando a conexão do Raspberry Pi com o painel de debates do BME280" lightbox="../media/rpi-bmp280_i2c.png":::

<span data-ttu-id="d5ee2-119">A seguir estão as conexões do Raspberry Pi com a análise de BME280:</span><span class="sxs-lookup"><span data-stu-id="d5ee2-119">The following are the connections from the Raspberry Pi to the BME280 breakout:</span></span>

- <span data-ttu-id="d5ee2-120">3.3 v a VIN *ou* 3v3 (mostrado em vermelho)</span><span class="sxs-lookup"><span data-stu-id="d5ee2-120">3.3V to VIN *OR* 3V3 (shown in red)</span></span>
- <span data-ttu-id="d5ee2-121">Terra a terra (preto)</span><span class="sxs-lookup"><span data-stu-id="d5ee2-121">Ground to GND (black)</span></span>
- <span data-ttu-id="d5ee2-122">SDA (GPIO 2) para SDI *ou* SDA (azul)</span><span class="sxs-lookup"><span data-stu-id="d5ee2-122">SDA (GPIO 2) to SDI *OR* SDA (blue)</span></span>
- <span data-ttu-id="d5ee2-123">SCL (GPIO 3) a SCK *ou* SCL (laranja)</span><span class="sxs-lookup"><span data-stu-id="d5ee2-123">SCL (GPIO 3) to SCK *OR* SCL (orange)</span></span>

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="d5ee2-124">Crie o aplicativo</span><span class="sxs-lookup"><span data-stu-id="d5ee2-124">Create the app</span></span>

<span data-ttu-id="d5ee2-125">Conclua as seguintes etapas em seu ambiente de desenvolvimento preferido:</span><span class="sxs-lookup"><span data-stu-id="d5ee2-125">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="d5ee2-126">Crie um novo aplicativo de console .NET usando a [CLI do .net](../../core/tools/dotnet-new.md) ou o [Visual Studio](../../core/tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d5ee2-126">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="d5ee2-127">Nomeie-o como *SensorTutorial*.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-127">Name it *SensorTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o SensorTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="d5ee2-128">Substitua o conteúdo do *Program.cs* pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="d5ee2-128">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/SensorTutorial/Program.cs" :::

    <span data-ttu-id="d5ee2-129">No código anterior:</span><span class="sxs-lookup"><span data-stu-id="d5ee2-129">In the preceding code:</span></span>

    - <span data-ttu-id="d5ee2-130">`i2cSettings` é definido como uma nova instância do `I2cConnectionSettings` .</span><span class="sxs-lookup"><span data-stu-id="d5ee2-130">`i2cSettings` is set to a new instance of `I2cConnectionSettings`.</span></span> <span data-ttu-id="d5ee2-131">O construtor define o `busId` parâmetro como 1 e o `deviceAddress` parâmetro como `Bme280.DefaultI2cAddress` .</span><span class="sxs-lookup"><span data-stu-id="d5ee2-131">The constructor sets the `busId` parameter to 1 and the `deviceAddress` parameter to `Bme280.DefaultI2cAddress`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="d5ee2-132">Alguns fabricantes de debates BME280 usam o valor de endereço secundário.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-132">Some BME280 breakout manufacturers use the secondary address value.</span></span> <span data-ttu-id="d5ee2-133">Para esses dispositivos, use `Bme280.SecondaryI2cAddress` .</span><span class="sxs-lookup"><span data-stu-id="d5ee2-133">For those devices, use `Bme280.SecondaryI2cAddress`.</span></span>

    - <span data-ttu-id="d5ee2-134">Uma [declaração using](../../csharp/whats-new/csharp-8.md#using-declarations) cria uma instância do `I2cDevice` chamando `I2cDevice.Create` e passando `i2cSettings` .</span><span class="sxs-lookup"><span data-stu-id="d5ee2-134">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `I2cDevice` by calling `I2cDevice.Create` and passing in `i2cSettings`.</span></span> <span data-ttu-id="d5ee2-135">Isso `I2cDevice` representa o barramento I2C.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-135">This `I2cDevice` represents the I2C bus.</span></span> <span data-ttu-id="d5ee2-136">A `using` declaração garante que o objeto seja descartado e que os recursos de hardware sejam liberados corretamente.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-136">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="d5ee2-137">Outra `using` declaração cria uma instância do `Bme280` para representar o sensor.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-137">Another `using` declaration creates an instance of `Bme280` to represent the sensor.</span></span> <span data-ttu-id="d5ee2-138">O `I2cDevice` é passado no construtor.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-138">The `I2cDevice` is passed in the constructor.</span></span>
    - <span data-ttu-id="d5ee2-139">O tempo necessário para o chip tomar medidas com as configurações atuais (padrão) do chip é recuperado chamando `GetMeasurementDuration` .</span><span class="sxs-lookup"><span data-stu-id="d5ee2-139">The time required for the chip to take measurements with the chip's current (default) settings is retrieved by calling `GetMeasurementDuration`.</span></span>
    - <span data-ttu-id="d5ee2-140">Um `while` loop é executado indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-140">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="d5ee2-141">Cada iteração:</span><span class="sxs-lookup"><span data-stu-id="d5ee2-141">Each iteration:</span></span>
        1. <span data-ttu-id="d5ee2-142">Limpa o console.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-142">Clears the console.</span></span>
        1. <span data-ttu-id="d5ee2-143">Define o modo de energia como `Bmx280PowerMode.Forced` .</span><span class="sxs-lookup"><span data-stu-id="d5ee2-143">Sets the power mode to `Bmx280PowerMode.Forced`.</span></span> <span data-ttu-id="d5ee2-144">Isso força o chip a executar uma medição, armazenar os resultados e, em seguida, dormir.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-144">This forces the chip to perform one measurement, store the results, and then sleep.</span></span>
        1. <span data-ttu-id="d5ee2-145">Lê os valores de temperatura, pressão, umidade e altitude.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-145">Reads the values for temperature, pressure, humidity, and altitude.</span></span>

            > [!NOTE]
            > <span data-ttu-id="d5ee2-146">A altitude é calculada pela Associação de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-146">Altitude is calculated by the device binding.</span></span> <span data-ttu-id="d5ee2-147">Essa sobrecarga de `TryReadAltitude` usa pressão do nível médio do mar para gerar uma estimativa.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-147">This overload of `TryReadAltitude` uses mean sea level pressure to generate an estimate.</span></span>

        1. <span data-ttu-id="d5ee2-148">Grava as condições ambientais atuais no console.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-148">Writes the current environmental conditions to the console.</span></span>
        1. <span data-ttu-id="d5ee2-149">Dorme 1000 MS.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-149">Sleeps 1000 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="d5ee2-150">Execute o aplicativo no Raspberry Pi alternando para o diretório de implantação e executando o executável.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-150">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./SensorTutorial
    ```

    <span data-ttu-id="d5ee2-151">Observe a saída do sensor no console.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-151">Observe the sensor output in the console.</span></span>

1. <span data-ttu-id="d5ee2-152">Encerre o programa pressionando <kbd>Ctrl + C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d5ee2-152">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="d5ee2-153">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="d5ee2-153">Congratulations!</span></span> <span data-ttu-id="d5ee2-154">Você usou I2C para ler valores de um sensor de pressão de temperatura/umidade/barométrica!</span><span class="sxs-lookup"><span data-stu-id="d5ee2-154">You've used I2C to read values from a temperature/humidity/barometric pressure sensor!</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="d5ee2-155">Obter o código-fonte</span><span class="sxs-lookup"><span data-stu-id="d5ee2-155">Get the source code</span></span>

<span data-ttu-id="d5ee2-156">A fonte deste tutorial está [disponível no GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="d5ee2-156">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d5ee2-157">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d5ee2-157">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d5ee2-158">Saiba como exibir texto em um LCD</span><span class="sxs-lookup"><span data-stu-id="d5ee2-158">Learn how to display text on an LCD</span></span>](../tutorials/lcd-display.md)
