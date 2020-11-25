---
title: Método ImportTypes2
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
ms.openlocfilehash: 2ec7708edd86b9f2656d0eee434992c3b73200ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705040"
---
# <a name="importtypes2-method"></a><span data-ttu-id="c1ac3-102">Método ImportTypes2</span><span class="sxs-lookup"><span data-stu-id="c1ac3-102">ImportTypes2 Method</span></span>

<span data-ttu-id="c1ac3-103">Inicia a importação de tipos.</span><span class="sxs-lookup"><span data-stu-id="c1ac3-103">Initiates the import of types.</span></span> <span data-ttu-id="c1ac3-104">Chame esse método para começar a importar tipos de cada escopo importado por meio do [Método ImportFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="c1ac3-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ac3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c1ac3-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1ac3-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c1ac3-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="c1ac3-107">ID do assembly no qual importar.</span><span class="sxs-lookup"><span data-stu-id="c1ac3-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="c1ac3-108">ID do arquivo a partir do qual importar.</span><span class="sxs-lookup"><span data-stu-id="c1ac3-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="c1ac3-109">Escopo de base zero do qual importar.</span><span class="sxs-lookup"><span data-stu-id="c1ac3-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="c1ac3-110">Recebe o identificador do enumerador para os tipos no escopo fornecido.</span><span class="sxs-lookup"><span data-stu-id="c1ac3-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="c1ac3-111">Opcionalmente, recebe a interface de [interface IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c1ac3-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="c1ac3-112">Opcionalmente, recebe a contagem de tipos no escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="c1ac3-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1ac3-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="c1ac3-113">Return Value</span></span>  

 <span data-ttu-id="c1ac3-114">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="c1ac3-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ac3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1ac3-115">Requirements</span></span>  

 <span data-ttu-id="c1ac3-116">Requer ALink. h</span><span class="sxs-lookup"><span data-stu-id="c1ac3-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ac3-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="c1ac3-117">See also</span></span>

- [<span data-ttu-id="c1ac3-118">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="c1ac3-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c1ac3-119">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="c1ac3-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c1ac3-120">API do ALink</span><span class="sxs-lookup"><span data-stu-id="c1ac3-120">ALink API</span></span>](index.md)
