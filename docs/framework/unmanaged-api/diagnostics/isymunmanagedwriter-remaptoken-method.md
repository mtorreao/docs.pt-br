---
title: Método ISymUnmanagedWriter::RemapToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
ms.openlocfilehash: 8799815f7c6c6aefc7081f3583e6fd174cd478f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683551"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="96c16-102">Método ISymUnmanagedWriter::RemapToken</span><span class="sxs-lookup"><span data-stu-id="96c16-102">ISymUnmanagedWriter::RemapToken Method</span></span>

<span data-ttu-id="96c16-103">Notifica o gravador de símbolo de que um token de metadados foi remapeado conforme os metadados foram emitidos.</span><span class="sxs-lookup"><span data-stu-id="96c16-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="96c16-104">Se o gravador de símbolo tiver armazenado o token antigo no armazenamento de símbolo, ele deverá atualizar o token armazenado com o novo valor ou salvar o mapa do leitor de símbolo correspondente para remapear durante a fase de leitura.</span><span class="sxs-lookup"><span data-stu-id="96c16-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c16-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="96c16-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96c16-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="96c16-106">Parameters</span></span>  

 `oldToken`  
 <span data-ttu-id="96c16-107">no O token de metadados que foi remapeado.</span><span class="sxs-lookup"><span data-stu-id="96c16-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="96c16-108">no O novo token de metadados para o qual `oldToken` foi remapeado.</span><span class="sxs-lookup"><span data-stu-id="96c16-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96c16-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="96c16-109">Return Value</span></span>  

 <span data-ttu-id="96c16-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="96c16-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96c16-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96c16-111">Requirements</span></span>  

 <span data-ttu-id="96c16-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="96c16-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c16-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="96c16-113">See also</span></span>

- [<span data-ttu-id="96c16-114">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="96c16-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
