---
title: Método IMetaDataEmit2::SaveDeltaToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: dad916d74c4e754d8fd3ffb62024e49617f5de05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702011"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="679b4-102">Método IMetaDataEmit2::SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="679b4-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>

<span data-ttu-id="679b4-103">Salva as alterações da sessão de edição e continuação atual para o fluxo especificado.</span><span class="sxs-lookup"><span data-stu-id="679b4-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="679b4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="679b4-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="679b4-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="679b4-105">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="679b4-106">no Um ponteiro de interface para o fluxo gravável no qual salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="679b4-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="679b4-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="679b4-107">[in] Reserved.</span></span> <span data-ttu-id="679b4-108">Esse valor precisa ser zero.</span><span class="sxs-lookup"><span data-stu-id="679b4-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="679b4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="679b4-109">Requirements</span></span>  

 <span data-ttu-id="679b4-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="679b4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="679b4-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="679b4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="679b4-112">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="679b4-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="679b4-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="679b4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="679b4-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="679b4-114">See also</span></span>

- [<span data-ttu-id="679b4-115">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="679b4-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="679b4-116">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="679b4-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
