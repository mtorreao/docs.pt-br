---
title: Início rápido – usar o .NET para impulsionar um Raspberry Pi sensor HAT
description: Introdução às bibliotecas de IoT do .NET em 5 minutos usando um sensor de detecção, uma placa complementar para o Raspberry Pi.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: quickstart
ms.prod: dotnet
ms.openlocfilehash: 09e0c46a08e08a2021a9dffe214d3d62d6fb8ec5
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "96585605"
---
# <a name="quickstart---use-net-to-drive-a-raspberry-pi-sense-hat"></a>Início rápido – usar o .NET para impulsionar um Raspberry Pi sensor HAT

O Raspberry Pi [sensor Hat](https://www.raspberrypi.org/products/sense-hat/) <span class="docon docon-navigate-external x-hidden-focus"></span> é uma placa complementar para o Raspberry Pi. O sensor chapéu é equipado com uma matriz de LED RGB de 8 × 8, um joystick de cinco botões e inclui os seguintes sensores:

- Giroscópio
- Acelerômetro
- Magnetômetro
- Temperatura
- Pressão de barométrica
- Umidade

Este guia de início rápido usa o .NET para recuperar valores de sensor do sensor chapéu, responder à entrada de um joystick e orientar a matriz de LED.

## <a name="prerequisites"></a>Pré-requisitos

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- Sensor de detecção

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="run-the-quickstart"></a>Executar o início rápido

Anexe o sensor chapéu ao seu Raspberry Pi. Em um prompt do bash no Raspberry Pi (local ou remoto), execute o seguinte comando:

```bash
. <(wget -q -O - https://aka.ms/dotnet-iot-sensehat-quickstart)
```

O comando baixa e executa um script. O script:

- Instala o SDK do .NET.
- Clona um repositório GitHub que inclui o projeto de início rápido do Sense HAT.
- Compila o projeto.
- Executa o projeto.

Observe a saída do console conforme os dados do sensor são exibidos. A matriz de LED exibe um pixel amarelo em um campo de azul. Manter o joystick em qualquer direção move o pixel amarelo nessa direção. Clicar no botão do joystick central faz com que o plano de fundo mude de azul para vermelho.

## <a name="get-the-source-code"></a>Obter o código-fonte

A fonte para este guia de início rápido está [disponível no GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart). <span class="docon docon-navigate-external x-hidden-focus"></span>

## <a name="next-steps"></a>Próximas etapas

> [!div class="nextstepaction"]
> [Saiba como usar Uso Geral entrada/saída para piscar um LED](../tutorials/blink-led.md)
