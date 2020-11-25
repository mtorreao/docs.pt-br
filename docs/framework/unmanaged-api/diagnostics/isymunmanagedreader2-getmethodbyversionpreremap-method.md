---
title: Método ISymUnmanagedReader2::GetMethodByVersionPreRemap
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
ms.openlocfilehash: 5484242562deaf463b7435ad4e54735a7abee45e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730481"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="1e58d-102">Método ISymUnmanagedReader2::GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="1e58d-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>

<span data-ttu-id="1e58d-103">Obtém um método de leitor de símbolo, dado um token de método e um número de versão de edição e continuação.</span><span class="sxs-lookup"><span data-stu-id="1e58d-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="1e58d-104">Os números de versão começam em 1 e são incrementados cada vez que o método é alterado como resultado de uma operação de edição e continuação.</span><span class="sxs-lookup"><span data-stu-id="1e58d-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e58d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1e58d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e58d-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1e58d-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="1e58d-107">no O token de metadados do método.</span><span class="sxs-lookup"><span data-stu-id="1e58d-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="1e58d-108">no A versão do método.</span><span class="sxs-lookup"><span data-stu-id="1e58d-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1e58d-109">fora Um ponteiro para a interface [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) retornada.</span><span class="sxs-lookup"><span data-stu-id="1e58d-109">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e58d-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="1e58d-110">Return Value</span></span>  

 <span data-ttu-id="1e58d-111">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="1e58d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e58d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e58d-112">Requirements</span></span>  

 <span data-ttu-id="1e58d-113">**Cabeçalho:** CorSym. idl.</span><span class="sxs-lookup"><span data-stu-id="1e58d-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="1e58d-114">CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1e58d-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e58d-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="1e58d-115">See also</span></span>

- [<span data-ttu-id="1e58d-116">Interface ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="1e58d-116">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
