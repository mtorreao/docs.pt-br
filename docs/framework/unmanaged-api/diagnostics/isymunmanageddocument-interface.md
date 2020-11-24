---
title: Interface ISymUnmanagedDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: 83c683e1f60f13f7cee4ddc6fe5af5a94e36eb93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692170"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="e21a8-102">Interface ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="e21a8-102">ISymUnmanagedDocument Interface</span></span>

<span data-ttu-id="e21a8-103">Representa um documento referenciado por um repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e21a8-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="e21a8-104">Um documento é definido por um Uniform Resource Locator (URL) e um GUID de tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="e21a8-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="e21a8-105">Você pode localizar o documento independentemente de como ele é armazenado usando a URL e o tipo de documento GUID.</span><span class="sxs-lookup"><span data-stu-id="e21a8-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="e21a8-106">Você pode armazenar a origem do documento no repositório de símbolos e recuperá-lo por meio desta interface.</span><span class="sxs-lookup"><span data-stu-id="e21a8-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e21a8-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="e21a8-107">Methods</span></span>  
  
|<span data-ttu-id="e21a8-108">Método</span><span class="sxs-lookup"><span data-stu-id="e21a8-108">Method</span></span>|<span data-ttu-id="e21a8-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e21a8-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e21a8-110">Método FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="e21a8-110">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="e21a8-111">Retorna a linha mais próxima que é um ponto de sequência, dada uma linha neste documento que pode ou não ser um ponto de sequência.</span><span class="sxs-lookup"><span data-stu-id="e21a8-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="e21a8-112">Método GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="e21a8-112">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="e21a8-113">Obtém a soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="e21a8-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="e21a8-114">Método GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="e21a8-114">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="e21a8-115">Obtém o identificador de algoritmo de soma de verificação ou retorna um GUID de todos os zeros se não houver nenhuma soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="e21a8-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="e21a8-116">Método GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="e21a8-116">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="e21a8-117">Obtém o tipo de documento deste documento.</span><span class="sxs-lookup"><span data-stu-id="e21a8-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="e21a8-118">Método GetLanguage</span><span class="sxs-lookup"><span data-stu-id="e21a8-118">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="e21a8-119">Obtém o identificador de idioma deste documento.</span><span class="sxs-lookup"><span data-stu-id="e21a8-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="e21a8-120">Método GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="e21a8-120">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="e21a8-121">Obtém o fornecedor do idioma deste documento.</span><span class="sxs-lookup"><span data-stu-id="e21a8-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="e21a8-122">Método GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="e21a8-122">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="e21a8-123">Obtém o comprimento, em bytes, da origem inserida.</span><span class="sxs-lookup"><span data-stu-id="e21a8-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="e21a8-124">Método GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="e21a8-124">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="e21a8-125">Retorna o intervalo especificado da fonte inserida para o buffer fornecido.</span><span class="sxs-lookup"><span data-stu-id="e21a8-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="e21a8-126">Método GetURL</span><span class="sxs-lookup"><span data-stu-id="e21a8-126">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="e21a8-127">Retorna a URL deste documento.</span><span class="sxs-lookup"><span data-stu-id="e21a8-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="e21a8-128">Método HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="e21a8-128">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="e21a8-129">Retorna `true` se o documento tem origem inserida nos símbolos de depuração; caso contrário, retorna `false` .</span><span class="sxs-lookup"><span data-stu-id="e21a8-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e21a8-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="e21a8-130">See also</span></span>

- [<span data-ttu-id="e21a8-131">Interfaces de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e21a8-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
