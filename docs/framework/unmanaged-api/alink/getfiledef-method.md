---
title: Método GetFileDef
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
ms.openlocfilehash: 42935813579d7f1d55a9f1daf9d8c6c1241f85be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684701"
---
# <a name="getfiledef-method"></a><span data-ttu-id="d9cfb-102">Método GetFileDef</span><span class="sxs-lookup"><span data-stu-id="d9cfb-102">GetFileDef Method</span></span>

<span data-ttu-id="d9cfb-103">Recupera o token FileDef real usado nos metadados (em oposição ao token atribuído pelo ALink).</span><span class="sxs-lookup"><span data-stu-id="d9cfb-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9cfb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d9cfb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9cfb-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d9cfb-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="d9cfb-106">ID do assembly.</span><span class="sxs-lookup"><span data-stu-id="d9cfb-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="d9cfb-107">Token do arquivo adicionado como recuperado do método AddFile ou do método AddImport.</span><span class="sxs-lookup"><span data-stu-id="d9cfb-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="d9cfb-108">Recebe o token FileDef.</span><span class="sxs-lookup"><span data-stu-id="d9cfb-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9cfb-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="d9cfb-109">Return Value</span></span>  

 <span data-ttu-id="d9cfb-110">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="d9cfb-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9cfb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9cfb-111">Requirements</span></span>  

 <span data-ttu-id="d9cfb-112">Requer ALink. h</span><span class="sxs-lookup"><span data-stu-id="d9cfb-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9cfb-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="d9cfb-113">See also</span></span>

- [<span data-ttu-id="d9cfb-114">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="d9cfb-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d9cfb-115">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="d9cfb-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d9cfb-116">API do ALink</span><span class="sxs-lookup"><span data-stu-id="d9cfb-116">ALink API</span></span>](index.md)
