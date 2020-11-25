---
title: Método IMetaDataImport::GetTypeSpecFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
ms.openlocfilehash: 62495aa4280bb1799af09fea2e550ae6107e09e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729142"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="35b45-102">Método IMetaDataImport::GetTypeSpecFromToken</span><span class="sxs-lookup"><span data-stu-id="35b45-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>

<span data-ttu-id="35b45-103">Obtém a assinatura de metadados binários da especificação de tipo representada pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="35b45-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b45-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="35b45-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (
   [in]  mdTypeSpec            typespec,
   [out] PCCOR_SIGNATURE       *ppvSig,
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35b45-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="35b45-105">Parameters</span></span>  

 `typespec`  
 <span data-ttu-id="35b45-106">no O token TypeSpec associado à assinatura de metadados solicitada.</span><span class="sxs-lookup"><span data-stu-id="35b45-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="35b45-107">fora Um ponteiro para a assinatura de metadados binários.</span><span class="sxs-lookup"><span data-stu-id="35b45-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="35b45-108">fora O tamanho, em bytes, da assinatura de metadados.</span><span class="sxs-lookup"><span data-stu-id="35b45-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35b45-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="35b45-109">Return Value</span></span>  

 <span data-ttu-id="35b45-110">Um HRESULT que indica êxito ou falha.</span><span class="sxs-lookup"><span data-stu-id="35b45-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="35b45-111">As falhas podem ser testadas com a macro com falha.</span><span class="sxs-lookup"><span data-stu-id="35b45-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35b45-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35b45-112">Requirements</span></span>  

 <span data-ttu-id="35b45-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35b45-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b45-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="35b45-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35b45-115">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35b45-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35b45-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35b45-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b45-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="35b45-117">See also</span></span>

- [<span data-ttu-id="35b45-118">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="35b45-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="35b45-119">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="35b45-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
