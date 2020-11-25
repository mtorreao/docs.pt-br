---
title: Estrutura PublicKeyBlob
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
ms.openlocfilehash: 42cd3cc22fbbb8eb3d5ac44544fce36650b6461f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705924"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="939fb-102">Estrutura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="939fb-102">PublicKeyBlob Structure</span></span>

<span data-ttu-id="939fb-103">Representa, em formato binário, a chave pública de um par de chaves pública/privada.</span><span class="sxs-lookup"><span data-stu-id="939fb-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="939fb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="939fb-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a><span data-ttu-id="939fb-105">Membros</span><span class="sxs-lookup"><span data-stu-id="939fb-105">Members</span></span>  
  
|<span data-ttu-id="939fb-106">Membro</span><span class="sxs-lookup"><span data-stu-id="939fb-106">Member</span></span>|<span data-ttu-id="939fb-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="939fb-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="939fb-108">O identificador do algoritmo de assinatura (do tipo `ALG_ID` , conforme definido em Wincrypt. h) da chave pública.</span><span class="sxs-lookup"><span data-stu-id="939fb-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="939fb-109">O identificador do algoritmo de hash (do tipo `ALG_ID` , conforme definido em Wincrypt. h) da chave pública.</span><span class="sxs-lookup"><span data-stu-id="939fb-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="939fb-110">O comprimento da chave em bytes.</span><span class="sxs-lookup"><span data-stu-id="939fb-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="939fb-111">Uma matriz de bytes de comprimento variável que contém o valor da chave no formato retornado pela CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="939fb-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="939fb-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="939fb-112">Remarks</span></span>  

 <span data-ttu-id="939fb-113">A `PublicKeyBlob` estrutura é usada por [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)e outras funções de nome forte para representar a chave pública de um par de chaves pública/privada.</span><span class="sxs-lookup"><span data-stu-id="939fb-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="939fb-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="939fb-114">Requirements</span></span>  

 <span data-ttu-id="939fb-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="939fb-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="939fb-116">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="939fb-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="939fb-117">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="939fb-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="939fb-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="939fb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939fb-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="939fb-119">See also</span></span>

- [<span data-ttu-id="939fb-120">Função StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="939fb-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="939fb-121">Função StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="939fb-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
