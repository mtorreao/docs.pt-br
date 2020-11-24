---
title: Método IMetaDataEmit::SetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: b0cc28807938bcfb9b2465093ff4cfb94066ee98
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675055"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="2e403-102">Método IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="2e403-102">IMetaDataEmit::SetParamProps Method</span></span>

<span data-ttu-id="2e403-103">Define ou altera recursos de um parâmetro de método que foi definido por uma chamada anterior para [IMetaDataEmit::D efineparam](imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="2e403-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e403-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2e403-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e403-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2e403-105">Parameters</span></span>  

 `pd`  
 <span data-ttu-id="2e403-106">no O token para o parâmetro de destino.</span><span class="sxs-lookup"><span data-stu-id="2e403-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="2e403-107">no O nome do parâmetro em Unicode.</span><span class="sxs-lookup"><span data-stu-id="2e403-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="2e403-108">no Os sinalizadores para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2e403-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2e403-109">no O ELEMENT_TYPE_ \* para o valor constante.</span><span class="sxs-lookup"><span data-stu-id="2e403-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2e403-110">no O valor da constante para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2e403-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2e403-111">no O tamanho em caracteres (Unicode) de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="2e403-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e403-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e403-112">Requirements</span></span>  

 <span data-ttu-id="2e403-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e403-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e403-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2e403-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e403-115">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e403-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e403-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e403-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e403-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="2e403-117">See also</span></span>

- [<span data-ttu-id="2e403-118">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2e403-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2e403-119">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2e403-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
