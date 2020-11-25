---
title: Método ICLRRuntimeInfo::SetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: 8020db491c3b66be38a9f6cbcb7551721859dcd5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723110"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="e7e85-102">Método ICLRRuntimeInfo::SetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="e7e85-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>

<span data-ttu-id="e7e85-103">Define os sinalizadores de inicialização e o arquivo de configuração do host que será usado para iniciar o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e7e85-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="e7e85-104">Esse método substitui o uso do `startupFlags` parâmetro nas funções [CorBindToRuntimeEx](corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e7e85-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e85-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e7e85-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7e85-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e7e85-106">Parameters</span></span>  

 `dwStartupFlags`  
 <span data-ttu-id="e7e85-107">no Os sinalizadores de inicialização do host a serem definidos.</span><span class="sxs-lookup"><span data-stu-id="e7e85-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="e7e85-108">Use os mesmos sinalizadores que as funções [CorBindToRuntimeEx](corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e7e85-108">Use the same flags as with the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="e7e85-109">no O caminho do diretório do arquivo de configuração do host a ser definido.</span><span class="sxs-lookup"><span data-stu-id="e7e85-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7e85-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="e7e85-110">Return Value</span></span>  

 <span data-ttu-id="e7e85-111">Esse método retorna o HRESULT específico a seguir, bem como erros HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="e7e85-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e7e85-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7e85-112">HRESULT</span></span>|<span data-ttu-id="e7e85-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="e7e85-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7e85-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7e85-114">S_OK</span></span>|<span data-ttu-id="e7e85-115">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="e7e85-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7e85-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="e7e85-116">Remarks</span></span>  

 <span data-ttu-id="e7e85-117">Um host multi-threaded deve sincronizar chamadas para esse método.</span><span class="sxs-lookup"><span data-stu-id="e7e85-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="e7e85-118">Caso contrário, o thread A pode chamar o `SetStartupFlags` método depois que o thread b concluir uma chamada para `SetStartupFlags` e antes do thread b iniciar o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e7e85-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e85-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7e85-119">Requirements</span></span>  

 <span data-ttu-id="e7e85-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7e85-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e85-121">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="e7e85-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e7e85-122">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7e85-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7e85-123">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e85-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e85-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="e7e85-124">See also</span></span>

- [<span data-ttu-id="e7e85-125">Interface ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="e7e85-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="e7e85-126">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="e7e85-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="e7e85-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="e7e85-127">Hosting</span></span>](index.md)
