---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: e095221e1f17cdf4a63c2fe86d5ba050e354e471
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240687"
---
# <a name="customchannelstester"></a><span data-ttu-id="0c681-102">CustomChannelsTester</span><span class="sxs-lookup"><span data-stu-id="0c681-102">CustomChannelsTester</span></span>

<span data-ttu-id="0c681-103">O `CustomChannelsTester` é uma ferramenta que você pode usar para testar suas implementações de canal personalizadas em um conjunto de contratos de serviço predefinidos.</span><span class="sxs-lookup"><span data-stu-id="0c681-103">The `CustomChannelsTester` is a tool that you can use to test your custom channel implementations against a set of predefined service contracts.</span></span> <span data-ttu-id="0c681-104">Você pode selecionar o conjunto de contratos de serviço e passá-lo para a ferramenta usando um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="0c681-104">You can select the set of service contracts and pass it to the tool using an XML file.</span></span> <span data-ttu-id="0c681-105">Em seguida, a ferramenta gera o serviço e o cliente que exercitam suas implementações de canal personalizadas durante a troca de mensagens.</span><span class="sxs-lookup"><span data-stu-id="0c681-105">The tool then generates the service and client that exercises your custom channel implementations during message exchange.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="0c681-106">Para criar a ferramenta</span><span class="sxs-lookup"><span data-stu-id="0c681-106">To build the tool</span></span>  
  
1. <span data-ttu-id="0c681-107">Para compilar a solução, siga as instruções em [criando os exemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c681-107">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="0c681-108">A criação da solução gera três arquivos: CustomChannelsTester.exe, TestSpec.xml e SampleRun. cmd.</span><span class="sxs-lookup"><span data-stu-id="0c681-108">Building the solution generates three files: CustomChannelsTester.exe, TestSpec.xml and SampleRun.cmd.</span></span> <span data-ttu-id="0c681-109">O arquivo SampleRun. cmd tem uma linha de comando de exemplo que mostra como usar essa ferramenta para testar o exemplo de [transporte: UDP](transport-udp.md) .</span><span class="sxs-lookup"><span data-stu-id="0c681-109">The file SampleRun.cmd has a sample command line that shows how to use this tool to test the [Transport: UDP](transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="0c681-110">Para executar a ferramenta</span><span class="sxs-lookup"><span data-stu-id="0c681-110">To run the tool</span></span>  
  
- <span data-ttu-id="0c681-111">No prompt de comando, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0c681-111">At the command prompt type the following command:</span></span>  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     <span data-ttu-id="0c681-112">O uso da `/binding` opção é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="0c681-112">Using the `/binding` option is required.</span></span>  
  
     <span data-ttu-id="0c681-113">`/dll` será necessário se "Binding" não for uma associação fornecida pelo sistema fornecida pelo Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0c681-113">`/dll` is required if "binding" is not a system-provided binding provided by Windows Communication Foundation (WCF).</span></span>  
  
     <span data-ttu-id="0c681-114">`/testspec` é opcional.</span><span class="sxs-lookup"><span data-stu-id="0c681-114">`/testspec` is optional.</span></span>  
  
     <span data-ttu-id="0c681-115">Isso cria servidores e clientes com base nas especificações de teste e na associação.</span><span class="sxs-lookup"><span data-stu-id="0c681-115">This creates server and clients based on the test specifications and the binding.</span></span>  
  
     <span data-ttu-id="0c681-116">Executa o cliente e o servidor e retorna os resultados.</span><span class="sxs-lookup"><span data-stu-id="0c681-116">Executes the client and server and returns the results.</span></span>  
  
     <span data-ttu-id="0c681-117">Este é o XML de exemplo para a descrição das especificações de teste (testspec.xml):</span><span class="sxs-lookup"><span data-stu-id="0c681-117">The following is the sample XML for the description of the test specifications (testspec.xml):</span></span>  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>
    <!-- Test a sessionful / sessionless contract-->
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the client. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
