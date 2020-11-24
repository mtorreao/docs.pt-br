---
title: Método ICorDebugManagedCallback::LoadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: 6f1672d40cd495d3ec099abc703639cf52460703
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679657"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="ecc43-102">Método ICorDebugManagedCallback::LoadClass</span><span class="sxs-lookup"><span data-stu-id="ecc43-102">ICorDebugManagedCallback::LoadClass Method</span></span>

<span data-ttu-id="ecc43-103">Notifica o depurador de que uma classe foi carregada.</span><span class="sxs-lookup"><span data-stu-id="ecc43-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc43-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ecc43-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecc43-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ecc43-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="ecc43-106">no Um ponteiro para um objeto ICorDebugAppDomain que representa o domínio do aplicativo no qual a classe foi carregada.</span><span class="sxs-lookup"><span data-stu-id="ecc43-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="ecc43-107">no Um ponteiro para um objeto ICorDebugClass que representa a classe.</span><span class="sxs-lookup"><span data-stu-id="ecc43-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecc43-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="ecc43-108">Remarks</span></span>  

 <span data-ttu-id="ecc43-109">Esse retorno de chamada ocorrerá somente se o carregamento da classe tiver sido habilitado para o módulo que contém a classe.</span><span class="sxs-lookup"><span data-stu-id="ecc43-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="ecc43-110">O carregamento de classe é sempre habilitado para módulos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="ecc43-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="ecc43-111">O `LoadClass` retorno de chamada fornece um tempo apropriado para associar pontos de interrupção a classes recém-gerado em módulos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="ecc43-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecc43-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecc43-112">Requirements</span></span>  

 <span data-ttu-id="ecc43-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecc43-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecc43-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecc43-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecc43-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecc43-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecc43-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecc43-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc43-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="ecc43-117">See also</span></span>

- [<span data-ttu-id="ecc43-118">Método UnloadClass</span><span class="sxs-lookup"><span data-stu-id="ecc43-118">UnloadClass Method</span></span>](icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="ecc43-119">Interface ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="ecc43-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
