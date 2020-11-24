---
title: Função CreateApplicationContext
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
ms.openlocfilehash: 9418be85f5b72bac8eed7f5ea4af4fc42439b01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683219"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="8a642-102">Função CreateApplicationContext</span><span class="sxs-lookup"><span data-stu-id="8a642-102">CreateApplicationContext Function</span></span>

<span data-ttu-id="8a642-103">Essa função dá suporte à infraestrutura de .NET Framework e não se destina a ser usada diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="8a642-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a642-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8a642-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a642-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8a642-105">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="8a642-106">no Um ponteiro para um nome amigável.</span><span class="sxs-lookup"><span data-stu-id="8a642-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="8a642-107">fora Um ponteiro para um contexto de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8a642-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a642-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a642-108">Requirements</span></span>  

 <span data-ttu-id="8a642-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a642-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a642-110">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8a642-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8a642-111">**Biblioteca:** Incluído como um recurso no Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="8a642-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="8a642-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a642-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a642-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="8a642-113">See also</span></span>

- [<span data-ttu-id="8a642-114">Interface IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="8a642-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="8a642-115">Funções estáticas globais de fusão</span><span class="sxs-lookup"><span data-stu-id="8a642-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="8a642-116">Cache de assemblies global</span><span class="sxs-lookup"><span data-stu-id="8a642-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)
