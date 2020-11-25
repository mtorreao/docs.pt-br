---
title: Método ImportFile
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
ms.openlocfilehash: f30307884a268008fd4d1a8de31ec5a49b6ab92d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705235"
---
# <a name="importfile-method"></a><span data-ttu-id="060ab-102">Método ImportFile</span><span class="sxs-lookup"><span data-stu-id="060ab-102">ImportFile Method</span></span>

<span data-ttu-id="060ab-103">Importa assemblies e módulos desvinculados.</span><span class="sxs-lookup"><span data-stu-id="060ab-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="060ab-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="060ab-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="060ab-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="060ab-105">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="060ab-106">Nome totalmente qualificado do arquivo a ser importado.</span><span class="sxs-lookup"><span data-stu-id="060ab-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="060ab-107">Nome de arquivo de saída opcional que pode ser usado para renomear o arquivo, pois ele está vinculado ao assembly.</span><span class="sxs-lookup"><span data-stu-id="060ab-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="060ab-108">Se for TRUE, os irporttypes serão usados; caso contrário, a importação deverá ser executada manualmente.</span><span class="sxs-lookup"><span data-stu-id="060ab-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="060ab-109">Ponteiro para o token em que uma ID de arquivo exclusiva será armazenada.</span><span class="sxs-lookup"><span data-stu-id="060ab-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="060ab-110">O arquivo pode ser um assembly ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="060ab-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="060ab-111">Recebe o ponteiro para a [interface IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="060ab-111">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="060ab-112">Poderá ser NULL se o arquivo não for um assembly.</span><span class="sxs-lookup"><span data-stu-id="060ab-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="060ab-113">Ponteiro para a contagem de arquivos e/ou escopos que foram importados.</span><span class="sxs-lookup"><span data-stu-id="060ab-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="060ab-114">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="060ab-114">Return Value</span></span>  

 <span data-ttu-id="060ab-115">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="060ab-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="060ab-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="060ab-116">Requirements</span></span>  

 <span data-ttu-id="060ab-117">Requer ALink. h</span><span class="sxs-lookup"><span data-stu-id="060ab-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="060ab-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="060ab-118">See also</span></span>

- [<span data-ttu-id="060ab-119">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="060ab-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="060ab-120">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="060ab-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="060ab-121">API do ALink</span><span class="sxs-lookup"><span data-stu-id="060ab-121">ALink API</span></span>](index.md)
