---
title: Método ICorDebugManagedCallback3::CustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: f30c9b6746d0e1594994870a96e94eb8105e4c94
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700828"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="0ede3-102">Método ICorDebugManagedCallback3::CustomNotification</span><span class="sxs-lookup"><span data-stu-id="0ede3-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>

<span data-ttu-id="0ede3-103">Indica que uma notificação de depurador personalizada foi gerada.</span><span class="sxs-lookup"><span data-stu-id="0ede3-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ede3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0ede3-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ede3-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0ede3-105">Parameters</span></span>  

 `pThread`  
 <span data-ttu-id="0ede3-106">no Um ponteiro para o thread que gerou a notificação.</span><span class="sxs-lookup"><span data-stu-id="0ede3-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="0ede3-107">no Um ponteiro para o domínio do aplicativo que contém o thread que gerou a notificação.</span><span class="sxs-lookup"><span data-stu-id="0ede3-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ede3-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="0ede3-108">Return Value</span></span>  

 <span data-ttu-id="0ede3-109">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="0ede3-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0ede3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ede3-110">HRESULT</span></span>|<span data-ttu-id="0ede3-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="0ede3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ede3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ede3-112">S_OK</span></span>|<span data-ttu-id="0ede3-113">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="0ede3-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0ede3-114">Exceções</span><span class="sxs-lookup"><span data-stu-id="0ede3-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ede3-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="0ede3-115">Remarks</span></span>  

 <span data-ttu-id="0ede3-116">Uma chamada subsequente para o método [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) recupera o objeto de thread que foi passado para o <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="0ede3-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0ede3-117">O tipo do objeto de thread deve ter sido habilitado anteriormente chamando o método [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0ede3-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="0ede3-118">O depurador pode ler parâmetros específicos de tipo dos campos do objeto de thread e pode armazenar respostas em campos.</span><span class="sxs-lookup"><span data-stu-id="0ede3-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="0ede3-119">A interface [ICorDebug](icordebug-interface.md) impõe nenhuma política sobre os tipos de notificações ou seu conteúdo, e a semântica das notificações é estritamente um contrato entre os depuradores, os aplicativos e a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ede3-119">The [ICorDebug](icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ede3-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ede3-120">Requirements</span></span>  

 <span data-ttu-id="0ede3-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ede3-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ede3-122">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ede3-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ede3-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ede3-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ede3-124">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ede3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ede3-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="0ede3-125">See also</span></span>

- [<span data-ttu-id="0ede3-126">Interface ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="0ede3-126">ICorDebugManagedCallback3 Interface</span></span>](icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="0ede3-127">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="0ede3-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0ede3-128">Depuração</span><span class="sxs-lookup"><span data-stu-id="0ede3-128">Debugging</span></span>](index.md)
