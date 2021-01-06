---
title: Visão geral do SDK do Azure para .NET
description: Fornece uma visão geral do que é o SDK do Azure para .NET e as etapas básicas para usar o SDK em um aplicativo .NET
ms.date: 11/30/2020
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 3ec1ee9e8da3a6e03581ce2a29a655ec0d68fe54
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701056"
---
# <a name="azure-sdk-for-net-overview"></a><span data-ttu-id="9f939-103">Visão geral do SDK do Azure para .NET</span><span class="sxs-lookup"><span data-stu-id="9f939-103">Azure SDK for .NET overview</span></span>

## <a name="what-is-the-azure-sdk-for-net"></a><span data-ttu-id="9f939-104">O que é o SDK do Azure para .NET</span><span class="sxs-lookup"><span data-stu-id="9f939-104">What is the Azure SDK for .NET</span></span>

<span data-ttu-id="9f939-105">O **SDK do Azure para .net** foi projetado para facilitar o uso dos serviços do Azure de seus aplicativos .net.</span><span class="sxs-lookup"><span data-stu-id="9f939-105">The **Azure SDK for .NET** is designed to make it easy to use Azure services from your .NET applications.</span></span>  <span data-ttu-id="9f939-106">Se estiver carregando e baixando arquivos no armazenamento de BLOBs, recuperando os segredos do aplicativo de Azure Key Vault ou processando notificações de hubs de eventos do Azure, o SDK do Azure para .NET fornece uma interface consistente e familiar para acessar os serviços do Azure.</span><span class="sxs-lookup"><span data-stu-id="9f939-106">Whether it is uploading and downloading files to Blob Storage, retrieving application secrets from Azure Key Vault, or processing notifications from Azure Event Hubs, the Azure SDK for .NET provides a consistent and familiar interface to access Azure services.</span></span>  

<span data-ttu-id="9f939-107">O SDK do Azure para .NET está disponível como uma série de pacotes NuGet que podem ser usados em aplicativos .NET Core (2,1 e superior) e .NET Framework (4.6.1 e superior).</span><span class="sxs-lookup"><span data-stu-id="9f939-107">The Azure SDK for .NET is available as series of NuGet packages that can be used in both .NET Core (2.1 and higher) and .NET Framework (4.6.1 and higher) applications.</span></span>

![Diagrama mostrando como os aplicativos .NET usam o SDK do Azure para acessar os serviços do Azure](./media/azure-sdk-for-dotnet-overview.png)

## <a name="use-the-azure-sdk-for-net-in-your-applications"></a><span data-ttu-id="9f939-109">Usar o SDK do Azure para .NET em seus aplicativos</span><span class="sxs-lookup"><span data-stu-id="9f939-109">Use the Azure SDK for .NET in your applications</span></span>

<span data-ttu-id="9f939-110">Para usar um pacote do SDK do Azure em um de seus aplicativos .NET, você deve seguir estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9f939-110">To use an Azure SDK package in one of your .NET applications, you want to follow these steps.</span></span>

1. <span data-ttu-id="9f939-111">**Localize o pacote SDK apropriado-** Use a [lista pacote](../packages.md) para localizar o pacote apropriado para o serviço do Azure com o qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="9f939-111">**Locate the appropriate SDK package -** Use the [package list](../packages.md) to find the appropriate package for the Azure service you are working with.</span></span>  <span data-ttu-id="9f939-112">É recomendável que a maioria dos serviços tenha um pacote de cliente para trabalhar com o serviço e um pacote de gerenciamento para criar e gerenciar instâncias do serviço.</span><span class="sxs-lookup"><span data-stu-id="9f939-112">Be advised that most services have a client package for working with the service and a management package for creating and managing instances of the service.</span></span>  <span data-ttu-id="9f939-113">Na maioria dos casos, você desejará o pacote do cliente.</span><span class="sxs-lookup"><span data-stu-id="9f939-113">In most cases, you will want the client package.</span></span>  <span data-ttu-id="9f939-114">Instale este pacote em seu aplicativo usando o NuGet.</span><span class="sxs-lookup"><span data-stu-id="9f939-114">Install this package in your application using NuGet.</span></span>

2. <span data-ttu-id="9f939-115">**Configurar a autenticação para seu aplicativo-** Para acessar os recursos do Azure, seu aplicativo precisará ter as credenciais apropriadas e os direitos de acesso atribuídos no Azure.</span><span class="sxs-lookup"><span data-stu-id="9f939-115">**Set up authentication for your application -** To access Azure resources, your application will need to have the appropriate credentials and access rights assigned in Azure.</span></span>  <span data-ttu-id="9f939-116">Saiba como configurar a autenticação na [autenticação de aplicativos .net para o Azure](../authentication.md).</span><span class="sxs-lookup"><span data-stu-id="9f939-116">Learn how to configure authentication in [Authenticating .NET applications to Azure](../authentication.md).</span></span>

3. <span data-ttu-id="9f939-117">**Escrever código usando o SDK em seu aplicativo-** Ao trabalhar com os serviços do Azure, seu código criará primeiro um objeto de cliente para trabalhar com o serviço e, em seguida, chamará métodos nesse objeto de cliente para interagir com o serviço.</span><span class="sxs-lookup"><span data-stu-id="9f939-117">**Write code using the SDK in your application -** When working with Azure services, your code will first create a client object to work with the service and then call methods on that client object to interact with the service.</span></span>  <span data-ttu-id="9f939-118">Os métodos síncrono e assíncrono são fornecidos.</span><span class="sxs-lookup"><span data-stu-id="9f939-118">Both synchronous and asynchronous methods are provided.</span></span>  <span data-ttu-id="9f939-119">Os exemplos de uso de cada pacote do SDK individual são fornecidos em toda a documentação do Azure.</span><span class="sxs-lookup"><span data-stu-id="9f939-119">Examples of using each individual SDK package are provided throughout the Azure documentation.</span></span>

4. <span data-ttu-id="9f939-120">**Configurar o registro em log para o SDK (opcional)-** Se precisar diagnosticar problemas entre seu aplicativo e o Azure, você poderá [habilitar o registro em log no SDK do Azure para .net](./logging.md).</span><span class="sxs-lookup"><span data-stu-id="9f939-120">**Configure logging for the SDK (optional) -** If you need to diagnose issues between your application and Azure, you can [enable logging in the Azure SDK for .NET](./logging.md).</span></span>
