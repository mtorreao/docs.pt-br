---
title: Ler valores de um conversor analógico/digital
description: Saiba como ler valores de tensão variável usando um conversor analógico para digital.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: eda6d8980d256c8063f2bfe1e051b0cb90b587ad
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96585644"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="read-values-from-an-analog-to-digital-converter"></a><span data-ttu-id="cd9ee-103">Ler valores de um conversor analógico/digital</span><span class="sxs-lookup"><span data-stu-id="cd9ee-103">Read values from an analog-to-digital converter</span></span>

<span data-ttu-id="cd9ee-104">Um ADC (conversor analógico para digital) é um dispositivo que pode ler um valor de tensão de entrada analógica e convertê-lo em um valor digital.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-104">An analog-to-digital converter (ADC) is a device that can read an analog input voltage value and convert it into a digital value.</span></span> <span data-ttu-id="cd9ee-105">ADCs são usados para ler valores de thermistors, potentiometers e outros dispositivos que alteram a resistência com base em determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-105">ADCs are used for reading values from thermistors, potentiometers, and other devices that change resistance based on certain conditions.</span></span>

<span data-ttu-id="cd9ee-106">Neste tópico, você usará o .NET para ler valores de um ADC à medida que você modular a voltagem de entrada com um potentiometer.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-106">In this topic, you will use .NET to read values from an ADC as you modulate the input voltage with a potentiometer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cd9ee-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="cd9ee-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="cd9ee-108">[MCP3008](https://www.microchip.com/wwwproducts/MCP3008) <span class="docon docon-navigate-external x-hidden-focus"></span> conversor analógico para digital</span><span class="sxs-lookup"><span data-stu-id="cd9ee-108">[MCP3008](https://www.microchip.com/wwwproducts/MCP3008) <span class="docon docon-navigate-external x-hidden-focus"></span> analog-to-digital converter</span></span>
- <span data-ttu-id="cd9ee-109">Potentiometer de três pinos</span><span class="sxs-lookup"><span data-stu-id="cd9ee-109">Three-pin potentiometer</span></span>
- <span data-ttu-id="cd9ee-110">Placa universal</span><span class="sxs-lookup"><span data-stu-id="cd9ee-110">Breadboard</span></span>
- <span data-ttu-id="cd9ee-111">Cabos de jumper</span><span class="sxs-lookup"><span data-stu-id="cd9ee-111">Jumper wires</span></span>
- <span data-ttu-id="cd9ee-112">Painel de debates do Raspberry Pi GPIO (opcional/recomendado)</span><span class="sxs-lookup"><span data-stu-id="cd9ee-112">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [prepare-pi-spi](../includes/prepare-pi-spi.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="cd9ee-113">Preparar o hardware</span><span class="sxs-lookup"><span data-stu-id="cd9ee-113">Prepare the hardware</span></span>

<span data-ttu-id="cd9ee-114">Use os componentes de hardware para criar o circuito, conforme ilustrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="cd9ee-114">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-trimpot_spi-thumb.png" alt-text="Um diagrama Fritzing mostrando um circuito com um MCP3008 ADC e um potentiometer" lightbox="../media/rpi-trimpot_spi.png":::

<span data-ttu-id="cd9ee-116">O MCP3008 usa a SPI (interface de periférico serial) para se comunicar.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-116">The MCP3008 uses Serial Peripheral Interface (SPI) to communicate.</span></span> <span data-ttu-id="cd9ee-117">A seguir estão as conexões do MCP3008 com o Raspberry Pi e potentiometer:</span><span class="sxs-lookup"><span data-stu-id="cd9ee-117">The following are the connections from the MCP3008 to the Raspberry Pi and potentiometer:</span></span>

- <span data-ttu-id="cd9ee-118">V<sub>DD</sub> para 3.3 v (mostrado em vermelho)</span><span class="sxs-lookup"><span data-stu-id="cd9ee-118">V<sub>DD</sub> to 3.3V (shown in red)</span></span>
- <span data-ttu-id="cd9ee-119">V<sub>ref</sub> a 3.3 v (vermelho)</span><span class="sxs-lookup"><span data-stu-id="cd9ee-119">V<sub>REF</sub> to 3.3V (red)</span></span>
- <span data-ttu-id="cd9ee-120">AGND para terra (preto)</span><span class="sxs-lookup"><span data-stu-id="cd9ee-120">AGND to ground (black)</span></span>
- <span data-ttu-id="cd9ee-121">CLK a SCLK (laranja)</span><span class="sxs-lookup"><span data-stu-id="cd9ee-121">CLK to SCLK (orange)</span></span>
- <span data-ttu-id="cd9ee-122">D de<sub>saída</sub> para miso (laranja)</span><span class="sxs-lookup"><span data-stu-id="cd9ee-122">D<sub>OUT</sub> to MISO (orange)</span></span>
- <span data-ttu-id="cd9ee-123">D<sub>no</sub> MOSI (laranja)</span><span class="sxs-lookup"><span data-stu-id="cd9ee-123">D<sub>IN</sub> to MOSI (orange)</span></span>
- <span data-ttu-id="cd9ee-124">CS/SHDN para CE0 (verde)</span><span class="sxs-lookup"><span data-stu-id="cd9ee-124">CS/SHDN to CE0 (green)</span></span>
- <span data-ttu-id="cd9ee-125">DGND para terra (preto)</span><span class="sxs-lookup"><span data-stu-id="cd9ee-125">DGND to ground (black)</span></span>
- <span data-ttu-id="cd9ee-126">CH0 para pino de variável (intermediária) em potentiometer (amarelo)</span><span class="sxs-lookup"><span data-stu-id="cd9ee-126">CH0 to variable (middle) pin on potentiometer (yellow)</span></span>

<span data-ttu-id="cd9ee-127">Forneça 3,3 V e terra para os Pins externos no potentiometer.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-127">Supply 3.3V and ground to the outer pins on the potentiometer.</span></span> <span data-ttu-id="cd9ee-128">A ordem não é importante.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-128">Order is unimportant.</span></span>

<span data-ttu-id="cd9ee-129">Consulte os seguintes diagramas de pinagem conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="cd9ee-129">Refer to the following pinout diagrams as needed:</span></span>

| <span data-ttu-id="cd9ee-130">MCP3008</span><span class="sxs-lookup"><span data-stu-id="cd9ee-130">MCP3008</span></span>  | <span data-ttu-id="cd9ee-131">Raspberry Pi GPIO</span><span class="sxs-lookup"><span data-stu-id="cd9ee-131">Raspberry Pi GPIO</span></span> |
|----------|-------------------|
| :::image type="content" source="../media/mcp3008-diagram-thumb.png" alt-text="Um diagrama que mostra a pinagem do MCP3008" lightbox="../media/mcp3008-diagram.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Um diagrama que mostra a pinagem do cabeçalho GPIO do Raspberry Pi. Imagem de cortesia Raspberry Pi Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br /><span data-ttu-id="cd9ee-134">[Imagem de cortesia Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).</span><span class="sxs-lookup"><span data-stu-id="cd9ee-134">[Image courtesy Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).</span></span>
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="cd9ee-135">Crie o aplicativo</span><span class="sxs-lookup"><span data-stu-id="cd9ee-135">Create the app</span></span>

<span data-ttu-id="cd9ee-136">Conclua as seguintes etapas em seu ambiente de desenvolvimento preferido:</span><span class="sxs-lookup"><span data-stu-id="cd9ee-136">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="cd9ee-137">Crie um novo aplicativo de console .NET usando a [CLI do .net](../../core/tools/dotnet-new.md) ou o [Visual Studio](../../core/tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="cd9ee-137">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="cd9ee-138">Nomeie-o como *AdcTutorial*.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-138">Name it *AdcTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o AdcTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="cd9ee-139">Substitua o conteúdo do *Program.cs* pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="cd9ee-139">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/AdcTutorial/Program.cs" :::

    <span data-ttu-id="cd9ee-140">No código anterior:</span><span class="sxs-lookup"><span data-stu-id="cd9ee-140">In the preceding code:</span></span>

    - <span data-ttu-id="cd9ee-141">`hardwareSpiSettings` é definido como uma nova instância do `SpiConnectionSettings` .</span><span class="sxs-lookup"><span data-stu-id="cd9ee-141">`hardwareSpiSettings` is set to a new instance of `SpiConnectionSettings`.</span></span> <span data-ttu-id="cd9ee-142">O construtor define o `busId` parâmetro como 0 e o `chipSelectLine` parâmetro como 0.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-142">The constructor sets the `busId` parameter to 0 and the `chipSelectLine` parameter to 0.</span></span>
    - <span data-ttu-id="cd9ee-143">Uma [declaração using](../../csharp/whats-new/csharp-8.md#using-declarations) cria uma instância do `SpiDevice` chamando `SpiDevice.Create` e passando `hardwareSpiSettings` .</span><span class="sxs-lookup"><span data-stu-id="cd9ee-143">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `SpiDevice` by calling `SpiDevice.Create` and passing in `hardwareSpiSettings`.</span></span> <span data-ttu-id="cd9ee-144">Isso `SpiDevice` representa o barramento SPI.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-144">This `SpiDevice` represents the SPI bus.</span></span> <span data-ttu-id="cd9ee-145">A `using` declaração garante que o objeto seja descartado e que os recursos de hardware sejam liberados corretamente.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-145">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="cd9ee-146">Outra `using` declaração cria uma instância do `Mcp3008` e passa o `SpiDevice` para o construtor.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-146">Another `using` declaration creates an instance of `Mcp3008` and passes the `SpiDevice` into the constructor.</span></span>
    - <span data-ttu-id="cd9ee-147">Um `while` loop é executado indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-147">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="cd9ee-148">Cada iteração:</span><span class="sxs-lookup"><span data-stu-id="cd9ee-148">Each iteration:</span></span>
        1. <span data-ttu-id="cd9ee-149">Lê o valor de CH0 no ADC chamando `mcp.Read(0)` .</span><span class="sxs-lookup"><span data-stu-id="cd9ee-149">Reads the value of CH0 on the ADC by calling `mcp.Read(0)`.</span></span>
        1. <span data-ttu-id="cd9ee-150">Divide o valor de 10,24.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-150">Divides the value by 10.24.</span></span> <span data-ttu-id="cd9ee-151">O MCP3008 é um ADC de 10 bits, o que significa que ele retorna 1024 valores possíveis variando 0-1023.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-151">The MCP3008 is a 10-bit ADC, which means it returns 1024 possible values ranging 0-1023.</span></span> <span data-ttu-id="cd9ee-152">Dividir o valor de 10,24 representa o valor como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-152">Dividing the value by 10.24 represents the value as a percentage.</span></span>
        1. <span data-ttu-id="cd9ee-153">Arredonda o valor para o número inteiro mais próximo.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-153">Rounds the value to the nearest integer.</span></span>
        1. <span data-ttu-id="cd9ee-154">Grava o valor no console formatado como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-154">Writes the value to the console formatted as a percentage.</span></span>
        1. <span data-ttu-id="cd9ee-155">Dorme 500 ms.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-155">Sleeps 500 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="cd9ee-156">Execute o aplicativo no Raspberry Pi alternando para o diretório de implantação e executando o executável.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-156">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./AdcTutorial
    ```

    <span data-ttu-id="cd9ee-157">Observe a saída à medida que você gira o potentiometer de discagem.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-157">Observe the output as you rotate the potentiometer dial.</span></span> <span data-ttu-id="cd9ee-158">Isso ocorre devido ao potentiometer que varia a voltagem fornecida para CH0 no ADC.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-158">This is due to the potentiometer varying the voltage supplied to CH0 on the ADC.</span></span> <span data-ttu-id="cd9ee-159">O ADC compara a tensão de entrada em CH0 com a voltagem de referência fornecida para V<sub>ref</sub> para gerar um valor.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-159">The ADC compares the input voltage on CH0 to the reference voltage supplied to V<sub>REF</sub> to generate a value.</span></span>

1. <span data-ttu-id="cd9ee-160">Encerre o programa pressionando <kbd>Ctrl + C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-160">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="cd9ee-161">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="cd9ee-161">Congratulations!</span></span> <span data-ttu-id="cd9ee-162">Você usou o SPI para ler valores de um conversor analógico para digital.</span><span class="sxs-lookup"><span data-stu-id="cd9ee-162">You've used SPI to read values from an analog-to-digital converter.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="cd9ee-163">Obter o código-fonte</span><span class="sxs-lookup"><span data-stu-id="cd9ee-163">Get the source code</span></span>

<span data-ttu-id="cd9ee-164">A fonte deste tutorial está [disponível no GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial).</span><span class="sxs-lookup"><span data-stu-id="cd9ee-164">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial).</span></span> <span class="docon docon-navigate-external x-hidden-focus"></span>

## <a name="next-steps"></a><span data-ttu-id="cd9ee-165">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="cd9ee-165">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cd9ee-166">Saiba como usar Uso Geral entrada/saída para piscar um LED</span><span class="sxs-lookup"><span data-stu-id="cd9ee-166">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
