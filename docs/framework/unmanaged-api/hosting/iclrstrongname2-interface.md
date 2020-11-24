---
title: Interface ICLRStrongName2
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
ms.openlocfilehash: df570f32d694ec21e9642e75b4965e169afaccfc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677642"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="15a7f-102">Interface ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="15a7f-102">ICLRStrongName2 Interface</span></span>

<span data-ttu-id="15a7f-103">Fornece a capacidade de criar nomes fortes usando o grupo SHA-2 de algoritmos de hash seguro (SHA-256, SHA-384 e SHA-512).</span><span class="sxs-lookup"><span data-stu-id="15a7f-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15a7f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="15a7f-104">Methods</span></span>  
  
|<span data-ttu-id="15a7f-105">Método</span><span class="sxs-lookup"><span data-stu-id="15a7f-105">Method</span></span>|<span data-ttu-id="15a7f-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="15a7f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15a7f-107">Método StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="15a7f-107">StrongNameGetPublicKeyEx Method</span></span>](strongnamegetpublickeyex-method.md)|<span data-ttu-id="15a7f-108">Obtém a chave pública de um par de chaves pública/privada e especifica um algoritmo de hash e um algoritmo de assinatura.</span><span class="sxs-lookup"><span data-stu-id="15a7f-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="15a7f-109">Método StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="15a7f-109">StrongNameSignatureVerificationEx2 Method</span></span>](strongnamesignatureverificationex2-method.md)|<span data-ttu-id="15a7f-110">Verifica a assinatura de um assembly com nome forte e fornece um mapeamento da chave ECMA para uma chave real.</span><span class="sxs-lookup"><span data-stu-id="15a7f-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15a7f-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="15a7f-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a7f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15a7f-112">Requirements</span></span>  

 <span data-ttu-id="15a7f-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15a7f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15a7f-114">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="15a7f-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="15a7f-115">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15a7f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15a7f-116">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15a7f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
