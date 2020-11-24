---
title: Método ISymUnmanagedReader::UpdateSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
ms.openlocfilehash: 6670d985eed4c55550b23d3f4110ee20f3b75661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675822"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="932eb-102">Método ISymUnmanagedReader::UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="932eb-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>

<span data-ttu-id="932eb-103">Atualiza o repositório de símbolos existente com um repositório de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="932eb-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="932eb-104">Esse método é usado em cenários de edição e continuação para atualizar o armazenamento de símbolo para corresponder deltas ao arquivo PE (executável portátil) original.</span><span class="sxs-lookup"><span data-stu-id="932eb-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="932eb-105">Você precisa especificar apenas um dos `filename` parâmetros ou `pIStream` , não ambos.</span><span class="sxs-lookup"><span data-stu-id="932eb-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="932eb-106">Se `filename` for especificado, o armazenamento de símbolos será atualizado com os símbolos nesse arquivo.</span><span class="sxs-lookup"><span data-stu-id="932eb-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="932eb-107">Se `pIStream` for especificado, o repositório será atualizado com os dados do <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="932eb-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="932eb-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="932eb-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="932eb-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="932eb-109">Parameters</span></span>  

 `filename`  
 <span data-ttu-id="932eb-110">no O nome do arquivo que contém o armazenamento de símbolo.</span><span class="sxs-lookup"><span data-stu-id="932eb-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="932eb-111">no O fluxo de arquivos, usado como uma alternativa ao `filename` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="932eb-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="932eb-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="932eb-112">Return Value</span></span>  

 <span data-ttu-id="932eb-113">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="932eb-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="932eb-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="932eb-114">Requirements</span></span>  

 <span data-ttu-id="932eb-115">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="932eb-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="932eb-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="932eb-116">See also</span></span>

- [<span data-ttu-id="932eb-117">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="932eb-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
