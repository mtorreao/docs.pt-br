---
title: Método IMetaDataEmit2::DefineMethodSpec
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
ms.openlocfilehash: 817b3a18b047bfca1f3a7c7099920a12e6253f58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712827"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="197a0-102">Método IMetaDataEmit2::DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="197a0-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>

<span data-ttu-id="197a0-103">Cria uma instância genérica de um método e Obtém um token para a definição.</span><span class="sxs-lookup"><span data-stu-id="197a0-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="197a0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="197a0-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="197a0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="197a0-105">Parameters</span></span>  

 `tkParent`  
 <span data-ttu-id="197a0-106">no Um token para o método do qual criar a instância genérica.</span><span class="sxs-lookup"><span data-stu-id="197a0-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="197a0-107">O token deve ser do tipo `mdMethodDef` ou `mdMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="197a0-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="197a0-108">no Um ponteiro para a assinatura COM+ binária do método.</span><span class="sxs-lookup"><span data-stu-id="197a0-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="197a0-109">no O tamanho, em bytes, de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="197a0-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="197a0-110">fora Um token para a definição de assinatura de metadados do método.</span><span class="sxs-lookup"><span data-stu-id="197a0-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="197a0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="197a0-111">Requirements</span></span>  

 <span data-ttu-id="197a0-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="197a0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="197a0-113">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="197a0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="197a0-114">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="197a0-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="197a0-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="197a0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="197a0-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="197a0-116">See also</span></span>

- [<span data-ttu-id="197a0-117">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="197a0-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="197a0-118">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="197a0-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
