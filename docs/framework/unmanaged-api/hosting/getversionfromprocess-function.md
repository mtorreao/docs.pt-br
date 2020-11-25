---
title: Função GetVersionFromProcess
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: da0d159da6eef7745c1fa7f7320d5e1355f6e413
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721875"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="54fab-102">Função GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="54fab-102">GetVersionFromProcess Function</span></span>

<span data-ttu-id="54fab-103">Obtém o número de versão do Common Language Runtime (CLR) associado ao identificador de processo especificado.</span><span class="sxs-lookup"><span data-stu-id="54fab-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="54fab-104">Essa função foi preterida no .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="54fab-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54fab-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="54fab-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54fab-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="54fab-106">Parameters</span></span>  

 `hProcess`  
 <span data-ttu-id="54fab-107">no Um identificador para um processo.</span><span class="sxs-lookup"><span data-stu-id="54fab-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="54fab-108">fora Um buffer que contém a cadeia de caracteres de número de versão após a conclusão bem-sucedida do método.</span><span class="sxs-lookup"><span data-stu-id="54fab-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="54fab-109">no O comprimento do buffer de versão.</span><span class="sxs-lookup"><span data-stu-id="54fab-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="54fab-110">fora Um ponteiro para o comprimento da cadeia de caracteres do número de versão.</span><span class="sxs-lookup"><span data-stu-id="54fab-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54fab-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="54fab-111">Return Value</span></span>  

 <span data-ttu-id="54fab-112">Esse método retorna códigos de erro padrão de Component Object Model (COM), conforme definido no WinError. h, além dos valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="54fab-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="54fab-113">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="54fab-113">Return code</span></span>|<span data-ttu-id="54fab-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="54fab-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="54fab-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="54fab-115">S_OK</span></span>|<span data-ttu-id="54fab-116">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="54fab-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="54fab-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="54fab-117">E_INVALIDARG</span></span>|<span data-ttu-id="54fab-118">`pVersion` é NULL e `cchBuffer` não é nulo, ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="54fab-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="54fab-119">- ou -</span><span class="sxs-lookup"><span data-stu-id="54fab-119">-or-</span></span><br /><br /> <span data-ttu-id="54fab-120">`hProcess` Não é um identificador válido para um processo.</span><span class="sxs-lookup"><span data-stu-id="54fab-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="54fab-121">- ou -</span><span class="sxs-lookup"><span data-stu-id="54fab-121">-or-</span></span><br /><br /> <span data-ttu-id="54fab-122">O CLR não está carregado.</span><span class="sxs-lookup"><span data-stu-id="54fab-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="54fab-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="54fab-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="54fab-124">`cchBuffer` é nulo ou menor que o comprimento da cadeia de caracteres da versão.</span><span class="sxs-lookup"><span data-stu-id="54fab-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="54fab-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="54fab-125">E_NOTIMPL</span></span>|<span data-ttu-id="54fab-126">Esse método não está disponível no sistema operacional Microsoft Windows 95, Microsoft Windows 98 ou Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="54fab-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54fab-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54fab-127">Requirements</span></span>  

 <span data-ttu-id="54fab-128">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54fab-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54fab-129">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="54fab-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54fab-130">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54fab-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54fab-131">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54fab-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54fab-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="54fab-132">See also</span></span>

- [<span data-ttu-id="54fab-133">Função GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="54fab-133">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="54fab-134">Função GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="54fab-134">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)
- [<span data-ttu-id="54fab-135">Funções de hospedagem CLR reprovadas</span><span class="sxs-lookup"><span data-stu-id="54fab-135">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
