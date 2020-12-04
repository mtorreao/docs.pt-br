---
title: Portabilidade e regras de interoperabilidade (análise de código)
description: Saiba mais sobre a portabilidade da regra de análise de código e as regras de interoperabilidade
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.Portablityrules
- vs.codeanalysis.Interoperabilityrules
helpviewer_keywords:
- managed code analysis rules, interoperability rules, portability rules
- portability rules
- warnings, portability
- interoperability rules
- warnings, interoperability
author: gewarren
ms.author: gewarren
ms.openlocfilehash: a20cd77e13c4a8b95633d129990667f0a8de3ee8
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "96584727"
---
# <a name="portability-and-interoperability-rules"></a><span data-ttu-id="eb4ff-103">Regras de portabilidade e interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="eb4ff-103">Portability and interoperability rules</span></span>

<span data-ttu-id="eb4ff-104">As regras de portabilidade dão suporte à portabilidade em diferentes plataformas.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-104">Portability rules support portability across different platforms.</span></span> <span data-ttu-id="eb4ff-105">As regras de interoperabilidade dão suporte à interação com clientes COM.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-105">Interoperability rules support interaction with COM clients.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eb4ff-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="eb4ff-106">In this section</span></span>

| <span data-ttu-id="eb4ff-107">Regra</span><span class="sxs-lookup"><span data-stu-id="eb4ff-107">Rule</span></span> | <span data-ttu-id="eb4ff-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb4ff-108">Description</span></span> |
| - | - |
| [<span data-ttu-id="eb4ff-109">CA1401: P/Invokes não devem estar visíveis</span><span class="sxs-lookup"><span data-stu-id="eb4ff-109">CA1401: P/Invokes should not be visible</span></span>](ca1401.md) | <span data-ttu-id="eb4ff-110">Um método público ou protegido em um tipo público tem o atributo System.Runtime.InteropServices.DllImportAttribute (também implementado pela palavra-chave declare em Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="eb4ff-110">A public or protected method in a public type has the System.Runtime.InteropServices.DllImportAttribute attribute (also implemented by the Declare keyword in Visual Basic).</span></span> <span data-ttu-id="eb4ff-111">Esses métodos não devem ser expostos.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-111">Such methods should not be exposed.</span></span> |
| [<span data-ttu-id="eb4ff-112">CA1416: validar a compatibilidade da plataforma</span><span class="sxs-lookup"><span data-stu-id="eb4ff-112">CA1416: Validate platform compatibility</span></span>](ca1416.md) | <span data-ttu-id="eb4ff-113">O uso de APIs dependentes de plataforma em um componente faz com que o código não funcione mais em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-113">Using platform-dependent APIs on a component makes the code no longer work across all platforms.</span></span> |
| [<span data-ttu-id="eb4ff-114">CA1417: não usar `OutAttribute` em parâmetros de cadeia de caracteres para P/Invokes</span><span class="sxs-lookup"><span data-stu-id="eb4ff-114">CA1417: Do not use `OutAttribute` on string parameters for P/Invokes</span></span>](ca1417.md) | <span data-ttu-id="eb4ff-115">Parâmetros de cadeia de caracteres passados por valor com o `OutAttribute` podem desestabilizar o tempo de execução se a cadeia de caracteres for uma cadeia de caracteres interna.</span><span class="sxs-lookup"><span data-stu-id="eb4ff-115">String parameters passed by value with the `OutAttribute` can destabilize the runtime if the string is an interned string.</span></span> |
