---
title: Método EmitManifest
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
ms.openlocfilehash: b1c005e58f18b03a7da5f3836f719b95c41bca95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684935"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="6ddab-102">Método EmitManifest</span><span class="sxs-lookup"><span data-stu-id="6ddab-102">EmitManifest Method</span></span>

<span data-ttu-id="6ddab-103">Emite o manifesto final.</span><span class="sxs-lookup"><span data-stu-id="6ddab-103">Emits the final manifest.</span></span> <span data-ttu-id="6ddab-104">Chame esse método depois de importar todos os outros arquivos e definir todas as opções.</span><span class="sxs-lookup"><span data-stu-id="6ddab-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="6ddab-105">Não chame esse método para módulos não associados.</span><span class="sxs-lookup"><span data-stu-id="6ddab-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ddab-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6ddab-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ddab-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6ddab-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="6ddab-108">ID do assembly.</span><span class="sxs-lookup"><span data-stu-id="6ddab-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="6ddab-109">Recebe o tamanho a ser reservado no arquivo de assembly, recuperado da [função StrongNameSignatureSize](../strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="6ddab-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="6ddab-110">Opcionalmente, recebe o token do manifesto do assembly.</span><span class="sxs-lookup"><span data-stu-id="6ddab-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ddab-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="6ddab-111">Return Value</span></span>  

 <span data-ttu-id="6ddab-112">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="6ddab-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ddab-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ddab-113">Requirements</span></span>  

 <span data-ttu-id="6ddab-114">Requer ALink. h.</span><span class="sxs-lookup"><span data-stu-id="6ddab-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ddab-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="6ddab-115">See also</span></span>

- [<span data-ttu-id="6ddab-116">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="6ddab-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6ddab-117">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="6ddab-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6ddab-118">API do ALink</span><span class="sxs-lookup"><span data-stu-id="6ddab-118">ALink API</span></span>](index.md)
