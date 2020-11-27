---
title: 'Como: especificar o tipo de credencial de cliente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: b45d7b58d8a1fe79f9d7a8cff6e328b46633985c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293670"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="b2ae8-102">Como: especificar o tipo de credencial de cliente</span><span class="sxs-lookup"><span data-stu-id="b2ae8-102">How to: Specify the Client Credential Type</span></span>

<span data-ttu-id="b2ae8-103">Depois de definir um modo de segurança (transporte ou mensagem), você tem a opção de definir o tipo de credencial do cliente.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="b2ae8-104">Essa propriedade especifica o tipo de credencial que o cliente deve fornecer ao serviço para autenticação.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="b2ae8-105">Para obter mais informações sobre como definir o modo de segurança (uma etapa necessária antes de definir o tipo de credencial do cliente), consulte [como: definir o modo de segurança](how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b2ae8-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="b2ae8-106">Para definir o tipo de credencial do cliente no código</span><span class="sxs-lookup"><span data-stu-id="b2ae8-106">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="b2ae8-107">Crie uma instância da associação que será usada pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="b2ae8-108">Este exemplo usa a <xref:System.ServiceModel.WSHttpBinding> associação.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="b2ae8-109">Defina a propriedade <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> com um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="b2ae8-110">Este exemplo usa o modo de mensagem.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-110">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="b2ae8-111">Defina a propriedade <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> com um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="b2ae8-112">Este exemplo o define para usar a autenticação do Windows ( <xref:System.ServiceModel.MessageCredentialType.Windows> ).</span><span class="sxs-lookup"><span data-stu-id="b2ae8-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="b2ae8-113">Para definir o tipo de credencial do cliente na configuração</span><span class="sxs-lookup"><span data-stu-id="b2ae8-113">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="b2ae8-114">Adicione um [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) elemento ao arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-114">Add a [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="b2ae8-115">Como um elemento filho, adicione um [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-115">As a child element, add a [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="b2ae8-116">Adicione uma associação apropriada.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-116">Add an appropriate binding.</span></span> <span data-ttu-id="b2ae8-117">Este exemplo usa o [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-117">This example uses the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="b2ae8-118">Adicione um [\<binding>](../configure-apps/file-schema/wcf/bindings.md) elemento e defina o `name` atributo para um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-118">Add a [\<binding>](../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="b2ae8-119">Este exemplo usa o nome "Securebinding".</span><span class="sxs-lookup"><span data-stu-id="b2ae8-119">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="b2ae8-120">Adicione uma `<security>` associação.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-120">Add a `<security>` binding.</span></span> <span data-ttu-id="b2ae8-121">Defina o `mode` atributo para um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="b2ae8-122">Este exemplo o define como `"Message"` .</span><span class="sxs-lookup"><span data-stu-id="b2ae8-122">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="b2ae8-123">Adicione um `<message>` elemento ou `<transport>` , conforme determinado pelo modo de segurança.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="b2ae8-124">Defina o `clientCredentialType` atributo para um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="b2ae8-125">Este exemplo usa o `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="b2ae8-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b2ae8-126">Veja também</span><span class="sxs-lookup"><span data-stu-id="b2ae8-126">See also</span></span>

- [<span data-ttu-id="b2ae8-127">Serviços de segurança</span><span class="sxs-lookup"><span data-stu-id="b2ae8-127">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="b2ae8-128">Como: definir o modo de segurança</span><span class="sxs-lookup"><span data-stu-id="b2ae8-128">How to: Set the Security Mode</span></span>](how-to-set-the-security-mode.md)
