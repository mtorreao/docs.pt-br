---
title: Método IMetaDataError::OnError
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
ms.openlocfilehash: 6f6e531c99d341eba39939a184d2424256d9e155
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701855"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="4e350-102">Método IMetaDataError::OnError</span><span class="sxs-lookup"><span data-stu-id="4e350-102">IMetaDataError::OnError Method</span></span>

<span data-ttu-id="4e350-103">Fornece uma notificação de erros que ocorrem durante a mesclagem de metadados.</span><span class="sxs-lookup"><span data-stu-id="4e350-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e350-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4e350-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e350-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4e350-105">Parameters</span></span>  

 `hrError`  
 <span data-ttu-id="4e350-106">no O valor de erro HRESULT retornado ao método de chamada.</span><span class="sxs-lookup"><span data-stu-id="4e350-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="4e350-107">no O token de metadados do objeto de código que estava sendo mesclado quando o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="4e350-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e350-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e350-108">Requirements</span></span>  

 <span data-ttu-id="4e350-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e350-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e350-110">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4e350-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e350-111">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e350-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e350-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e350-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e350-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="4e350-113">See also</span></span>

- [<span data-ttu-id="4e350-114">Interface IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="4e350-114">IMetaDataError Interface</span></span>](imetadataerror-interface.md)
