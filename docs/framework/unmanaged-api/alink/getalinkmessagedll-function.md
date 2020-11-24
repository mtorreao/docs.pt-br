---
title: Função GetALinkMessageDll
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 554bd32ae965b21a88a09577749bbd7975f5ec7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684740"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="10df1-102">Função GetALinkMessageDll</span><span class="sxs-lookup"><span data-stu-id="10df1-102">GetALinkMessageDll Function</span></span>

<span data-ttu-id="10df1-103">Localiza e carrega a DLL de mensagem.</span><span class="sxs-lookup"><span data-stu-id="10df1-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="10df1-104">Retornará 0 se a DLL de mensagem não puder ser localizada ou carregada.</span><span class="sxs-lookup"><span data-stu-id="10df1-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="10df1-105">A DLL de mensagem deve estar em um subdiretório cujo nome é uma ID de idioma ou no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="10df1-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10df1-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="10df1-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="10df1-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10df1-107">Requirements</span></span>  

 <span data-ttu-id="10df1-108">**Cabeçalho:** ALink. h</span><span class="sxs-lookup"><span data-stu-id="10df1-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="10df1-109">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="10df1-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10df1-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="10df1-110">See also</span></span>

- [<span data-ttu-id="10df1-111">Al.exe (vinculador de assembly)</span><span class="sxs-lookup"><span data-stu-id="10df1-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
