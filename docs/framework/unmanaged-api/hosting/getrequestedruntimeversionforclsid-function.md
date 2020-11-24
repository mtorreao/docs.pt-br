---
title: Função GetRequestedRuntimeVersionForCLSID
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
ms.openlocfilehash: 3afb89a42d7e26c5e89e6f9458ef3406cc0102ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684181"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="34410-102">Função GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="34410-102">GetRequestedRuntimeVersionForCLSID Function</span></span>

<span data-ttu-id="34410-103">Obtém as informações de versão do Common Language Runtime (CLR) apropriadas para a classe com o especificado `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="34410-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="34410-104">Essa função foi preterida no .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="34410-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34410-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="34410-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34410-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="34410-106">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="34410-107">no  O `CLSID` do componente.</span><span class="sxs-lookup"><span data-stu-id="34410-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="34410-108">fora  Um buffer que contém a cadeia de caracteres de número de versão após a conclusão bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="34410-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="34410-109">no  O tamanho, em caracteres largos, do `pVersion` buffer.</span><span class="sxs-lookup"><span data-stu-id="34410-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="34410-110">fora O comprimento, em bytes, do buffer retornado.</span><span class="sxs-lookup"><span data-stu-id="34410-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="34410-111">no  Um dos valores de CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="34410-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="34410-112">Os seguintes valores têm suporte:</span><span class="sxs-lookup"><span data-stu-id="34410-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="34410-113">CLSID_RESOLUTION_DEFAULT: (0x0) especifica que o comportamento de interoperabilidade padrão deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="34410-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="34410-114">CLSID_RESOLUTION_REGISTERED: (0x1) especifica que o registro deve ser pesquisado e que a política de Shim deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="34410-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34410-115">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="34410-115">Return Value</span></span>  
  
|<span data-ttu-id="34410-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34410-116">HRESULT</span></span>|<span data-ttu-id="34410-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="34410-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34410-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="34410-118">S_OK</span></span>|<span data-ttu-id="34410-119">A função retornou com êxito.</span><span class="sxs-lookup"><span data-stu-id="34410-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="34410-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="34410-120">E_INVALIDARG</span></span>|<span data-ttu-id="34410-121">Um dos parâmetros tem um tipo ou formato inválido.</span><span class="sxs-lookup"><span data-stu-id="34410-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="34410-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="34410-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="34410-123">O `pVersion` buffer não é grande o suficiente para manter a cadeia de caracteres da versão inteira.</span><span class="sxs-lookup"><span data-stu-id="34410-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="34410-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="34410-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="34410-125">Não há nenhuma classe registrada com o especificado `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="34410-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="34410-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="34410-126">E_POINTER</span></span>|<span data-ttu-id="34410-127">`dwLength` é nulo ou `cchBuffer` é grande o suficiente para conter a cadeia de caracteres de versão, mas `pVersion` é nulo.</span><span class="sxs-lookup"><span data-stu-id="34410-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34410-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34410-128">Requirements</span></span>  

 <span data-ttu-id="34410-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34410-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34410-130">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="34410-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34410-131">**.NET Framework versões:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34410-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34410-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="34410-132">See also</span></span>

- [<span data-ttu-id="34410-133">Funções de hospedagem CLR reprovadas</span><span class="sxs-lookup"><span data-stu-id="34410-133">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
