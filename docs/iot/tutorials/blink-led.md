---
title: Fazer um LED piscar
description: Saiba como piscar um LED com as bibliotecas IoT do .NET.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 07a050c0655f9cae3d7f2b924c0dd07ac1c6c0b9
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96585646"
---
# <a name="blink-an-led"></a><span data-ttu-id="1641b-103">Fazer um LED piscar</span><span class="sxs-lookup"><span data-stu-id="1641b-103">Blink an LED</span></span>

<span data-ttu-id="1641b-104">Os Pins de e/s de uso geral (GPIO) podem ser controlados individualmente.</span><span class="sxs-lookup"><span data-stu-id="1641b-104">General-purpose I/O (GPIO) pins can be controlled individually.</span></span> <span data-ttu-id="1641b-105">Isso é útil para controlar LEDs, retransmissões e outros dispositivos com estado.</span><span class="sxs-lookup"><span data-stu-id="1641b-105">This is useful for controlling LEDs, relays, and other stateful devices.</span></span> <span data-ttu-id="1641b-106">Neste tópico, você usará o .NET e seus PINs de GPIO do Raspberry Pi para ligar um LED e piscar repetidamente.</span><span class="sxs-lookup"><span data-stu-id="1641b-106">In this topic, you will use .NET and your Raspberry Pi's GPIO pins to power an LED and blink it repeatedly.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1641b-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1641b-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="1641b-108">LED de 5 mm</span><span class="sxs-lookup"><span data-stu-id="1641b-108">5 mm LED</span></span>
- <span data-ttu-id="1641b-109">330 resresistência Ω</span><span class="sxs-lookup"><span data-stu-id="1641b-109">330 Ω resistor</span></span>
- <span data-ttu-id="1641b-110">Placa universal</span><span class="sxs-lookup"><span data-stu-id="1641b-110">Breadboard</span></span>
- <span data-ttu-id="1641b-111">Cabos de jumper</span><span class="sxs-lookup"><span data-stu-id="1641b-111">Jumper wires</span></span>
- <span data-ttu-id="1641b-112">Painel de debates do Raspberry Pi GPIO (opcional/recomendado)</span><span class="sxs-lookup"><span data-stu-id="1641b-112">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [ensure-ssh](../includes/ensure-ssh.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="1641b-113">Preparar o hardware</span><span class="sxs-lookup"><span data-stu-id="1641b-113">Prepare the hardware</span></span>

<span data-ttu-id="1641b-114">Use os componentes de hardware para criar o circuito, conforme ilustrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="1641b-114">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-led_bb-thumb.png" alt-text="Um diagrama Fritzing mostrando um circuito com um LED e um resistor" lightbox="../media/rpi-led_bb.png":::

<span data-ttu-id="1641b-116">A imagem acima ilustra as seguintes conexões:</span><span class="sxs-lookup"><span data-stu-id="1641b-116">The image above depicts the following connections:</span></span>

- <span data-ttu-id="1641b-117">GPIO 18 para LEDs nó (mais longo, líder positivo)</span><span class="sxs-lookup"><span data-stu-id="1641b-117">GPIO 18 to LED anode (longer, positive lead)</span></span>
- <span data-ttu-id="1641b-118">Catodo de LED (Lead de menor, negativo) a 330 Ω de resresistência (qualquer fim)</span><span class="sxs-lookup"><span data-stu-id="1641b-118">LED cathode (shorter, negative lead) to 330 Ω resistor (either end)</span></span>
- <span data-ttu-id="1641b-119">330 resresistência Ω (outra extremidade) ao solo</span><span class="sxs-lookup"><span data-stu-id="1641b-119">330 Ω resistor (other end) to ground</span></span>

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="1641b-120">Crie o aplicativo</span><span class="sxs-lookup"><span data-stu-id="1641b-120">Create the app</span></span>

<span data-ttu-id="1641b-121">Conclua as seguintes etapas em seu ambiente de desenvolvimento preferido:</span><span class="sxs-lookup"><span data-stu-id="1641b-121">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="1641b-122">Crie um novo aplicativo de console .NET usando a [CLI do .net](../../core/tools/dotnet-new.md) ou o [Visual Studio](../../core/tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="1641b-122">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="1641b-123">Nomeie-o como *BlinkTutorial*.</span><span class="sxs-lookup"><span data-stu-id="1641b-123">Name it *BlinkTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o BlinkTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="1641b-124">Substitua o conteúdo do *Program.cs* pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="1641b-124">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/BlinkTutorial/Program.cs" :::

    <span data-ttu-id="1641b-125">No código anterior:</span><span class="sxs-lookup"><span data-stu-id="1641b-125">In the preceding code:</span></span>

    - <span data-ttu-id="1641b-126">Uma [declaração using](../../csharp/whats-new/csharp-8.md#using-declarations) cria uma instância do `GpioController` .</span><span class="sxs-lookup"><span data-stu-id="1641b-126">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `GpioController`.</span></span> <span data-ttu-id="1641b-127">A `using` declaração garante que o objeto seja descartado e que os recursos de hardware sejam liberados corretamente.</span><span class="sxs-lookup"><span data-stu-id="1641b-127">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="1641b-128">O GPIO pino 18 está aberto para saída</span><span class="sxs-lookup"><span data-stu-id="1641b-128">GPIO pin 18 is opened for output</span></span>
    - <span data-ttu-id="1641b-129">Um `while` loop é executado indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="1641b-129">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="1641b-130">Cada iteração:</span><span class="sxs-lookup"><span data-stu-id="1641b-130">Each iteration:</span></span>
        1. <span data-ttu-id="1641b-131">Grava um valor no GPIO pino 18.</span><span class="sxs-lookup"><span data-stu-id="1641b-131">Writes a value to GPIO pin 18.</span></span> <span data-ttu-id="1641b-132">Se `ledOn` for true, ele gravará `PinValue.High` (ativado).</span><span class="sxs-lookup"><span data-stu-id="1641b-132">If `ledOn` is true, it writes `PinValue.High` (on).</span></span> <span data-ttu-id="1641b-133">Caso contrário, ele grava `PinValue.Low` .</span><span class="sxs-lookup"><span data-stu-id="1641b-133">Otherwise, it writes `PinValue.Low`.</span></span>
        1. <span data-ttu-id="1641b-134">Dorme 1000 MS.</span><span class="sxs-lookup"><span data-stu-id="1641b-134">Sleeps 1000 ms.</span></span>
        1. <span data-ttu-id="1641b-135">Alterna o valor de `ledOn` .</span><span class="sxs-lookup"><span data-stu-id="1641b-135">Toggles the value of `ledOn`.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="1641b-136">Execute o aplicativo no Raspberry Pi alternando para o diretório de implantação e executando o executável.</span><span class="sxs-lookup"><span data-stu-id="1641b-136">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./BlinkTutorial
    ```

    <span data-ttu-id="1641b-137">O LED pisca e a cada segundo.</span><span class="sxs-lookup"><span data-stu-id="1641b-137">The LED blinks off and on every second.</span></span>

1. <span data-ttu-id="1641b-138">Encerre o programa pressionando <kbd>Ctrl + C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="1641b-138">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="1641b-139">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="1641b-139">Congratulations!</span></span> <span data-ttu-id="1641b-140">Você usou o GPIO para piscar um LED.</span><span class="sxs-lookup"><span data-stu-id="1641b-140">You've used GPIO to blink an LED.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="1641b-141">Obter o código-fonte</span><span class="sxs-lookup"><span data-stu-id="1641b-141">Get the source code</span></span>

<span data-ttu-id="1641b-142">A fonte deste tutorial está [disponível no GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="1641b-142">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1641b-143">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="1641b-143">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1641b-144">Saiba como ler condições ambientais de um sensor</span><span class="sxs-lookup"><span data-stu-id="1641b-144">Learn how to read environmental conditions from a sensor</span></span>](../tutorials/temp-sensor.md)
