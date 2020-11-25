---
title: Método IAssemblyName::GetProperty
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
ms.openlocfilehash: 3a6f19d9fc90972e767625fadf30cc4af50d9017
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727881"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="03b8c-102">Método IAssemblyName::GetProperty</span><span class="sxs-lookup"><span data-stu-id="03b8c-102">IAssemblyName::GetProperty Method</span></span>

<span data-ttu-id="03b8c-103">Obtém um ponteiro para a propriedade referenciada pelo identificador de propriedade especificado.</span><span class="sxs-lookup"><span data-stu-id="03b8c-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03b8c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="03b8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03b8c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="03b8c-105">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="03b8c-106">no O identificador exclusivo para a propriedade solicitada.</span><span class="sxs-lookup"><span data-stu-id="03b8c-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="03b8c-107">fora Os dados de propriedade retornados.</span><span class="sxs-lookup"><span data-stu-id="03b8c-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="03b8c-108">[entrada, saída] O tamanho, em bytes, de `pvProperty` .</span><span class="sxs-lookup"><span data-stu-id="03b8c-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03b8c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03b8c-109">Requirements</span></span>  

 <span data-ttu-id="03b8c-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03b8c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03b8c-111">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="03b8c-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="03b8c-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03b8c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b8c-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="03b8c-113">See also</span></span>

- [<span data-ttu-id="03b8c-114">Interface IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="03b8c-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
