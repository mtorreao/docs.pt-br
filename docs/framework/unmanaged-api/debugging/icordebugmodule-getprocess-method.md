---
title: Método ICorDebugModule::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
ms.openlocfilehash: 8f4b9e73e0d716561dd64bc0df702d835e0eee06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709954"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="c58dd-102">Método ICorDebugModule::GetProcess</span><span class="sxs-lookup"><span data-stu-id="c58dd-102">ICorDebugModule::GetProcess Method</span></span>

<span data-ttu-id="c58dd-103">Obtém o processo de contenção deste módulo.</span><span class="sxs-lookup"><span data-stu-id="c58dd-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c58dd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c58dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c58dd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c58dd-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="c58dd-106">fora Um ponteiro para o endereço de um objeto ICorDebugProcess que representa o processo que contém este módulo.</span><span class="sxs-lookup"><span data-stu-id="c58dd-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c58dd-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c58dd-107">Requirements</span></span>  

 <span data-ttu-id="c58dd-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c58dd-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c58dd-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c58dd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c58dd-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c58dd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c58dd-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c58dd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
