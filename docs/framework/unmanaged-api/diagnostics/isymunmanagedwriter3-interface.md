---
title: Interface ISymUnmanagedWriter3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
ms.openlocfilehash: dfc2e39a6a39e7386bd7358d422d5c6978ec42ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683284"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="2250d-102">Interface ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="2250d-102">ISymUnmanagedWriter3 Interface</span></span>

<span data-ttu-id="2250d-103">Representa um gravador de símbolo e fornece métodos para definir documentos, pontos de sequência, escopos lexicais e variáveis.</span><span class="sxs-lookup"><span data-stu-id="2250d-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="2250d-104">Essa interface estende a interface [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2250d-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2250d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2250d-105">Methods</span></span>  
  
|<span data-ttu-id="2250d-106">Método</span><span class="sxs-lookup"><span data-stu-id="2250d-106">Method</span></span>|<span data-ttu-id="2250d-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2250d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2250d-108">Método Commit</span><span class="sxs-lookup"><span data-stu-id="2250d-108">Commit Method</span></span>](isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="2250d-109">Confirma as alterações gravadas até o fluxo.</span><span class="sxs-lookup"><span data-stu-id="2250d-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="2250d-110">Método OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="2250d-110">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="2250d-111">Abre um método e fornece seu deslocamento de seção real na imagem.</span><span class="sxs-lookup"><span data-stu-id="2250d-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2250d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2250d-112">Requirements</span></span>  

 <span data-ttu-id="2250d-113">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2250d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2250d-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="2250d-114">See also</span></span>

- [<span data-ttu-id="2250d-115">Interfaces de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2250d-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="2250d-116">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="2250d-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="2250d-117">Interface ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="2250d-117">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
