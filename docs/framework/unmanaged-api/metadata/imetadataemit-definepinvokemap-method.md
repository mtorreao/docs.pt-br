---
title: Método IMetaDataEmit::DefinePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: b46d39ab3958227c1fca24ceb3a9934f2778aa2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719496"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="975f5-102">Método IMetaDataEmit::DefinePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="975f5-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>

<span data-ttu-id="975f5-103">Define os recursos da assinatura PInvoke do método referenciado pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="975f5-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="975f5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="975f5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="975f5-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="975f5-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="975f5-106">no O token para o método de destino.</span><span class="sxs-lookup"><span data-stu-id="975f5-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="975f5-107">no Sinalizadores usados pelo PInvoke para fazer o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="975f5-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="975f5-108">no O nome do método de exportação de destino em uma DLL não gerenciada.</span><span class="sxs-lookup"><span data-stu-id="975f5-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="975f5-109">no O token para a DLL nativa de destino.</span><span class="sxs-lookup"><span data-stu-id="975f5-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="975f5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="975f5-110">Requirements</span></span>  

 <span data-ttu-id="975f5-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="975f5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="975f5-112">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="975f5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="975f5-113">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="975f5-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="975f5-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="975f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="975f5-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="975f5-115">See also</span></span>

- [<span data-ttu-id="975f5-116">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="975f5-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="975f5-117">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="975f5-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
