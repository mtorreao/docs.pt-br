---
title: Interface ISymUnmanagedVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: 93e1f8eb17f06e42ddb243f88c593979fcb28030
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733276"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="a0d62-102">Interface ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="a0d62-102">ISymUnmanagedVariable Interface</span></span>

<span data-ttu-id="a0d62-103">Representa uma variável, como um parâmetro, uma variável local ou um campo.</span><span class="sxs-lookup"><span data-stu-id="a0d62-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0d62-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a0d62-104">Methods</span></span>  
  
|<span data-ttu-id="a0d62-105">Método</span><span class="sxs-lookup"><span data-stu-id="a0d62-105">Method</span></span>|<span data-ttu-id="a0d62-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a0d62-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0d62-107">Método GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="a0d62-107">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="a0d62-108">Obtém o primeiro campo de endereço para essa variável.</span><span class="sxs-lookup"><span data-stu-id="a0d62-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="a0d62-109">Seu significado depende do tipo de endereço.</span><span class="sxs-lookup"><span data-stu-id="a0d62-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="a0d62-110">Método GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="a0d62-110">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="a0d62-111">Obtém o segundo campo de endereço para essa variável.</span><span class="sxs-lookup"><span data-stu-id="a0d62-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="a0d62-112">Seu significado depende do tipo de endereço.</span><span class="sxs-lookup"><span data-stu-id="a0d62-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="a0d62-113">Método GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="a0d62-113">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="a0d62-114">Obtém o terceiro campo de endereço para essa variável.</span><span class="sxs-lookup"><span data-stu-id="a0d62-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="a0d62-115">Seu significado depende do tipo de endereço.</span><span class="sxs-lookup"><span data-stu-id="a0d62-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="a0d62-116">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="a0d62-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="a0d62-117">Obtém o tipo de endereço dessa variável.</span><span class="sxs-lookup"><span data-stu-id="a0d62-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="a0d62-118">Método GetAttributes</span><span class="sxs-lookup"><span data-stu-id="a0d62-118">GetAttributes Method</span></span>](isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="a0d62-119">Obtém os sinalizadores de atributo para essa variável.</span><span class="sxs-lookup"><span data-stu-id="a0d62-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="a0d62-120">Método GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="a0d62-120">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="a0d62-121">Obtém o deslocamento final dessa variável dentro de seu pai.</span><span class="sxs-lookup"><span data-stu-id="a0d62-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="a0d62-122">Método GetName</span><span class="sxs-lookup"><span data-stu-id="a0d62-122">GetName Method</span></span>](isymunmanagedvariable-getname-method.md)|<span data-ttu-id="a0d62-123">Obtém o nome dessa variável.</span><span class="sxs-lookup"><span data-stu-id="a0d62-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="a0d62-124">Método GetSignature</span><span class="sxs-lookup"><span data-stu-id="a0d62-124">GetSignature Method</span></span>](isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="a0d62-125">Obtém a assinatura dessa variável.</span><span class="sxs-lookup"><span data-stu-id="a0d62-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="a0d62-126">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="a0d62-126">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="a0d62-127">Obtém o deslocamento inicial dessa variável dentro de seu pai.</span><span class="sxs-lookup"><span data-stu-id="a0d62-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0d62-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0d62-128">Requirements</span></span>  

 <span data-ttu-id="a0d62-129">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a0d62-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d62-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="a0d62-130">See also</span></span>

- [<span data-ttu-id="a0d62-131">Interfaces de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a0d62-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
