---
title: Interface ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: c2b57897e4f0e8b23337302f344065d79677e0c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725801"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="afb9a-102">Interface ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="afb9a-102">ISymUnmanagedWriter4 Interface</span></span>

<span data-ttu-id="afb9a-103">Interface ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="afb9a-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb9a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="afb9a-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="afb9a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="afb9a-105">Methods</span></span>  

 <span data-ttu-id="afb9a-106">Essa interface contém os seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="afb9a-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="afb9a-107">Método</span><span class="sxs-lookup"><span data-stu-id="afb9a-107">Method</span></span>|<span data-ttu-id="afb9a-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="afb9a-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="afb9a-109">Método GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="afb9a-109">GetDebugInfoWithPadding Method</span></span>](isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="afb9a-110">O funciona da mesma forma que o [método GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , exceto pelo fato de que a cadeia de caracteres de caminho é preenchida com zeros após o caractere nulo de terminação para tornar os dados da cadeia de caracteres um tamanho fixo `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="afb9a-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="afb9a-111">O preenchimento só será fornecido se o comprimento da cadeia de caracteres do caminho for menor que `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="afb9a-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="afb9a-112">Isso facilita a gravação de ferramentas que diferenciam arquivos PE.</span><span class="sxs-lookup"><span data-stu-id="afb9a-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="afb9a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="afb9a-113">Requirements</span></span>  

 <span data-ttu-id="afb9a-114">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="afb9a-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb9a-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="afb9a-115">See also</span></span>

- [<span data-ttu-id="afb9a-116">Interfaces de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="afb9a-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="afb9a-117">Interface ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="afb9a-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
