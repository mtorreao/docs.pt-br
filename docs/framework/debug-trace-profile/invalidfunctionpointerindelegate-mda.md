---
title: MDA invalidFunctionPointerInDelegate
description: Examine o MDA (Assistente de depuração gerenciada) invalidFunctionPointerInDelegate, que será invocado se um ponteiro de função inválido for passado para criar um delegado.
ms.date: 03/30/2017
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
ms.openlocfilehash: 8072d35a45cb1e0590aa5533210d0e0f86913164
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272612"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="ab746-103">MDA invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="ab746-103">invalidFunctionPointerInDelegate MDA</span></span>

<span data-ttu-id="ab746-104">O `invalidFunctionPointerInDelegate` MDA (assistente de depuração gerenciada) é ativado quando é informado um ponteiro de função inválido para construir um representante ao invés de um ponteiro de função nativo.</span><span class="sxs-lookup"><span data-stu-id="ab746-104">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ab746-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="ab746-105">Symptoms</span></span>  

 <span data-ttu-id="ab746-106">Violações de acesso ou dano inesperado à memória ao usar um representante no lugar de um ponteiro de função.</span><span class="sxs-lookup"><span data-stu-id="ab746-106">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ab746-107">Causa</span><span class="sxs-lookup"><span data-stu-id="ab746-107">Cause</span></span>  

 <span data-ttu-id="ab746-108">Foi especificado um ponteiro de função inválido.</span><span class="sxs-lookup"><span data-stu-id="ab746-108">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ab746-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="ab746-109">Resolution</span></span>  

 <span data-ttu-id="ab746-110">Especifique um ponteiro de função válido</span><span class="sxs-lookup"><span data-stu-id="ab746-110">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ab746-111">Efeito sobre o runtime</span><span class="sxs-lookup"><span data-stu-id="ab746-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="ab746-112">Esse MDA não tem efeito sobre o CLR.</span><span class="sxs-lookup"><span data-stu-id="ab746-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ab746-113">Saída</span><span class="sxs-lookup"><span data-stu-id="ab746-113">Output</span></span>  

 <span data-ttu-id="ab746-114">O ponteiro de função inválido.</span><span class="sxs-lookup"><span data-stu-id="ab746-114">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ab746-115">Configuração</span><span class="sxs-lookup"><span data-stu-id="ab746-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab746-116">Veja também</span><span class="sxs-lookup"><span data-stu-id="ab746-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ab746-117">Diagnosticando erros com assistentes de depuração gerenciados</span><span class="sxs-lookup"><span data-stu-id="ab746-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ab746-118">Realizando marshaling de interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="ab746-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
