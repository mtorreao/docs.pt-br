---
title: Interface ISymENCUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: acb8d48ed6314756e2c1a10fff314a303799fb24
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707276"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="5f025-102">Interface ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="5f025-102">ISymENCUnmanagedMethod Interface</span></span>

<span data-ttu-id="5f025-103">Fornece informações para o recurso Editar e continuar.</span><span class="sxs-lookup"><span data-stu-id="5f025-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f025-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5f025-104">Methods</span></span>  
  
|<span data-ttu-id="5f025-105">Método</span><span class="sxs-lookup"><span data-stu-id="5f025-105">Method</span></span>|<span data-ttu-id="5f025-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="5f025-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f025-107">Método GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="5f025-107">GetDocumentsForMethod Method</span></span>](isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="5f025-108">Obtém os documentos em que este método tem linhas.</span><span class="sxs-lookup"><span data-stu-id="5f025-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="5f025-109">Método GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="5f025-109">GetDocumentsForMethodCount Method</span></span>](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="5f025-110">Obtém o número de documentos em que esse método tem linhas.</span><span class="sxs-lookup"><span data-stu-id="5f025-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="5f025-111">Método GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="5f025-111">GetFileNameFromOffset Method</span></span>](isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="5f025-112">Obtém o nome do arquivo da linha associada a um deslocamento.</span><span class="sxs-lookup"><span data-stu-id="5f025-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="5f025-113">Método GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="5f025-113">GetLineFromOffset Method</span></span>](isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="5f025-114">Obtém as informações de linha associadas a um deslocamento.</span><span class="sxs-lookup"><span data-stu-id="5f025-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="5f025-115">Método GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="5f025-115">GetSourceExtentInDocument Method</span></span>](isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="5f025-116">Obtém a menor linha inicial e a linha final maior para o método em um documento específico.</span><span class="sxs-lookup"><span data-stu-id="5f025-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f025-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f025-117">Requirements</span></span>  

 <span data-ttu-id="5f025-118">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5f025-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f025-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="5f025-119">See also</span></span>

- [<span data-ttu-id="5f025-120">Interfaces de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5f025-120">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
