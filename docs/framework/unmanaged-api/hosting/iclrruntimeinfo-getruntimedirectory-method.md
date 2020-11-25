---
title: Método ICLRRuntimeInfo::GetRuntimeDirectory
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
ms.openlocfilehash: 24679118e4255282f7da3ff8be2ce9c08250e181
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732041"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="2df1f-102">Método ICLRRuntimeInfo::GetRuntimeDirectory</span><span class="sxs-lookup"><span data-stu-id="2df1f-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>

<span data-ttu-id="2df1f-103">Obtém o diretório de instalação do Common Language Runtime (CLR) associado a essa interface.</span><span class="sxs-lookup"><span data-stu-id="2df1f-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="2df1f-104">Esse método substitui a função [GetCORSystemDirectory](getcorsystemdirectory-function.md) fornecida no .NET Framework versões 2,0, 3,0 e 3,5.</span><span class="sxs-lookup"><span data-stu-id="2df1f-104">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df1f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2df1f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2df1f-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2df1f-106">Parameters</span></span>  

 `pwzBuffer`  
 <span data-ttu-id="2df1f-107">fora Retorna o diretório de instalação do CLR.</span><span class="sxs-lookup"><span data-stu-id="2df1f-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="2df1f-108">O caminho de instalação é totalmente qualificado; por exemplo, "c:\Windows\Microsoft.NET\Framework\v1.0.3705 \\ ".</span><span class="sxs-lookup"><span data-stu-id="2df1f-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="2df1f-109">[entrada, saída] Especifica o tamanho de `pwzBuffer` para evitar estouros de buffer.</span><span class="sxs-lookup"><span data-stu-id="2df1f-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="2df1f-110">Se `pwzBuffer` for NULL, `pchBuffer` retornará o tamanho necessário de `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="2df1f-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2df1f-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="2df1f-111">Return Value</span></span>  

 <span data-ttu-id="2df1f-112">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="2df1f-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2df1f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2df1f-113">HRESULT</span></span>|<span data-ttu-id="2df1f-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="2df1f-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2df1f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="2df1f-115">S_OK</span></span>|<span data-ttu-id="2df1f-116">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="2df1f-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="2df1f-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="2df1f-117">E_POINTER</span></span>|<span data-ttu-id="2df1f-118">`pwzBuffer` ou `pchBuffer` é nulo.</span><span class="sxs-lookup"><span data-stu-id="2df1f-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2df1f-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="2df1f-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2df1f-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2df1f-120">Requirements</span></span>  

 <span data-ttu-id="2df1f-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2df1f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2df1f-122">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="2df1f-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2df1f-123">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2df1f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2df1f-124">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2df1f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df1f-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="2df1f-125">See also</span></span>

- [<span data-ttu-id="2df1f-126">Interface ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="2df1f-126">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="2df1f-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="2df1f-127">Hosting</span></span>](index.md)
