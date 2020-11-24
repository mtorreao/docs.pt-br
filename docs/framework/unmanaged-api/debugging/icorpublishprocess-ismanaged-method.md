---
title: Método ICorPublishProcess::IsManaged
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: dfe247bda75c3695c7c09b85729b4e057c13c62d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692625"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="46ffc-102">Método ICorPublishProcess::IsManaged</span><span class="sxs-lookup"><span data-stu-id="46ffc-102">ICorPublishProcess::IsManaged Method</span></span>

<span data-ttu-id="46ffc-103">Obtém um valor que indica se o processo referenciado por este [ICorPublishProcess](icorpublishprocess-interface.md) é conhecido por ter código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="46ffc-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ffc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="46ffc-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46ffc-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="46ffc-105">Parameters</span></span>  

 `pbManaged`  
 <span data-ttu-id="46ffc-106">fora Um ponteiro para um valor booliano que indica se o processo tem código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="46ffc-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="46ffc-107">O valor é `true` se o processo tiver código gerenciado; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="46ffc-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46ffc-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="46ffc-108">Remarks</span></span>  

 <span data-ttu-id="46ffc-109">Como a versão atual do `ICorPublishProcess` permite acesso apenas a processos que têm código gerenciado, o `IsManaged` sempre retorna `true` .</span><span class="sxs-lookup"><span data-stu-id="46ffc-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46ffc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46ffc-110">Requirements</span></span>  

 <span data-ttu-id="46ffc-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46ffc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46ffc-112">**Cabeçalho:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="46ffc-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="46ffc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46ffc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46ffc-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46ffc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ffc-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="46ffc-115">See also</span></span>

- [<span data-ttu-id="46ffc-116">Interface ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="46ffc-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
