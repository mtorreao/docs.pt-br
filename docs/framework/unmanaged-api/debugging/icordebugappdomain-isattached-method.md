---
title: Método ICorDebugAppDomain::IsAttached
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: 898398b731832e698a43eb270bbdc63bb3867bb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702167"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="b214b-102">Método ICorDebugAppDomain::IsAttached</span><span class="sxs-lookup"><span data-stu-id="b214b-102">ICorDebugAppDomain::IsAttached Method</span></span>

<span data-ttu-id="b214b-103">Obtém um valor que indica se o depurador está anexado ao domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b214b-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b214b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b214b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b214b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b214b-105">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="b214b-106">[fora] `true` Se o depurador estiver anexado ao domínio do aplicativo; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="b214b-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b214b-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="b214b-107">Remarks</span></span>  

 <span data-ttu-id="b214b-108">Os métodos ICorDebugController não podem ser usados até que o depurador seja anexado ao domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b214b-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b214b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b214b-109">Requirements</span></span>  

 <span data-ttu-id="b214b-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b214b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b214b-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b214b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b214b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b214b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b214b-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b214b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
