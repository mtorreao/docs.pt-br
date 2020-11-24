---
title: Método LinkResource
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
ms.openlocfilehash: 4f2f13976dfd4e5601bf8b54bed7b851884fbb9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690441"
---
# <a name="linkresource-method"></a><span data-ttu-id="f0173-102">Método LinkResource</span><span class="sxs-lookup"><span data-stu-id="f0173-102">LinkResource Method</span></span>

<span data-ttu-id="f0173-103">Links em um recurso.</span><span class="sxs-lookup"><span data-stu-id="f0173-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0173-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f0173-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0173-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f0173-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="f0173-106">ID do assembly.</span><span class="sxs-lookup"><span data-stu-id="f0173-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="f0173-107">Nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="f0173-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="f0173-108">Novo nome de arquivo opcional.</span><span class="sxs-lookup"><span data-stu-id="f0173-108">Optional new file name.</span></span> <span data-ttu-id="f0173-109">Se não for NULL, `pszFileName` será copiado para pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="f0173-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="f0173-110">Nome do recurso.</span><span class="sxs-lookup"><span data-stu-id="f0173-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f0173-111">Sinalizadores de acessibilidade, como `mrPublic` e `mrPrivate` .</span><span class="sxs-lookup"><span data-stu-id="f0173-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="f0173-112">Esse parâmetro pode ser passado para o [método DefineManifestResource](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="f0173-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0173-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="f0173-113">Return Value</span></span>  

 <span data-ttu-id="f0173-114">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="f0173-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0173-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0173-115">Requirements</span></span>  

 <span data-ttu-id="f0173-116">Requer ALink. h.</span><span class="sxs-lookup"><span data-stu-id="f0173-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0173-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="f0173-117">See also</span></span>

- [<span data-ttu-id="f0173-118">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="f0173-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f0173-119">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="f0173-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f0173-120">API do ALink</span><span class="sxs-lookup"><span data-stu-id="f0173-120">ALink API</span></span>](index.md)
