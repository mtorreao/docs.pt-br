---
title: Método ICorProfilerCallback::RemotingClientReceivingReply
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
ms.openlocfilehash: 058c66af85da6c902e3d628e1b1479bb88c4fa85
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704845"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="a3ab4-102">Método ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="a3ab4-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>

<span data-ttu-id="a3ab4-103">Notifica o criador de perfil de que a parte do lado do servidor de uma chamada de comunicação remota foi concluída e que o cliente agora está recebendo e prestes a processar a resposta.</span><span class="sxs-lookup"><span data-stu-id="a3ab4-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3ab4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a3ab4-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="a3ab4-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a3ab4-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="a3ab4-106">no Um valor que corresponderá com o valor fornecido em [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) sob estas condições:</span><span class="sxs-lookup"><span data-stu-id="a3ab4-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="a3ab4-107">Os cookies de GUID de comunicação remota estão ativos.</span><span class="sxs-lookup"><span data-stu-id="a3ab4-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="a3ab4-108">O canal tem sucesso ao transmitir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="a3ab4-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="a3ab4-109">Os cookies de GUID estão ativos no processo do lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="a3ab4-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="a3ab4-110">Isso permite um emparelhamento fácil de chamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="a3ab4-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="a3ab4-111">no Um valor que é `true` se a chamada for assíncrona; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="a3ab4-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3ab4-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3ab4-112">Requirements</span></span>  

 <span data-ttu-id="a3ab4-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3ab4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3ab4-114">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="a3ab4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3ab4-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3ab4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3ab4-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3ab4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ab4-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="a3ab4-117">See also</span></span>

- [<span data-ttu-id="a3ab4-118">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a3ab4-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
