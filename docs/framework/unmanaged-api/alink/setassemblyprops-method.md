---
title: Método SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
ms.openlocfilehash: 4b0de5f9759491f1303edc978b1548e91214daf8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733744"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="49e79-102">Método SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="49e79-102">SetAssemblyProps Method</span></span>

<span data-ttu-id="49e79-103">Atribui propriedades no nível do assembly.</span><span class="sxs-lookup"><span data-stu-id="49e79-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49e79-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="49e79-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="49e79-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="49e79-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="49e79-106">ID do assembly.</span><span class="sxs-lookup"><span data-stu-id="49e79-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="49e79-107">Arquivo que define a propriedade.</span><span class="sxs-lookup"><span data-stu-id="49e79-107">File that defines the property.</span></span> <span data-ttu-id="49e79-108">Pode ser NULL se não `AssemblyID` indicar um netmodule não associado.</span><span class="sxs-lookup"><span data-stu-id="49e79-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="49e79-109">Indica a opção a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="49e79-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="49e79-110">Novo valor da opção.</span><span class="sxs-lookup"><span data-stu-id="49e79-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49e79-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="49e79-111">Return Value</span></span>  

 <span data-ttu-id="49e79-112">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="49e79-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49e79-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49e79-113">Requirements</span></span>  

 <span data-ttu-id="49e79-114">Requer ALink. h.</span><span class="sxs-lookup"><span data-stu-id="49e79-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e79-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="49e79-115">See also</span></span>

- [<span data-ttu-id="49e79-116">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="49e79-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="49e79-117">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="49e79-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="49e79-118">API do ALink</span><span class="sxs-lookup"><span data-stu-id="49e79-118">ALink API</span></span>](index.md)
