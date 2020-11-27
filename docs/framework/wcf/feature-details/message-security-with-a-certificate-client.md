---
title: Segurança da mensagens com um cliente de certificado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
ms.openlocfilehash: 4a1cb6d804d313f438fc8e7a92946d55f73b9ee5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288574"
---
# <a name="message-security-with-a-certificate-client"></a><span data-ttu-id="7a8fc-102">Segurança da mensagens com um cliente de certificado</span><span class="sxs-lookup"><span data-stu-id="7a8fc-102">Message Security with a Certificate Client</span></span>

<span data-ttu-id="7a8fc-103">O cenário a seguir mostra um cliente Windows Communication Foundation (WCF) e um serviço protegido usando o modo de segurança da mensagem.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured using message security mode.</span></span> <span data-ttu-id="7a8fc-104">O cliente e o serviço são autenticados com certificados.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-104">Both the client and the service are authenticated with certificates.</span></span> <span data-ttu-id="7a8fc-105">Para obter mais informações, consulte [segurança de aplicativo distribuído](distributed-application-security.md).</span><span class="sxs-lookup"><span data-stu-id="7a8fc-105">For more information, see [Distributed Application Security](distributed-application-security.md).</span></span>

 ![Captura de tela que mostra um cliente com certificado.](./media/message-security-with-a-certificate-client/client-with-certificate.gif)  
  
 <span data-ttu-id="7a8fc-107">Para um aplicativo de exemplo, consulte [certificado de segurança da mensagem](../samples/message-security-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="7a8fc-107">For a sample application, see [Message Security Certificate](../samples/message-security-certificate.md).</span></span>  

|<span data-ttu-id="7a8fc-108">Característica</span><span class="sxs-lookup"><span data-stu-id="7a8fc-108">Characteristic</span></span>|<span data-ttu-id="7a8fc-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="7a8fc-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7a8fc-110">Modo de segurança</span><span class="sxs-lookup"><span data-stu-id="7a8fc-110">Security Mode</span></span>|<span data-ttu-id="7a8fc-111">Mensagem</span><span class="sxs-lookup"><span data-stu-id="7a8fc-111">Message</span></span>|  
|<span data-ttu-id="7a8fc-112">Interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="7a8fc-112">Interoperability</span></span>|<span data-ttu-id="7a8fc-113">Somente WCF</span><span class="sxs-lookup"><span data-stu-id="7a8fc-113">WCF only</span></span>|  
|<span data-ttu-id="7a8fc-114">Autenticação (servidor)</span><span class="sxs-lookup"><span data-stu-id="7a8fc-114">Authentication (Server)</span></span>|<span data-ttu-id="7a8fc-115">Usando o certificado de serviço</span><span class="sxs-lookup"><span data-stu-id="7a8fc-115">Using service certificate</span></span>|  
|<span data-ttu-id="7a8fc-116">Autenticação (cliente)</span><span class="sxs-lookup"><span data-stu-id="7a8fc-116">Authentication (Client)</span></span>|<span data-ttu-id="7a8fc-117">Usando o certificado do cliente</span><span class="sxs-lookup"><span data-stu-id="7a8fc-117">Using client certificate</span></span>|  
|<span data-ttu-id="7a8fc-118">Integridade</span><span class="sxs-lookup"><span data-stu-id="7a8fc-118">Integrity</span></span>|<span data-ttu-id="7a8fc-119">Sim</span><span class="sxs-lookup"><span data-stu-id="7a8fc-119">Yes</span></span>|  
|<span data-ttu-id="7a8fc-120">Confidencialidade</span><span class="sxs-lookup"><span data-stu-id="7a8fc-120">Confidentiality</span></span>|<span data-ttu-id="7a8fc-121">Yes</span><span class="sxs-lookup"><span data-stu-id="7a8fc-121">Yes</span></span>|  
|<span data-ttu-id="7a8fc-122">Transport</span><span class="sxs-lookup"><span data-stu-id="7a8fc-122">Transport</span></span>|<span data-ttu-id="7a8fc-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="7a8fc-123">HTTP</span></span>|  
|<span data-ttu-id="7a8fc-124">Associação</span><span class="sxs-lookup"><span data-stu-id="7a8fc-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="7a8fc-125">Serviço</span><span class="sxs-lookup"><span data-stu-id="7a8fc-125">Service</span></span>  

 <span data-ttu-id="7a8fc-126">O código e a configuração a seguir devem ser executados de forma independente.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7a8fc-127">Realize uma destas ações:</span><span class="sxs-lookup"><span data-stu-id="7a8fc-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="7a8fc-128">Crie um serviço autônomo usando o código sem configuração.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="7a8fc-129">Crie um serviço usando a configuração fornecida, mas não defina nenhum ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7a8fc-130">Código</span><span class="sxs-lookup"><span data-stu-id="7a8fc-130">Code</span></span>  

 <span data-ttu-id="7a8fc-131">O código a seguir mostra como criar um ponto de extremidade de serviço que usa segurança de mensagem para estabelecer um contexto seguro.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-131">The following code shows how to create a service endpoint that uses message security to establish a secure context.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a><span data-ttu-id="7a8fc-132">Configuração</span><span class="sxs-lookup"><span data-stu-id="7a8fc-132">Configuration</span></span>  

 <span data-ttu-id="7a8fc-133">A configuração a seguir pode ser usada em vez do código.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-133">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndCertificateClient"
                  name="SecuredByClientCertificate"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="7a8fc-134">Cliente</span><span class="sxs-lookup"><span data-stu-id="7a8fc-134">Client</span></span>  

 <span data-ttu-id="7a8fc-135">O código e a configuração a seguir devem ser executados de forma independente.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-135">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7a8fc-136">Realize uma destas ações:</span><span class="sxs-lookup"><span data-stu-id="7a8fc-136">Do one of the following:</span></span>  
  
- <span data-ttu-id="7a8fc-137">Crie um cliente autônomo usando o código (e o código do cliente).</span><span class="sxs-lookup"><span data-stu-id="7a8fc-137">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="7a8fc-138">Crie um cliente que não defina nenhum endereço de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-138">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="7a8fc-139">Em vez disso, use o construtor do cliente que usa o nome da configuração como um argumento.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-139">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="7a8fc-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7a8fc-140">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="7a8fc-141">Código</span><span class="sxs-lookup"><span data-stu-id="7a8fc-141">Code</span></span>  

 <span data-ttu-id="7a8fc-142">O código a seguir cria o cliente.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-142">The following code creates the client.</span></span> <span data-ttu-id="7a8fc-143">A associação é a segurança do modo de mensagem e o tipo de credencial do cliente é definido como `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="7a8fc-143">The binding is to message mode security, and the client credential type is set to `Certificate`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a><span data-ttu-id="7a8fc-144">Configuração</span><span class="sxs-lookup"><span data-stu-id="7a8fc-144">Configuration</span></span>  

 <span data-ttu-id="7a8fc-145">A configuração a seguir especifica o certificado do cliente usando um comportamento de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-145">The following configuration specifies the client certificate using an endpoint behavior.</span></span> <span data-ttu-id="7a8fc-146">Para obter mais informações sobre certificados, consulte [Working with Certificates](working-with-certificates.md) (Trabalhando com certificados).</span><span class="sxs-lookup"><span data-stu-id="7a8fc-146">For more information about certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="7a8fc-147">O código também usa um `identity` elemento <> para especificar um DNS (sistema de nomes de domínio) da identidade do servidor esperada.</span><span class="sxs-lookup"><span data-stu-id="7a8fc-147">The code also uses an <`identity`> element to specify a Domain Name System (DNS) of the expected server identity.</span></span> <span data-ttu-id="7a8fc-148">Para obter mais informações sobre identidade, consulte [identidade de serviço e autenticação](service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="7a8fc-148">For more information about identity, see [Service Identity and Authentication](service-identity-and-authentication.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
               storeLocation="LocalMachine"  
              x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="endpointCredentialsBehavior"  
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a8fc-149">Veja também</span><span class="sxs-lookup"><span data-stu-id="7a8fc-149">See also</span></span>

- [<span data-ttu-id="7a8fc-150">Visão geral de segurança</span><span class="sxs-lookup"><span data-stu-id="7a8fc-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="7a8fc-151">Identidade e autenticação de serviço</span><span class="sxs-lookup"><span data-stu-id="7a8fc-151">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)
- [<span data-ttu-id="7a8fc-152">Trabalhando com certificados</span><span class="sxs-lookup"><span data-stu-id="7a8fc-152">Working with Certificates</span></span>](working-with-certificates.md)
- <span data-ttu-id="7a8fc-153">[Modelo de segurança para o Windows Server app Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="7a8fc-153">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
