---
title: Método ICLRMetaHost::ExitProcess
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: 6d601ac3ece801353b630c74ed852c2657f25d7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730455"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="5d10a-102">Método ICLRMetaHost::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="5d10a-102">ICLRMetaHost::ExitProcess Method</span></span>

<span data-ttu-id="5d10a-103">Tenta desligar todos os tempos de execução carregados normalmente e, em seguida, encerra o processo.</span><span class="sxs-lookup"><span data-stu-id="5d10a-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="5d10a-104">Substitui a função [CorExitProcess](corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="5d10a-104">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d10a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5d10a-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d10a-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5d10a-106">Parameters</span></span>  

 `iExitCode`  
 <span data-ttu-id="5d10a-107">no O código de saída do processo.</span><span class="sxs-lookup"><span data-stu-id="5d10a-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d10a-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="5d10a-108">Return Value</span></span>  

 <span data-ttu-id="5d10a-109">Esse método nunca retorna, portanto, seu valor de retorno é indefinido.</span><span class="sxs-lookup"><span data-stu-id="5d10a-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d10a-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="5d10a-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d10a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d10a-111">Requirements</span></span>  

 <span data-ttu-id="5d10a-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d10a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d10a-113">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="5d10a-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5d10a-114">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d10a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d10a-115">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d10a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d10a-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="5d10a-116">See also</span></span>

- [<span data-ttu-id="5d10a-117">Interface ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="5d10a-117">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="5d10a-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="5d10a-118">Hosting</span></span>](index.md)
