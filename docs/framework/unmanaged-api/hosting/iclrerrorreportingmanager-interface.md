---
title: Interface ICLRErrorReportingManager
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
ms.openlocfilehash: d3816c8a3b6204b053505aa888eb28d696f8990b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677831"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="c8d32-102">Interface ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="c8d32-102">ICLRErrorReportingManager Interface</span></span>

<span data-ttu-id="c8d32-103">Fornece métodos que permitem ao host configurar despejos de pilha personalizados para o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="c8d32-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8d32-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c8d32-104">Methods</span></span>  
  
|<span data-ttu-id="c8d32-105">Método</span><span class="sxs-lookup"><span data-stu-id="c8d32-105">Method</span></span>|<span data-ttu-id="c8d32-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c8d32-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8d32-107">Método BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="c8d32-107">BeginCustomDump Method</span></span>](iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="c8d32-108">Especifica a configuração de despejos de pilha personalizados para o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="c8d32-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="c8d32-109">Método EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="c8d32-109">EndCustomDump Method</span></span>](iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="c8d32-110">Limpa a configuração de despejo de pilha personalizado que foi definida por uma chamada anterior para `BeginCustomDump` .</span><span class="sxs-lookup"><span data-stu-id="c8d32-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="c8d32-111">Método GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="c8d32-111">GetBucketParametersForCurrentException Method</span></span>](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="c8d32-112">Obtém o Bucket do Watson para a exceção atual no thread de chamada.</span><span class="sxs-lookup"><span data-stu-id="c8d32-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8d32-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="c8d32-113">Remarks</span></span>  

 <span data-ttu-id="c8d32-114">O `BeginCustomDump` método define a configuração de despejo de pilha personalizado.</span><span class="sxs-lookup"><span data-stu-id="c8d32-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="c8d32-115">O `EndCustomDump` método limpa a configuração de despejo de pilha personalizada e libera qualquer estado associado.</span><span class="sxs-lookup"><span data-stu-id="c8d32-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="c8d32-116">Ele deve ser chamado após a conclusão do despejo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c8d32-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c8d32-117">Falha ao chamar `EndCustomDump` faz com que a memória seja vazada.</span><span class="sxs-lookup"><span data-stu-id="c8d32-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8d32-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8d32-118">Requirements</span></span>  

 <span data-ttu-id="c8d32-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8d32-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8d32-120">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c8d32-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8d32-121">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8d32-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8d32-122">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8d32-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d32-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="c8d32-123">See also</span></span>

- [<span data-ttu-id="c8d32-124">Enumeração ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="c8d32-124">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="c8d32-125">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="c8d32-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
