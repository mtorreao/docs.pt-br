---
title: Método SetAssemblyFile
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 45eed17b91f70d4188d1d89fc91a41455f3e845b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732639"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="02929-102">Método SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="02929-102">SetAssemblyFile Method</span></span>

<span data-ttu-id="02929-103">Atribui o nome do assembly a ser compilado.</span><span class="sxs-lookup"><span data-stu-id="02929-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="02929-104">Não para uso na produção de módulos não associados.</span><span class="sxs-lookup"><span data-stu-id="02929-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02929-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="02929-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="02929-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="02929-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="02929-107">Nome totalmente qualificado do arquivo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="02929-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="02929-108">Ponteiro para interface de [interface IMetaDataEmit](../metadata/imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="02929-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="02929-109">Sinalizadores, conforme definido na [Enumeração AssemblyFlags](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="02929-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="02929-110">Ponteiro para a ID do assembly resultante.</span><span class="sxs-lookup"><span data-stu-id="02929-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02929-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="02929-111">Return Value</span></span>  

 <span data-ttu-id="02929-112">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="02929-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02929-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02929-113">Requirements</span></span>  

 <span data-ttu-id="02929-114">Requer ALink. h.</span><span class="sxs-lookup"><span data-stu-id="02929-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02929-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="02929-115">See also</span></span>

- [<span data-ttu-id="02929-116">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="02929-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="02929-117">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="02929-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="02929-118">API do ALink</span><span class="sxs-lookup"><span data-stu-id="02929-118">ALink API</span></span>](index.md)
