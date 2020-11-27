---
title: Using Multiple Authentication Schemes with WCF
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: 3aae9bff4300af97f7b179d9d8115340a26e715a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289419"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="8cdec-102">Using Multiple Authentication Schemes with WCF</span><span class="sxs-lookup"><span data-stu-id="8cdec-102">Using Multiple Authentication Schemes with WCF</span></span>

<span data-ttu-id="8cdec-103">O WCF agora permite que você especifique vários esquemas de autenticação em um único ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="8cdec-103">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="8cdec-104">Além disso, os serviços hospedados na Web podem herdar suas configurações de autenticação diretamente do IIS.</span><span class="sxs-lookup"><span data-stu-id="8cdec-104">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="8cdec-105">Os serviços auto-hospedados podem especificar quais esquemas de autenticação podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="8cdec-105">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="8cdec-106">Para obter mais informações sobre como definir configurações de autenticação no IIS, consulte [autenticação do IIS](https://go.microsoft.com/fwlink/?LinkId=232458)</span><span class="sxs-lookup"><span data-stu-id="8cdec-106">For more information about setting authentication settings in IIS, see [IIS Authentication](https://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="8cdec-107">Serviços IIS-Hosteds</span><span class="sxs-lookup"><span data-stu-id="8cdec-107">IIS-Hosted Services</span></span>  

 <span data-ttu-id="8cdec-108">Para serviços hospedados no IIS, defina os esquemas de autenticação que você deseja usar no IIS.</span><span class="sxs-lookup"><span data-stu-id="8cdec-108">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="8cdec-109">Em seguida, no arquivo de web.config do seu serviço, em sua configuração de associação, especifique o tipo clientCredential como "InheritedFromHost", conforme mostrado no trecho de código XML a seguir:</span><span class="sxs-lookup"><span data-stu-id="8cdec-109">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="8cdec-110">Você pode especificar que você deseja que apenas um subconjunto de esquemas de autenticação seja usado com seu serviço usando o ServiceAuthenticationBehavior ou o \<serviceAuthenticationManager> elemento.</span><span class="sxs-lookup"><span data-stu-id="8cdec-110">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="8cdec-111">Ao configurar isso no código, use o ServiceAuthenticationBehavior conforme mostrado no trecho de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="8cdec-111">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="8cdec-112">Ao configurar isso em um arquivo de configuração, use o \<serviceAuthenticationManager> elemento, conforme mostrado no trecho de código XML a seguir.</span><span class="sxs-lookup"><span data-stu-id="8cdec-112">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="8cdec-113">Isso garantirá que apenas um subconjunto dos esquemas de autenticação listados aqui será considerado para ser aplicado no ponto de extremidade do serviço, dependendo do que está selecionado no IIS.</span><span class="sxs-lookup"><span data-stu-id="8cdec-113">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="8cdec-114">Isso significa que um desenvolvedor pode excluir, por exemplo, a autenticação básica da lista omitindo-a da listagem de serviços de autenticação e, mesmo que esteja habilitada no IIS, ela não será aplicada no ponto de extremidade de serviço</span><span class="sxs-lookup"><span data-stu-id="8cdec-114">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="8cdec-115">Serviços Self-Hosteds</span><span class="sxs-lookup"><span data-stu-id="8cdec-115">Self-Hosted Services</span></span>  

 <span data-ttu-id="8cdec-116">Os serviços auto-hospedados são configurados de maneira um pouco diferente, já que não há nenhum IIS para herdar as configurações.</span><span class="sxs-lookup"><span data-stu-id="8cdec-116">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="8cdec-117">Aqui, você usa o \<serviceAuthenticationManager> elemento ou ServiceAuthenticationBehavior para especificar as configurações de autenticação que serão herdadas.</span><span class="sxs-lookup"><span data-stu-id="8cdec-117">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="8cdec-118">No código, ele tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="8cdec-118">In code it looks like this:</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="8cdec-119">Em configuração, ele tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="8cdec-119">In config, it looks like this:</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="8cdec-120">E, em seguida, você pode especificar InheritFromHost em suas configurações de associação, conforme mostrado no trecho de código XML a seguir.</span><span class="sxs-lookup"><span data-stu-id="8cdec-120">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="8cdec-121">Como alternativa, você pode especificar os esquemas de autenticação em uma associação personalizada, definindo os esquemas de autenticação no elemento de associação de transporte HTTP, conforme mostrado no trecho de configuração a seguir.</span><span class="sxs-lookup"><span data-stu-id="8cdec-121">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8cdec-122">Veja também</span><span class="sxs-lookup"><span data-stu-id="8cdec-122">See also</span></span>

- [<span data-ttu-id="8cdec-123">Associações e segurança</span><span class="sxs-lookup"><span data-stu-id="8cdec-123">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="8cdec-124">Pontos de extremidade: endereços, associações e contratos</span><span class="sxs-lookup"><span data-stu-id="8cdec-124">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="8cdec-125">Configurando associações fornecidas pelo sistema</span><span class="sxs-lookup"><span data-stu-id="8cdec-125">Configuring System-Provided Bindings</span></span>](configuring-system-provided-bindings.md)
- [<span data-ttu-id="8cdec-126">Recursos de segurança com associações personalizadas</span><span class="sxs-lookup"><span data-stu-id="8cdec-126">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="8cdec-127">Associações</span><span class="sxs-lookup"><span data-stu-id="8cdec-127">Bindings</span></span>](bindings.md)
- [<span data-ttu-id="8cdec-128">Associações personalizadas</span><span class="sxs-lookup"><span data-stu-id="8cdec-128">Custom Bindings</span></span>](../extending/custom-bindings.md)
