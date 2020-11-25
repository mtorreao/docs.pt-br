---
title: ICorDebugILCode2::Método GetLocalVarSigToken
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
ms.openlocfilehash: 33533c9e3bfbe78abeddb5ed591f741219826127
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728626"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="bc9bd-102">ICorDebugILCode2::Método GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="bc9bd-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>

<span data-ttu-id="bc9bd-103">[Com suporte no .NET Framework 4.5.2 e versões posteriores]</span><span class="sxs-lookup"><span data-stu-id="bc9bd-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="bc9bd-104">Obtém o token de metadados para a assinatura de variável local para a função que é representada por esta instância.</span><span class="sxs-lookup"><span data-stu-id="bc9bd-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc9bd-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bc9bd-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc9bd-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bc9bd-106">Parameters</span></span>  

 `pmdSig`  
 <span data-ttu-id="bc9bd-107">[out] Um ponteiro para o token `mdSignature` para a assinatura de variável local desta função ou `mdSignatureNil` se não houver uma assinatura (isto é, se a função não tiver variáveis locais).</span><span class="sxs-lookup"><span data-stu-id="bc9bd-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc9bd-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="bc9bd-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc9bd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc9bd-109">Requirements</span></span>  

 <span data-ttu-id="bc9bd-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc9bd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc9bd-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc9bd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc9bd-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc9bd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc9bd-113">**.NET Framework versões:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc9bd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9bd-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="bc9bd-114">See also</span></span>

- [<span data-ttu-id="bc9bd-115">Interface ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="bc9bd-115">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="bc9bd-116">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="bc9bd-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
