---
title: Função CallFunctionShim
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
ms.openlocfilehash: f72c987294d7768eacf112c622ab15494fb75e34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685780"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="90cad-102">Função CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="90cad-102">CallFunctionShim Function</span></span>

<span data-ttu-id="90cad-103">Faz uma chamada para a função que tem o nome e os parâmetros especificados na biblioteca especificada.</span><span class="sxs-lookup"><span data-stu-id="90cad-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="90cad-104">Essa função foi preterida no .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="90cad-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90cad-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="90cad-105">Syntax</span></span>  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90cad-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="90cad-106">Parameters</span></span>  

 `szDllName`  
 <span data-ttu-id="90cad-107">no O nome da biblioteca que contém a função.</span><span class="sxs-lookup"><span data-stu-id="90cad-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="90cad-108">no O nome da função.</span><span class="sxs-lookup"><span data-stu-id="90cad-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="90cad-109">no O primeiro argumento a ser passado para a função.</span><span class="sxs-lookup"><span data-stu-id="90cad-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="90cad-110">no O segundo argumento a ser passado para a função.</span><span class="sxs-lookup"><span data-stu-id="90cad-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="90cad-111">no A versão da biblioteca que contém a função.</span><span class="sxs-lookup"><span data-stu-id="90cad-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="90cad-112">no Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="90cad-112">[in] Reserved for future use.</span></span> <span data-ttu-id="90cad-113">Passe zero neste parâmetro.</span><span class="sxs-lookup"><span data-stu-id="90cad-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90cad-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90cad-114">Requirements</span></span>  

 <span data-ttu-id="90cad-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90cad-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90cad-116">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="90cad-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90cad-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="90cad-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90cad-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90cad-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90cad-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="90cad-119">See also</span></span>

- [<span data-ttu-id="90cad-120">Funções de hospedagem CLR reprovadas</span><span class="sxs-lookup"><span data-stu-id="90cad-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
