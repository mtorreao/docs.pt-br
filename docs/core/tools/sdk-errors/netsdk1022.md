---
title: 'NETSDK1022: itens duplicados foram incluídos.'
description: Como resolver a mensagem de item duplicada com base em inclusões padrão.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: c2bdbbb5503e5e4f6e6826f95f5a2cb08c908ceb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717858"
---
# <a name="netsdk1022-duplicate-items-were-included"></a><span data-ttu-id="eda24-103">NETSDK1022: itens duplicados foram incluídos.</span><span class="sxs-lookup"><span data-stu-id="eda24-103">NETSDK1022: Duplicate items were included.</span></span>

<span data-ttu-id="eda24-104">**Este artigo aplica-se a:** ✔️ SDK 2.1.100 do .NET Core e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="eda24-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="eda24-105">A partir do Visual Studio 2017/MSBuild versão 15,3, o SDK do .NET inclui automaticamente itens do diretório do projeto por padrão.</span><span class="sxs-lookup"><span data-stu-id="eda24-105">Starting in Visual Studio 2017 / MSBuild version 15.3, the .NET SDK automatically includes items from the project directory by default.</span></span>  <span data-ttu-id="eda24-106">Isso inclui `Compile` `Content` destinos e.</span><span class="sxs-lookup"><span data-stu-id="eda24-106">This includes `Compile` and `Content` targets.</span></span>  <span data-ttu-id="eda24-107">Isso deve limpar muito o arquivo do projeto e reduzir a complexidade que você tem.</span><span class="sxs-lookup"><span data-stu-id="eda24-107">This should greatly clean up your project file and reduce the complexity you have there.</span></span>

<span data-ttu-id="eda24-108">Você pode reverter para o comportamento anterior definindo a propriedade correta como false.</span><span class="sxs-lookup"><span data-stu-id="eda24-108">You can revert to the earlier behavior by setting the correct property to false.</span></span>

<span data-ttu-id="eda24-109">Exemplo de `Compile` itens:</span><span class="sxs-lookup"><span data-stu-id="eda24-109">Example for `Compile` items:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
