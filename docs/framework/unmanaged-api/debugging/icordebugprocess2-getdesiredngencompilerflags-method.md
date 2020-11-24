---
title: Método ICorDebugProcess2::GetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: 223f66639ae24f2a54f1bc936f4a0765573356eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673885"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="0c283-102">Método ICorDebugProcess2::GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="0c283-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>

<span data-ttu-id="0c283-103">Obtém as configurações de sinalizador do compilador atual que o Common Language Runtime (CLR) usa para selecionar a imagem pré-compilada (ou seja, nativa) correta a ser carregada nesse processo.</span><span class="sxs-lookup"><span data-stu-id="0c283-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c283-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0c283-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c283-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0c283-105">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="0c283-106">fora Um ponteiro para uma combinação de bits de valor de enumeração de [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) que são usados para selecionar a imagem pré-compilada correta a ser carregada.</span><span class="sxs-lookup"><span data-stu-id="0c283-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c283-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="0c283-107">Remarks</span></span>  

 <span data-ttu-id="0c283-108">Use o método [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) para definir os sinalizadores que o CLR usará para selecionar a imagem previamente compilada correta a ser carregada.</span><span class="sxs-lookup"><span data-stu-id="0c283-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c283-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c283-109">Requirements</span></span>  

 <span data-ttu-id="0c283-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c283-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c283-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c283-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c283-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c283-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c283-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c283-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
