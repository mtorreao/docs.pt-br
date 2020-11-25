---
title: Interface IInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
ms.openlocfilehash: f56a9049cd4b503124abe9dd4866dc91779e268e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721056"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="cd101-102">Interface IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="cd101-102">IInstallReferenceEnum Interface</span></span>

<span data-ttu-id="cd101-103">Representa um enumerador para os assemblies referenciados instalados no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="cd101-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd101-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cd101-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cd101-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cd101-105">Methods</span></span>  
  
|<span data-ttu-id="cd101-106">Método</span><span class="sxs-lookup"><span data-stu-id="cd101-106">Method</span></span>|<span data-ttu-id="cd101-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="cd101-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd101-108">Método GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="cd101-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="cd101-109">Obtém um ponteiro para o próximo `IInstallReferenceItem` contido neste `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="cd101-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd101-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd101-110">Requirements</span></span>  

 <span data-ttu-id="cd101-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd101-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd101-112">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="cd101-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cd101-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd101-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd101-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="cd101-114">See also</span></span>

- [<span data-ttu-id="cd101-115">Interfaces de fusão</span><span class="sxs-lookup"><span data-stu-id="cd101-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="cd101-116">Interface IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="cd101-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
