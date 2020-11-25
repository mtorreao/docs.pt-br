---
title: Método INotifyConnection2::UnregisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: 90220c2bfea683ff0472473e180c9e11ea568672
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720029"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="bd6b4-102">Método INotifyConnection2::UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="bd6b4-102">INotifyConnection2::UnregisterNotifySource Method</span></span>

<span data-ttu-id="bd6b4-103">Remove um objeto de origem de notificação especificado da conexão.</span><span class="sxs-lookup"><span data-stu-id="bd6b4-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd6b4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bd6b4-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd6b4-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bd6b4-105">Parameters</span></span>  

 `in_pNotifySource`  
 <span data-ttu-id="bd6b4-106">no Objeto de notificação a ser cancelado.</span><span class="sxs-lookup"><span data-stu-id="bd6b4-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd6b4-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="bd6b4-107">Return Value</span></span>  

 <span data-ttu-id="bd6b4-108">S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="bd6b4-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd6b4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd6b4-109">Requirements</span></span>  

 <span data-ttu-id="bd6b4-110">**Cabeçalho:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="bd6b4-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd6b4-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="bd6b4-111">See also</span></span>

- [<span data-ttu-id="bd6b4-112">Interface INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="bd6b4-112">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="bd6b4-113">Interface INotifySource2</span><span class="sxs-lookup"><span data-stu-id="bd6b4-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="bd6b4-114">Interface INotifySink2</span><span class="sxs-lookup"><span data-stu-id="bd6b4-114">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="bd6b4-115">Método RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="bd6b4-115">RegisterNotifySource Method</span></span>](inotifyconnection2-registernotifysource-method.md)
