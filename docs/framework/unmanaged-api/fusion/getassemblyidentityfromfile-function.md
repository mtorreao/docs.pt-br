---
title: Função GetAssemblyIdentityFromFile
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 9580dd3bc5a7279549e8deadac95d35a33da74f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724475"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="bcfed-102">Função GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="bcfed-102">GetAssemblyIdentityFromFile Function</span></span>

<span data-ttu-id="bcfed-103">Obtém um ponteiro para um `IUnknown` objeto com o especificado `IID` no assembly no caminho do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="bcfed-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfed-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bcfed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcfed-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bcfed-105">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="bcfed-106">no Um caminho válido para o assembly solicitado.</span><span class="sxs-lookup"><span data-stu-id="bcfed-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="bcfed-107">no O `IID` da interface a ser retornada.</span><span class="sxs-lookup"><span data-stu-id="bcfed-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="bcfed-108">fora O ponteiro de interface retornado.</span><span class="sxs-lookup"><span data-stu-id="bcfed-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcfed-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bcfed-109">Requirements</span></span>  

 <span data-ttu-id="bcfed-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcfed-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcfed-111">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="bcfed-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bcfed-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcfed-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfed-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="bcfed-113">See also</span></span>

- [<span data-ttu-id="bcfed-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="bcfed-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="bcfed-115">Funções estáticas globais de fusão</span><span class="sxs-lookup"><span data-stu-id="bcfed-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
