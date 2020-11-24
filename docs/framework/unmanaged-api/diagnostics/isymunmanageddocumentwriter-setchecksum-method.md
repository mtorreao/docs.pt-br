---
title: Método ISymUnmanagedDocumentWriter::SetCheckSum
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
ms.openlocfilehash: 58055d9ea56d7928729d289198965752985d8e0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688894"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="22c16-102">Método ISymUnmanagedDocumentWriter::SetCheckSum</span><span class="sxs-lookup"><span data-stu-id="22c16-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>

<span data-ttu-id="22c16-103">Define informações de soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="22c16-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c16-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="22c16-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22c16-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="22c16-105">Parameters</span></span>  

 `algorithmId`  
 <span data-ttu-id="22c16-106">no O GUID que representa o identificador do algoritmo.</span><span class="sxs-lookup"><span data-stu-id="22c16-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="22c16-107">no Um `ULONG32` que indica o tamanho, em bytes, do `checkSum` buffer.</span><span class="sxs-lookup"><span data-stu-id="22c16-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="22c16-108">no O buffer que armazena as informações de soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="22c16-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22c16-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="22c16-109">Return Value</span></span>  

 <span data-ttu-id="22c16-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="22c16-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22c16-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22c16-111">Requirements</span></span>  

 <span data-ttu-id="22c16-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="22c16-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c16-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="22c16-113">See also</span></span>

- [<span data-ttu-id="22c16-114">Interface ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="22c16-114">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
