---
title: Método IMetaDataDispenserEx::GetCORSystemDirectory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
ms.openlocfilehash: ea0e6f96028afc201f498119976eb87aa762a6eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681685"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="bb4f0-102">Método IMetaDataDispenserEx::GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="bb4f0-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>

<span data-ttu-id="bb4f0-103">Obtém o diretório que contém o Common Language Runtime atual (CLR).</span><span class="sxs-lookup"><span data-stu-id="bb4f0-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="bb4f0-104">Esse método só tem suporte para uso por depuradores fora do processo.</span><span class="sxs-lookup"><span data-stu-id="bb4f0-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="bb4f0-105">Se for chamado de outro componente, ele retornará E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="bb4f0-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb4f0-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bb4f0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb4f0-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bb4f0-107">Parameters</span></span>  

 `szBuffer`  
 <span data-ttu-id="bb4f0-108">fora O buffer para receber o nome do diretório.</span><span class="sxs-lookup"><span data-stu-id="bb4f0-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="bb4f0-109">no O tamanho, em bytes, de `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="bb4f0-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="bb4f0-110">fora O número de bytes realmente retornados em `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="bb4f0-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb4f0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb4f0-111">Requirements</span></span>  

 <span data-ttu-id="bb4f0-112">**Plataforma:** Consulte [requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb4f0-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb4f0-113">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bb4f0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb4f0-114">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb4f0-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb4f0-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb4f0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4f0-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="bb4f0-116">See also</span></span>

- [<span data-ttu-id="bb4f0-117">Interface IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="bb4f0-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="bb4f0-118">Interface IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="bb4f0-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
