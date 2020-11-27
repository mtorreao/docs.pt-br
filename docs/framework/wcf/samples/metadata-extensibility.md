---
title: Extensibilidade de metadados
ms.date: 03/30/2017
ms.assetid: f92fcc76-0806-4c84-9d63-7aae0d3899de
ms.openlocfilehash: fb37e33026a5f99bfa033f04eea0bb85fbbe65c7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294320"
---
# <a name="metadata-extensibility"></a>Extensibilidade de metadados

Esta seção contém exemplos que demonstram metadados personalizados.  
  
## <a name="in-this-section"></a>Nesta seção  

 [Ponto de extremidade de metadados seguros personalizados](custom-secure-metadata-endpoint.md)  
 Demonstra como implementar um serviço com um ponto de extremidade de metadados seguro que usa uma das associações de troca de não-metadados e como configurar a [ferramenta de utilitário de metadados ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) ou clientes para buscar os metadados desse ponto de extremidade de metadados.  
  
 [Publicação personalizada de WSDL](custom-wsdl-publication.md)  
 Demonstra como implementar um <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> em um atributo personalizado <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> para exportar Propriedades de atributo como anotações WSDL, entre outras funcionalidades.
