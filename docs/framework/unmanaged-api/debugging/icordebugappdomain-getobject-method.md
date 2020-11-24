---
title: Método ICorDebugAppDomain::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
ms.openlocfilehash: a163667ea7eca1ed817d642efdb8fc4efa2a0651
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676056"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="382f5-102">Método ICorDebugAppDomain::GetObject</span><span class="sxs-lookup"><span data-stu-id="382f5-102">ICorDebugAppDomain::GetObject Method</span></span>

<span data-ttu-id="382f5-103">Obtém um ponteiro de interface para o domínio do aplicativo Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="382f5-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="382f5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="382f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="382f5-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="382f5-105">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="382f5-106">fora Um ponteiro para o endereço de um objeto de interface ICorDebugValue que representa o domínio do aplicativo CLR.</span><span class="sxs-lookup"><span data-stu-id="382f5-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="382f5-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="382f5-107">Return Value</span></span>  

 <span data-ttu-id="382f5-108">Se um objeto gerenciado não <xref:System.AppDomain?displayProperty=nameWithType> tiver sido construído para esse domínio de aplicativo, o método retornará `S_FALSE` e colocará `NULL` em `*ppObject` .</span><span class="sxs-lookup"><span data-stu-id="382f5-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="382f5-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="382f5-109">Remarks</span></span>  

 <span data-ttu-id="382f5-110">Cada domínio de aplicativo em um processo pode ter um <xref:System.AppDomain?displayProperty=nameWithType> objeto gerenciado no tempo de execução que o representa.</span><span class="sxs-lookup"><span data-stu-id="382f5-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="382f5-111">Essa função obtém um objeto de interface ICorDebugValue que corresponde a esse <xref:System.AppDomain?displayProperty=nameWithType> objeto gerenciado.</span><span class="sxs-lookup"><span data-stu-id="382f5-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="382f5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="382f5-112">Requirements</span></span>  

 <span data-ttu-id="382f5-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="382f5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="382f5-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="382f5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="382f5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="382f5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="382f5-116">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="382f5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
