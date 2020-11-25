---
title: Método ITypeNameFactory::ParseTypeName
ms.date: 03/30/2017
api_name:
- ITypeNameFactory.ParseTypeName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ParseTypeName
helpviewer_keywords:
- ITypeNameFactory::ParseTypeName method [.NET Framework hosting]
- ParseTypeName method [.NET Framework hosting]
ms.assetid: 13c9f063-371c-4911-a5e7-e1e0b88ae382
topic_type:
- apiref
ms.openlocfilehash: 2b4d22fac7125ad113aaef5b093396a065f682c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728713"
---
# <a name="itypenamefactoryparsetypename-method"></a><span data-ttu-id="06073-102">Método ITypeNameFactory::ParseTypeName</span><span class="sxs-lookup"><span data-stu-id="06073-102">ITypeNameFactory::ParseTypeName Method</span></span>

<span data-ttu-id="06073-103">Esse método oferece suporte a infraestrutura do .NET Framework e não se destina a ser usado diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="06073-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06073-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="06073-104">Syntax</span></span>  
  
```cpp  
HRESULT ParseTypeName (  
    [in]  LPCWSTR             szName,  
    [out] DWORD*              pError,  
    [out, retval] ITypeName** ppTypeName  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="06073-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06073-105">Requirements</span></span>  

 <span data-ttu-id="06073-106">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06073-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06073-107">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="06073-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06073-108">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06073-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06073-109">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06073-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06073-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="06073-110">See also</span></span>

- [<span data-ttu-id="06073-111">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="06073-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
