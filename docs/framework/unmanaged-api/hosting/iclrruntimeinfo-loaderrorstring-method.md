---
title: Método ICLRRuntimeInfo::LoadErrorString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
ms.openlocfilehash: 0e029aa848a6630ae00c834dd2b924dc4ebce537
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671766"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="a23b7-102">Método ICLRRuntimeInfo::LoadErrorString</span><span class="sxs-lookup"><span data-stu-id="a23b7-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>

<span data-ttu-id="a23b7-103">Traduz um valor HRESULT em uma mensagem de erro apropriada para a cultura especificada.</span><span class="sxs-lookup"><span data-stu-id="a23b7-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="a23b7-104">Esse método substitui as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="a23b7-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="a23b7-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="a23b7-105">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="a23b7-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="a23b7-106">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="a23b7-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a23b7-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a23b7-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a23b7-108">Parameters</span></span>  

 `iResourceID`  
 <span data-ttu-id="a23b7-109">no O HRESULT a ser traduzido.</span><span class="sxs-lookup"><span data-stu-id="a23b7-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="a23b7-110">fora A cadeia de caracteres da mensagem associada ao HRESULT fornecido.</span><span class="sxs-lookup"><span data-stu-id="a23b7-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="a23b7-111">[entrada, saída] O tamanho de `pwzbuffer` para evitar estouros de buffer.</span><span class="sxs-lookup"><span data-stu-id="a23b7-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="a23b7-112">Se `pwzbuffer` for NULL, `pcchBuffer` fornecerá o tamanho esperado de `pwzbuffer` para permitir a prealocação.</span><span class="sxs-lookup"><span data-stu-id="a23b7-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="a23b7-113">no O identificador de cultura.</span><span class="sxs-lookup"><span data-stu-id="a23b7-113">[in] The culture identifier.</span></span> <span data-ttu-id="a23b7-114">Para usar a cultura padrão, você deve especificar-1.</span><span class="sxs-lookup"><span data-stu-id="a23b7-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a23b7-115">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="a23b7-115">Return Value</span></span>  

 <span data-ttu-id="a23b7-116">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="a23b7-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a23b7-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a23b7-117">HRESULT</span></span>|<span data-ttu-id="a23b7-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="a23b7-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a23b7-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a23b7-119">S_OK</span></span>|<span data-ttu-id="a23b7-120">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="a23b7-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="a23b7-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a23b7-121">E_POINTER</span></span>|<span data-ttu-id="a23b7-122">`pcchBuffer` é nulo.</span><span class="sxs-lookup"><span data-stu-id="a23b7-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="a23b7-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a23b7-123">E_INVALIDARG</span></span>|<span data-ttu-id="a23b7-124">`pwzBuffer` é nulo.</span><span class="sxs-lookup"><span data-stu-id="a23b7-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a23b7-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a23b7-125">Requirements</span></span>  

 <span data-ttu-id="a23b7-126">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a23b7-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a23b7-127">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="a23b7-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a23b7-128">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a23b7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a23b7-129">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a23b7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a23b7-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="a23b7-130">See also</span></span>

- [<span data-ttu-id="a23b7-131">Interface ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="a23b7-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="a23b7-132">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="a23b7-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a23b7-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="a23b7-133">Hosting</span></span>](index.md)
