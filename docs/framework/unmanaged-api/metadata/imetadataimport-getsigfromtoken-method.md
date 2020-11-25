---
title: Método IMetaDataImport::GetSigFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
ms.openlocfilehash: 67abdfd8f8c67299eae757533f20df69392f25b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729181"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="1c74d-102">Método IMetaDataImport::GetSigFromToken</span><span class="sxs-lookup"><span data-stu-id="1c74d-102">IMetaDataImport::GetSigFromToken Method</span></span>

<span data-ttu-id="1c74d-103">Obtém a assinatura de metadados binários associada ao token especificado.</span><span class="sxs-lookup"><span data-stu-id="1c74d-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c74d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1c74d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c74d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1c74d-105">Parameters</span></span>  

 `mdSig`  
 <span data-ttu-id="1c74d-106">no O token para o qual retornar a assinatura de metadados binários.</span><span class="sxs-lookup"><span data-stu-id="1c74d-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="1c74d-107">fora Um ponteiro para a assinatura de metadados retornada.</span><span class="sxs-lookup"><span data-stu-id="1c74d-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="1c74d-108">fora O tamanho em bytes da assinatura de metadados binários.</span><span class="sxs-lookup"><span data-stu-id="1c74d-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c74d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c74d-109">Requirements</span></span>  

 <span data-ttu-id="1c74d-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c74d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c74d-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1c74d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c74d-112">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c74d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c74d-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c74d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c74d-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="1c74d-114">See also</span></span>

- [<span data-ttu-id="1c74d-115">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1c74d-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1c74d-116">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1c74d-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
