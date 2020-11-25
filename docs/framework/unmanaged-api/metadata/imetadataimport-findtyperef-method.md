---
title: Método IMetaDataImport::FindTypeRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
ms.openlocfilehash: 3c96a9b601824cc4001568c4656f968fad70cf39
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711280"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="d31a0-102">Método IMetaDataImport::FindTypeRef</span><span class="sxs-lookup"><span data-stu-id="d31a0-102">IMetaDataImport::FindTypeRef Method</span></span>

<span data-ttu-id="d31a0-103">Obtém um ponteiro para o token TypeRef para a <xref:System.Type> referência que está no escopo especificado e que tem o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="d31a0-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d31a0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d31a0-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d31a0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d31a0-105">Parameters</span></span>  

 `tkResolutionScope`  
 <span data-ttu-id="d31a0-106">no Um token ModuleRef, AssemblyRef ou TypeRef que especifica o módulo, o assembly ou o tipo, respectivamente, no qual a referência de tipo é definida.</span><span class="sxs-lookup"><span data-stu-id="d31a0-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="d31a0-107">no O nome da referência de tipo a ser pesquisada.</span><span class="sxs-lookup"><span data-stu-id="d31a0-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="d31a0-108">fora Um ponteiro para o token TypeRef correspondente.</span><span class="sxs-lookup"><span data-stu-id="d31a0-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d31a0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d31a0-109">Requirements</span></span>  

 <span data-ttu-id="d31a0-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d31a0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d31a0-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d31a0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d31a0-112">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d31a0-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d31a0-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d31a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d31a0-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="d31a0-114">See also</span></span>

- [<span data-ttu-id="d31a0-115">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d31a0-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d31a0-116">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d31a0-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
