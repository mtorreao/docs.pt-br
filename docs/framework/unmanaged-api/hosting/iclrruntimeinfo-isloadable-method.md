---
title: Método ICLRRuntimeInfo::IsLoadable
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
ms.openlocfilehash: 2236e815211168d8e7105375b75f30128f7f209a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714959"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="1d28b-102">Método ICLRRuntimeInfo::IsLoadable</span><span class="sxs-lookup"><span data-stu-id="1d28b-102">ICLRRuntimeInfo::IsLoadable Method</span></span>

<span data-ttu-id="1d28b-103">Indica se o tempo de execução associado a essa interface pode ser carregado no processo atual, levando em conta outros tempos de execução que já podem estar carregados no processo.</span><span class="sxs-lookup"><span data-stu-id="1d28b-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d28b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1d28b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d28b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1d28b-105">Parameters</span></span>  

 `pbLoadable`  
 <span data-ttu-id="1d28b-106">[fora] `true` Se esse tempo de execução puder ser carregado no processo atual; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="1d28b-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d28b-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="1d28b-107">Return Value</span></span>  

 <span data-ttu-id="1d28b-108">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="1d28b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1d28b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d28b-109">HRESULT</span></span>|<span data-ttu-id="1d28b-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d28b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d28b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d28b-111">S_OK</span></span>|<span data-ttu-id="1d28b-112">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="1d28b-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="1d28b-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1d28b-113">E_POINTER</span></span>|<span data-ttu-id="1d28b-114">`pbLoadable` é nulo.</span><span class="sxs-lookup"><span data-stu-id="1d28b-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d28b-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="1d28b-115">Remarks</span></span>  

 <span data-ttu-id="1d28b-116">Se outro tempo de execução já estiver carregado no processo e o tempo de execução associado a essa interface puder ser carregado para execução lado a lado no processo, `pbLoadable` retorna `true` .</span><span class="sxs-lookup"><span data-stu-id="1d28b-116">If another runtime is already loaded into the process, and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="1d28b-117">Se os dois tempos de execução não puderem ser executados lado a lado no processo, o `pbLoadable` retornará `false` .</span><span class="sxs-lookup"><span data-stu-id="1d28b-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="1d28b-118">Por exemplo, o Common Language Runtime (CLR) versão 4 pode ser executado lado a lado no mesmo processo com o CLR versão 2,0 ou CLR versão 1,1.</span><span class="sxs-lookup"><span data-stu-id="1d28b-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="1d28b-119">No entanto, o CLR versão 1,1 e a versão 2,0 do CLR não podem ser executados lado a lado no processo.</span><span class="sxs-lookup"><span data-stu-id="1d28b-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="1d28b-120">Se nenhum tempo de execução for carregado no processo, esse método sempre retornará `true` .</span><span class="sxs-lookup"><span data-stu-id="1d28b-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d28b-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d28b-121">Requirements</span></span>  

 <span data-ttu-id="1d28b-122">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d28b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d28b-123">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="1d28b-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1d28b-124">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d28b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d28b-125">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d28b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d28b-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="1d28b-126">See also</span></span>

- [<span data-ttu-id="1d28b-127">Interface ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="1d28b-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="1d28b-128">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="1d28b-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="1d28b-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="1d28b-129">Hosting</span></span>](index.md)
