---
title: Estrutura StackTrace_SimpleContext
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
ms.openlocfilehash: 30775b4a6f904d06b9c77e6b2b64aec693c446d7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671792"
---
# <a name="stacktrace_simplecontext-structure"></a><span data-ttu-id="0f852-102">Estrutura StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="0f852-102">StackTrace_SimpleContext Structure</span></span>

<span data-ttu-id="0f852-103">Fornece um contexto simples que pode ser usado em lugar de uma estrutura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="0f852-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f852-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0f852-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="0f852-105">Membros</span><span class="sxs-lookup"><span data-stu-id="0f852-105">Members</span></span>  
  
|<span data-ttu-id="0f852-106">Membro</span><span class="sxs-lookup"><span data-stu-id="0f852-106">Member</span></span>|<span data-ttu-id="0f852-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0f852-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="0f852-108">O ponteiro de pilha ou o ponteiro de pilha Enter (ESP) em plataformas x86.</span><span class="sxs-lookup"><span data-stu-id="0f852-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="0f852-109">O deslocamento do quadro ou o EBP se registra em plataformas x86.</span><span class="sxs-lookup"><span data-stu-id="0f852-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="0f852-110">O ponteiro de instrução ou o EIP (ponteiro de instrução Enter) em plataformas x86.</span><span class="sxs-lookup"><span data-stu-id="0f852-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f852-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="0f852-111">Remarks</span></span>  

 <span data-ttu-id="0f852-112">Como as funções de rastreamento de pilha normalmente precisam retornar apenas o endereço, o deslocamento do quadro e o endereço da pilha, você pode, opcionalmente, usar a `SimpleContext` estrutura em vez de uma `CONTEXT` estrutura grande.</span><span class="sxs-lookup"><span data-stu-id="0f852-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f852-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f852-113">Requirements</span></span>  

 <span data-ttu-id="0f852-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f852-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f852-115">**Cabeçalho:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="0f852-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="0f852-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f852-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f852-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="0f852-117">See also</span></span>

- [<span data-ttu-id="0f852-118">Estruturas de depuração</span><span class="sxs-lookup"><span data-stu-id="0f852-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="0f852-119">Depuração</span><span class="sxs-lookup"><span data-stu-id="0f852-119">Debugging</span></span>](index.md)
