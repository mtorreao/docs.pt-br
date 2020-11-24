---
title: Método EmitAssembly
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
ms.openlocfilehash: b85b2576660f77eb901c504d398e8bc7909882f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676368"
---
# <a name="emitassembly-method"></a><span data-ttu-id="afe63-102">Método EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="afe63-102">EmitAssembly Method</span></span>

<span data-ttu-id="afe63-103">Cria o assembly.</span><span class="sxs-lookup"><span data-stu-id="afe63-103">Creates the assembly.</span></span> <span data-ttu-id="afe63-104">Chame esse método depois que todos os outros arquivos forem fechados, exceto o arquivo do assembly.</span><span class="sxs-lookup"><span data-stu-id="afe63-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="afe63-105">Não chame esse método ao produzir módulos desvinculados.</span><span class="sxs-lookup"><span data-stu-id="afe63-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afe63-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="afe63-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="afe63-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="afe63-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="afe63-108">ID do assembly.</span><span class="sxs-lookup"><span data-stu-id="afe63-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afe63-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="afe63-109">Return Value</span></span>  

 <span data-ttu-id="afe63-110">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="afe63-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afe63-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="afe63-111">Requirements</span></span>  

 <span data-ttu-id="afe63-112">Requer ALink. h</span><span class="sxs-lookup"><span data-stu-id="afe63-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe63-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="afe63-113">See also</span></span>

- [<span data-ttu-id="afe63-114">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="afe63-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="afe63-115">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="afe63-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="afe63-116">API do ALink</span><span class="sxs-lookup"><span data-stu-id="afe63-116">ALink API</span></span>](index.md)
