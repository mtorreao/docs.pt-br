---
title: Método ICorDebugProcess5::GetTypeLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: 32277e8adcd4bb08c8d0480eb3b4e7e4b5949479
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723123"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="15a01-102">Método ICorDebugProcess5::GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="15a01-102">ICorDebugProcess5::GetTypeLayout Method</span></span>

<span data-ttu-id="15a01-103">Obtém informações sobre o layout de um objeto na memória com base em seu identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="15a01-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15a01-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="15a01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15a01-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="15a01-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="15a01-106">no Um [COR_TYPEID](cor-typeid-structure.md) token que especifica o tipo cujo layout é desejado.</span><span class="sxs-lookup"><span data-stu-id="15a01-106">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="15a01-107">fora Um ponteiro para uma estrutura de [COR_TYPE_LAYOUT](cor-type-layout-structure.md) que contém informações sobre o layout do objeto na memória.</span><span class="sxs-lookup"><span data-stu-id="15a01-107">[out] A pointer to a [COR_TYPE_LAYOUT](cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15a01-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="15a01-108">Remarks</span></span>  

 <span data-ttu-id="15a01-109">O `ICorDebugProcess5::GetTypeLayout` método fornece informações sobre um objeto com base em seu [COR_TYPEID](cor-typeid-structure.md), que é retornado por vários outros métodos [ICorDebugProcess5](icordebugprocess5-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="15a01-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="15a01-110">As informações são fornecidas por uma estrutura de [COR_TYPE_LAYOUT](cor-type-layout-structure.md) que é populada pelo método.</span><span class="sxs-lookup"><span data-stu-id="15a01-110">The information is provided by a [COR_TYPE_LAYOUT](cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a01-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15a01-111">Requirements</span></span>  

 <span data-ttu-id="15a01-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15a01-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15a01-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15a01-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15a01-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15a01-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15a01-115">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15a01-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a01-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="15a01-116">See also</span></span>

- [<span data-ttu-id="15a01-117">Estrutura COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="15a01-117">COR_TYPE_LAYOUT Structure</span></span>](cor-type-layout-structure.md)
- [<span data-ttu-id="15a01-118">Interface ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="15a01-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="15a01-119">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="15a01-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
