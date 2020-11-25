---
title: Método ICorProfilerCallback::RemotingServerSendingReply
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
ms.openlocfilehash: 1d876644ae35d13a481b01d9e0e5ff0d0764ca18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713945"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="b0cf7-102">Método ICorProfilerCallback::RemotingServerSendingReply</span><span class="sxs-lookup"><span data-stu-id="b0cf7-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>

<span data-ttu-id="b0cf7-103">Notifica o criador de perfil de que o processo concluiu o processamento de uma solicitação de invocação de método remoto e está prestes a transmitir a resposta por meio de um canal.</span><span class="sxs-lookup"><span data-stu-id="b0cf7-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0cf7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b0cf7-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0cf7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b0cf7-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="b0cf7-106">no Um ponteiro para um GUID que corresponderá com o valor fornecido em [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) sob estas condições:</span><span class="sxs-lookup"><span data-stu-id="b0cf7-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="b0cf7-107">Os cookies de GUID de comunicação remota estão ativos.</span><span class="sxs-lookup"><span data-stu-id="b0cf7-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="b0cf7-108">O canal tem sucesso ao transmitir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="b0cf7-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="b0cf7-109">Os cookies de GUID estão ativos no processo do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="b0cf7-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="b0cf7-110">Isso permite um emparelhamento fácil de chamadas remotas e a criação de uma pilha de chamadas lógica.</span><span class="sxs-lookup"><span data-stu-id="b0cf7-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="b0cf7-111">no Um valor que é `true` se a chamada for assíncrona; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="b0cf7-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0cf7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0cf7-112">Requirements</span></span>  

 <span data-ttu-id="b0cf7-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0cf7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0cf7-114">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="b0cf7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b0cf7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0cf7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0cf7-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0cf7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0cf7-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="b0cf7-117">See also</span></span>

- [<span data-ttu-id="b0cf7-118">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b0cf7-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
