---
title: Método IMetaDataImport::GetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: 5a442d8d0916b0e86f25c03507de66fc999f2159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711228"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="c931c-102">Método IMetaDataImport::GetClassLayout</span><span class="sxs-lookup"><span data-stu-id="c931c-102">IMetaDataImport::GetClassLayout Method</span></span>

<span data-ttu-id="c931c-103">Obtém informações de layout para a classe referenciada pelo token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="c931c-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c931c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c931c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c931c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c931c-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="c931c-106">no O token de TypeDef para a classe com o layout a ser retornado.</span><span class="sxs-lookup"><span data-stu-id="c931c-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="c931c-107">fora Um dos valores 1, 2, 4, 8 ou 16, que representa o tamanho do pacote da classe.</span><span class="sxs-lookup"><span data-stu-id="c931c-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="c931c-108">fora Uma matriz de valores de [COR_FIELD_OFFSET](cor-field-offset-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="c931c-108">[out] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c931c-109">no O tamanho máximo da `rFieldOffset` matriz.</span><span class="sxs-lookup"><span data-stu-id="c931c-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="c931c-110">fora O número de elementos retornados em `rFieldOffset` .</span><span class="sxs-lookup"><span data-stu-id="c931c-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="c931c-111">fora O tamanho em bytes da classe representada por `td` .</span><span class="sxs-lookup"><span data-stu-id="c931c-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c931c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c931c-112">Requirements</span></span>  

 <span data-ttu-id="c931c-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c931c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c931c-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c931c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c931c-115">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c931c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c931c-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c931c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c931c-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="c931c-117">See also</span></span>

- [<span data-ttu-id="c931c-118">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c931c-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c931c-119">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c931c-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
