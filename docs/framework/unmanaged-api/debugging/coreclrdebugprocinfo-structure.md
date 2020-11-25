---
title: Estrutura CoreClrDebugProcInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: 5996393fd1a0504f9c3d3f9f07aa0e3d886a0787
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719691"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="410bf-102">Estrutura CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="410bf-102">CoreClrDebugProcInfo Structure</span></span>

<span data-ttu-id="410bf-103">Representa um processo que está sendo executado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="410bf-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="410bf-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="410bf-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="410bf-105">Membros</span><span class="sxs-lookup"><span data-stu-id="410bf-105">Members</span></span>  
  
|<span data-ttu-id="410bf-106">Membro</span><span class="sxs-lookup"><span data-stu-id="410bf-106">Member</span></span>|<span data-ttu-id="410bf-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="410bf-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="410bf-108">Identificador de processo atribuído pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="410bf-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="410bf-109">Identificador de processo atribuído pelo proxy de depuração remota em execução no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="410bf-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="410bf-110">Esse identificador recicla com menos frequência do que o identificador do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="410bf-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="410bf-111">Linha de comando do processo.</span><span class="sxs-lookup"><span data-stu-id="410bf-111">Command-line of the process.</span></span> <span data-ttu-id="410bf-112">Esse membro pode estar truncado.</span><span class="sxs-lookup"><span data-stu-id="410bf-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="410bf-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="410bf-113">Requirements</span></span>  

 <span data-ttu-id="410bf-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="410bf-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="410bf-115">**Cabeçalho:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="410bf-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="410bf-116">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="410bf-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="410bf-117">**Versões do .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="410bf-117">**.NET Framework Versions:** 3.5 SP1</span></span>
