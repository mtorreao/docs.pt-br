---
title: Método IMetaDataImport::GetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: b4e7209c357f21a3f0de5770b483b673d5a5570b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729207"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="34331-102">Método IMetaDataImport::GetRVA</span><span class="sxs-lookup"><span data-stu-id="34331-102">IMetaDataImport::GetRVA Method</span></span>

<span data-ttu-id="34331-103">Obtém o endereço virtual relativo (RVA) e os sinalizadores de implementação do método ou do campo representado pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="34331-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34331-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="34331-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34331-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="34331-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="34331-106">no Um token de metadados MethodDef ou FieldDef que representa o objeto de código para o qual retornar o RVA.</span><span class="sxs-lookup"><span data-stu-id="34331-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="34331-107">Se o token for um FieldDef, o campo deverá ser uma variável global.</span><span class="sxs-lookup"><span data-stu-id="34331-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="34331-108">fora Um ponteiro para o endereço virtual relativo do objeto de código representado pelo token.</span><span class="sxs-lookup"><span data-stu-id="34331-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="34331-109">fora Um ponteiro para os sinalizadores de implementação do método.</span><span class="sxs-lookup"><span data-stu-id="34331-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="34331-110">Esse valor é um bitmask da enumeração [CorMethodImpl](cormethodimpl-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="34331-110">This value is a bitmask from the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="34331-111">O valor de `pdwImplFlags` será válido somente se `tk` for um token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="34331-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34331-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34331-112">Requirements</span></span>  

 <span data-ttu-id="34331-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34331-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34331-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="34331-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34331-115">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="34331-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34331-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34331-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34331-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="34331-117">See also</span></span>

- [<span data-ttu-id="34331-118">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="34331-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="34331-119">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="34331-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
