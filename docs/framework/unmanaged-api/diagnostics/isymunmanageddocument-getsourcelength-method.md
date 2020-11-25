---
title: Método ISymUnmanagedDocument::GetSourceLength
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
ms.openlocfilehash: c384fe6c4357c63bc56f9f9b1cc907dea64fddf7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700932"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="665f0-102">Método ISymUnmanagedDocument::GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="665f0-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>

<span data-ttu-id="665f0-103">Obtém o comprimento, em bytes, da origem inserida.</span><span class="sxs-lookup"><span data-stu-id="665f0-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="665f0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="665f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="665f0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="665f0-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="665f0-106">fora Um ponteiro para uma variável que indica o comprimento, em bytes, da fonte inserida.</span><span class="sxs-lookup"><span data-stu-id="665f0-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="665f0-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="665f0-107">Return Value</span></span>  

 <span data-ttu-id="665f0-108">S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="665f0-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665f0-109">Confira também</span><span class="sxs-lookup"><span data-stu-id="665f0-109">See also</span></span>

- [<span data-ttu-id="665f0-110">Interface ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="665f0-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
