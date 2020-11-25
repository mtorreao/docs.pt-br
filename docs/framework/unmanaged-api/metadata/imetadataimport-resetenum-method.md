---
title: Método IMetaDataImport::ResetEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
ms.openlocfilehash: 52c35b3bd726d4c83c6745bf99940faa44ea7338
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702843"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="3be01-102">Método IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="3be01-102">IMetaDataImport::ResetEnum Method</span></span>

<span data-ttu-id="3be01-103">Redefine o enumerador especificado para a posição especificada.</span><span class="sxs-lookup"><span data-stu-id="3be01-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be01-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3be01-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3be01-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3be01-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="3be01-106">no O enumerador a ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="3be01-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="3be01-107">no A nova posição na qual colocar o enumerador.</span><span class="sxs-lookup"><span data-stu-id="3be01-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3be01-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3be01-108">Requirements</span></span>  

 <span data-ttu-id="3be01-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3be01-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3be01-110">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3be01-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3be01-111">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3be01-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3be01-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3be01-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be01-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="3be01-113">See also</span></span>

- [<span data-ttu-id="3be01-114">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3be01-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3be01-115">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3be01-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
