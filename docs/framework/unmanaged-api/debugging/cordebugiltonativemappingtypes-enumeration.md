---
title: Enumeração CorDebugIlToNativeMappingTypes
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
ms.openlocfilehash: ecb88195e3ecc7c540679a683005798247afe57f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712398"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="43972-102">Enumeração CorDebugIlToNativeMappingTypes</span><span class="sxs-lookup"><span data-stu-id="43972-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>

<span data-ttu-id="43972-103">Indica se um intervalo específico de instruções nativas, representado por uma instância da estrutura COR_DEBUG_IL_TO_NATIVE_MAP, corresponde a uma região de código especial.</span><span class="sxs-lookup"><span data-stu-id="43972-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43972-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="43972-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="43972-105">Membros</span><span class="sxs-lookup"><span data-stu-id="43972-105">Members</span></span>  
  
|<span data-ttu-id="43972-106">Membro</span><span class="sxs-lookup"><span data-stu-id="43972-106">Member</span></span>|<span data-ttu-id="43972-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="43972-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="43972-108">O intervalo de instruções nativas não corresponde a nenhuma região de código especial.</span><span class="sxs-lookup"><span data-stu-id="43972-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="43972-109">O intervalo de instruções nativas corresponde ao prólogo.</span><span class="sxs-lookup"><span data-stu-id="43972-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="43972-110">O intervalo de instruções nativas corresponde ao epílogo.</span><span class="sxs-lookup"><span data-stu-id="43972-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43972-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43972-111">Requirements</span></span>  

 <span data-ttu-id="43972-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43972-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43972-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43972-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43972-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43972-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43972-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43972-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43972-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="43972-116">See also</span></span>

- [<span data-ttu-id="43972-117">Método GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="43972-117">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="43972-118">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="43972-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
