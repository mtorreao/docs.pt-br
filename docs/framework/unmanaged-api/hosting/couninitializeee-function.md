---
title: Função CoUninitializeEE
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: e6616392eaa23f8ba40247c5aabd12e4d530cea1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687841"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="c1e07-102">Função CoUninitializeEE</span><span class="sxs-lookup"><span data-stu-id="c1e07-102">CoUninitializeEE Function</span></span>

<span data-ttu-id="c1e07-103">`CoUninitializeEE` é obsoleto e não fornece nenhuma funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="c1e07-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1e07-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c1e07-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="c1e07-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="c1e07-105">Remarks</span></span>  

 <span data-ttu-id="c1e07-106">O mecanismo de execução de Common Language Runtime não pode ser descarregado de um processo.</span><span class="sxs-lookup"><span data-stu-id="c1e07-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="c1e07-107">Para desligar a chamada do mecanismo de execução [CorExitProcess](corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="c1e07-107">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1e07-108">Confira também</span><span class="sxs-lookup"><span data-stu-id="c1e07-108">See also</span></span>

- [<span data-ttu-id="c1e07-109">Função CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="c1e07-109">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="c1e07-110">Funções estáticas globais de metadados</span><span class="sxs-lookup"><span data-stu-id="c1e07-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
