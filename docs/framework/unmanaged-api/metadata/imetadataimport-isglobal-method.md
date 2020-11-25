---
title: Método IMetaDataImport::IsGlobal
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
ms.openlocfilehash: 0d76abf8a9c923089f367ab4e1786ac8cc92622d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702960"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="22ee3-102">Método IMetaDataImport::IsGlobal</span><span class="sxs-lookup"><span data-stu-id="22ee3-102">IMetaDataImport::IsGlobal Method</span></span>

<span data-ttu-id="22ee3-103">Obtém um valor que indica se o campo, o método ou o tipo representado pelo token de metadados especificado tem escopo global.</span><span class="sxs-lookup"><span data-stu-id="22ee3-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ee3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="22ee3-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22ee3-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="22ee3-105">Parameters</span></span>  

 `pd`  
 <span data-ttu-id="22ee3-106">no Um token de metadados que representa um tipo, campo ou método.</span><span class="sxs-lookup"><span data-stu-id="22ee3-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="22ee3-107">[fora] 1 se o objeto tiver escopo global; caso contrário, 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="22ee3-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22ee3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22ee3-108">Requirements</span></span>  

 <span data-ttu-id="22ee3-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22ee3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ee3-110">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="22ee3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22ee3-111">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22ee3-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22ee3-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22ee3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ee3-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="22ee3-113">See also</span></span>

- [<span data-ttu-id="22ee3-114">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="22ee3-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="22ee3-115">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="22ee3-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
