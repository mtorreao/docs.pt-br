---
title: Interface ISymUnmanagedBinder3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: 0cb0b91f2dca8203c37599400b3b61f84eb7d282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727309"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="6021f-102">Interface ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="6021f-102">ISymUnmanagedBinder3 Interface</span></span>

<span data-ttu-id="6021f-103">Estende a interface do fichário de símbolos.</span><span class="sxs-lookup"><span data-stu-id="6021f-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="6021f-104">Obtenha essa interface chamando `QueryInterface` um objeto que implementa a `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="6021f-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6021f-105">É um risco de segurança abrir um arquivo de banco de dados do programa (PDB) de uma fonte não confiável.</span><span class="sxs-lookup"><span data-stu-id="6021f-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6021f-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="6021f-106">Methods</span></span>  
  
|<span data-ttu-id="6021f-107">Método</span><span class="sxs-lookup"><span data-stu-id="6021f-107">Method</span></span>|<span data-ttu-id="6021f-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="6021f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6021f-109">Método GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="6021f-109">GetReaderFromCallback Method</span></span>](isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="6021f-110">Permite que o usuário implemente ou forneça por meio de um retorno de chamada `IID_IDiaReadExeAtRVACallback` ou `IID_IDiaReadExeAtOffsetCallback` para obter as informações do diretório de depuração da memória</span><span class="sxs-lookup"><span data-stu-id="6021f-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6021f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6021f-111">Requirements</span></span>  

 <span data-ttu-id="6021f-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6021f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6021f-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="6021f-113">See also</span></span>

- [<span data-ttu-id="6021f-114">Interfaces de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="6021f-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="6021f-115">Interface ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="6021f-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="6021f-116">Interface ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="6021f-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
