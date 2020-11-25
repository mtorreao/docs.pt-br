---
title: Método ITypeName::GetNames
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
ms.openlocfilehash: 91e73f8e3d2e3c372d3fe1c4fd4fccf6ff67b363
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727803"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="17eb7-102">Método ITypeName::GetNames</span><span class="sxs-lookup"><span data-stu-id="17eb7-102">ITypeName::GetNames Method</span></span>

<span data-ttu-id="17eb7-103">Esse método oferece suporte a infraestrutura do .NET Framework e não se destina a ser usado diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="17eb7-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17eb7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="17eb7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="17eb7-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17eb7-105">Requirements</span></span>  

 <span data-ttu-id="17eb7-106">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17eb7-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17eb7-107">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="17eb7-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17eb7-108">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17eb7-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17eb7-109">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17eb7-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17eb7-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="17eb7-110">See also</span></span>

- [<span data-ttu-id="17eb7-111">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="17eb7-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
