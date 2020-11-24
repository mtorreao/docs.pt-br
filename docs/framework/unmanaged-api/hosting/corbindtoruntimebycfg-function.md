---
title: Função CorBindToRuntimeByCfg
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: d319382b577844a804c3e4562676491a15de5f63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673768"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="0c842-102">Função CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="0c842-102">CorBindToRuntimeByCfg Function</span></span>

<span data-ttu-id="0c842-103">Carrega o Common Language Runtime (CLR) em um processo usando informações de versão lidas de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="0c842-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="0c842-104">Essa função foi preterida no .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0c842-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c842-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0c842-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c842-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0c842-106">Parameters</span></span>  

 `pCfgStream`  
 <span data-ttu-id="0c842-107">no Um ponteiro para um `IStream` objeto que lê o arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="0c842-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="0c842-108">no Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="0c842-108">[in] Reserved for future use.</span></span> <span data-ttu-id="0c842-109">Use 0 (zero) como valor.</span><span class="sxs-lookup"><span data-stu-id="0c842-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="0c842-110">no Um valor da enumeração de [STARTUP_FLAGS](startup-flags-enumeration.md) que especifica o comportamento de inicialização do CLR.</span><span class="sxs-lookup"><span data-stu-id="0c842-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="0c842-111">no O `CLSID` da coclass que implementa a interface [ICorRuntimeHost](icorruntimehost-interface.md) ou [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0c842-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="0c842-112">Os valores com suporte são CLSID_CorRuntimeHost ou CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="0c842-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="0c842-113">no O `IID` de ou a `ICorRuntimeHost` `ICLRRuntimeHost` interface.</span><span class="sxs-lookup"><span data-stu-id="0c842-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="0c842-114">Os valores com suporte são IID_ICorRuntimeHost ou IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="0c842-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="0c842-115">fora Um ponteiro para o endereço da interface retornada.</span><span class="sxs-lookup"><span data-stu-id="0c842-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c842-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="0c842-116">Remarks</span></span>  

 <span data-ttu-id="0c842-117">O formato do arquivo XML é modelado após o arquivo de configuração de aplicativo padrão.</span><span class="sxs-lookup"><span data-stu-id="0c842-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="0c842-118">Para obter mais informações sobre arquivos XML, consulte [esquema do arquivo de configuração](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c842-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c842-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c842-119">Requirements</span></span>  

 <span data-ttu-id="0c842-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c842-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c842-121">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0c842-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c842-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c842-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c842-123">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c842-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c842-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="0c842-124">See also</span></span>

- [<span data-ttu-id="0c842-125">Função CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="0c842-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="0c842-126">Função CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="0c842-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="0c842-127">Função CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="0c842-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="0c842-128">Função CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0c842-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="0c842-129">Interface ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0c842-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="0c842-130">Funções de hospedagem CLR reprovadas</span><span class="sxs-lookup"><span data-stu-id="0c842-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
