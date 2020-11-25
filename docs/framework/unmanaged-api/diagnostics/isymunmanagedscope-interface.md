---
title: Interface ISymUnmanagedScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 9256342ad3a91e6770d6fd19d9d2f94fab267d3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725879"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="8d4fe-102">Interface ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="8d4fe-102">ISymUnmanagedScope Interface</span></span>

<span data-ttu-id="8d4fe-103">Representa um escopo léxico dentro de um método.</span><span class="sxs-lookup"><span data-stu-id="8d4fe-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d4fe-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8d4fe-104">Methods</span></span>  
  
|<span data-ttu-id="8d4fe-105">Método</span><span class="sxs-lookup"><span data-stu-id="8d4fe-105">Method</span></span>|<span data-ttu-id="8d4fe-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8d4fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d4fe-107">Método GetChildren</span><span class="sxs-lookup"><span data-stu-id="8d4fe-107">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="8d4fe-108">Obtém os filhos deste escopo.</span><span class="sxs-lookup"><span data-stu-id="8d4fe-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="8d4fe-109">Método GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="8d4fe-109">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="8d4fe-110">Obtém o deslocamento de fim deste escopo.</span><span class="sxs-lookup"><span data-stu-id="8d4fe-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="8d4fe-111">Método GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="8d4fe-111">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="8d4fe-112">Obtém uma contagem das variáveis locais definidas neste escopo.</span><span class="sxs-lookup"><span data-stu-id="8d4fe-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="8d4fe-113">Método GetLocals</span><span class="sxs-lookup"><span data-stu-id="8d4fe-113">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="8d4fe-114">Obtém as variáveis locais definidas nesse escopo.</span><span class="sxs-lookup"><span data-stu-id="8d4fe-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="8d4fe-115">Método GetMethod</span><span class="sxs-lookup"><span data-stu-id="8d4fe-115">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="8d4fe-116">Obtém o método que contém esse escopo.</span><span class="sxs-lookup"><span data-stu-id="8d4fe-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="8d4fe-117">Método GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="8d4fe-117">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="8d4fe-118">Obtém os namespaces que estão sendo usados nesse escopo.</span><span class="sxs-lookup"><span data-stu-id="8d4fe-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="8d4fe-119">Método GetParent</span><span class="sxs-lookup"><span data-stu-id="8d4fe-119">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="8d4fe-120">Obtém o escopo pai deste escopo.</span><span class="sxs-lookup"><span data-stu-id="8d4fe-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="8d4fe-121">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="8d4fe-121">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="8d4fe-122">Obtém o deslocamento inicial para este escopo.</span><span class="sxs-lookup"><span data-stu-id="8d4fe-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d4fe-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d4fe-123">Requirements</span></span>  

 <span data-ttu-id="8d4fe-124">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8d4fe-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d4fe-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="8d4fe-125">See also</span></span>

- [<span data-ttu-id="8d4fe-126">Interfaces de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="8d4fe-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="8d4fe-127">Interface ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="8d4fe-127">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
