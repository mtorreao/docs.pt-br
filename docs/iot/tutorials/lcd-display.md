---
title: Exibir texto em uma tela LCD
description: Saiba como exibir caracteres em uma tela de cristal líquido com as bibliotecas IoT do .NET.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: d4c3e373207e23877903491871f4d09e11000c1a
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96585641"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="display-text-on-an-lcd"></a><span data-ttu-id="f52a7-103">Exibir texto em uma tela LCD</span><span class="sxs-lookup"><span data-stu-id="f52a7-103">Display text on an LCD</span></span>

<span data-ttu-id="f52a7-104">As exibições de caractere LCD são úteis para exibir informações sem a necessidade de um monitor externo.</span><span class="sxs-lookup"><span data-stu-id="f52a7-104">LCD character displays are useful for displaying information without the need for an external monitor.</span></span> <span data-ttu-id="f52a7-105">As exibições comuns de caracteres de LCD podem ser conectadas diretamente aos pins do GPIO, mas essa abordagem requer o uso de até 10 pinos do GPIO.</span><span class="sxs-lookup"><span data-stu-id="f52a7-105">Common LCD character displays can be connected directly to the GPIO pins, but such an approach requires the use of up to 10 GPIO pins.</span></span> <span data-ttu-id="f52a7-106">Para cenários que exigem a conexão a uma combinação de dispositivos, a maior parte do cabeçalho GPIO para uma exibição de caractere geralmente é impraticável.</span><span class="sxs-lookup"><span data-stu-id="f52a7-106">For scenarios that require connecting to a combination of devices, devoting so much of the GPIO header to a character display is often impractical.</span></span>

<span data-ttu-id="f52a7-107">Muitos fabricantes vendem 20x4 de caracteres de LCD com um expansor de GPIO integrado.</span><span class="sxs-lookup"><span data-stu-id="f52a7-107">Many manufacturers sell 20x4 LCD character displays with an integrated GPIO expander.</span></span> <span data-ttu-id="f52a7-108">A exibição de caractere conecta-se diretamente ao expansor do GPIO, que se conecta ao Raspberry Pi por meio do protocolo serial do circuito de Inter-Integrated (I2C).</span><span class="sxs-lookup"><span data-stu-id="f52a7-108">The character display connects directly to the GPIO expander, which then connects to the Raspberry Pi via the Inter-Integrated Circuit (I2C) serial protocol.</span></span>

<span data-ttu-id="f52a7-109">Neste tópico, você usará o .NET para exibir texto em uma exibição de caractere de LCD usando um expansor de GPIO I2C.</span><span class="sxs-lookup"><span data-stu-id="f52a7-109">In this topic, you will use .NET to display text on an LCD character display using an I2C GPIO expander.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f52a7-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f52a7-110">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="f52a7-111">[exibição de caractere LCD 20x4 com interface I2C](https://www.bing.com/images/search?q=20x4+lcd+display+with+i2c)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="f52a7-111">[20x4 LCD Character Display with I2C interface](https://www.bing.com/images/search?q=20x4+lcd+display+with+i2c) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="f52a7-112">Cabos de jumper</span><span class="sxs-lookup"><span data-stu-id="f52a7-112">Jumper wires</span></span>
- <span data-ttu-id="f52a7-113">Placa universal (opcional/recomendado)</span><span class="sxs-lookup"><span data-stu-id="f52a7-113">Breadboard (optional/recommended)</span></span>
- <span data-ttu-id="f52a7-114">Painel de debates do Raspberry Pi GPIO (opcional/recomendado)</span><span class="sxs-lookup"><span data-stu-id="f52a7-114">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!NOTE]
> <span data-ttu-id="f52a7-115">Há muitos fabricantes de telas de caracteres de LCD.</span><span class="sxs-lookup"><span data-stu-id="f52a7-115">There are many manufacturers of LCD character displays.</span></span> <span data-ttu-id="f52a7-116">A maioria dos designs são idênticos e o fabricante não deve fazer nenhuma diferença na funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f52a7-116">Most designs are identical, and the manufacturer shouldn't make any difference to the functionality.</span></span> <span data-ttu-id="f52a7-117">Para referência, este tutorial foi desenvolvido com o [LCD2004 do amfundador](https://www.sunfounder.com/lcd2004-module.html) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="f52a7-117">For reference, this tutorial was developed with the [SunFounder LCD2004](https://www.sunfounder.com/lcd2004-module.html) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="f52a7-118">Preparar o hardware</span><span class="sxs-lookup"><span data-stu-id="f52a7-118">Prepare the hardware</span></span>

<span data-ttu-id="f52a7-119">Use cabos de jumper para conectar os quatro Pins no expansor do GPIO do I2C ao Raspberry Pi da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f52a7-119">Use jumper wires to connect the four pins on the I2C GPIO expander to the Raspberry Pi as follows:</span></span>

- <span data-ttu-id="f52a7-120">GND para terra</span><span class="sxs-lookup"><span data-stu-id="f52a7-120">GND to ground</span></span>
- <span data-ttu-id="f52a7-121">VCC a 5V</span><span class="sxs-lookup"><span data-stu-id="f52a7-121">VCC to 5V</span></span>
- <span data-ttu-id="f52a7-122">SDA para SDA (GPIO 2)</span><span class="sxs-lookup"><span data-stu-id="f52a7-122">SDA to SDA (GPIO 2)</span></span>
- <span data-ttu-id="f52a7-123">SCL para SCL (GPIO 3)</span><span class="sxs-lookup"><span data-stu-id="f52a7-123">SCL to SCL (GPIO 3)</span></span>

<span data-ttu-id="f52a7-124">Consulte as seguintes figuras, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="f52a7-124">Refer to the following figures as needed:</span></span>

| <span data-ttu-id="f52a7-125">Interface I2C (parte traseira da exibição)</span><span class="sxs-lookup"><span data-stu-id="f52a7-125">I2C interface (back of display)</span></span> | <span data-ttu-id="f52a7-126">Raspberry Pi GPIO</span><span class="sxs-lookup"><span data-stu-id="f52a7-126">Raspberry Pi GPIO</span></span> |
|---------------------------------|-------------------|
| :::image type="content" source="../media/character-display-i2c-thumb.png" alt-text="Uma imagem da parte traseira da exibição de caractere mostrando o expansor de GPIO de I2C." lightbox="../media/character-display-i2c.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Um diagrama que mostra a pinagem do cabeçalho GPIO do Raspberry Pi. Imagem de cortesia Raspberry Pi Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br /><span data-ttu-id="f52a7-129">[Imagem de cortesia Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="f52a7-129">[Image courtesy Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="f52a7-130">Crie o aplicativo</span><span class="sxs-lookup"><span data-stu-id="f52a7-130">Create the app</span></span>

<span data-ttu-id="f52a7-131">Conclua as seguintes etapas em seu ambiente de desenvolvimento preferido:</span><span class="sxs-lookup"><span data-stu-id="f52a7-131">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="f52a7-132">Crie um novo aplicativo de console .NET usando a [CLI do .net](../../core/tools/dotnet-new.md) ou o [Visual Studio](../../core/tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="f52a7-132">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="f52a7-133">Nomeie-o como *LcdTutorial*.</span><span class="sxs-lookup"><span data-stu-id="f52a7-133">Name it *LcdTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o LcdTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="f52a7-134">Substitua o conteúdo do *Program.cs* pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="f52a7-134">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/LcdTutorial/Program.cs" :::

    <span data-ttu-id="f52a7-135">No código anterior:</span><span class="sxs-lookup"><span data-stu-id="f52a7-135">In the preceding code:</span></span>

    - <span data-ttu-id="f52a7-136">Uma [declaração using](../../csharp/whats-new/csharp-8.md#using-declarations) cria uma instância do `I2cDevice` chamando `I2cDevice.Create` e passando um novo `I2cConnectionSettings` com os `busId` `deviceAddress` parâmetros e.</span><span class="sxs-lookup"><span data-stu-id="f52a7-136">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `I2cDevice` by calling `I2cDevice.Create` and passing in a new `I2cConnectionSettings` with the `busId` and `deviceAddress` parameters.</span></span> <span data-ttu-id="f52a7-137">Isso `I2cDevice` representa o barramento I2C.</span><span class="sxs-lookup"><span data-stu-id="f52a7-137">This `I2cDevice` represents the I2C bus.</span></span> <span data-ttu-id="f52a7-138">A `using` declaração garante que o objeto seja descartado e que os recursos de hardware sejam liberados corretamente.</span><span class="sxs-lookup"><span data-stu-id="f52a7-138">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>

        > [!WARNING]
        > <span data-ttu-id="f52a7-139">O endereço do dispositivo para o expansor do GPIO depende do chip usado pelo fabricante.</span><span class="sxs-lookup"><span data-stu-id="f52a7-139">The device address for the GPIO expander depends on the chip used by the manufacturer.</span></span> <span data-ttu-id="f52a7-140">Os expansores GPIO equipados com um PCF8574 usam o endereço `0x27` , enquanto aqueles que usam chips PCF8574A usam `0x3F` .</span><span class="sxs-lookup"><span data-stu-id="f52a7-140">GPIO expanders equipped with a PCF8574 use the address `0x27`, while those using PCF8574A chips use `0x3F`.</span></span> <span data-ttu-id="f52a7-141">Consulte a documentação do LCD.</span><span class="sxs-lookup"><span data-stu-id="f52a7-141">Consult your LCD's documentation.</span></span>

    - <span data-ttu-id="f52a7-142">Outra `using` declaração cria uma instância do `Pcf8574` e passa o `I2cDevice` para o construtor.</span><span class="sxs-lookup"><span data-stu-id="f52a7-142">Another `using` declaration creates an instance of `Pcf8574` and passes the `I2cDevice` into the constructor.</span></span> <span data-ttu-id="f52a7-143">Essa instância representa o expansor do GPIO.</span><span class="sxs-lookup"><span data-stu-id="f52a7-143">This instance represents the GPIO expander.</span></span>
    - <span data-ttu-id="f52a7-144">Outra `using` declaração cria uma instância do `Lcd2004` para representar a exibição.</span><span class="sxs-lookup"><span data-stu-id="f52a7-144">Another `using` declaration creates an instance of `Lcd2004` to represent the display.</span></span> <span data-ttu-id="f52a7-145">Vários parâmetros são passados para o construtor que descreve as configurações a serem usadas para se comunicar com o expansor do GPIO.</span><span class="sxs-lookup"><span data-stu-id="f52a7-145">Several parameters are passed to the constructor describing the settings to use to communicate with the GPIO expander.</span></span> <span data-ttu-id="f52a7-146">O expansor do GPIO é passado como o `controller` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f52a7-146">The GPIO expander is passed as the `controller` parameter.</span></span>
    - <span data-ttu-id="f52a7-147">Um `while` loop é executado indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="f52a7-147">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="f52a7-148">Cada iteração:</span><span class="sxs-lookup"><span data-stu-id="f52a7-148">Each iteration:</span></span>
        1. <span data-ttu-id="f52a7-149">Limpa a exibição.</span><span class="sxs-lookup"><span data-stu-id="f52a7-149">Clears the display.</span></span>
        1. <span data-ttu-id="f52a7-150">Define a posição do cursor para a primeira posição na linha atual.</span><span class="sxs-lookup"><span data-stu-id="f52a7-150">Sets the cursor position to the first position on the current line.</span></span>
        1. <span data-ttu-id="f52a7-151">Grava a hora atual para a exibição na posição atual do cursor.</span><span class="sxs-lookup"><span data-stu-id="f52a7-151">Writes the current time to the display at the current cursor position.</span></span>
        1. <span data-ttu-id="f52a7-152">Itera o contador de linha atual.</span><span class="sxs-lookup"><span data-stu-id="f52a7-152">Iterates the current line counter.</span></span>
        1. <span data-ttu-id="f52a7-153">Dorme 1000 MS.</span><span class="sxs-lookup"><span data-stu-id="f52a7-153">Sleeps 1000 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="f52a7-154">Execute o aplicativo no Raspberry Pi alternando para o diretório de implantação e executando o executável.</span><span class="sxs-lookup"><span data-stu-id="f52a7-154">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./LcdTutorial
    ```

    <span data-ttu-id="f52a7-155">Observe que o caractere LCD é exibido conforme a hora atual é exibida em cada linha.</span><span class="sxs-lookup"><span data-stu-id="f52a7-155">Observe the LCD character display as the current time displays on each line.</span></span>

    > [!TIP]
    > <span data-ttu-id="f52a7-156">Se a exibição estiver acesa, mas você não vir nenhum texto, tente ajustar o contraste de discagem na parte traseira da tela.</span><span class="sxs-lookup"><span data-stu-id="f52a7-156">If the display is lit but you don't see any text, try adjusting the contrast dial on the back of the display.</span></span>

1. <span data-ttu-id="f52a7-157">Encerre o programa pressionando <kbd>Ctrl + C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f52a7-157">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="f52a7-158">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="f52a7-158">Congratulations!</span></span> <span data-ttu-id="f52a7-159">Você exibiu o texto em um LCD usando um expansor I2C e um de GPIO!</span><span class="sxs-lookup"><span data-stu-id="f52a7-159">You've displayed text on an LCD using a I2C and a GPIO expander!</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="f52a7-160">Obter o código-fonte</span><span class="sxs-lookup"><span data-stu-id="f52a7-160">Get the source code</span></span>

<span data-ttu-id="f52a7-161">A fonte deste tutorial está [disponível no GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="f52a7-161">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f52a7-162">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f52a7-162">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f52a7-163">Saiba como usar Uso Geral entrada/saída para piscar um LED</span><span class="sxs-lookup"><span data-stu-id="f52a7-163">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
