---
title: Método ICorDebugProcess::IsTransitionStub
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: 2996c219ccf4e975c45fb531807abc4a608bae73
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694770"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="7b43e-102">Método ICorDebugProcess::IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="7b43e-102">ICorDebugProcess::IsTransitionStub Method</span></span>

<span data-ttu-id="7b43e-103">Obtém um valor que indica se um endereço está dentro de um stub que causará uma transição para o código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="7b43e-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b43e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7b43e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b43e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7b43e-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="7b43e-106">no Um `CORDB_ADDRESS` valor que especifica o endereço em questão.</span><span class="sxs-lookup"><span data-stu-id="7b43e-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="7b43e-107">fora Um ponteiro para um valor booliano que é `true` se o endereço especificado estiver dentro de um stub que causará uma transição para o código gerenciado; caso contrário, \* `pbTransitionStub` será `false` .</span><span class="sxs-lookup"><span data-stu-id="7b43e-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b43e-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="7b43e-108">Remarks</span></span>  

 <span data-ttu-id="7b43e-109">O `IsTransitionStub` método pode ser usado por código de depuração não gerenciado para decidir quando retornar o controle de etapas para o stepper gerenciado.</span><span class="sxs-lookup"><span data-stu-id="7b43e-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="7b43e-110">Você também pode identificar stubs de transição examinando as informações no arquivo executável portátil (PE).</span><span class="sxs-lookup"><span data-stu-id="7b43e-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b43e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b43e-111">Requirements</span></span>  

 <span data-ttu-id="7b43e-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b43e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b43e-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b43e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b43e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b43e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b43e-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b43e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
