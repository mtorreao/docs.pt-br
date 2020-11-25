---
title: Método IMetaDataEmit::DefineMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: 597ba1884351ee6d8b7eb7e0f3f01ce3ad733304
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716636"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="a0948-102">Método IMetaDataEmit::DefineMemberRef</span><span class="sxs-lookup"><span data-stu-id="a0948-102">IMetaDataEmit::DefineMemberRef Method</span></span>

<span data-ttu-id="a0948-103">Define uma referência a um membro de um módulo fora do escopo atual e Obtém um token para essa definição de referência.</span><span class="sxs-lookup"><span data-stu-id="a0948-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0948-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a0948-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0948-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a0948-105">Parameters</span></span>  

 `tkImport`  
 <span data-ttu-id="a0948-106">no Token para a classe ou a interface do membro de destino, se o membro não for global; Se o membro for global, o `mdModuleRef` token para esse outro arquivo.</span><span class="sxs-lookup"><span data-stu-id="a0948-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="a0948-107">no O nome do membro de destino.</span><span class="sxs-lookup"><span data-stu-id="a0948-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="a0948-108">no A assinatura do membro de destino.</span><span class="sxs-lookup"><span data-stu-id="a0948-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="a0948-109">no A contagem de bytes em `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="a0948-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="a0948-110">fora O `mdMemberRef` token atribuído.</span><span class="sxs-lookup"><span data-stu-id="a0948-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0948-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0948-111">Requirements</span></span>  

 <span data-ttu-id="a0948-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0948-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0948-113">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a0948-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0948-114">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0948-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0948-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0948-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0948-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="a0948-116">See also</span></span>

- [<span data-ttu-id="a0948-117">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a0948-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a0948-118">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a0948-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
