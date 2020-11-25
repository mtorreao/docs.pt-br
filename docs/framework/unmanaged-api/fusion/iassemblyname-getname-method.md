---
title: Método IAssemblyName::GetName
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
ms.openlocfilehash: 58b8b83ce1db9338612cbaa01a0db0862cf1054e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727894"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="4c690-102">Método IAssemblyName::GetName</span><span class="sxs-lookup"><span data-stu-id="4c690-102">IAssemblyName::GetName Method</span></span>

<span data-ttu-id="4c690-103">Obtém o nome simples e não criptografado do assembly referenciado por este objeto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4c690-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c690-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4c690-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c690-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4c690-105">Parameters</span></span>  

 `lpcwBuffer`  
 <span data-ttu-id="4c690-106">[entrada, saída] O tamanho de `pwzName` , em caracteres largos, incluindo o caractere de terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="4c690-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="4c690-107">fora Um buffer para conter o nome do assembly referenciado.</span><span class="sxs-lookup"><span data-stu-id="4c690-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c690-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4c690-108">Requirements</span></span>  

 <span data-ttu-id="4c690-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c690-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c690-110">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4c690-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4c690-111">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c690-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c690-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="4c690-112">See also</span></span>

- [<span data-ttu-id="4c690-113">Interface IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="4c690-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
