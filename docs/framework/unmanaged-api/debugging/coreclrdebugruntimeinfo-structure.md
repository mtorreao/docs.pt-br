---
title: Estrutura CoreClrDebugRuntimeInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugRuntimeInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type:
- apiref
ms.openlocfilehash: 3cc9a1cfb26a784c32d66168bb01d41f91dd5f66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722358"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="9c3be-102">Estrutura CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="9c3be-102">CoreClrDebugRuntimeInfo Structure</span></span>

<span data-ttu-id="9c3be-103">Representa uma instância de Common Language Runtime (CLR) que é carregada em um processo em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9c3be-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c3be-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9c3be-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="9c3be-105">Membros</span><span class="sxs-lookup"><span data-stu-id="9c3be-105">Members</span></span>  
  
|<span data-ttu-id="9c3be-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9c3be-106">Member</span></span>|<span data-ttu-id="9c3be-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9c3be-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="9c3be-108">Identificador de tempo de execução atribuído pelo proxy de depuração remota em execução no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="9c3be-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9c3be-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c3be-109">Requirements</span></span>  

 <span data-ttu-id="9c3be-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c3be-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c3be-111">**Cabeçalho:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="9c3be-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="9c3be-112">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="9c3be-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="9c3be-113">**Versões do .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="9c3be-113">**.NET Framework Versions:** 3.5 SP1</span></span>
