---
title: 'Como: definir configurações de serviço de COM+'
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
ms.openlocfilehash: b75f5c2a64b7184959e929439893b33193aa7bae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257464"
---
# <a name="how-to-configure-com-service-settings"></a><span data-ttu-id="70830-102">Como: definir configurações de serviço de COM+</span><span class="sxs-lookup"><span data-stu-id="70830-102">How to: Configure COM+ Service Settings</span></span>

<span data-ttu-id="70830-103">Quando uma interface de aplicativo é adicionada ou removida usando a ferramenta de configuração de serviço COM+, a configuração do serviço Web é atualizada no arquivo de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="70830-103">When an application interface is added or removed by using the COM+ Service Configuration tool, the Web service configuration is updated within the application's configuration file.</span></span> <span data-ttu-id="70830-104">No modo hospedado do COM+, o arquivo de Application.config é colocado no diretório raiz do aplicativo (%PROGRAMFILES%\ComPlus Applications \\ {AppID} é o padrão).</span><span class="sxs-lookup"><span data-stu-id="70830-104">In the COM+ hosted mode, the Application.config file is placed in the Application Root Directory (%PROGRAMFILES%\ComPlus Applications\\{appid} is the default).</span></span> <span data-ttu-id="70830-105">Em qualquer um dos modos hospedados na Web, o arquivo de Web.config é colocado no diretório vroot especificado.</span><span class="sxs-lookup"><span data-stu-id="70830-105">In either of the Web-hosted modes, the Web.config file is placed in the specified vroot directory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70830-106">A assinatura de mensagens deve ser usada para proteger contra violação de mensagens entre um cliente e um servidor.</span><span class="sxs-lookup"><span data-stu-id="70830-106">Message signing should be used to protect against tampering of messages between a client and a server.</span></span> <span data-ttu-id="70830-107">Além disso, a criptografia da camada de transporte ou de mensagem deve ser usada para proteger contra a divulgação de informações de mensagens entre um cliente e um servidor.</span><span class="sxs-lookup"><span data-stu-id="70830-107">Also, message or transport layer encryption should be used to protect against information disclosure from messages between a client and a server.</span></span> <span data-ttu-id="70830-108">Assim como acontece com os serviços do Windows Communication Foundation (WCF), você deve usar a limitação para limitar o número de chamadas simultâneas, conexões, instâncias e operações pendentes.</span><span class="sxs-lookup"><span data-stu-id="70830-108">As with Windows Communication Foundation (WCF) services, you should use throttling to limit the number of concurrent calls, connections, instances, and pending operations.</span></span> <span data-ttu-id="70830-109">Isso ajuda a evitar o excesso de consumo de recursos.</span><span class="sxs-lookup"><span data-stu-id="70830-109">This helps prevent over-consumption of resources.</span></span> <span data-ttu-id="70830-110">O comportamento de limitação é especificado por meio das configurações do arquivo de configuração de serviço.</span><span class="sxs-lookup"><span data-stu-id="70830-110">Throttling behavior is specified through service configuration file settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70830-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="70830-111">Example</span></span>  

 <span data-ttu-id="70830-112">Considere um componente que implementa a seguinte interface:</span><span class="sxs-lookup"><span data-stu-id="70830-112">Consider a component that implements the following interface:</span></span>  
  
```csharp
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 <span data-ttu-id="70830-113">Se o componente for exposto como um serviço Web, o contrato de serviço correspondente que é exposto e os clientes precisarem estar em conformidade, será o seguinte:</span><span class="sxs-lookup"><span data-stu-id="70830-113">If the component is exposed as a Web service, the corresponding service contract that is exposed, and that clients would need to conform to, is as follows:</span></span>  
  
```csharp
[ServiceContract(Session = true,  
Namespace = "http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7",  
Name = "IFinances")]  
public interface IFinancesContract : IDisposable  
{  
    [OperationContract]  
    string Debit(string accountNo, double amount);  
    [OperationContract]  
    string Credit(string accountNo, double amount);  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="70830-114">Os formulários de IID fazem parte do namespace inicial do contrato.</span><span class="sxs-lookup"><span data-stu-id="70830-114">IID forms part of the initial namespace for the contract.</span></span>  
  
 <span data-ttu-id="70830-115">Os aplicativos cliente que usam esse serviço precisariam estar em conformidade com esse contrato, juntamente com o uso de uma associação compatível com aquela especificada na configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="70830-115">Client applications that use this service would need to conform to this contract, along with using a binding that is compatible with the one specified in the application configuration.</span></span>  
  
 <span data-ttu-id="70830-116">O exemplo de código a seguir mostra um arquivo de configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="70830-116">The following code example shows a default configuration file.</span></span> <span data-ttu-id="70830-117">Sendo um serviço Web Windows Communication Foundation (WCF), isso está em conformidade com o esquema de configuração do modelo de serviço padrão e pode ser editado da mesma forma que outros arquivos de configuração de serviços WCF.</span><span class="sxs-lookup"><span data-stu-id="70830-117">Being a Windows Communication Foundation (WCF) Web service, this conforms to the standard service model configuration schema and can be edited in the same way as other WCF services configuration files.</span></span>  
  
 <span data-ttu-id="70830-118">As modificações típicas incluem:</span><span class="sxs-lookup"><span data-stu-id="70830-118">Typical modifications would include:</span></span>  
  
- <span data-ttu-id="70830-119">Alterar o endereço do ponto de extremidade do formulário ApplicationName/ComponentName/InterfaceName padrão para um formulário mais utilizável.</span><span class="sxs-lookup"><span data-stu-id="70830-119">Changing the endpoint address from the default ApplicationName/ComponentName/InterfaceName form to a more usable form.</span></span>  
  
- <span data-ttu-id="70830-120">Modificar o namespace do serviço do `http://tempuri.org/InterfaceID` formulário padrão para um formulário mais relevante.</span><span class="sxs-lookup"><span data-stu-id="70830-120">Modifying the namespace of the service from the default `http://tempuri.org/InterfaceID` form to a more relevant form.</span></span>  
  
- <span data-ttu-id="70830-121">Alterando o ponto de extremidade para usar uma associação de transporte diferente.</span><span class="sxs-lookup"><span data-stu-id="70830-121">Changing the endpoint to use a different transport binding.</span></span>  
  
     <span data-ttu-id="70830-122">No caso hospedado no COM+, o transporte de pipes nomeados é usado por padrão, mas um transporte fora da máquina, como o TCP, pode ser usado em vez disso.</span><span class="sxs-lookup"><span data-stu-id="70830-122">In the COM+-hosted case, the named pipes transport is used by default, but an off-machine transport like TCP can be used instead.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="comNonTransactionalBinding" />  
                <binding name="comTransactionalBinding" transactionFlow="true" />  
            </netNamedPipeBinding>  
        </bindings>  
        <comContracts>  
            <comContract contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"  
                name="IFinances" namespace="http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7"  
                requiresSession="true">  
                <exposedMethods>  
                    <add exposedMethod="Debit" />  
                    <add exposedMethod="Credit" />  
                </exposedMethods>  
            </comContract>  
        </comContracts>  
        <services>  
            <service name="{DCDB24CC-0B19-4534-95CD-FBBFF4D67DD9},{C942B840-AD54-4A44-B5F7-928130980AB9}">  
                <endpoint address="IFinances" binding="netNamedPipeBinding" bindingConfiguration="comNonTransactionalBinding"  
                    contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" />  
                <host>  
                    <baseAddresses>  
                        <add baseAddress="net.pipe://localhost/ServiceModelDocSampleApp/ServiceModelDocSample.esFinance" />  
                    </baseAddresses>  
                </host>  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70830-123">Veja também</span><span class="sxs-lookup"><span data-stu-id="70830-123">See also</span></span>

- [<span data-ttu-id="70830-124">Integração com aplicativos COM+</span><span class="sxs-lookup"><span data-stu-id="70830-124">Integrating with COM+ Applications</span></span>](integrating-with-com-plus-applications.md)
