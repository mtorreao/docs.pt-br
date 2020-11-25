---
title: Método ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: e2c04672e51ffb16043b14735cd5375073194c27
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732613"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="2c383-102">Método ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="2c383-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>

<span data-ttu-id="2c383-103">Fornece informações sobre funções exportadas de runtime para ajudar a percorrer o código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="2c383-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c383-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2c383-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c383-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2c383-105">Parameters</span></span>  

 <span data-ttu-id="2c383-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="2c383-106">pszExportName</span></span>  
 <span data-ttu-id="2c383-107">[in] O nome de uma função de exportação de runtime gravada na tabela de exportação PE.</span><span class="sxs-lookup"><span data-stu-id="2c383-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="2c383-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="2c383-108">invokeKind</span></span>  
 <span data-ttu-id="2c383-109">fora Um ponteiro para um membro da enumeração [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) que descreve como a função exportada invocará o código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="2c383-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="2c383-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="2c383-110">invokePurpose</span></span>  
 <span data-ttu-id="2c383-111">fora Um ponteiro para um membro da enumeração [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) que descreve por que a função exportada chamará o código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="2c383-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c383-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="2c383-112">Return Value</span></span>  

 <span data-ttu-id="2c383-113">O método pode retornar os valores listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="2c383-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="2c383-114">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="2c383-114">Return value</span></span>|<span data-ttu-id="2c383-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="2c383-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="2c383-116">A chamada de método foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="2c383-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="2c383-117">`pInvokeKind` ou `pInvokePurpose` é **nulo**.</span><span class="sxs-lookup"><span data-stu-id="2c383-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="2c383-118">Outros valores `HRESULT` com falha.</span><span class="sxs-lookup"><span data-stu-id="2c383-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="2c383-119">Conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="2c383-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c383-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="2c383-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c383-121">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2c383-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c383-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c383-122">Requirements</span></span>  

 <span data-ttu-id="2c383-123">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c383-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c383-124">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c383-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c383-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c383-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c383-126">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c383-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c383-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c383-127">See also</span></span>

- [<span data-ttu-id="2c383-128">Interface ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="2c383-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="2c383-129">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="2c383-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
