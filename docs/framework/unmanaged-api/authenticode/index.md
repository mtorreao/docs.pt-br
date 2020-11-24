---
title: Authenticode (referência de API não gerenciada)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 9b3e1585278bda82dedf7542e866a551867b9c9f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674041"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="81c86-102">Authenticode (referência de API não gerenciada)</span><span class="sxs-lookup"><span data-stu-id="81c86-102">Authenticode (Unmanaged API Reference)</span></span>

<span data-ttu-id="81c86-103">Oferece suporte à criação de licença Authenticode XrML e módulo de verificação.</span><span class="sxs-lookup"><span data-stu-id="81c86-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="81c86-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="81c86-104">In This Section</span></span>  

 [<span data-ttu-id="81c86-105">Função _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="81c86-105">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="81c86-106">Recupera o hash SHA-1 da chave pública associada à chave privada usada para assinar o certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="81c86-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="81c86-107">Função _AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="81c86-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="81c86-108">Computa o token de chave pública do nome forte de um formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="81c86-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="81c86-109">Função _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="81c86-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="81c86-110">Converte um Módulo e um Expoente em um token de chave pública com nome forte.</span><span class="sxs-lookup"><span data-stu-id="81c86-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="81c86-111">Função CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="81c86-111">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="81c86-112">Libera os recursos alocados para a estrutura AXL_AUTHENTICODE_SIGNER_INFO.</span><span class="sxs-lookup"><span data-stu-id="81c86-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="81c86-113">Função CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="81c86-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="81c86-114">Libera recursos alocados para a estrutura AXL_AUTHENTICODE_TIMESTAMPER_INFO.</span><span class="sxs-lookup"><span data-stu-id="81c86-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="81c86-115">Função CertTimestampAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="81c86-115">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="81c86-116">Adiciona carimbo de data/hora a uma licença Authenticode XrML criada por CertCreateAuthenticodeLicense.</span><span class="sxs-lookup"><span data-stu-id="81c86-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="81c86-117">Função CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="81c86-117">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="81c86-118">Verifica a validade de uma licença XrML Authenticode.</span><span class="sxs-lookup"><span data-stu-id="81c86-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="81c86-119">Estrutura AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="81c86-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="81c86-120">Define as informações sobre o signatário do Authenticode.</span><span class="sxs-lookup"><span data-stu-id="81c86-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="81c86-121">Estrutura AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="81c86-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="81c86-122">Define as informações sobre o carimbo de data/hora do Authenticode.</span><span class="sxs-lookup"><span data-stu-id="81c86-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c86-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="81c86-123">See also</span></span>

- [<span data-ttu-id="81c86-124">Referência de API não gerenciada</span><span class="sxs-lookup"><span data-stu-id="81c86-124">Unmanaged API Reference</span></span>](../index.md)
