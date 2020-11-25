---
title: Método ICLRRuntimeInfo::GetProcAddress
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: 028cfd51a713d8598598566a5b1edcf3fc70ecfc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732054"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="30cf0-102">Método ICLRRuntimeInfo::GetProcAddress</span><span class="sxs-lookup"><span data-stu-id="30cf0-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>

<span data-ttu-id="30cf0-103">Obtém o endereço de uma função especificada que foi exportada do Common Language Runtime (CLR) associado a esta interface.</span><span class="sxs-lookup"><span data-stu-id="30cf0-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="30cf0-104">Esse método substitui a função [GetRealProcAddress](getrealprocaddress-function.md) .</span><span class="sxs-lookup"><span data-stu-id="30cf0-104">This method supersedes the [GetRealProcAddress](getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30cf0-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="30cf0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30cf0-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="30cf0-106">Parameters</span></span>  

 `pszProcName`  
 <span data-ttu-id="30cf0-107">no O nome da função exportada.</span><span class="sxs-lookup"><span data-stu-id="30cf0-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="30cf0-108">fora O endereço da função exportada.</span><span class="sxs-lookup"><span data-stu-id="30cf0-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30cf0-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="30cf0-109">Return Value</span></span>  

 <span data-ttu-id="30cf0-110">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="30cf0-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="30cf0-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30cf0-111">HRESULT</span></span>|<span data-ttu-id="30cf0-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="30cf0-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30cf0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="30cf0-113">S_OK</span></span>|<span data-ttu-id="30cf0-114">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="30cf0-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="30cf0-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="30cf0-115">E_POINTER</span></span>|<span data-ttu-id="30cf0-116">`pszProcName` ou `ppProc` é nulo.</span><span class="sxs-lookup"><span data-stu-id="30cf0-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="30cf0-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="30cf0-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="30cf0-118">A função especificada não é uma função exportada.</span><span class="sxs-lookup"><span data-stu-id="30cf0-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30cf0-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="30cf0-119">Remarks</span></span>  

 <span data-ttu-id="30cf0-120">Esse método faz com que o CLR seja carregado, mas não inicializado.</span><span class="sxs-lookup"><span data-stu-id="30cf0-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30cf0-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30cf0-121">Requirements</span></span>  

 <span data-ttu-id="30cf0-122">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30cf0-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30cf0-123">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="30cf0-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="30cf0-124">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30cf0-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30cf0-125">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30cf0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30cf0-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="30cf0-126">See also</span></span>

- [<span data-ttu-id="30cf0-127">Interface ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="30cf0-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="30cf0-128">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="30cf0-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="30cf0-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="30cf0-129">Hosting</span></span>](index.md)
