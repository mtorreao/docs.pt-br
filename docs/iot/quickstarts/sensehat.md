---
title: Início rápido – usar o .NET para impulsionar um Raspberry Pi sensor HAT
description: Introdução às bibliotecas de IoT do .NET em 5 minutos usando um sensor de detecção, uma placa complementar para o Raspberry Pi.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: quickstart
ms.prod: dotnet
ms.openlocfilehash: 2919db55304590f5557aa0cbda50cc4bd6640443
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739524"
---
# <a name="quickstart---use-net-to-drive-a-raspberry-pi-sense-hat"></a><span data-ttu-id="4dd8d-103">Início rápido – usar o .NET para impulsionar um Raspberry Pi sensor HAT</span><span class="sxs-lookup"><span data-stu-id="4dd8d-103">Quickstart - Use .NET to drive a Raspberry Pi Sense HAT</span></span>

<span data-ttu-id="4dd8d-104">O Raspberry Pi [sensor Hat](https://www.raspberrypi.org/products/sense-hat/) <span class="docon docon-navigate-external x-hidden-focus"></span> (**H** hardware **A** ttached em **T** op) é um quadro complementar para o Raspberry Pi.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-104">The Raspberry Pi [Sense HAT](https://www.raspberrypi.org/products/sense-hat/) <span class="docon docon-navigate-external x-hidden-focus"></span> (**H** ardware **A** ttached on **T** op) is an add-on board for Raspberry Pi.</span></span> <span data-ttu-id="4dd8d-105">O sensor chapéu é equipado com uma matriz de LED RGB de 8 × 8, um joystick de cinco botões e inclui os seguintes sensores:</span><span class="sxs-lookup"><span data-stu-id="4dd8d-105">The Sense HAT is equipped with an 8×8 RGB LED matrix, a five-button joystick, and includes the following sensors:</span></span>

- <span data-ttu-id="4dd8d-106">Giroscópio</span><span class="sxs-lookup"><span data-stu-id="4dd8d-106">Gyroscope</span></span>
- <span data-ttu-id="4dd8d-107">Acelerômetro</span><span class="sxs-lookup"><span data-stu-id="4dd8d-107">Accelerometer</span></span>
- <span data-ttu-id="4dd8d-108">Magnetômetro</span><span class="sxs-lookup"><span data-stu-id="4dd8d-108">Magnetometer</span></span>
- <span data-ttu-id="4dd8d-109">Temperatura</span><span class="sxs-lookup"><span data-stu-id="4dd8d-109">Temperature</span></span>
- <span data-ttu-id="4dd8d-110">Pressão de barométrica</span><span class="sxs-lookup"><span data-stu-id="4dd8d-110">Barometric pressure</span></span>
- <span data-ttu-id="4dd8d-111">Umidade</span><span class="sxs-lookup"><span data-stu-id="4dd8d-111">Humidity</span></span>

<span data-ttu-id="4dd8d-112">Este guia de início rápido usa o .NET para recuperar valores de sensor do sensor chapéu, responder à entrada de um joystick e orientar a matriz de LED.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-112">This quickstart uses .NET to retrieve sensor values from the Sense HAT, respond to joystick input, and drive the LED matrix.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4dd8d-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4dd8d-113">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="4dd8d-114">Sensor de detecção</span><span class="sxs-lookup"><span data-stu-id="4dd8d-114">Sense HAT</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="run-the-quickstart"></a><span data-ttu-id="4dd8d-115">Executar o início rápido</span><span class="sxs-lookup"><span data-stu-id="4dd8d-115">Run the quickstart</span></span>

<span data-ttu-id="4dd8d-116">Anexe o sensor chapéu ao seu Raspberry Pi.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-116">Attach the Sense HAT to your Raspberry Pi.</span></span> <span data-ttu-id="4dd8d-117">Em um prompt do bash no Raspberry Pi (local ou remoto), execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4dd8d-117">From a Bash prompt on the Raspberry Pi (local or remote), run the following command:</span></span>

```bash
. <(wget -q -O - https://aka.ms/dotnet-iot-sensehat-quickstart)
```

<span data-ttu-id="4dd8d-118">O comando baixa e executa um script.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-118">The command downloads and runs a script.</span></span> <span data-ttu-id="4dd8d-119">O script:</span><span class="sxs-lookup"><span data-stu-id="4dd8d-119">The script:</span></span>

- <span data-ttu-id="4dd8d-120">Instala o SDK do .NET.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-120">Installs the .NET SDK.</span></span>
- <span data-ttu-id="4dd8d-121">Clona um repositório GitHub que inclui o projeto de início rápido do Sense HAT.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-121">Clones a GitHub repository that includes the Sense HAT quickstart project.</span></span>
- <span data-ttu-id="4dd8d-122">Compila o projeto.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-122">Builds the project.</span></span>
- <span data-ttu-id="4dd8d-123">Executa o projeto.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-123">Runs the project.</span></span>

<span data-ttu-id="4dd8d-124">Observe a saída do console conforme os dados do sensor são exibidos.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-124">Observe the console output as sensor data is displayed.</span></span> <span data-ttu-id="4dd8d-125">A matriz de LED exibe um pixel amarelo em um campo de azul.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-125">The LED matrix displays a yellow pixel on a field of blue.</span></span> <span data-ttu-id="4dd8d-126">Manter o joystick em qualquer direção move o pixel amarelo nessa direção.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-126">Holding the joystick in any direction moves the yellow pixel in that direction.</span></span> <span data-ttu-id="4dd8d-127">Clicar no botão do joystick central faz com que o plano de fundo mude de azul para vermelho.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-127">Clicking the center joystick button causes the background to switch from blue to red.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="4dd8d-128">Obter o código-fonte</span><span class="sxs-lookup"><span data-stu-id="4dd8d-128">Get the source code</span></span>

<span data-ttu-id="4dd8d-129">A fonte para este guia de início rápido está [disponível no GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="4dd8d-129">The source for this quickstart is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4dd8d-130">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4dd8d-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4dd8d-131">Saiba como usar Uso Geral entrada/saída para piscar um LED</span><span class="sxs-lookup"><span data-stu-id="4dd8d-131">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
