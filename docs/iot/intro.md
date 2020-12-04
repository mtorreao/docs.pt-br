---
title: Desenvolver aplicativos para dispositivos IoT com as bibliotecas IoT do .NET
description: Saiba como o .NET pode ser usado para criar aplicativos para dispositivos e cenários de IoT.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: overview
ms.prod: dotnet
ms.openlocfilehash: c3d05ec5b05780f91404c3c27e91bcd602b0faeb
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "96585606"
---
# <a name="develop-apps-for-iot-devices-with-the-net-iot-libraries"></a><span data-ttu-id="8e7b8-103">Desenvolver aplicativos para dispositivos IoT com as bibliotecas IoT do .NET</span><span class="sxs-lookup"><span data-stu-id="8e7b8-103">Develop apps for IoT devices with the .NET IoT Libraries</span></span>

<span data-ttu-id="8e7b8-104">O .NET é executado em uma variedade de plataformas e arquiteturas.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-104">.NET runs on a variety of platforms and architectures.</span></span> <span data-ttu-id="8e7b8-105">As placas IoT (Internet das coisas) comuns, como Raspberry Pi e Hummingboard, têm suporte.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-105">Common Internet of things (IoT) boards, such as Raspberry Pi and Hummingboard, are supported.</span></span> <span data-ttu-id="8e7b8-106">Os aplicativos de IoT normalmente interagem com hardware especializado, como sensores, conversores analógicos para digitais e dispositivos de LCD.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-106">IoT apps typically interact with specialized hardware, such as sensors, analog-to-digital converters, and LCD devices.</span></span> <span data-ttu-id="8e7b8-107">As bibliotecas IoT do .NET habilitam esses cenários.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-107">The .NET IoT Libraries enable these scenarios.</span></span>

## <a name="video-overview"></a><span data-ttu-id="8e7b8-108">Visão geral em vídeo</span><span class="sxs-lookup"><span data-stu-id="8e7b8-108">Video overview</span></span>

<!--markdownlint-disable MD034 -->
> [!VIDEO https://channel9.msdn.com/Series/IoT-101/Intro-to-IOT-with-NET-Core-1-of-9/player]

## <a name="libraries"></a><span data-ttu-id="8e7b8-109">Bibliotecas</span><span class="sxs-lookup"><span data-stu-id="8e7b8-109">Libraries</span></span>

<span data-ttu-id="8e7b8-110">As bibliotecas IoT do .NET são compostas por dois pacotes NuGet:</span><span class="sxs-lookup"><span data-stu-id="8e7b8-110">The .NET IoT Libraries are composed of two NuGet packages:</span></span>

- <span data-ttu-id="8e7b8-111">[System. Device. GPIO](https://www.nuget.org/packages/System.Device.Gpio/)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="8e7b8-111">[System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="8e7b8-112">[IOT. Device. Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="8e7b8-112">[Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>

### <a name="systemdevicegpio"></a><span data-ttu-id="8e7b8-113">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="8e7b8-113">System.Device.Gpio</span></span>

<span data-ttu-id="8e7b8-114">`System.Device.Gpio` o oferece suporte a uma variedade de protocolos para interagir com Pins de hardware de nível baixo para controlar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-114">`System.Device.Gpio` supports a variety of protocols for interacting with low-level hardware pins to control devices.</span></span> <span data-ttu-id="8e7b8-115">Elas incluem:</span><span class="sxs-lookup"><span data-stu-id="8e7b8-115">These include:</span></span>

- <span data-ttu-id="8e7b8-116">E/s de finalidade geral (GPIO)</span><span class="sxs-lookup"><span data-stu-id="8e7b8-116">General-purpose I/O (GPIO)</span></span>
- <span data-ttu-id="8e7b8-117">Circuito de Inter-Integrated (I2C)</span><span class="sxs-lookup"><span data-stu-id="8e7b8-117">Inter-Integrated Circuit (I2C)</span></span>
- <span data-ttu-id="8e7b8-118">SPI (interface de periférico serial)</span><span class="sxs-lookup"><span data-stu-id="8e7b8-118">Serial Peripheral Interface (SPI)</span></span>
- <span data-ttu-id="8e7b8-119">Modulação de largura de pulso (PWM)</span><span class="sxs-lookup"><span data-stu-id="8e7b8-119">Pulse Width Modulation (PWM)</span></span>
- <span data-ttu-id="8e7b8-120">Porta serial</span><span class="sxs-lookup"><span data-stu-id="8e7b8-120">Serial port</span></span>

### <a name="iotdevicebindings"></a><span data-ttu-id="8e7b8-121">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="8e7b8-121">Iot.Device.Bindings</span></span>

<span data-ttu-id="8e7b8-122">O `Iot.Device.Bindings` pacote:</span><span class="sxs-lookup"><span data-stu-id="8e7b8-122">The `Iot.Device.Bindings` package:</span></span>

* <span data-ttu-id="8e7b8-123">Contém [associações de dispositivo](https://github.com/dotnet/iot/blob/master/src/devices/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> para simplificar o desenvolvimento de aplicativos encapsulando System. Device. GPIO.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-123">Contains [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> to streamline app development by wrapping System.Device.Gpio.</span></span>
* <span data-ttu-id="8e7b8-124">O tem suporte da Comunidade e associações adicionais são adicionadas continuamente.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-124">Is community-supported, and additional bindings are added continually.</span></span>

<span data-ttu-id="8e7b8-125">As associações de dispositivo usadas com frequência incluem:</span><span class="sxs-lookup"><span data-stu-id="8e7b8-125">Commonly used device bindings include:</span></span>

- <span data-ttu-id="8e7b8-126">[CharacterLcd-exibição de caracteres de LCD](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="8e7b8-126">[CharacterLcd - LCD character display](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="8e7b8-127">[SN74HC595-registro de deslocamento de 8 bits](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="8e7b8-127">[SN74HC595 - 8-bit shift register](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="8e7b8-128">[BrickPi3](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="8e7b8-128">[BrickPi3](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="8e7b8-129">[Driver de matriz com LED de Max7219](https://github.com/dotnet/iot/tree/master/src/devices/Max7219)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="8e7b8-129">[Max7219 - LED Matrix driver](https://github.com/dotnet/iot/tree/master/src/devices/Max7219) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="8e7b8-130">[Matriz de LED RGBLedMatrix-RGB](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="8e7b8-130">[RGBLedMatrix - RGB LED Matrix](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="8e7b8-131">Sistemas operacionais compatíveis</span><span class="sxs-lookup"><span data-stu-id="8e7b8-131">Supported operating systems</span></span>

<span data-ttu-id="8e7b8-132">`System.Device.Gpio` tem suporte na maioria das versões do Linux que dão suporte ao ARM/ARM64 e ao Windows 10 IoT Core.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-132">`System.Device.Gpio` is supported on most versions of Linux that support ARM/ARM64 and Windows 10 IoT Core.</span></span>

> [!TIP]
> <span data-ttu-id="8e7b8-133">Para o Raspberry Pi, o [Raspberry Pi os](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> (anteriormente Raspbian) é recomendado.  </span><span class="sxs-lookup"><span data-stu-id="8e7b8-133">For Raspberry Pi, [Raspberry Pi OS](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)  <span class="docon docon-navigate-external x-hidden-focus"></span> (formerly Raspbian) is recommended.</span></span>

## <a name="supported-hardware-platforms"></a><span data-ttu-id="8e7b8-134">Plataformas de hardware com suporte</span><span class="sxs-lookup"><span data-stu-id="8e7b8-134">Supported hardware platforms</span></span>

<span data-ttu-id="8e7b8-135">`System.Device.Gpio` é compatível com a maioria das plataformas de quadro único.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-135">`System.Device.Gpio` is compatible with most single-board platforms.</span></span> <span data-ttu-id="8e7b8-136">As plataformas recomendadas são Raspberry Pi (2 e superior) e Hummingboard.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-136">Recommended platforms are Raspberry Pi (2 and greater) and Hummingboard.</span></span> <span data-ttu-id="8e7b8-137">Outras plataformas conhecidas para serem compatíveis são BeagleBoard e ODROID.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-137">Other platforms known to be compatible are BeagleBoard and ODROID.</span></span>

<span data-ttu-id="8e7b8-138">As plataformas de PC têm suporte por meio do uso de uma ponte USB para SPI/I2C.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-138">PC platforms are supported via the use of a USB to SPI/I2C bridge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e7b8-139">Não há suporte para .NET em dispositivos de arquitetura ARMv6, incluindo dispositivos Raspberry Pi zero e Raspberry Pi antes do Raspberry Pi 2.</span><span class="sxs-lookup"><span data-stu-id="8e7b8-139">.NET is not supported on ARMv6 architecture devices, including Raspberry Pi Zero and Raspberry Pi devices prior to Raspberry Pi 2.</span></span>

## <a name="resources"></a><span data-ttu-id="8e7b8-140">Recursos</span><span class="sxs-lookup"><span data-stu-id="8e7b8-140">Resources</span></span>

- <span data-ttu-id="8e7b8-141">[Bibliotecas IOT do .net no GitHub](https://github.com/dotnet/iot)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="8e7b8-141">[.NET IoT Libraries on Github](https://github.com/dotnet/iot) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
