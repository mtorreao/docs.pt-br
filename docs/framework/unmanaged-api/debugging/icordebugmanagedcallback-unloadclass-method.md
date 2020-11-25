---
title: Método ICorDebugManagedCallback::UnloadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: 6efd451c6895e8fef443e2e86afa6e98279c6493
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723994"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="088ad-102">Método ICorDebugManagedCallback::UnloadClass</span><span class="sxs-lookup"><span data-stu-id="088ad-102">ICorDebugManagedCallback::UnloadClass Method</span></span>

<span data-ttu-id="088ad-103">Notifica o depurador de que uma classe está sendo descarregada.</span><span class="sxs-lookup"><span data-stu-id="088ad-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="088ad-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="088ad-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="088ad-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="088ad-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="088ad-106">no Um ponteiro para um objeto ICorDebugAppDomain que representa o domínio do aplicativo que contém a classe.</span><span class="sxs-lookup"><span data-stu-id="088ad-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="088ad-107">no Um ponteiro para um objeto ICorDebugClass que representa a classe.</span><span class="sxs-lookup"><span data-stu-id="088ad-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="088ad-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="088ad-108">Remarks</span></span>  

 <span data-ttu-id="088ad-109">A classe não deve ser referenciada após esta chamada.</span><span class="sxs-lookup"><span data-stu-id="088ad-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="088ad-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="088ad-110">Requirements</span></span>  

 <span data-ttu-id="088ad-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="088ad-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="088ad-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="088ad-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="088ad-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="088ad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="088ad-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="088ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="088ad-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="088ad-115">See also</span></span>

- [<span data-ttu-id="088ad-116">Método LoadClass</span><span class="sxs-lookup"><span data-stu-id="088ad-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="088ad-117">Interface ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="088ad-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
