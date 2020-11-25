---
title: Método IMetaDataDispenserEx::FindAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
ms.openlocfilehash: c11a4498610c3e82590a0ff9be1247173e70be76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713386"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="efc67-102">Método IMetaDataDispenserEx::FindAssembly</span><span class="sxs-lookup"><span data-stu-id="efc67-102">IMetaDataDispenserEx::FindAssembly Method</span></span>

<span data-ttu-id="efc67-103">Este método não está implementado.</span><span class="sxs-lookup"><span data-stu-id="efc67-103">This method is not implemented.</span></span> <span data-ttu-id="efc67-104">Se chamado, ele retornará E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="efc67-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efc67-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="efc67-105">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efc67-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="efc67-106">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="efc67-107">no Não usado.</span><span class="sxs-lookup"><span data-stu-id="efc67-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="efc67-108">no Não usado.</span><span class="sxs-lookup"><span data-stu-id="efc67-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="efc67-109">no Não usado.</span><span class="sxs-lookup"><span data-stu-id="efc67-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="efc67-110">no O assembly a ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="efc67-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="efc67-111">fora O nome simples do assembly.</span><span class="sxs-lookup"><span data-stu-id="efc67-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="efc67-112">no O tamanho, em bytes, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="efc67-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="efc67-113">fora O número de caracteres realmente retornados em `szName` .</span><span class="sxs-lookup"><span data-stu-id="efc67-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efc67-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efc67-114">Requirements</span></span>  

 <span data-ttu-id="efc67-115">**Plataforma:** Consulte [requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efc67-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efc67-116">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="efc67-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="efc67-117">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="efc67-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="efc67-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efc67-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc67-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="efc67-119">See also</span></span>

- [<span data-ttu-id="efc67-120">Interface IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="efc67-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="efc67-121">Interface IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="efc67-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
