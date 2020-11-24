---
title: Método ICorRuntimeHost::LocksHeldByLogicalThread
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
ms.openlocfilehash: 16f34d91861f9fcae51691ab13549bdf1ef333a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671493"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="8393c-102">Método ICorRuntimeHost::LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="8393c-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>

<span data-ttu-id="8393c-103">Recupera o número de bloqueios que o thread atual mantém.</span><span class="sxs-lookup"><span data-stu-id="8393c-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="8393c-104">Esse método oferece suporte a infraestrutura do .NET Framework e não se destina a ser usado diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="8393c-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8393c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8393c-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8393c-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8393c-106">Parameters</span></span>  

 `pCount`  
 <span data-ttu-id="8393c-107">fora Um ponteiro para o número de bloqueios que o thread atual mantém.</span><span class="sxs-lookup"><span data-stu-id="8393c-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8393c-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8393c-108">Requirements</span></span>  

 <span data-ttu-id="8393c-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8393c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8393c-110">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8393c-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8393c-111">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8393c-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8393c-112">**Versões do .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="8393c-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8393c-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="8393c-113">See also</span></span>

- [<span data-ttu-id="8393c-114">Interface ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8393c-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
