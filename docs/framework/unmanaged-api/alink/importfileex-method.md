---
title: Método ImportFileEx
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
ms.openlocfilehash: 9e373f133830a5bc1f3cf7bdc8034cb67725d797
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705196"
---
# <a name="importfileex-method"></a><span data-ttu-id="99674-102">Método ImportFileEx</span><span class="sxs-lookup"><span data-stu-id="99674-102">ImportFileEx Method</span></span>

<span data-ttu-id="99674-103">Importações indicadas módulo de assembly ou não associado.</span><span class="sxs-lookup"><span data-stu-id="99674-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99674-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="99674-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="99674-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="99674-105">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="99674-106">Nome totalmente qualificado do arquivo do qual importar.</span><span class="sxs-lookup"><span data-stu-id="99674-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="99674-107">Nome opcional do arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="99674-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="99674-108">Se for TRUE, os irporttypes serão usados; caso contrário, a importação deverá ser executada manualmente.</span><span class="sxs-lookup"><span data-stu-id="99674-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="99674-109">Sinalizadores a serem passados para o [método OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="99674-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="99674-110">Recebe a ID do arquivo que está sendo importado.</span><span class="sxs-lookup"><span data-stu-id="99674-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="99674-111">Recebe interface de [interface IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de escopo de importação de assembly.</span><span class="sxs-lookup"><span data-stu-id="99674-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="99674-112">Será definido como NULL se o arquivo não for um assembly.</span><span class="sxs-lookup"><span data-stu-id="99674-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="99674-113">Recebe a contagem de escopos e/ou arquivos importados.</span><span class="sxs-lookup"><span data-stu-id="99674-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99674-114">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="99674-114">Return Value</span></span>  

 <span data-ttu-id="99674-115">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="99674-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99674-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99674-116">Requirements</span></span>  

 <span data-ttu-id="99674-117">Requer ALink. h.</span><span class="sxs-lookup"><span data-stu-id="99674-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99674-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="99674-118">See also</span></span>

- [<span data-ttu-id="99674-119">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="99674-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="99674-120">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="99674-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="99674-121">API do ALink</span><span class="sxs-lookup"><span data-stu-id="99674-121">ALink API</span></span>](index.md)
