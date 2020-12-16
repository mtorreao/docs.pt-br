---
title: Aviso de SYSLIB0008
description: Saiba mais sobre o obsoletion que gera SYSLIB0008 de aviso de tempo de compilação.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2b573f4b28cdf79107395f5cb38a4226d0ccc11e
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596427"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a><span data-ttu-id="bcabc-103">SYSLIB0008: não há suporte para CreatePdbGenerator</span><span class="sxs-lookup"><span data-stu-id="bcabc-103">SYSLIB0008: CreatePdbGenerator is not supported</span></span>

<span data-ttu-id="bcabc-104">A <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> API está marcada como obsoleta, começando no .net 5,0.</span><span class="sxs-lookup"><span data-stu-id="bcabc-104">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> API is marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="bcabc-105">O uso dessa API gera aviso `SYSLIB0008` no momento da compilação.</span><span class="sxs-lookup"><span data-stu-id="bcabc-105">Using this API generates warning `SYSLIB0008` at compile time.</span></span>

## <a name="suppress-the-warning"></a><span data-ttu-id="bcabc-106">Suprimir o aviso</span><span class="sxs-lookup"><span data-stu-id="bcabc-106">Suppress the warning</span></span>

<span data-ttu-id="bcabc-107">Se você não puder alterar seu código, poderá suprimir o aviso por meio de uma `#pragma` diretiva ou `<NoWarn>` configuração de projeto.</span><span class="sxs-lookup"><span data-stu-id="bcabc-107">If you cannot change your code, you can suppress the warning through a `#pragma` directive or a `<NoWarn>` project setting.</span></span> <span data-ttu-id="bcabc-108">Para obter exemplos, consulte [suprimir avisos](../syslib-obsoletions.md#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="bcabc-108">For examples, see [Suppress warnings](../syslib-obsoletions.md#suppress-warnings).</span></span>
