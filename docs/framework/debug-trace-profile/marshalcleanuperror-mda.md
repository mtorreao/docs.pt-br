---
title: MDA marshalCleanupError
description: Examine o MDA (Assistente de depuração gerenciada) marshalCleanupError, que é invocado porque ocorreu um erro inesperado ao limpar estruturas temporárias.
ms.date: 03/30/2017
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
ms.openlocfilehash: e65136f022caa7b1e18a27f7b97a4ef4c27f42d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271182"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="4a322-103">MDA marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="4a322-103">marshalCleanupError MDA</span></span>

<span data-ttu-id="4a322-104">O MDA (assistente de depuração gerenciado) do `marshalCleanupError` é ativado quando o CLR (Common Language Runtime) encontra um erro ao tentar limpar estruturas temporárias e a memória usada para realizar marshaling de tipos de dados entre limites de código gerenciado e nativo.</span><span class="sxs-lookup"><span data-stu-id="4a322-104">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4a322-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="4a322-105">Symptoms</span></span>  

 <span data-ttu-id="4a322-106">A perda de memória ocorre em transações de código gerenciado e nativo, no estado de runtime, como quando a cultura de thread não é restaurada ou quando há um erro na limpeza de <xref:System.Runtime.InteropServices.SafeHandle>.</span><span class="sxs-lookup"><span data-stu-id="4a322-106">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4a322-107">Causa</span><span class="sxs-lookup"><span data-stu-id="4a322-107">Cause</span></span>  

 <span data-ttu-id="4a322-108">Ocorreu um erro inesperado durante a limpeza das estruturas temporárias.</span><span class="sxs-lookup"><span data-stu-id="4a322-108">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4a322-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="4a322-109">Resolution</span></span>  

 <span data-ttu-id="4a322-110">Verifique se há erro em todas as implementações do destruidor, do finalizador e do marshaler personalizado <xref:System.Runtime.InteropServices.SafeHandle>.</span><span class="sxs-lookup"><span data-stu-id="4a322-110">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4a322-111">Efeito sobre o runtime</span><span class="sxs-lookup"><span data-stu-id="4a322-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="4a322-112">Esse MDA não tem efeito sobre o CLR.</span><span class="sxs-lookup"><span data-stu-id="4a322-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4a322-113">Saída</span><span class="sxs-lookup"><span data-stu-id="4a322-113">Output</span></span>  

 <span data-ttu-id="4a322-114">Uma mensagem que indica que a operação falhou durante a limpeza.</span><span class="sxs-lookup"><span data-stu-id="4a322-114">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4a322-115">Configuração</span><span class="sxs-lookup"><span data-stu-id="4a322-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a322-116">Veja também</span><span class="sxs-lookup"><span data-stu-id="4a322-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="4a322-117">Diagnosticando erros com assistentes de depuração gerenciados</span><span class="sxs-lookup"><span data-stu-id="4a322-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="4a322-118">Realizando marshaling de interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="4a322-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
