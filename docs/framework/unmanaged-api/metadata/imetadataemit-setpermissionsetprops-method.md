---
title: Método IMetaDataEmit::SetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: 4c3e0953d71020ba62ee4ab68aa9e21ea3f0f521
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675029"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="7d15f-102">Método IMetaDataEmit::SetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="7d15f-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>

<span data-ttu-id="7d15f-103">Define ou atualiza recursos da assinatura de metadados de um conjunto de permissões definido por uma chamada anterior para [IMetaDataEmit::D efinepermissionset](imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="7d15f-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d15f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7d15f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d15f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7d15f-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="7d15f-106">no Um token de metadados que representa o objeto a ser decorado.</span><span class="sxs-lookup"><span data-stu-id="7d15f-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="7d15f-107">no Um valor de [CorDeclSecurity](cordeclsecurity-enumeration.md) que especifica o tipo de segurança declarativa a ser usado.</span><span class="sxs-lookup"><span data-stu-id="7d15f-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="7d15f-108">no O BLOB de permissão.</span><span class="sxs-lookup"><span data-stu-id="7d15f-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="7d15f-109">no O tamanho, em bytes, de `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="7d15f-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="7d15f-110">fora Um `mdPermission` token de metadados que representa as permissões atualizadas.</span><span class="sxs-lookup"><span data-stu-id="7d15f-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d15f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d15f-111">Requirements</span></span>  

 <span data-ttu-id="7d15f-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d15f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d15f-113">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7d15f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d15f-114">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d15f-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d15f-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d15f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d15f-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="7d15f-116">See also</span></span>

- [<span data-ttu-id="7d15f-117">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7d15f-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7d15f-118">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7d15f-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
