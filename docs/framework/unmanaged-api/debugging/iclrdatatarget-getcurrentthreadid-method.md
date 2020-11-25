---
title: Método ICLRDataTarget::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
ms.openlocfilehash: 3a355822710394e9351f10be78dea283e2e9907c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703584"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="16d0c-102">Método ICLRDataTarget::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="16d0c-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>

<span data-ttu-id="16d0c-103">Obtém o identificador do sistema operacional para o thread atual.</span><span class="sxs-lookup"><span data-stu-id="16d0c-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d0c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="16d0c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16d0c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="16d0c-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="16d0c-106">fora Um ponteiro para o identificador do sistema operacional do thread atual para o processo de destino.</span><span class="sxs-lookup"><span data-stu-id="16d0c-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16d0c-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="16d0c-107">Remarks</span></span>  

 <span data-ttu-id="16d0c-108">Se não houver nenhum thread atual para o processo de destino, o `GetCurrentThreadID` método poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="16d0c-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16d0c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16d0c-109">Requirements</span></span>  

 <span data-ttu-id="16d0c-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16d0c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16d0c-111">**Cabeçalho:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="16d0c-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="16d0c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16d0c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16d0c-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16d0c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d0c-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="16d0c-114">See also</span></span>

- [<span data-ttu-id="16d0c-115">Interface ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="16d0c-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
