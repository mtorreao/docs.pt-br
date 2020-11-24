---
title: Método IAssemblyName::SetProperty
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
ms.openlocfilehash: 04b3e73e2166efb2ec0821d21da3da4c53b0ca4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688647"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="6b86d-102">Método IAssemblyName::SetProperty</span><span class="sxs-lookup"><span data-stu-id="6b86d-102">IAssemblyName::SetProperty Method</span></span>

<span data-ttu-id="6b86d-103">Define o valor da propriedade referenciada pelo identificador de propriedade especificado.</span><span class="sxs-lookup"><span data-stu-id="6b86d-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b86d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6b86d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b86d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6b86d-105">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="6b86d-106">no O identificador exclusivo da propriedade cujo valor será definido.</span><span class="sxs-lookup"><span data-stu-id="6b86d-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="6b86d-107">no O valor para o qual definir a propriedade referenciada `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="6b86d-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="6b86d-108">no O tamanho, em bytes, de `pvProperty` .</span><span class="sxs-lookup"><span data-stu-id="6b86d-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b86d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b86d-109">Requirements</span></span>  

 <span data-ttu-id="6b86d-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b86d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b86d-111">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6b86d-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6b86d-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b86d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b86d-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="6b86d-113">See also</span></span>

- [<span data-ttu-id="6b86d-114">Interface IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="6b86d-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
