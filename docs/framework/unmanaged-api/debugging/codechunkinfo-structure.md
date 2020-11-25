---
title: Estrutura CodeChunkInfo
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
ms.openlocfilehash: 11197246662a93f6a8b57c6e61e49505a9999d00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727424"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="90a7a-102">Estrutura CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="90a7a-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="90a7a-103">Representa uma única parte de código na memória.</span><span class="sxs-lookup"><span data-stu-id="90a7a-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90a7a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="90a7a-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="90a7a-105">Membros</span><span class="sxs-lookup"><span data-stu-id="90a7a-105">Members</span></span>  
  
|<span data-ttu-id="90a7a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="90a7a-106">Member</span></span>|<span data-ttu-id="90a7a-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="90a7a-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="90a7a-108">Um `CORDB_ADDRESS` valor que especifica o endereço inicial da parte.</span><span class="sxs-lookup"><span data-stu-id="90a7a-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="90a7a-109">O tamanho, em bytes, da parte.</span><span class="sxs-lookup"><span data-stu-id="90a7a-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90a7a-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="90a7a-110">Remarks</span></span>  

 <span data-ttu-id="90a7a-111">A única parte do código é uma região de código nativo que faz parte de um objeto de código, como uma função.</span><span class="sxs-lookup"><span data-stu-id="90a7a-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90a7a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90a7a-112">Requirements</span></span>  

 <span data-ttu-id="90a7a-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90a7a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90a7a-114">**Cabeçalho:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="90a7a-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="90a7a-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90a7a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90a7a-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90a7a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a7a-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="90a7a-117">See also</span></span>

- [<span data-ttu-id="90a7a-118">Método GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="90a7a-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="90a7a-119">Estruturas de depuração</span><span class="sxs-lookup"><span data-stu-id="90a7a-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="90a7a-120">Depuração</span><span class="sxs-lookup"><span data-stu-id="90a7a-120">Debugging</span></span>](index.md)
