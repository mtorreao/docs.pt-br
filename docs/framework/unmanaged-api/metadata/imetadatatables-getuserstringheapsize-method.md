---
title: Método IMetaDataTables::GetUserStringHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
ms.openlocfilehash: 048010f00f6581a29c6b1a3150bf5ae8822b5664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672455"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="d28b2-102">Método IMetaDataTables::GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="d28b2-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>

<span data-ttu-id="d28b2-103">Obtém o tamanho, em bytes, do heap de cadeia de caracteres do usuário.</span><span class="sxs-lookup"><span data-stu-id="d28b2-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d28b2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d28b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d28b2-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d28b2-105">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="d28b2-106">fora Um ponteiro para o tamanho, em bytes, do heap de cadeia de caracteres do usuário.</span><span class="sxs-lookup"><span data-stu-id="d28b2-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d28b2-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d28b2-107">Requirements</span></span>  

 <span data-ttu-id="d28b2-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d28b2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d28b2-109">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d28b2-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d28b2-110">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d28b2-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d28b2-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d28b2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d28b2-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="d28b2-112">See also</span></span>

- [<span data-ttu-id="d28b2-113">Interface IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="d28b2-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="d28b2-114">Interface IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="d28b2-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
