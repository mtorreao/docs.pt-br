---
title: Método ICorDebugModule::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
ms.openlocfilehash: c2aecadf8688e763a69bd40ca877e44bc0ce5c29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710020"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="59ef2-102">Método ICorDebugModule::GetName</span><span class="sxs-lookup"><span data-stu-id="59ef2-102">ICorDebugModule::GetName Method</span></span>

<span data-ttu-id="59ef2-103">Obtém o nome do arquivo do módulo.</span><span class="sxs-lookup"><span data-stu-id="59ef2-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59ef2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="59ef2-104">Syntax</span></span>  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59ef2-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="59ef2-105">Parameters</span></span>  

 `cchname`  
 <span data-ttu-id="59ef2-106">no O tamanho da `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="59ef2-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="59ef2-107">no Um ponteiro para o comprimento do nome retornado.</span><span class="sxs-lookup"><span data-stu-id="59ef2-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="59ef2-108">fora Uma matriz que armazena o nome retornado.</span><span class="sxs-lookup"><span data-stu-id="59ef2-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59ef2-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="59ef2-109">Remarks</span></span>  

 <span data-ttu-id="59ef2-110">O `GetName` método retornará um S_OK HRESULT se o nome do arquivo do módulo corresponder ao nome no disco.</span><span class="sxs-lookup"><span data-stu-id="59ef2-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="59ef2-111">`GetName` Retorna um S_FALSE HRESULT se o nome for criei, como para um módulo dinâmico ou na memória.</span><span class="sxs-lookup"><span data-stu-id="59ef2-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59ef2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59ef2-112">Requirements</span></span>  

 <span data-ttu-id="59ef2-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59ef2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59ef2-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59ef2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59ef2-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59ef2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59ef2-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59ef2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ef2-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="59ef2-117">See also</span></span>
