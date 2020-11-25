---
title: 'NETSDK1073: o FrameworkReference não foi reconhecido'
description: Como resolver o problema em que o FrameworkReference não pode ser encontrado.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 2b2dbf2a0d3e13dca4fe634529b7951f2333ce28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713022"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a><span data-ttu-id="2a363-103">NETSDK1073: o FrameworkReference não foi reconhecido</span><span class="sxs-lookup"><span data-stu-id="2a363-103">NETSDK1073: The FrameworkReference was not recognized</span></span>

<span data-ttu-id="2a363-104">**Este artigo aplica-se a:** ✔️ SDK 2.1.100 do .NET Core e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="2a363-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="2a363-105">Esse erro normalmente significa que há uma versão de um determinado FrameworkReference que o SDK não pode localizar.</span><span class="sxs-lookup"><span data-stu-id="2a363-105">This error typically means there is a version of a particular FrameworkReference that the SDK cannot find.</span></span> <span data-ttu-id="2a363-106">Tente excluir as pastas *obj* e *bin* e execute `dotnet restore` para baixar novamente os pacotes de direcionamento mais recentes.</span><span class="sxs-lookup"><span data-stu-id="2a363-106">Try deleting your *obj* and *bin* folders and running `dotnet restore` to redownload the latest targeting packs.</span></span>

<span data-ttu-id="2a363-107">Como alternativa, pode haver um problema com a instalação, portanto, verifique se você está nas versões mais recentes do .NET e do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a363-107">Alternatively, there could be an issue with your install, so ensure you're on the latest versions of .NET and Visual Studio</span></span>
