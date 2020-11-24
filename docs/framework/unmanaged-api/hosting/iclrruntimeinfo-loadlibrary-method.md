---
title: Método ICLRRuntimeInfo::LoadLibrary
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: aa45c814568188a5fe93e3acd2514cb54bb0f984
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688608"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="df435-102">Método ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="df435-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>

<span data-ttu-id="df435-103">Carrega uma biblioteca de .NET Framework do Common Language Runtime (CLR) representado por uma interface [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="df435-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="df435-104">Esse método substitui a função [LoadLibraryShim](loadlibraryshim-function.md) .</span><span class="sxs-lookup"><span data-stu-id="df435-104">This method supersedes the [LoadLibraryShim](loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df435-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df435-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df435-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="df435-106">Parameters</span></span>  

 `pwzDllName`  
 <span data-ttu-id="df435-107">no O nome do assembly a ser carregado.</span><span class="sxs-lookup"><span data-stu-id="df435-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="df435-108">fora Um identificador para o assembly carregado.</span><span class="sxs-lookup"><span data-stu-id="df435-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df435-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="df435-109">Return Value</span></span>  

 <span data-ttu-id="df435-110">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="df435-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="df435-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df435-111">HRESULT</span></span>|<span data-ttu-id="df435-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="df435-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df435-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="df435-113">S_OK</span></span>|<span data-ttu-id="df435-114">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="df435-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="df435-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="df435-115">E_POINTER</span></span>|<span data-ttu-id="df435-116">`pwzDllName` ou `phndModule` é nulo.</span><span class="sxs-lookup"><span data-stu-id="df435-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="df435-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="df435-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="df435-118">Não há memória suficiente disponível para lidar com a solicitação.</span><span class="sxs-lookup"><span data-stu-id="df435-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df435-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="df435-119">Remarks</span></span>  

 <span data-ttu-id="df435-120">Esse método carrega somente DLLs incluídas no pacote redistribuível .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="df435-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="df435-121">Ele não pode carregar assemblies gerados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="df435-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df435-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df435-122">Requirements</span></span>  

 <span data-ttu-id="df435-123">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df435-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df435-124">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="df435-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="df435-125">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df435-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df435-126">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df435-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df435-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="df435-127">See also</span></span>

- [<span data-ttu-id="df435-128">Interface ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="df435-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="df435-129">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="df435-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="df435-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="df435-130">Hosting</span></span>](index.md)
