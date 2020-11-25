---
title: Função InitDbgTransportManager
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
ms.openlocfilehash: a5b4783eadb8045733b9ebd6d10c4e31f7829498
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716675"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="5ede2-102">Função InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="5ede2-102">InitDbgTransportManager Function</span></span>

<span data-ttu-id="5ede2-103">Inicializa o Gerenciador de transporte para se conectar a um destino remoto para enumeração de processo e tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="5ede2-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ede2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5ede2-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5ede2-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="5ede2-105">Return Value</span></span>  

 <span data-ttu-id="5ede2-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ede2-106">S_OK</span></span>  
 <span data-ttu-id="5ede2-107">Sucesso.</span><span class="sxs-lookup"><span data-stu-id="5ede2-107">Success.</span></span>  
  
 <span data-ttu-id="5ede2-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5ede2-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="5ede2-109">A função não pôde alocar memória para um Gerenciador de transporte.</span><span class="sxs-lookup"><span data-stu-id="5ede2-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="5ede2-110">E_FAIL (ou outros códigos de retorno de E_)</span><span class="sxs-lookup"><span data-stu-id="5ede2-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="5ede2-111">Outras falhas.</span><span class="sxs-lookup"><span data-stu-id="5ede2-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ede2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ede2-112">Requirements</span></span>  

 <span data-ttu-id="5ede2-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ede2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ede2-114">**Cabeçalho:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="5ede2-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="5ede2-115">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="5ede2-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="5ede2-116">**Versões do .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="5ede2-116">**.NET Framework Versions:** 3.5 SP1</span></span>
