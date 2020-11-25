---
title: Enumeração CorSymVarFlag
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
ms.openlocfilehash: ed08d9f818f6fc180dbd655243488bf8a527ae11
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725281"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="c7e50-102">Enumeração CorSymVarFlag</span><span class="sxs-lookup"><span data-stu-id="c7e50-102">CorSymVarFlag Enumeration</span></span>

<span data-ttu-id="c7e50-103">Indica se uma variável é gerada pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="c7e50-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7e50-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c7e50-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="c7e50-105">Membros</span><span class="sxs-lookup"><span data-stu-id="c7e50-105">Members</span></span>  
  
|<span data-ttu-id="c7e50-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c7e50-106">Member</span></span>|<span data-ttu-id="c7e50-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c7e50-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="c7e50-108">Indica que a variável fornecida é gerada pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="c7e50-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7e50-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c7e50-109">Requirements</span></span>  

 <span data-ttu-id="c7e50-110">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c7e50-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e50-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="c7e50-111">See also</span></span>

- [<span data-ttu-id="c7e50-112">Enumerações de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c7e50-112">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
