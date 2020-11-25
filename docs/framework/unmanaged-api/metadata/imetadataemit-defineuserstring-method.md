---
title: Método IMetaDataEmit::DefineUserString
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
ms.openlocfilehash: ed3c20fe8272ca3205079d26df0b7bde12e58307
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732691"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="30a09-102">Método IMetaDataEmit::DefineUserString</span><span class="sxs-lookup"><span data-stu-id="30a09-102">IMetaDataEmit::DefineUserString Method</span></span>

<span data-ttu-id="30a09-103">Obtém um token de metadados para a cadeia de caracteres literal especificada.</span><span class="sxs-lookup"><span data-stu-id="30a09-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a09-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="30a09-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30a09-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="30a09-105">Parameters</span></span>  

 `szString`  
 <span data-ttu-id="30a09-106">no A cadeia de caracteres do usuário a ser armazenada.</span><span class="sxs-lookup"><span data-stu-id="30a09-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="30a09-107">no A contagem de caracteres largos em `szString` .</span><span class="sxs-lookup"><span data-stu-id="30a09-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="30a09-108">fora O token de cadeia de caracteres atribuído.</span><span class="sxs-lookup"><span data-stu-id="30a09-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a09-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30a09-109">Requirements</span></span>  

 <span data-ttu-id="30a09-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30a09-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a09-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="30a09-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30a09-112">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30a09-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30a09-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30a09-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a09-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="30a09-114">See also</span></span>

- [<span data-ttu-id="30a09-115">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="30a09-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="30a09-116">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="30a09-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
