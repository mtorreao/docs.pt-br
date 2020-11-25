---
title: 'NETSDK1059: o projeto contém uma ferramenta CLI do .NET obsoleta'
description: Como resolver o problema de um projeto que contém uma ferramenta CLI do .NET obsoleta.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: b80f42495e1aff8d37008946f10f68c195d5a9ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713113"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a><span data-ttu-id="a4623-103">NETSDK1059: o projeto contém uma ferramenta CLI do .NET obsoleta</span><span class="sxs-lookup"><span data-stu-id="a4623-103">NETSDK1059: Project contains obsolete .NET CLI tool</span></span>

<span data-ttu-id="a4623-104">**Este artigo aplica-se a:** ✔️ SDK 2.1.100 do .NET Core e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="a4623-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="a4623-105">Quando o SDK do .NET emite aviso NETSDK1059, seu projeto contém uma ferramenta CLI do .NET obsoleta.</span><span class="sxs-lookup"><span data-stu-id="a4623-105">When the .NET SDK issues warning NETSDK1059, your project contains an obsolete .NET CLI tool.</span></span> <span data-ttu-id="a4623-106">A partir do .NET Core 2,1, essas ferramentas estão incluídas no SDK do .NET e não precisam ser referenciadas explicitamente pelo projeto.</span><span class="sxs-lookup"><span data-stu-id="a4623-106">As of .NET Core 2.1, these tools are included in the .NET SDK and do not need to be explicitly referenced by the project.</span></span> <span data-ttu-id="a4623-107">Mais informações para a migração para o .NET Core 2,1 podem ser encontradas [aqui](https://aka.ms/dotnetclitools-in-box).</span><span class="sxs-lookup"><span data-stu-id="a4623-107">More information for migrating to .NET Core 2.1 can be found [here](https://aka.ms/dotnetclitools-in-box).</span></span>
