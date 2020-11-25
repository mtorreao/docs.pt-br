---
title: Método IMetaDataEmit::SetFieldProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: 0f98fb64b43822c437c39df2f3c51a222ef386b9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730390"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="ff2d7-102">Método IMetaDataEmit::SetFieldProps</span><span class="sxs-lookup"><span data-stu-id="ff2d7-102">IMetaDataEmit::SetFieldProps Method</span></span>

<span data-ttu-id="ff2d7-103">Define ou atualiza o valor padrão para o campo referenciado pelo token do campo especificado.</span><span class="sxs-lookup"><span data-stu-id="ff2d7-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff2d7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ff2d7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff2d7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ff2d7-105">Parameters</span></span>  

 `fd`  
 <span data-ttu-id="ff2d7-106">no O token para o campo de destino.</span><span class="sxs-lookup"><span data-stu-id="ff2d7-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="ff2d7-107">no Atributos de campo.</span><span class="sxs-lookup"><span data-stu-id="ff2d7-107">[in] Field attributes.</span></span> <span data-ttu-id="ff2d7-108">Esta é uma bitmask de `CorFieldAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="ff2d7-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="ff2d7-109">no O `ELEMENT_TYPE_` *\** para o valor da constante.</span><span class="sxs-lookup"><span data-stu-id="ff2d7-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="ff2d7-110">Esse é um `CorElementType` valor.</span><span class="sxs-lookup"><span data-stu-id="ff2d7-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="ff2d7-111">Se uma constante não estiver sendo definida, defina esse valor como `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="ff2d7-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="ff2d7-112">no O valor constante para o campo.</span><span class="sxs-lookup"><span data-stu-id="ff2d7-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="ff2d7-113">no O tamanho, em caracteres Unicode, de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="ff2d7-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff2d7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff2d7-114">Requirements</span></span>  

 <span data-ttu-id="ff2d7-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff2d7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff2d7-116">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ff2d7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff2d7-117">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff2d7-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff2d7-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff2d7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff2d7-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="ff2d7-119">See also</span></span>

- [<span data-ttu-id="ff2d7-120">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ff2d7-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ff2d7-121">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ff2d7-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
