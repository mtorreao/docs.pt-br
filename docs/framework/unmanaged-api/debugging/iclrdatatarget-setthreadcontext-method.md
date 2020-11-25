---
title: Método ICLRDataTarget::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: c135c051637858682c22db58d562e1d50eea562b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723695"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="8b2d7-102">Método ICLRDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="8b2d7-102">ICLRDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="8b2d7-103">Define o contexto atual do thread especificado no processo de destino.</span><span class="sxs-lookup"><span data-stu-id="8b2d7-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="8b2d7-104">Esse método é chamado pelos serviços de acesso a dados do Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8b2d7-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b2d7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8b2d7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b2d7-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8b2d7-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="8b2d7-107">no O identificador do sistema operacional de um thread no processo de destino.</span><span class="sxs-lookup"><span data-stu-id="8b2d7-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="8b2d7-108">no O tamanho do contexto.</span><span class="sxs-lookup"><span data-stu-id="8b2d7-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="8b2d7-109">no Ponteiro para um buffer que contém o contexto.</span><span class="sxs-lookup"><span data-stu-id="8b2d7-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="8b2d7-110">Os dados no `context` buffer estarão no formato da estrutura do Win32 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="8b2d7-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="8b2d7-111">O contexto especifica dados de registro específicos do processador, de modo que a definição da estrutura do Win32 `CONTEXT` depende da arquitetura do processador.</span><span class="sxs-lookup"><span data-stu-id="8b2d7-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="8b2d7-112">Consulte o arquivo de cabeçalho WinNT. h para obter a definição da estrutura do Win32 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="8b2d7-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b2d7-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="8b2d7-113">Remarks</span></span>  

 <span data-ttu-id="8b2d7-114">Este método é implementado pelo autor do aplicativo de depuração.</span><span class="sxs-lookup"><span data-stu-id="8b2d7-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b2d7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b2d7-115">Requirements</span></span>  

 <span data-ttu-id="8b2d7-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b2d7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b2d7-117">**Cabeçalho:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="8b2d7-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8b2d7-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b2d7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b2d7-119">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b2d7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2d7-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="8b2d7-120">See also</span></span>

- [<span data-ttu-id="8b2d7-121">Interface ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="8b2d7-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
