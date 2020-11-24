---
title: Método ISymUnmanagedReader::GetMethodByVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
ms.openlocfilehash: 64e6b9a1942e9a69e43de3d2f09564814328ec08
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689609"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="9a559-102">Método ISymUnmanagedReader::GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="9a559-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>

<span data-ttu-id="9a559-103">Obtém um método de leitor de símbolo, dado um token de método e um número de versão de edição e cópia.</span><span class="sxs-lookup"><span data-stu-id="9a559-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="9a559-104">Os números de versão começam em 1 e são incrementados cada vez que o método é alterado como resultado de uma operação de edição e cópia.</span><span class="sxs-lookup"><span data-stu-id="9a559-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a559-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9a559-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a559-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9a559-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="9a559-107">no O token do método.</span><span class="sxs-lookup"><span data-stu-id="9a559-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="9a559-108">no A versão do método.</span><span class="sxs-lookup"><span data-stu-id="9a559-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9a559-109">fora Um ponteiro para a interface retornada.</span><span class="sxs-lookup"><span data-stu-id="9a559-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a559-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="9a559-110">Return Value</span></span>  

 <span data-ttu-id="9a559-111">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="9a559-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a559-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a559-112">Requirements</span></span>  

 <span data-ttu-id="9a559-113">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9a559-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a559-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="9a559-114">See also</span></span>

- [<span data-ttu-id="9a559-115">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="9a559-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
