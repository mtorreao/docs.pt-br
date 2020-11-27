---
title: 'Como: fazer referência de forma consistente aos certificados X.509'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: b5be8990384178c1954834204c23c0b9cf4a5ad9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257269"
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="8dd64-102">Como: fazer referência de forma consistente aos certificados X.509</span><span class="sxs-lookup"><span data-stu-id="8dd64-102">How to: Consistently Reference X.509 Certificates</span></span>

<span data-ttu-id="8dd64-103">Você pode identificar um certificado de várias maneiras: pelo hash do certificado, pelo emissor e número de série, ou pelo identificador de chave da entidade (esqui).</span><span class="sxs-lookup"><span data-stu-id="8dd64-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="8dd64-104">A esqui fornece uma identificação exclusiva para a chave pública da entidade do certificado e é geralmente usada ao trabalhar com a assinatura digital XML.</span><span class="sxs-lookup"><span data-stu-id="8dd64-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="8dd64-105">O valor de esqui geralmente faz parte do certificado X. 509 como uma *extensão de certificado x. 509*.</span><span class="sxs-lookup"><span data-stu-id="8dd64-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> <span data-ttu-id="8dd64-106">Windows Communication Foundation (WCF) tem um *estilo de referência* padrão que usa o emissor e o número de série se a extensão de esqui está ausente do certificado.</span><span class="sxs-lookup"><span data-stu-id="8dd64-106">Windows Communication Foundation (WCF) has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="8dd64-107">Se o certificado contiver a extensão de esqui, o estilo de referência padrão usará a esqui para apontar para o certificado.</span><span class="sxs-lookup"><span data-stu-id="8dd64-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="8dd64-108">Se for o meio-caminho do desenvolvimento de um aplicativo, você alternar do uso de certificados que não usam a extensão de esqui para certificados que usam a extensão de esqui, o estilo de referência usado em mensagens geradas pelo WCF também é alterado.</span><span class="sxs-lookup"><span data-stu-id="8dd64-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in WCF-generated messages also changes.</span></span>  
  
 <span data-ttu-id="8dd64-109">Se um estilo de referência consistente for necessário independentemente da presença da extensão de esqui, será possível configurar o estilo de referência desejado, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="8dd64-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dd64-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8dd64-110">Example</span></span>  

 <span data-ttu-id="8dd64-111">O exemplo a seguir cria um elemento de associação de segurança personalizado que usa um único estilo de referência consistente, o nome do emissor e o número de série.</span><span class="sxs-lookup"><span data-stu-id="8dd64-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8dd64-112">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="8dd64-112">Compiling the Code</span></span>  

 <span data-ttu-id="8dd64-113">Os namespaces a seguir são necessários para compilar o código:</span><span class="sxs-lookup"><span data-stu-id="8dd64-113">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="8dd64-114">Veja também</span><span class="sxs-lookup"><span data-stu-id="8dd64-114">See also</span></span>

- [<span data-ttu-id="8dd64-115">Trabalhando com certificados</span><span class="sxs-lookup"><span data-stu-id="8dd64-115">Working with Certificates</span></span>](working-with-certificates.md)
