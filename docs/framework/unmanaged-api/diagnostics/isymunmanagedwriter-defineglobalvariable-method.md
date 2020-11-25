---
title: Método ISymUnmanagedWriter::DefineGlobalVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
ms.openlocfilehash: bc389b7247a6b1d6ce16cb3cf350f1672213b2e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716415"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="85303-102">Método ISymUnmanagedWriter::DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="85303-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>

<span data-ttu-id="85303-103">Define uma única variável global.</span><span class="sxs-lookup"><span data-stu-id="85303-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85303-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="85303-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85303-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="85303-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="85303-106">no Um ponteiro para um `WCHAR` que define o nome da variável global.</span><span class="sxs-lookup"><span data-stu-id="85303-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="85303-107">no Os atributos da variável global.</span><span class="sxs-lookup"><span data-stu-id="85303-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="85303-108">no Um `ULONG32` que indica o tamanho, em caracteres, do `signature` buffer.</span><span class="sxs-lookup"><span data-stu-id="85303-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="85303-109">no A assinatura de variável global.</span><span class="sxs-lookup"><span data-stu-id="85303-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="85303-110">no O tipo de endereço.</span><span class="sxs-lookup"><span data-stu-id="85303-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="85303-111">no O primeiro endereço para a especificação de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="85303-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="85303-112">no O segundo endereço para a especificação de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="85303-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="85303-113">no O terceiro endereço para a especificação de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="85303-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85303-114">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="85303-114">Return Value</span></span>  

 <span data-ttu-id="85303-115">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="85303-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85303-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85303-116">Requirements</span></span>  

 <span data-ttu-id="85303-117">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="85303-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85303-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="85303-118">See also</span></span>

- [<span data-ttu-id="85303-119">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="85303-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="85303-120">Método DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="85303-120">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="85303-121">Método DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="85303-121">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)
