---
title: 'NETSDK1005 e NETSDK1047: o arquivo de ativo está com destino ausente'
description: Como resolver o problema de um arquivo de ativo que não tem um destino.
author: sfoslund
ms.topic: error-reference
ms.date: 12/17/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: e3e7389adf6a9a715d44661a5f7cbae5efe299e4
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678166"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a><span data-ttu-id="018c6-103">NETSDK1005 e NETSDK1047: o arquivo de ativo está com destino ausente</span><span class="sxs-lookup"><span data-stu-id="018c6-103">NETSDK1005 and NETSDK1047: Asset file is missing target</span></span>

<span data-ttu-id="018c6-104">**Este artigo aplica-se a:** ✔️ SDK 2.1.100 do .NET Core e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="018c6-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="018c6-105">Quando o SDK do .NET emite o erro NETSDK1005 ou NETSDK1047, o arquivo de ativos do projeto não tem informações sobre uma de suas estruturas de destino.</span><span class="sxs-lookup"><span data-stu-id="018c6-105">When the .NET SDK issues error NETSDK1005 or NETSDK1047, the project's assets file is missing information on one of your target frameworks.</span></span> <span data-ttu-id="018c6-106">O NuGet grava um arquivo chamado *project.assets.js* na pasta *obj* e o SDK do .NET usa-o para obter informações sobre pacotes a serem passados para o compilador.</span><span class="sxs-lookup"><span data-stu-id="018c6-106">NuGet writes a file named *project.assets.json* in the *obj* folder, and the .NET SDK uses it to get information about packages to pass into the compiler.</span></span> <span data-ttu-id="018c6-107">No .NET 5, o NuGet adicionou um novo campo chamado `TargetFrameworkAlias` , de modo que as versões anteriores do MSBuild ou do NuGet gerem um arquivo de ativos sem o novo campo.</span><span class="sxs-lookup"><span data-stu-id="018c6-107">In .NET 5, NuGet added a new field named `TargetFrameworkAlias`, so earlier versions of MSBuild or NuGet generate an assets file without the new field.</span></span> <span data-ttu-id="018c6-108">Para obter mais informações, consulte [Error NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html).</span><span class="sxs-lookup"><span data-stu-id="018c6-108">For more information, see [error NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html).</span></span>

<span data-ttu-id="018c6-109">Aqui estão algumas ações que podem ser tomadas para resolver o erro:</span><span class="sxs-lookup"><span data-stu-id="018c6-109">Here are some actions you can take that may resolve the error:</span></span>

* <span data-ttu-id="018c6-110">Verifique se você está usando o MSBuild versão 16,8 ou posterior e a versão 5,8 ou posterior do NuGet e restaure o projeto depois de atualizar suas ferramentas.</span><span class="sxs-lookup"><span data-stu-id="018c6-110">Make sure that you're using MSBuild version 16.8 or later and NuGet version 5.8 or later, and restore the project after updating your tools.</span></span> <span data-ttu-id="018c6-111">Quando estiver usando o NuGet versão 5,8 ou posterior, você deverá usar o Visual Studio 2019 versão 16,8 ou posterior, o MSBuild versão 16,8 ou posterior e o SDK do .NET 5,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="018c6-111">When you're using NuGet version 5.8 or later, you should be using Visual Studio 2019 version 16.8 or later, MSBuild version 16.8 or later, and .NET 5.0 SDK or later.</span></span>

* <span data-ttu-id="018c6-112">Se você receber o erro ao criar um projeto no Visual Studio 2019 pela primeira vez depois de instalar a versão 16,8 ou depois de alterar a estrutura de destino do projeto, compile o projeto uma segunda vez.</span><span class="sxs-lookup"><span data-stu-id="018c6-112">If you get the error while building a project in Visual Studio 2019 for the first time after installing version 16.8 or after changing the project's target framework, build the project a second time.</span></span>

* <span data-ttu-id="018c6-113">Exclua a pasta *obj* antes de compilar o projeto.</span><span class="sxs-lookup"><span data-stu-id="018c6-113">Delete the *obj* folder before building the project.</span></span>

* <span data-ttu-id="018c6-114">Verifique se o valor de destino ausente está incluído na `TargetFrameworks` Propriedade do seu projeto.</span><span class="sxs-lookup"><span data-stu-id="018c6-114">Make sure that the missing target value is included in the `TargetFrameworks` property of your project.</span></span>
