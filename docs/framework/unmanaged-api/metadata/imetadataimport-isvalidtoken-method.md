---
title: Método IMetaDataImport::IsValidToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: b4dc1e60f3d29e2671882d1900a1c49e56969601
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702851"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="e8ff7-102">Método IMetaDataImport::IsValidToken</span><span class="sxs-lookup"><span data-stu-id="e8ff7-102">IMetaDataImport::IsValidToken Method</span></span>

<span data-ttu-id="e8ff7-103">Obtém um valor que indica se o token especificado contém uma referência válida a um objeto de código.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8ff7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e8ff7-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8ff7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e8ff7-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="e8ff7-106">no O token para verificar a validade de referência.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8ff7-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="e8ff7-107">Return Value</span></span>  

 <span data-ttu-id="e8ff7-108">`true` Se `tk` é um token de metadados válido dentro do escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="e8ff7-109">Caso contrário, `false`.</span><span class="sxs-lookup"><span data-stu-id="e8ff7-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8ff7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8ff7-110">Requirements</span></span>  

 <span data-ttu-id="e8ff7-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8ff7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8ff7-112">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e8ff7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8ff7-113">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8ff7-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8ff7-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8ff7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ff7-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="e8ff7-115">See also</span></span>

- [<span data-ttu-id="e8ff7-116">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e8ff7-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e8ff7-117">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e8ff7-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
