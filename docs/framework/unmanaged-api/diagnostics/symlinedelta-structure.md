---
title: Estrutura SYMLINEDELTA
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: dd45703540f8dc41b746ca03b4f09d74186aa9aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690935"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="ab1c3-102">Estrutura SYMLINEDELTA</span><span class="sxs-lookup"><span data-stu-id="ab1c3-102">SYMLINEDELTA Structure</span></span>

<span data-ttu-id="ab1c3-103">Fornece informações para o manipulador de símbolos sobre métodos que foram movidos como resultado de edições.</span><span class="sxs-lookup"><span data-stu-id="ab1c3-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1c3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ab1c3-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="ab1c3-105">Membros</span><span class="sxs-lookup"><span data-stu-id="ab1c3-105">Members</span></span>  
  
|<span data-ttu-id="ab1c3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ab1c3-106">Member</span></span>|<span data-ttu-id="ab1c3-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="ab1c3-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="ab1c3-108">O token de metadados do método.</span><span class="sxs-lookup"><span data-stu-id="ab1c3-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="ab1c3-109">O número de linhas que o método foi movido.</span><span class="sxs-lookup"><span data-stu-id="ab1c3-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab1c3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab1c3-110">Requirements</span></span>  

 <span data-ttu-id="ab1c3-111">**Cabeçalho:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="ab1c3-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab1c3-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="ab1c3-112">See also</span></span>

- [<span data-ttu-id="ab1c3-113">Estruturas de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ab1c3-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
