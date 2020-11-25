---
title: Método INotifySink2::OnSyncCallEnter
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
ms.openlocfilehash: 57d12a463bc0904e1a5c873d24f843e004b95101
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720003"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="df3e4-102">Método INotifySink2::OnSyncCallEnter</span><span class="sxs-lookup"><span data-stu-id="df3e4-102">INotifySink2::OnSyncCallEnter Method</span></span>

<span data-ttu-id="df3e4-103">É invocado ao inserir uma chamada.</span><span class="sxs-lookup"><span data-stu-id="df3e4-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df3e4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df3e4-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df3e4-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="df3e4-105">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="df3e4-106">no ID da chamada que está sendo inserida.</span><span class="sxs-lookup"><span data-stu-id="df3e4-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="df3e4-107">Consulte [estrutura de CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="df3e4-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="df3e4-108">no Buffer de chamadas.</span><span class="sxs-lookup"><span data-stu-id="df3e4-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="df3e4-109">no Tamanho do buffer de chamada, em bytes.</span><span class="sxs-lookup"><span data-stu-id="df3e4-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df3e4-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="df3e4-110">Return Value</span></span>  

 <span data-ttu-id="df3e4-111">S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="df3e4-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df3e4-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df3e4-112">Requirements</span></span>  

 <span data-ttu-id="df3e4-113">**Cabeçalho:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="df3e4-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3e4-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="df3e4-114">See also</span></span>

- [<span data-ttu-id="df3e4-115">Interface INotifySink2</span><span class="sxs-lookup"><span data-stu-id="df3e4-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="df3e4-116">Interface INotifySource2</span><span class="sxs-lookup"><span data-stu-id="df3e4-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="df3e4-117">Interface INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="df3e4-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
