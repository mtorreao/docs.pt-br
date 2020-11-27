---
title: Estendendo o sistema de metadados
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: 7113120a3cde6b4e6a7eb1d329da625e25996952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272977"
---
# <a name="extending-the-metadata-system"></a>Estendendo o sistema de metadados

O sistema de metadados do Windows Communication Foundation (WCF) é um grupo de classes e interfaces que representam os metadados necessários para implementar aplicativos baseados em serviço. Modifique ou estenda as classes ou implemente e configure as interfaces para exportar e importar metadados personalizados, como extensões WSDL (Web Services Description Language) ou declarações de WS-PolicyAttachments personalizadas.  
  
## <a name="in-this-section"></a>Nesta seção  

 [Exportando metadados personalizados para uma extensão do WCF](exporting-custom-metadata-for-a-wcf-extension.md)  
 Descreve como implementar e usar a <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface para inserir declarações de política personalizada em documentos WSDL.  
  
 [Importando metadados personalizados para uma extensão do WCF](importing-custom-metadata-for-a-wcf-extension.md)  
 Descreve como implementar e usar a <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface para ler e responder a declarações de política personalizadas em documentos WSDL.  
  
 [Publicando e recuperando metadados através de uma associação personalizada](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Descreve como trocar metadados em associações personalizadas.
