---
title: Função CreateAssemblyNameObject
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
ms.openlocfilehash: 995f1064c2f40005c4a19ef034d7edfd668b5d51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704156"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="dcfd3-102">Função CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="dcfd3-102">CreateAssemblyNameObject Function</span></span>

<span data-ttu-id="dcfd3-103">Obtém um ponteiro de interface para uma instância de [IAssemblyName](iassemblyname-interface.md) que representa a identidade exclusiva do assembly com o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="dcfd3-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcfd3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dcfd3-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcfd3-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dcfd3-105">Parameters</span></span>  

 `ppAssemblyNameObj`  
 <span data-ttu-id="dcfd3-106">fora O retornado `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="dcfd3-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="dcfd3-107">no O nome do assembly para o qual criar a nova `IAssemblyName` instância.</span><span class="sxs-lookup"><span data-stu-id="dcfd3-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dcfd3-108">no Sinalizadores a serem passados para o construtor de objeto.</span><span class="sxs-lookup"><span data-stu-id="dcfd3-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="dcfd3-109">no Reservado para extensibilidade futura.</span><span class="sxs-lookup"><span data-stu-id="dcfd3-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="dcfd3-110">`pvReserved` deve ser uma referência nula.</span><span class="sxs-lookup"><span data-stu-id="dcfd3-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcfd3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dcfd3-111">Requirements</span></span>  

 <span data-ttu-id="dcfd3-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcfd3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcfd3-113">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="dcfd3-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dcfd3-114">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dcfd3-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dcfd3-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcfd3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcfd3-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="dcfd3-116">See also</span></span>

- [<span data-ttu-id="dcfd3-117">Interface IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="dcfd3-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="dcfd3-118">Funções estáticas globais de fusão</span><span class="sxs-lookup"><span data-stu-id="dcfd3-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
