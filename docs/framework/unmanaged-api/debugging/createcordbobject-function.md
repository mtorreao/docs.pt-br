---
title: Função CreateCordbObject
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: eccdfcb60b2d2b5d652ccac948c01c16e7cb828d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725970"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="620a5-102">Função CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="620a5-102">CreateCordbObject Function</span></span>

<span data-ttu-id="620a5-103">Cria uma interface do depurador ([ICorDebug](icordebug-interface.md)) que fornece funcionalidade para instanciar uma sessão de depuração gerenciada em um processo remoto.</span><span class="sxs-lookup"><span data-stu-id="620a5-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="620a5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="620a5-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="620a5-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="620a5-105">Parameters</span></span>  

 `iDebuggerVersion`  
 <span data-ttu-id="620a5-106">no Versão do depurador do processo de destino.</span><span class="sxs-lookup"><span data-stu-id="620a5-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="620a5-107">Esse parâmetro deve ser CorDebugVersion_2_0 para depuração remota.</span><span class="sxs-lookup"><span data-stu-id="620a5-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="620a5-108">fora Ponteiro para um ponteiro para um objeto que será convertido em uma interface [ICorDebug](icordebug-interface.md) e retornado.</span><span class="sxs-lookup"><span data-stu-id="620a5-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="620a5-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="620a5-109">Return Value</span></span>  

 <span data-ttu-id="620a5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="620a5-110">S_OK</span></span>  
 <span data-ttu-id="620a5-111">O número de CLRs no processo foi determinado com êxito e as matrizes de identificador e caminho correspondentes foram preenchidas corretamente.</span><span class="sxs-lookup"><span data-stu-id="620a5-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="620a5-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="620a5-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="620a5-113">`ppCordb` é nulo ou `iDebuggerVersion` não é CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="620a5-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="620a5-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="620a5-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="620a5-115">Não é possível alocar memória suficiente para `ppCordb`</span><span class="sxs-lookup"><span data-stu-id="620a5-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="620a5-116">E_FAIL (ou outros códigos de retorno de E_)</span><span class="sxs-lookup"><span data-stu-id="620a5-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="620a5-117">Outras falhas.</span><span class="sxs-lookup"><span data-stu-id="620a5-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="620a5-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="620a5-118">Remarks</span></span>  

 <span data-ttu-id="620a5-119">A interface [ICorDebug](icordebug-interface.md) que é retornada no `ppCordb` é a interface de depuração de nível superior para todos os serviços de depuração gerenciados.</span><span class="sxs-lookup"><span data-stu-id="620a5-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="620a5-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="620a5-120">Requirements</span></span>  

 <span data-ttu-id="620a5-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="620a5-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="620a5-122">**Cabeçalho:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="620a5-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="620a5-123">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="620a5-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="620a5-124">**Versões do .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="620a5-124">**.NET Framework Versions:** 3.5 SP1</span></span>
