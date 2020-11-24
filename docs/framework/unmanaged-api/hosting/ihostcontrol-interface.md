---
title: Interface IHostControl
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 1bffef31702aa051d9ca865b18a67ac90c00cd00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680633"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="c907b-102">Interface IHostControl</span><span class="sxs-lookup"><span data-stu-id="c907b-102">IHostControl Interface</span></span>

<span data-ttu-id="c907b-103">Fornece métodos para configurar o carregamento de assemblies e para determinar a quais interfaces de hospedagem o host dá suporte.</span><span class="sxs-lookup"><span data-stu-id="c907b-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c907b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c907b-104">Methods</span></span>  
  
|<span data-ttu-id="c907b-105">Método</span><span class="sxs-lookup"><span data-stu-id="c907b-105">Method</span></span>|<span data-ttu-id="c907b-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c907b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c907b-107">Método GetHostManager</span><span class="sxs-lookup"><span data-stu-id="c907b-107">GetHostManager Method</span></span>](ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="c907b-108">Obtém um ponteiro de interface para a implementação do host da interface com o especificado `IID` .</span><span class="sxs-lookup"><span data-stu-id="c907b-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="c907b-109">Método SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="c907b-109">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="c907b-110">Notifica o host de que um domínio de aplicativo foi criado.</span><span class="sxs-lookup"><span data-stu-id="c907b-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c907b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c907b-111">Requirements</span></span>  

 <span data-ttu-id="c907b-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c907b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c907b-113">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c907b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c907b-114">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c907b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c907b-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c907b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c907b-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="c907b-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="c907b-117">Interface ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c907b-117">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="c907b-118">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="c907b-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="c907b-119">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="c907b-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
