---
title: Método ISymUnmanagedReader::GetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
ms.openlocfilehash: aa3b742babe4a94a43e4e6168dea67c0a0245eb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720575"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="b632b-102">Método ISymUnmanagedReader::GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="b632b-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>

<span data-ttu-id="b632b-103">Obtém um atributo personalizado com base no seu nome.</span><span class="sxs-lookup"><span data-stu-id="b632b-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="b632b-104">Ao contrário dos atributos personalizados de metadados, esses atributos personalizados são mantidos no repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="b632b-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b632b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b632b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b632b-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b632b-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="b632b-107">no O token de metadados para o objeto para o qual o atributo é solicitado.</span><span class="sxs-lookup"><span data-stu-id="b632b-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="b632b-108">no Um ponteiro para a variável que indica o atributo a ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="b632b-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="b632b-109">no O tamanho da `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="b632b-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="b632b-110">fora Um ponteiro para a variável que recebe o comprimento dos dados de atributo.</span><span class="sxs-lookup"><span data-stu-id="b632b-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="b632b-111">fora Um ponteiro para a variável que recebe os dados de atributo.</span><span class="sxs-lookup"><span data-stu-id="b632b-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b632b-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="b632b-112">Return Value</span></span>  

 <span data-ttu-id="b632b-113">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="b632b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b632b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b632b-114">Requirements</span></span>  

 <span data-ttu-id="b632b-115">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b632b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b632b-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="b632b-116">See also</span></span>

- [<span data-ttu-id="b632b-117">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="b632b-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
