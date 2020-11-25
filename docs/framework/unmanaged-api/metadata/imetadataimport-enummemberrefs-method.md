---
title: Método IMetaDataImport::EnumMemberRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
ms.openlocfilehash: d8b02e85efc2cd7364690dd42104a313ba6ec272
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711449"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="36568-102">Método IMetaDataImport::EnumMemberRefs</span><span class="sxs-lookup"><span data-stu-id="36568-102">IMetaDataImport::EnumMemberRefs Method</span></span>

<span data-ttu-id="36568-103">Enumera os tokens de MemberRef que representam os membros do tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="36568-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36568-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="36568-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36568-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="36568-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="36568-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="36568-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="36568-107">no Um token de TypeDef, TypeRef, MethodDef ou ModuleRef para o tipo cujos membros devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="36568-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="36568-108">fora A matriz usada para armazenar tokens de MemberRef.</span><span class="sxs-lookup"><span data-stu-id="36568-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="36568-109">no O tamanho máximo da `rMemberRefs` matriz.</span><span class="sxs-lookup"><span data-stu-id="36568-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="36568-110">fora O número real de tokens de MemberRef retornado em `rMemberRefs` .</span><span class="sxs-lookup"><span data-stu-id="36568-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36568-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="36568-111">Return Value</span></span>  
  
|<span data-ttu-id="36568-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36568-112">HRESULT</span></span>|<span data-ttu-id="36568-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="36568-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="36568-114">`EnumMemberRefs` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="36568-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="36568-115">Não há tokens de MemberRef para enumerar.</span><span class="sxs-lookup"><span data-stu-id="36568-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="36568-116">Nesse caso, `pcTokens` é zero.</span><span class="sxs-lookup"><span data-stu-id="36568-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36568-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36568-117">Requirements</span></span>  

 <span data-ttu-id="36568-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36568-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36568-119">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="36568-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36568-120">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36568-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36568-121">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36568-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36568-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="36568-122">See also</span></span>

- [<span data-ttu-id="36568-123">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="36568-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="36568-124">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="36568-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
