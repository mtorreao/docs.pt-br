---
title: Método IMetaDataDispenserEx::OpenScopeOnITypeInfo
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
ms.openlocfilehash: 6056a64b354f69ce39692173da01892870fba9e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682842"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="02fe0-102">Método IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="02fe0-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>

<span data-ttu-id="02fe0-103">Este método não está implementado.</span><span class="sxs-lookup"><span data-stu-id="02fe0-103">This method is not implemented.</span></span> <span data-ttu-id="02fe0-104">Se chamado, ele retornará E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="02fe0-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02fe0-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="02fe0-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02fe0-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="02fe0-106">Parameters</span></span>  

 `pITI`  
 <span data-ttu-id="02fe0-107">no Ponteiro para uma interface [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) que fornece as informações de tipo nas quais abrir o escopo.</span><span class="sxs-lookup"><span data-stu-id="02fe0-107">[in] Pointer to an [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="02fe0-108">no Os sinalizadores de modo aberto.</span><span class="sxs-lookup"><span data-stu-id="02fe0-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="02fe0-109">no A interface desejada.</span><span class="sxs-lookup"><span data-stu-id="02fe0-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="02fe0-110">fora Ponteiro para um ponteiro para a interface retornada.</span><span class="sxs-lookup"><span data-stu-id="02fe0-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02fe0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02fe0-111">Requirements</span></span>  

 <span data-ttu-id="02fe0-112">**Plataforma:** Consulte [requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02fe0-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02fe0-113">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="02fe0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02fe0-114">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="02fe0-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02fe0-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02fe0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02fe0-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="02fe0-116">See also</span></span>

- [<span data-ttu-id="02fe0-117">Interface IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="02fe0-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="02fe0-118">Interface IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="02fe0-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
