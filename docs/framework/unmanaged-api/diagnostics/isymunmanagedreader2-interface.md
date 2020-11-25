---
title: Interface ISymUnmanagedReader2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: 3f34be833d3ccb5c636d2c5f18ccb6e216ef2c49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709070"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="ceb86-102">Interface ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="ceb86-102">ISymUnmanagedReader2 Interface</span></span>

<span data-ttu-id="ceb86-103">Representa um leitor de símbolo que fornece acesso a documentos, métodos e variáveis em um repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="ceb86-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="ceb86-104">Essa interface estende a interface [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ceb86-104">This interface extends the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ceb86-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ceb86-105">Methods</span></span>  
  
|<span data-ttu-id="ceb86-106">Método</span><span class="sxs-lookup"><span data-stu-id="ceb86-106">Method</span></span>|<span data-ttu-id="ceb86-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="ceb86-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ceb86-108">Método GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="ceb86-108">GetMethodByVersionPreRemap Method</span></span>](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="ceb86-109">Obtenha um método de leitor de símbolo, dado um token de método e um número de versão de edição e continuação.</span><span class="sxs-lookup"><span data-stu-id="ceb86-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="ceb86-110">Método GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="ceb86-110">GetMethodsInDocument Method</span></span>](isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="ceb86-111">Obtém todos os métodos que têm informações de linha no documento fornecido.</span><span class="sxs-lookup"><span data-stu-id="ceb86-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="ceb86-112">Método GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="ceb86-112">GetSymAttributePreRemap Method</span></span>](isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="ceb86-113">Obtém um atributo personalizado com base no seu nome.</span><span class="sxs-lookup"><span data-stu-id="ceb86-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ceb86-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ceb86-114">Requirements</span></span>  

 <span data-ttu-id="ceb86-115">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ceb86-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb86-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="ceb86-116">See also</span></span>

- [<span data-ttu-id="ceb86-117">Interfaces de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ceb86-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ceb86-118">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="ceb86-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
