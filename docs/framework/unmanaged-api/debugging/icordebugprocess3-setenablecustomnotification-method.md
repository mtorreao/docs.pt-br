---
title: Método ICorDebugProcess3::SetEnableCustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
ms.openlocfilehash: 078e5cb03848564b42e30a079101d5a61e0074bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734017"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="44447-102">Método ICorDebugProcess3::SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="44447-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>

<span data-ttu-id="44447-103">Habilita e desabilita as notificações do depurador personalizado do tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="44447-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44447-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="44447-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44447-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="44447-105">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="44447-106">no O tipo que especifica as notificações de depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="44447-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="44447-107">[in] `true` para habilitar notificações personalizadas do depurador; `false` para desabilitar as notificações.</span><span class="sxs-lookup"><span data-stu-id="44447-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="44447-108">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="44447-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44447-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="44447-109">Remarks</span></span>  

 <span data-ttu-id="44447-110">Quando `fEnable` é definido como `true` , as chamadas para o <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> método disparam um retorno de chamada [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="44447-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="44447-111">As notificações são desabilitadas por padrão; Portanto, o depurador deve especificar os tipos de notificação que ele conhece e deseja manipular.</span><span class="sxs-lookup"><span data-stu-id="44447-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="44447-112">Como a classe [ICorDebugClass](icordebug-interface.md) tem o escopo definido pelo domínio do aplicativo, o depurador deve chamar `SetEnableCustomNotification` cada domínio do aplicativo no processo se desejar receber a notificação em todo o processo.</span><span class="sxs-lookup"><span data-stu-id="44447-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="44447-113">Começando com o .NET Framework 4, a única notificação com suporte é uma notificação de dependência entre threads.</span><span class="sxs-lookup"><span data-stu-id="44447-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44447-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44447-114">Requirements</span></span>  

 <span data-ttu-id="44447-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44447-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44447-116">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44447-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44447-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44447-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44447-118">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44447-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44447-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="44447-119">See also</span></span>

- [<span data-ttu-id="44447-120">Interface ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="44447-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="44447-121">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="44447-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="44447-122">Depuração</span><span class="sxs-lookup"><span data-stu-id="44447-122">Debugging</span></span>](index.md)
