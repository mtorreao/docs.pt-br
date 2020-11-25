---
title: Função StrongNameFreeBuffer
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
ms.openlocfilehash: d93bda046a79dbdec2195eee48fefc1e5538b2e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732249"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="10be0-102">Função StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="10be0-102">StrongNameFreeBuffer Function</span></span>

<span data-ttu-id="10be0-103">Libera a memória que foi alocada com uma chamada anterior a uma função de nome forte, como [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), ou [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="10be0-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="10be0-104">Esta função foi preterida.</span><span class="sxs-lookup"><span data-stu-id="10be0-104">This function has been deprecated.</span></span> <span data-ttu-id="10be0-105">Em vez disso, use o método [ICLRStrongName:: StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="10be0-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10be0-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="10be0-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10be0-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="10be0-107">Parameters</span></span>  

 `pbMemory`  
 <span data-ttu-id="10be0-108">no Um ponteiro para a memória para liberar.</span><span class="sxs-lookup"><span data-stu-id="10be0-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10be0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10be0-109">Requirements</span></span>  

 <span data-ttu-id="10be0-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10be0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10be0-111">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="10be0-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="10be0-112">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10be0-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10be0-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10be0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10be0-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="10be0-114">See also</span></span>

- [<span data-ttu-id="10be0-115">Método StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="10be0-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="10be0-116">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="10be0-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
