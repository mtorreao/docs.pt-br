---
title: Função CorExitProcess
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: f6d8114732a3b7c15d0a0258a28a362d661b030a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673614"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="d9512-102">Função CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="d9512-102">CorExitProcess Function</span></span>

<span data-ttu-id="d9512-103">Desliga o processo atual não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="d9512-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="d9512-104">Essa função foi preterida no .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d9512-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="d9512-105">Em vez disso, use o método [ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d9512-105">Use the [ICLRMetaHost::ExitProcess](iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9512-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d9512-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9512-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d9512-107">Parameters</span></span>  

 `exitCode`  
 <span data-ttu-id="d9512-108">Um inteiro que especifica o código de saída do processo.</span><span class="sxs-lookup"><span data-stu-id="d9512-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9512-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="d9512-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9512-110">Começando com o .NET Framework 4, `CorExitProcess` sai de cada tempo de execução iniciado no processo, não apenas o tempo de execução ao qual as APIs herdadas foram associadas.</span><span class="sxs-lookup"><span data-stu-id="d9512-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9512-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9512-111">Requirements</span></span>  

 <span data-ttu-id="d9512-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9512-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9512-113">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d9512-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9512-114">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9512-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9512-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9512-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9512-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="d9512-116">See also</span></span>

- [<span data-ttu-id="d9512-117">Funções de hospedagem CLR reprovadas</span><span class="sxs-lookup"><span data-stu-id="d9512-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
