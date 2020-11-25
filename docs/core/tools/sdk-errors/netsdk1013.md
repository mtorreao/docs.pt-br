---
title: 'NETSDK1013: o valor de TargetFramework não foi reconhecido.'
description: Como determinar e definir um valor de TargetFramework válido
author: marcpop
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1013
ms.openlocfilehash: 915ac22ad822d17c082498b469acbfb3f1a93efc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717859"
---
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a><span data-ttu-id="3d6c5-103">NETSDK1013: o valor de TargetFramework não foi reconhecido</span><span class="sxs-lookup"><span data-stu-id="3d6c5-103">NETSDK1013: The TargetFramework value was not recognized</span></span>

<span data-ttu-id="3d6c5-104">**Este artigo aplica-se a:** ✔️ SDK 3.1.100 do .NET Core e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="3d6c5-104">**This article applies to:** ✔️ .NET Core 3.1.100 SDK and later versions</span></span>

<span data-ttu-id="3d6c5-105">O SDK tenta analisar os valores fornecidos no arquivo de projeto para `<TargetFramework>` ou `<TargetFrameworks>` em um valor bem conhecido.</span><span class="sxs-lookup"><span data-stu-id="3d6c5-105">The SDK tries to parse the values provided in the project file for `<TargetFramework>` or `<TargetFrameworks>` into a well known value.</span></span>  <span data-ttu-id="3d6c5-106">Se o valor não for reconhecido, o `TargetFrameworkIdentifier` `TargetFrameworkVersion` valor ou poderá ser definido como uma cadeia de caracteres vazia ou `Unsupported` .</span><span class="sxs-lookup"><span data-stu-id="3d6c5-106">If the value is not recognized, the `TargetFrameworkIdentifier` or `TargetFrameworkVersion` value may be set to an empty string or `Unsupported`.</span></span>

<span data-ttu-id="3d6c5-107">Para resolver isso, verifique a ortografia do seu `TargetFramework` valor na lista de [estruturas com suporte](../../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="3d6c5-107">To resolve this, check the spelling of your `TargetFramework` value from the list of [supported frameworks](../../../standard/frameworks.md).</span></span>
<span data-ttu-id="3d6c5-108">Você também pode definir as `TargetFrameworkIdentifier` `TargetFrameworkVersion` Propriedades e diretamente em seu arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="3d6c5-108">You can also set the `TargetFrameworkIdentifier` and `TargetFrameworkVersion` properties directly in your project file.</span></span>

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
