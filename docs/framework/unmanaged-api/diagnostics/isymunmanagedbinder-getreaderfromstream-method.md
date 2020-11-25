---
title: Método ISymUnmanagedBinder::GetReaderFromStream
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
ms.openlocfilehash: 2d927b02b7deebecb53a2218e2ec0275a07307b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706951"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="ee28f-102">Método ISymUnmanagedBinder::GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="ee28f-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>

<span data-ttu-id="ee28f-103">Dada uma interface de metadados e um fluxo que contém o armazenamento de símbolo, retorna a estrutura [ISymUnmanagedReader](isymunmanagedreader-interface.md) correta que lerá os símbolos de depuração do repositório de símbolos fornecido.</span><span class="sxs-lookup"><span data-stu-id="ee28f-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee28f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ee28f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee28f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ee28f-105">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="ee28f-106">no Um ponteiro para a interface de importação de metadados.</span><span class="sxs-lookup"><span data-stu-id="ee28f-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="ee28f-107">no Um ponteiro para o fluxo que contém o armazenamento de símbolo.</span><span class="sxs-lookup"><span data-stu-id="ee28f-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ee28f-108">fora Um ponteiro que é definido para a interface [ISymUnmanagedReader](isymunmanagedreader-interface.md) retornada.</span><span class="sxs-lookup"><span data-stu-id="ee28f-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee28f-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="ee28f-109">Return Value</span></span>  

 <span data-ttu-id="ee28f-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="ee28f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee28f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee28f-111">Requirements</span></span>  

 <span data-ttu-id="ee28f-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ee28f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee28f-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="ee28f-113">See also</span></span>

- [<span data-ttu-id="ee28f-114">Interface ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="ee28f-114">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
