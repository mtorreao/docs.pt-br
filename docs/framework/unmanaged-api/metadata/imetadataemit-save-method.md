---
title: Método IMetaDataEmit::Save
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: cef238239417a0a30cd94eaa8bd60968cfa78859
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721992"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="a79e5-102">Método IMetaDataEmit::Save</span><span class="sxs-lookup"><span data-stu-id="a79e5-102">IMetaDataEmit::Save Method</span></span>

<span data-ttu-id="a79e5-103">Salva todos os metadados no escopo atual para o arquivo no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="a79e5-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a79e5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a79e5-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a79e5-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a79e5-105">Parameters</span></span>  

 `wzFile`  
 <span data-ttu-id="a79e5-106">no O nome do arquivo para salvar.</span><span class="sxs-lookup"><span data-stu-id="a79e5-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="a79e5-107">Se esse valor for nulo, a cópia na memória será salva no último local que foi usado.</span><span class="sxs-lookup"><span data-stu-id="a79e5-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="a79e5-108">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="a79e5-108">[in] Reserved.</span></span> <span data-ttu-id="a79e5-109">Deve ser zero.</span><span class="sxs-lookup"><span data-stu-id="a79e5-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a79e5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a79e5-110">Requirements</span></span>  

 <span data-ttu-id="a79e5-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a79e5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a79e5-112">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a79e5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a79e5-113">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a79e5-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a79e5-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a79e5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a79e5-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="a79e5-115">See also</span></span>

- [<span data-ttu-id="a79e5-116">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a79e5-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a79e5-117">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a79e5-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
