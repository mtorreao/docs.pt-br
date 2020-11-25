---
title: Método IMetaDataEmit::DefineSecurityAttributeSet
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
ms.openlocfilehash: 5caf07414c9e64169f272eb11169c4d4ee399c6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719457"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="fb99e-102">Método IMetaDataEmit::DefineSecurityAttributeSet</span><span class="sxs-lookup"><span data-stu-id="fb99e-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>

<span data-ttu-id="fb99e-103">Cria um conjunto de permissões de segurança para anexar ao objeto referenciado pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="fb99e-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb99e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fb99e-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb99e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fb99e-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="fb99e-106">no O token ao qual as informações de segurança estão anexadas.</span><span class="sxs-lookup"><span data-stu-id="fb99e-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="fb99e-107">no Uma matriz de `COR_SECATTR` estruturas.</span><span class="sxs-lookup"><span data-stu-id="fb99e-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="fb99e-108">no O número de elementos no `rSecAttrs` .</span><span class="sxs-lookup"><span data-stu-id="fb99e-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="fb99e-109">fora Se o método falhar, especifica o índice no `rSecAttrs` elemento que causou o problema.</span><span class="sxs-lookup"><span data-stu-id="fb99e-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb99e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb99e-110">Requirements</span></span>  

 <span data-ttu-id="fb99e-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb99e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb99e-112">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fb99e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb99e-113">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb99e-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb99e-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb99e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb99e-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="fb99e-115">See also</span></span>

- [<span data-ttu-id="fb99e-116">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="fb99e-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fb99e-117">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="fb99e-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
