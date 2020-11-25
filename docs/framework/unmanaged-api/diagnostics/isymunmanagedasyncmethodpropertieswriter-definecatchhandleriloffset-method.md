---
title: Método ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: a37d319a39b959700944f9e111d2945e286c99ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707133"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="3b71e-102">Método ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="3b71e-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>

<span data-ttu-id="3b71e-103">Define o deslocamento de IL para o manipulador catch gerado pelo compilador que encapsula um método assíncrono.</span><span class="sxs-lookup"><span data-stu-id="3b71e-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="3b71e-104">O deslocamento de IL do catch gerado é usado pelo depurador para lidar com o Catch como se fosse um código não-usuário, embora possa ocorrer em um método de código de usuário.</span><span class="sxs-lookup"><span data-stu-id="3b71e-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="3b71e-105">Em particular, ele é usado em resposta a um evento de exceção **CatchHandlerFound** .</span><span class="sxs-lookup"><span data-stu-id="3b71e-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b71e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3b71e-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b71e-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3b71e-107">Parameters</span></span>  
  
|<span data-ttu-id="3b71e-108">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="3b71e-108">Parameter</span></span>|<span data-ttu-id="3b71e-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b71e-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="3b71e-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="3b71e-110">Return Value</span></span>  

 <span data-ttu-id="3b71e-111">Retorna `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="3b71e-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b71e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b71e-112">Requirements</span></span>  

 <span data-ttu-id="3b71e-113">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3b71e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b71e-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="3b71e-114">See also</span></span>

- [<span data-ttu-id="3b71e-115">Interface ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="3b71e-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
