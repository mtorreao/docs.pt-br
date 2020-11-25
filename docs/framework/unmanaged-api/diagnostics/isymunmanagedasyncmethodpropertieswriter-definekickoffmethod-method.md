---
title: Método ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: 418a77855d1cb34a07f5957059b5a6f5a106c321
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707081"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="7c07e-102">Método ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="7c07e-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>

<span data-ttu-id="7c07e-103">Define o método inicial que inicia a operação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="7c07e-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c07e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7c07e-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c07e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7c07e-105">Parameters</span></span>  
  
|<span data-ttu-id="7c07e-106">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="7c07e-106">Parameter</span></span>|<span data-ttu-id="7c07e-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="7c07e-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="7c07e-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="7c07e-108">Return Value</span></span>  

 <span data-ttu-id="7c07e-109">Retorna `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7c07e-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c07e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c07e-110">Requirements</span></span>  

 <span data-ttu-id="7c07e-111">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7c07e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c07e-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="7c07e-112">See also</span></span>

- [<span data-ttu-id="7c07e-113">Interface ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="7c07e-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
