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
# <a name="publishing-metadata-endpoints"></a>Publicando pontos de extremidade de metadados

Os serviços Windows Communication Foundation (WCF) publicam metadados publicando um ou mais pontos de extremidade de metadados. A publicação de metadados de serviço torna os metadados disponíveis usando protocolos padronizados, como WS-MetadataExchange (MEX) e solicitações HTTP/GET. Os pontos de extremidade de metadados são semelhantes a outros pontos de extremidade de serviço, pois têm um endereço, uma associação e um contrato, e podem ser adicionados a um host de serviço por meio da configuração ou no código. Para habilitar a publicação de pontos de extremidade de metadados, você deve adicionar o <xref:System.ServiceModel.Description.ServiceMetadataBehavior> comportamento do serviço ao serviço.  
  
## <a name="in-this-section"></a>Nesta seção  

 [Como: publicar metadados para um serviço usando um arquivo de configuração](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Demonstra como configurar um serviço WCF para publicar metadados para que os clientes possam recuperar os metadados usando uma WS-MetadataExchange ou uma solicitação HTTP/GET usando a `?wsdl` cadeia de caracteres de consulta.  
  
 [Como: publicar metadados utilizando código para um serviço](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Demonstra como habilitar a publicação de metadados para um serviço WCF no código para que os clientes possam recuperar os metadados usando uma WS-MetadataExchange ou uma solicitação HTTP/GET usando a `?wsdl` cadeia de caracteres de consulta.  
  
## <a name="see-also"></a>Veja também

- [Publicando metadados](./feature-details/publishing-metadata.md)
