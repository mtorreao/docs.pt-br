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
# <a name="extending-the-metadata-system"></a><span data-ttu-id="a68f3-102">Estendendo o sistema de metadados</span><span class="sxs-lookup"><span data-stu-id="a68f3-102">Extending the Metadata System</span></span>

<span data-ttu-id="a68f3-103">O sistema de metadados do Windows Communication Foundation (WCF) é um grupo de classes e interfaces que representam os metadados necessários para implementar aplicativos baseados em serviço.</span><span class="sxs-lookup"><span data-stu-id="a68f3-103">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="a68f3-104">Modifique ou estenda as classes ou implemente e configure as interfaces para exportar e importar metadados personalizados, como extensões WSDL (Web Services Description Language) ou declarações de WS-PolicyAttachments personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a68f3-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a68f3-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a68f3-105">In This Section</span></span>  

 [<span data-ttu-id="a68f3-106">Exportando metadados personalizados para uma extensão do WCF</span><span class="sxs-lookup"><span data-stu-id="a68f3-106">Exporting Custom Metadata for a WCF Extension</span></span>](exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="a68f3-107">Descreve como implementar e usar a <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface para inserir declarações de política personalizada em documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="a68f3-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="a68f3-108">Importando metadados personalizados para uma extensão do WCF</span><span class="sxs-lookup"><span data-stu-id="a68f3-108">Importing Custom Metadata for a WCF Extension</span></span>](importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="a68f3-109">Descreve como implementar e usar a <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface para ler e responder a declarações de política personalizadas em documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="a68f3-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="a68f3-110">Publicando e recuperando metadados através de uma associação personalizada</span><span class="sxs-lookup"><span data-stu-id="a68f3-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="a68f3-111">Descreve como trocar metadados em associações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a68f3-111">Describes how to exchange metadata over custom bindings.</span></span>
