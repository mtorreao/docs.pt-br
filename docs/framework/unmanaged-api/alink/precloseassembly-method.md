---
title: Método PreCloseAssembly
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
ms.openlocfilehash: 31c0c5e23d1a985c2005693e25ca91379037482a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728674"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="529aa-102">Método PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="529aa-102">PreCloseAssembly Method</span></span>

<span data-ttu-id="529aa-103">Fecha o arquivo do assembly.</span><span class="sxs-lookup"><span data-stu-id="529aa-103">Closes the assembly file.</span></span> <span data-ttu-id="529aa-104">Chame esse método depois de fechar todos os outros arquivos, mas antes de fechar o arquivo do assembly.</span><span class="sxs-lookup"><span data-stu-id="529aa-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="529aa-105">Não chame esse método para módulos não associados.</span><span class="sxs-lookup"><span data-stu-id="529aa-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="529aa-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="529aa-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="529aa-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="529aa-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="529aa-108">ID do assembly.</span><span class="sxs-lookup"><span data-stu-id="529aa-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="529aa-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="529aa-109">Return Value</span></span>  

 <span data-ttu-id="529aa-110">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="529aa-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="529aa-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="529aa-111">Requirements</span></span>  

 <span data-ttu-id="529aa-112">Requer ALink. h.</span><span class="sxs-lookup"><span data-stu-id="529aa-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="529aa-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="529aa-113">See also</span></span>

- [<span data-ttu-id="529aa-114">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="529aa-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="529aa-115">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="529aa-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="529aa-116">API do ALink</span><span class="sxs-lookup"><span data-stu-id="529aa-116">ALink API</span></span>](index.md)
