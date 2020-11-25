---
title: Método IMetaDataEmit2::SaveDeltaToMemory
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: a4dbe090987248ef77ce371b5bc6fb42d898f726
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705404"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="74799-102">Método IMetaDataEmit2::SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="74799-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>

<span data-ttu-id="74799-103">Salva as alterações da sessão de edição e continuação atual na memória.</span><span class="sxs-lookup"><span data-stu-id="74799-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74799-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="74799-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74799-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="74799-105">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="74799-106">fora O endereço no qual começar a gravar o Delta de metadados.</span><span class="sxs-lookup"><span data-stu-id="74799-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="74799-107">no O tamanho das alterações.</span><span class="sxs-lookup"><span data-stu-id="74799-107">[in] The size of the changes.</span></span> <span data-ttu-id="74799-108">Use [IMetaDataEmit2:: GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) para determinar o tamanho.</span><span class="sxs-lookup"><span data-stu-id="74799-108">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74799-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74799-109">Requirements</span></span>  

 <span data-ttu-id="74799-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74799-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74799-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="74799-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74799-112">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74799-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74799-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74799-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74799-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="74799-114">See also</span></span>

- [<span data-ttu-id="74799-115">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="74799-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="74799-116">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="74799-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
