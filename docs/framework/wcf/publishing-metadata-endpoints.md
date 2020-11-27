---
title: Publicando pontos de extremidade de metadados
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 5be27a72c87d95e36a5b283e7930ba0a5191a5a1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249755"
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="85113-102">Publicando pontos de extremidade de metadados</span><span class="sxs-lookup"><span data-stu-id="85113-102">Publishing Metadata Endpoints</span></span>

<span data-ttu-id="85113-103">Os serviços Windows Communication Foundation (WCF) publicam metadados publicando um ou mais pontos de extremidade de metadados.</span><span class="sxs-lookup"><span data-stu-id="85113-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="85113-104">A publicação de metadados de serviço torna os metadados disponíveis usando protocolos padronizados, como WS-MetadataExchange (MEX) e solicitações HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="85113-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="85113-105">Os pontos de extremidade de metadados são semelhantes a outros pontos de extremidade de serviço, pois têm um endereço, uma associação e um contrato, e podem ser adicionados a um host de serviço por meio da configuração ou no código.</span><span class="sxs-lookup"><span data-stu-id="85113-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="85113-106">Para habilitar a publicação de pontos de extremidade de metadados, você deve adicionar o <xref:System.ServiceModel.Description.ServiceMetadataBehavior> comportamento do serviço ao serviço.</span><span class="sxs-lookup"><span data-stu-id="85113-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85113-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="85113-107">In This Section</span></span>  

 [<span data-ttu-id="85113-108">Como: publicar metadados para um serviço usando um arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="85113-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="85113-109">Demonstra como configurar um serviço WCF para publicar metadados para que os clientes possam recuperar os metadados usando uma WS-MetadataExchange ou uma solicitação HTTP/GET usando a `?wsdl` cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="85113-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="85113-110">Como: publicar metadados utilizando código para um serviço</span><span class="sxs-lookup"><span data-stu-id="85113-110">How to: Publish Metadata for a Service Using Code</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="85113-111">Demonstra como habilitar a publicação de metadados para um serviço WCF no código para que os clientes possam recuperar os metadados usando uma WS-MetadataExchange ou uma solicitação HTTP/GET usando a `?wsdl` cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="85113-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85113-112">Veja também</span><span class="sxs-lookup"><span data-stu-id="85113-112">See also</span></span>

- [<span data-ttu-id="85113-113">Publicando metadados</span><span class="sxs-lookup"><span data-stu-id="85113-113">Publishing Metadata</span></span>](./feature-details/publishing-metadata.md)
