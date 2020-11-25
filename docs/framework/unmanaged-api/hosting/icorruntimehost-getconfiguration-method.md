---
title: Método ICorRuntimeHost::GetConfiguration
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 2a50814a67be5a01a7413050683a915355665f3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720640"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="e0e7e-102">Método ICorRuntimeHost::GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0e7e-102">ICorRuntimeHost::GetConfiguration Method</span></span>

<span data-ttu-id="e0e7e-103">Obtém um objeto que permite ao host especificar a configuração de retorno de chamada do Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e0e7e-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0e7e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e0e7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0e7e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e0e7e-105">Parameters</span></span>  

 `pConfiguration`  
 <span data-ttu-id="e0e7e-106">fora Um ponteiro para o endereço de um objeto [ICorConfiguration](icorconfiguration-interface.md) que pode ser usado para configurar o CLR.</span><span class="sxs-lookup"><span data-stu-id="e0e7e-106">[out] A pointer to the address of an [ICorConfiguration](icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0e7e-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="e0e7e-107">Remarks</span></span>  

 <span data-ttu-id="e0e7e-108">O CLR deve ser configurado antes de sua inicialização; caso contrário, o `GetConfiguration` método retornará um HRESULT indicando um erro.</span><span class="sxs-lookup"><span data-stu-id="e0e7e-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e7e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0e7e-109">Requirements</span></span>  

 <span data-ttu-id="e0e7e-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0e7e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0e7e-111">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e0e7e-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0e7e-112">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0e7e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0e7e-113">**Versões do .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e0e7e-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e7e-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="e0e7e-114">See also</span></span>

- [<span data-ttu-id="e0e7e-115">Interface ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e0e7e-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
