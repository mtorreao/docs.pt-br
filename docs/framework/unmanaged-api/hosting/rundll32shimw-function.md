---
title: Função RunDll32ShimW
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
ms.openlocfilehash: dd053134792b80a006849e465bc0025cf77a9ad8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729948"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="cc041-102">Função RunDll32ShimW</span><span class="sxs-lookup"><span data-stu-id="cc041-102">RunDll32ShimW Function</span></span>

<span data-ttu-id="cc041-103">Executa o comando especificado.</span><span class="sxs-lookup"><span data-stu-id="cc041-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="cc041-104">Essa função foi preterida no .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="cc041-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc041-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cc041-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc041-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cc041-106">Parameters</span></span>  

 `hwnd`  
 <span data-ttu-id="cc041-107">no Um identificador para uma janela na qual a saída do comando será exibida.</span><span class="sxs-lookup"><span data-stu-id="cc041-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="cc041-108">no Um identificador para a biblioteca que contém o comando.</span><span class="sxs-lookup"><span data-stu-id="cc041-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="cc041-109">no Uma cadeia de caracteres que especifica o comando a ser executado.</span><span class="sxs-lookup"><span data-stu-id="cc041-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="cc041-110">no Um inteiro que especifica o modo de exibição para a janela de saída.</span><span class="sxs-lookup"><span data-stu-id="cc041-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc041-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc041-111">Requirements</span></span>  

 <span data-ttu-id="cc041-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc041-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc041-113">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cc041-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc041-114">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc041-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc041-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc041-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc041-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="cc041-116">See also</span></span>

- [<span data-ttu-id="cc041-117">Funções de hospedagem CLR reprovadas</span><span class="sxs-lookup"><span data-stu-id="cc041-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
