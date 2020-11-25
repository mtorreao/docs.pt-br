---
title: Método IMetaDataEmit::SetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 236fc848087f64c2327c2c9e790065cc3f64dc58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704299"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="4187a-102">Método IMetaDataEmit::SetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="4187a-102">IMetaDataEmit::SetPinvokeMap Method</span></span>

<span data-ttu-id="4187a-103">Define ou altera recursos da assinatura do PInvoke de um método, conforme definido por uma chamada anterior para [IMetaDataEmit::D efinepinvokemap](imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="4187a-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4187a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4187a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4187a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4187a-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="4187a-106">no O `mdToken` ao qual as informações de mapeamento se aplicam.</span><span class="sxs-lookup"><span data-stu-id="4187a-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="4187a-107">no Sinalizadores usados pelo PInvoke para fazer o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="4187a-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="4187a-108">Esta é uma bitmask de `CorPinvokeMap` valores.</span><span class="sxs-lookup"><span data-stu-id="4187a-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="4187a-109">no O nome da exportação de destino na DLL nativa.</span><span class="sxs-lookup"><span data-stu-id="4187a-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="4187a-110">no O `mdModuleRef` token para a dll não gerenciada de destino.</span><span class="sxs-lookup"><span data-stu-id="4187a-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4187a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4187a-111">Requirements</span></span>  

 <span data-ttu-id="4187a-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4187a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4187a-113">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4187a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4187a-114">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4187a-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4187a-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4187a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4187a-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="4187a-116">See also</span></span>

- [<span data-ttu-id="4187a-117">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4187a-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4187a-118">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4187a-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
