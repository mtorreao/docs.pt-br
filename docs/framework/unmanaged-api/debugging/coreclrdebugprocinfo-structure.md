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
# <a name="coreclrdebugprocinfo-structure"></a>Estrutura CoreClrDebugProcInfo

Representa um processo que está sendo executado em um computador remoto.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`m_dwPID`|Identificador de processo atribuído pelo sistema operacional.|  
|`m_dwInternalID`|Identificador de processo atribuído pelo proxy de depuração remota em execução no computador de destino. Esse identificador recicla com menos frequência do que o identificador do sistema operacional.|  
|`m_wszName`|Linha de comando do processo. Esse membro pode estar truncado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteca:** mscordbi_macx86.dll  
  
 **Versões do .NET Framework:** 3,5 SP1
