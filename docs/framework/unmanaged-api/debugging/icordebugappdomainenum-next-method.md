---
title: Método ICorDebugAppDomainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
ms.openlocfilehash: b315f38dc306727e33b52b84d17951a91ccdc39f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684467"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="45195-102">Método ICorDebugAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="45195-102">ICorDebugAppDomainEnum::Next Method</span></span>

<span data-ttu-id="45195-103">Obtém o número especificado de domínios de aplicativo da coleção, começando na posição atual do cursor.</span><span class="sxs-lookup"><span data-stu-id="45195-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45195-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="45195-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45195-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="45195-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="45195-106">no O número de domínios de aplicativo a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="45195-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="45195-107">fora Uma matriz de ponteiros, cada um dos quais aponta para um objeto ICorDebugAppDomain que representa um domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="45195-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="45195-108">fora Um ponteiro para o número de domínios de aplicativo realmente retornados.</span><span class="sxs-lookup"><span data-stu-id="45195-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="45195-109">Esse valor pode ser nulo se `celt` for um.</span><span class="sxs-lookup"><span data-stu-id="45195-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45195-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45195-110">Requirements</span></span>  

 <span data-ttu-id="45195-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45195-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45195-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45195-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45195-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45195-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45195-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45195-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
