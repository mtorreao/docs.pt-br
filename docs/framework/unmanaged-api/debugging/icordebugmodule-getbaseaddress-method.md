---
title: Método ICorDebugModule::GetBaseAddress
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
ms.openlocfilehash: 4562318c87b79fba5f3d99860ee438c0144e9aae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710240"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="3c7ee-102">Método ICorDebugModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="3c7ee-102">ICorDebugModule::GetBaseAddress Method</span></span>

<span data-ttu-id="3c7ee-103">Obtém o endereço base do módulo.</span><span class="sxs-lookup"><span data-stu-id="3c7ee-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c7ee-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3c7ee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c7ee-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3c7ee-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="3c7ee-106">fora Um `CORDB_ADDRESS` que especifica o endereço base do módulo.</span><span class="sxs-lookup"><span data-stu-id="3c7ee-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c7ee-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="3c7ee-107">Remarks</span></span>  

 <span data-ttu-id="3c7ee-108">Se o módulo for uma imagem nativa (ou seja, se o módulo foi produzido pelo gerador de imagem nativa, NGen.exe), seu endereço base será zero.</span><span class="sxs-lookup"><span data-stu-id="3c7ee-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c7ee-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c7ee-109">Requirements</span></span>  

 <span data-ttu-id="3c7ee-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c7ee-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c7ee-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c7ee-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c7ee-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c7ee-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c7ee-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c7ee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7ee-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="3c7ee-114">See also</span></span>
