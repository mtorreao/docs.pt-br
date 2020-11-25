---
title: Interface ISymUnmanagedSourceServerModule
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
ms.openlocfilehash: 5e438c75a29984e9200dc240f389f079a4eecfd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733948"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="2445e-102">Interface ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="2445e-102">ISymUnmanagedSourceServerModule Interface</span></span>

<span data-ttu-id="2445e-103">Fornece dados do servidor de origem para um módulo.</span><span class="sxs-lookup"><span data-stu-id="2445e-103">Provides source server data for a module.</span></span> <span data-ttu-id="2445e-104">Obtenha essa interface chamando `QueryInterface` em um objeto que implementa a interface [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2445e-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2445e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2445e-105">Methods</span></span>  
  
|<span data-ttu-id="2445e-106">Método</span><span class="sxs-lookup"><span data-stu-id="2445e-106">Method</span></span>|<span data-ttu-id="2445e-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2445e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2445e-108">Método GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="2445e-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="2445e-109">Retorna os dados do servidor de origem para o módulo.</span><span class="sxs-lookup"><span data-stu-id="2445e-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2445e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2445e-110">Requirements</span></span>  

 <span data-ttu-id="2445e-111">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2445e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2445e-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="2445e-112">See also</span></span>

- [<span data-ttu-id="2445e-113">Interfaces de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2445e-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
