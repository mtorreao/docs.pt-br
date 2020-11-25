---
title: Interface ICLRHostProtectionManager
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
ms.openlocfilehash: e8ead998907d55b0bfbf82e5f6f4e7c504f657ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714153"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="61b4e-102">Interface ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="61b4e-102">ICLRHostProtectionManager Interface</span></span>

<span data-ttu-id="61b4e-103">Permite que o host bloqueie classes gerenciadas, métodos, propriedades e campos específicos da execução em código parcialmente confiável.</span><span class="sxs-lookup"><span data-stu-id="61b4e-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61b4e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="61b4e-104">Methods</span></span>  
  
|<span data-ttu-id="61b4e-105">Método</span><span class="sxs-lookup"><span data-stu-id="61b4e-105">Method</span></span>|<span data-ttu-id="61b4e-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="61b4e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61b4e-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="61b4e-107">SetEagerSerializeGrantSets</span></span>](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="61b4e-108">Fornece uma garantia de que certas condições raras de corrida que podem causar erros fatais de Common Language Runtime (CLR) nunca surgirão.</span><span class="sxs-lookup"><span data-stu-id="61b4e-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="61b4e-109">Método SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="61b4e-109">SetProtectedCategories Method</span></span>](iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="61b4e-110">Especifica as categorias de tipos gerenciados e membros que devem ser impedidos de serem executados em código parcialmente confiável.</span><span class="sxs-lookup"><span data-stu-id="61b4e-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61b4e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61b4e-111">Requirements</span></span>  

 <span data-ttu-id="61b4e-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61b4e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61b4e-113">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="61b4e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61b4e-114">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61b4e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61b4e-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61b4e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b4e-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="61b4e-116">See also</span></span>

- [<span data-ttu-id="61b4e-117">Enumeração EApiCategories</span><span class="sxs-lookup"><span data-stu-id="61b4e-117">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="61b4e-118">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="61b4e-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
