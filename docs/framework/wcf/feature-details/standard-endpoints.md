---
title: Pontos de extremidade padrão
ms.date: 03/30/2017
ms.assetid: 3fcb4225-addc-44f2-935d-30e4943a8812
ms.openlocfilehash: a2f8d45990c5bc845aeee87ee82a2d043d6d1292
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246440"
---
# <a name="standard-endpoints"></a><span data-ttu-id="3a875-102">Pontos de extremidade padrão</span><span class="sxs-lookup"><span data-stu-id="3a875-102">Standard Endpoints</span></span>

<span data-ttu-id="3a875-103">Os pontos de extremidade são definidos especificando um endereço, uma associação e um contrato.</span><span class="sxs-lookup"><span data-stu-id="3a875-103">Endpoints are defined by specifying an address, a binding, and a contract.</span></span> <span data-ttu-id="3a875-104">Outros parâmetros que podem ser definidos em um ponto de extremidade incluem configuração de comportamento, cabeçalhos e URIs de escuta.</span><span class="sxs-lookup"><span data-stu-id="3a875-104">Other parameters that may be set on an endpoint include behavior configuration, headers, and listen URIs.</span></span>  <span data-ttu-id="3a875-105">Para determinados tipos de pontos de extremidade, esses valores não são alterados.</span><span class="sxs-lookup"><span data-stu-id="3a875-105">For certain types of endpoints these values do not change.</span></span> <span data-ttu-id="3a875-106">Por exemplo, os pontos de extremidade de troca de metadados sempre usam o <xref:System.ServiceModel.Description.IMetadataExchange> contrato.</span><span class="sxs-lookup"><span data-stu-id="3a875-106">For example, metadata exchange endpoints always use the <xref:System.ServiceModel.Description.IMetadataExchange> contract.</span></span> <span data-ttu-id="3a875-107">Outros pontos de extremidade, como <xref:System.ServiceModel.Description.WebHttpEndpoint> sempre requerer um comportamento de Endpoint especificado.</span><span class="sxs-lookup"><span data-stu-id="3a875-107">Other endpoints, such as <xref:System.ServiceModel.Description.WebHttpEndpoint> always require a specified endpoint behavior.</span></span> <span data-ttu-id="3a875-108">A usabilidade de um ponto de extremidade pode ser melhorada com o uso de pontos de extremidade com valores padrão para propriedades de Endpoint mais usadas.</span><span class="sxs-lookup"><span data-stu-id="3a875-108">The usability of an endpoint can be improved by having endpoints with default values for commonly used endpoint properties.</span></span> <span data-ttu-id="3a875-109">Os pontos de extremidade padrão permitem que um desenvolvedor defina um ponto de extremidade que tem valores padrão ou em que uma ou mais propriedades de pontos finais não são alteradas.</span><span class="sxs-lookup"><span data-stu-id="3a875-109">Standard endpoints enable a developer to define an endpoint that has default values or where one or more endpoint’s properties does not change.</span></span>  <span data-ttu-id="3a875-110">Esses pontos de extremidade permitem que você use um deles, sem precisar especificar informações de natureza estática.</span><span class="sxs-lookup"><span data-stu-id="3a875-110">These endpoints allow you to use such an endpoint without having to specify information of a static nature.</span></span> <span data-ttu-id="3a875-111">Os pontos de extremidade padrão podem ser usados para a infraestrutura e os pontos de extremidade do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3a875-111">Standard endpoints can be used for infrastructure and application endpoints.</span></span>  
  
## <a name="infrastructure-endpoints"></a><span data-ttu-id="3a875-112">Pontos de extremidade de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="3a875-112">Infrastructure Endpoints</span></span>  

 <span data-ttu-id="3a875-113">Um serviço pode expor pontos de extremidade com algumas das propriedades não explicitamente implementadas pelo autor do serviço.</span><span class="sxs-lookup"><span data-stu-id="3a875-113">A service may expose endpoints with some of the properties not explicitly implemented by the service author.</span></span> <span data-ttu-id="3a875-114">Por exemplo, o ponto de extremidade de troca de metadados expõe o <xref:System.ServiceModel.Description.IMetadataExchange> contrato, mas como um autor de serviço, você não implementa essa interface, ela é implementada pelo WCF.</span><span class="sxs-lookup"><span data-stu-id="3a875-114">For example, the metadata exchange endpoint exposes the <xref:System.ServiceModel.Description.IMetadataExchange> contract but as a service author you do not implement that interface, it is implemented by WCF.</span></span> <span data-ttu-id="3a875-115">Esses pontos de extremidade de infraestrutura têm valores padrão para uma ou mais propriedades de ponto de extremidades, alguns dos quais podem não ser alterados.</span><span class="sxs-lookup"><span data-stu-id="3a875-115">Such infrastructure endpoints have default values for one or more endpoint properties, some of which may be unalterable.</span></span> <span data-ttu-id="3a875-116">A <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> Propriedade do ponto de extremidade de troca de metadados deve ser <xref:System.ServiceModel.Description.IMetadataExchange> , enquanto outras propriedades, como a associação, podem ser fornecidas pelo desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="3a875-116">The <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> property of the metadata exchange endpoint must be <xref:System.ServiceModel.Description.IMetadataExchange>, while other properties like binding can be supplied by the developer.</span></span> <span data-ttu-id="3a875-117">Os pontos de extremidade de infraestrutura são identificados definindo a <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> propriedade como `true` .</span><span class="sxs-lookup"><span data-stu-id="3a875-117">Infrastructure endpoints are identified by setting the <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> property to `true`.</span></span>  
  
## <a name="application-endpoints"></a><span data-ttu-id="3a875-118">Pontos de extremidade do aplicativo</span><span class="sxs-lookup"><span data-stu-id="3a875-118">Application Endpoints</span></span>  

 <span data-ttu-id="3a875-119">Os desenvolvedores de aplicativos podem definir seus próprios pontos de extremidade padrão que especificam valores padrão para o endereço, a associação ou o contrato.</span><span class="sxs-lookup"><span data-stu-id="3a875-119">Application developers can define their own standard endpoints which specify default values for the address, binding, or contract.</span></span> <span data-ttu-id="3a875-120">Você define um ponto de extremidade padrão derivando uma classe de <xref:System.ServiceModel.Description.ServiceEndpoint> e definindo as propriedades apropriadas do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="3a875-120">You define a standard endpoint by deriving a class from <xref:System.ServiceModel.Description.ServiceEndpoint> and setting the appropriate endpoint properties.</span></span> <span data-ttu-id="3a875-121">Você pode fornecer valores padrão para propriedades que podem ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="3a875-121">You can provide default values for properties that can be changed.</span></span> <span data-ttu-id="3a875-122">Algumas outras propriedades terão valores estáticos que não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="3a875-122">Some other properties will have static values that cannot change.</span></span> <span data-ttu-id="3a875-123">O exemplo a seguir mostra como implementar um ponto de extremidade padrão.</span><span class="sxs-lookup"><span data-stu-id="3a875-123">The following example shows how to implement a standard endpoint.</span></span>  
  
```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    { }  

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    { }  

    // Create the custom endpoint with a fixed binding
    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    // Definition of the additional property of this endpoint
    public bool Property { get; set; }
}
```
  
 <span data-ttu-id="3a875-124">Para usar um ponto de extremidade personalizado definido pelo usuário em um arquivo de configuração, você deve derivar uma classe de <xref:System.ServiceModel.Configuration.StandardEndpointElement> , derivar uma classe de <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> e registrar o novo ponto de extremidade padrão na seção extensões em app.config ou machine.config.  O <xref:System.ServiceModel.Configuration.StandardEndpointElement> fornece suporte de configuração para o ponto de extremidade padrão, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="3a875-124">To use a user-defined custom endpoint in a configuration file you must derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointElement>, derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>, and register the new standard endpoint in the extensions section in app.config or machine.config.  The <xref:System.ServiceModel.Configuration.StandardEndpointElement> provides configuration support for the standard endpoint, as shown in the following example.</span></span>  
  
```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    // Definition of the additional property for the standard endpoint element
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    // The additional property needs to be added to the properties of the standard endpoint element
    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    // Return the type of this standard endpoint
    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    // Create the custom service endpoint
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```  
  
 <span data-ttu-id="3a875-125">O <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> fornece o tipo de backup para a coleção que aparece na seção <`standardEndpoints`> na configuração do ponto de extremidade padrão.</span><span class="sxs-lookup"><span data-stu-id="3a875-125">The <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> provides the backing type for the collection that appears under the <`standardEndpoints`> section in the configuration for the standard endpoint.</span></span>  <span data-ttu-id="3a875-126">O exemplo a seguir mostra como implementar essa classe.</span><span class="sxs-lookup"><span data-stu-id="3a875-126">The following example shows how to implement this class.</span></span>  
  
```csharp
public class CustomEndpointCollectionElement : StandardEndpointCollectionElement<CustomEndpoint, CustomEndpointElement>
{
    // ...
}
```

<span data-ttu-id="3a875-127">O exemplo a seguir mostra como registrar um ponto de extremidade padrão na seção extensões.</span><span class="sxs-lookup"><span data-stu-id="3a875-127">The following example shows how to register a standard endpoint in the extensions section.</span></span>

```xml  
<extensions>  
      <standardEndpointExtensions>  
        <add  
          name="customStandardEndpoint"  
          type="CustomEndpointCollectionElement, Example.dll,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
      </standardEndpointExtensions>
</extensions>  
```  
  
## <a name="configuring-a-standard-endpoint"></a><span data-ttu-id="3a875-128">Configurando um ponto de extremidade padrão</span><span class="sxs-lookup"><span data-stu-id="3a875-128">Configuring a Standard Endpoint</span></span>  

 <span data-ttu-id="3a875-129">Os pontos de extremidade padrão podem ser adicionados no código ou na configuração.</span><span class="sxs-lookup"><span data-stu-id="3a875-129">Standard endpoints can be added in code or in configuration.</span></span>  <span data-ttu-id="3a875-130">Para adicionar um ponto de extremidade padrão no código, basta instanciar o tipo de ponto de extremidade padrão apropriado e adicioná-lo ao host de serviço, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="3a875-130">To add a standard endpoint in code simply instantiate the appropriate standard endpoint type and add it to the service host as shown in the following example:</span></span>  
  
```csharp  
serviceHost.AddServiceEndpoint(new CustomEndpoint());  
```  
  
 <span data-ttu-id="3a875-131">Para adicionar um ponto de extremidade padrão na configuração, adicione um `endpoint` elemento <> ao `service` elemento> <e quaisquer definições de configuração necessárias no `standardEndpoints` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="3a875-131">To add a standard endpoint in configuration, add an <`endpoint`> element to the <`service`> element and any needed configuration settings in the <`standardEndpoints`> element.</span></span> <span data-ttu-id="3a875-132">O exemplo a seguir mostra como adicionar um <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> , um dos pontos de extremidade padrão fornecidos com o [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a875-132">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, one of the standard endpoints that ships with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
```xml  
<services>  
  <service>  
    <endpoint isSystemEndpoint="true" kind="udpDiscoveryEndpoint" />  
  </service>  
</services>  
<standardEndpoints>
  <udpDiscoveryEndpoint>  
     <standardEndpoint multicastAddress="soap.udp://239.255.255.250:3702" />
  </udpDiscoveryEndpoint>
</standardEndpoints>
```  
  
 <span data-ttu-id="3a875-133">O tipo de ponto de extremidade padrão é especificado usando o atributo Kind no `endpoint` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="3a875-133">The type of standard endpoint is specified using the kind attribute in the <`endpoint`> element.</span></span> <span data-ttu-id="3a875-134">O ponto de extremidade é configurado dentro do `standardEndpoints` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="3a875-134">The endpoint is configured within the <`standardEndpoints`> element.</span></span> <span data-ttu-id="3a875-135">No exemplo acima, um <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> ponto de extremidade é adicionado e configurado.</span><span class="sxs-lookup"><span data-stu-id="3a875-135">In the example above, a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint is added and configured.</span></span> <span data-ttu-id="3a875-136">O `udpDiscoveryEndpoint` elemento <> contém um> de <`standardEndpoint` que define a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> Propriedade do <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> .</span><span class="sxs-lookup"><span data-stu-id="3a875-136">The <`udpDiscoveryEndpoint`> element contains a <`standardEndpoint`> that sets the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> property of the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span></span>  
  
## <a name="standard-endpoints-shipped-with-the-net-framework"></a><span data-ttu-id="3a875-137">Pontos de extremidade padrão fornecidos com o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3a875-137">Standard Endpoints Shipped with the .NET Framework</span></span>  

 <span data-ttu-id="3a875-138">A tabela a seguir lista os pontos de extremidade padrão fornecidos com o [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a875-138">The following table lists the standard endpoints shipped with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 `Mex Endpoint`  
 <span data-ttu-id="3a875-139">Um ponto de extremidade padrão que é usado para expor metadados de serviço.</span><span class="sxs-lookup"><span data-stu-id="3a875-139">A standard endpoint that is used to expose service metadata.</span></span>  
  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
 <span data-ttu-id="3a875-140">Um ponto de extremidade padrão usado pelos serviços para enviar mensagens de comunicado.</span><span class="sxs-lookup"><span data-stu-id="3a875-140">A standard endpoint that is used by services to send announcement messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
 <span data-ttu-id="3a875-141">Um ponto de extremidade padrão que é usado pelos serviços para enviar mensagens de descoberta.</span><span class="sxs-lookup"><span data-stu-id="3a875-141">A standard endpoint that is used by services to send discovery messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
 <span data-ttu-id="3a875-142">Um ponto de extremidade padrão pré-configurado para operações de descoberta por meio de uma associação multicast UDP.</span><span class="sxs-lookup"><span data-stu-id="3a875-142">A standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
 <span data-ttu-id="3a875-143">Um ponto de extremidade padrão usado pelos serviços para enviar mensagens de comunicado por meio de uma associação UDP.</span><span class="sxs-lookup"><span data-stu-id="3a875-143">A standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <span data-ttu-id="3a875-144">Um ponto de extremidade padrão que usa WS-Discovery para localizar o endereço do ponto de extremidade dinamicamente no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="3a875-144">A standard endpoint that uses WS-Discovery to find the endpoint address dynamically at runtime.</span></span>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataEndpoint>  
 <span data-ttu-id="3a875-145">Um ponto de extremidade padrão para troca de metadados.</span><span class="sxs-lookup"><span data-stu-id="3a875-145">A standard endpoint for metadata exchange.</span></span>  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <span data-ttu-id="3a875-146">Um ponto de extremidade padrão com uma <xref:System.ServiceModel.WebHttpBinding> associação que adiciona automaticamente o <xref:System.ServiceModel.Description.WebHttpBehavior> comportamento</span><span class="sxs-lookup"><span data-stu-id="3a875-146">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebHttpBehavior> behavior</span></span>  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <span data-ttu-id="3a875-147">Um ponto de extremidade padrão com uma <xref:System.ServiceModel.WebHttpBinding> associação que adiciona automaticamente o <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> comportamento.</span><span class="sxs-lookup"><span data-stu-id="3a875-147">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> behavior.</span></span>  
  
 <xref:System.ServiceModel.Description.WebServiceEndpoint>  
 <span data-ttu-id="3a875-148">Um ponto de extremidade padrão com uma <xref:System.ServiceModel.WebHttpBinding> associação.</span><span class="sxs-lookup"><span data-stu-id="3a875-148">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>  
 <span data-ttu-id="3a875-149">Um ponto de extremidade padrão que permite chamar operações de controle em instâncias de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3a875-149">A standard endpoint that enables you to call control operations on workflow instances.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>  
 <span data-ttu-id="3a875-150">Um ponto de extremidade padrão que dá suporte à criação de fluxo de trabalho e à continuação de indicador.</span><span class="sxs-lookup"><span data-stu-id="3a875-150">A standard endpoint that supports workflow creation and bookmark resumption.</span></span>
