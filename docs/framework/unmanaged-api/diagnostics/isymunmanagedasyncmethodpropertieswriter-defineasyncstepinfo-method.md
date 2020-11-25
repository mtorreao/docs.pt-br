---
title: Método ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: f8c77e44183fd92704aa91ca1cfd7e3fa68aa27f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719613"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="c42f2-102">Método ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="c42f2-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>

<span data-ttu-id="c42f2-103">Defina um grupo de operações assíncronas Await no método atual.</span><span class="sxs-lookup"><span data-stu-id="c42f2-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="c42f2-104">Cada deslocamento de rendimento corresponde a uma instrução de retorno de Await, identificando um possível rendimento.</span><span class="sxs-lookup"><span data-stu-id="c42f2-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="c42f2-105">Cada `breakpointMethod` / `breakpointOffset` par informa onde a operação assíncrona será retomada, o que pode estar em um método diferente.</span><span class="sxs-lookup"><span data-stu-id="c42f2-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c42f2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c42f2-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c42f2-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c42f2-107">Parameters</span></span>  
  
|<span data-ttu-id="c42f2-108">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="c42f2-108">Parameter</span></span>|<span data-ttu-id="c42f2-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c42f2-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="c42f2-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="c42f2-110">Return Value</span></span>  

 <span data-ttu-id="c42f2-111">Retorna `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="c42f2-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c42f2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c42f2-112">Requirements</span></span>  

 <span data-ttu-id="c42f2-113">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c42f2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c42f2-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="c42f2-114">See also</span></span>

- [<span data-ttu-id="c42f2-115">Interface ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="c42f2-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
