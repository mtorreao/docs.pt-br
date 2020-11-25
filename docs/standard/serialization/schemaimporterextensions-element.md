---
title: Elemento <schemaImporterExtensions>
description: O <schemaImporterExtensions> elemento contém tipos que são usados pelo XmlSchemaImporter para mapeamento de tipos XSD para tipos .net.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 6b644ed1112b748be4dd301d6fa6f2a6416dc67e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722135"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="34d2a-103">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="34d2a-103">\<schemaImporterExtensions> element</span></span>

<span data-ttu-id="34d2a-104">Contém tipos que são usados pelo <xref:System.Xml.Serialization.XmlSchemaImporter> para mapeamento de tipos XSD para tipos .net.</span><span class="sxs-lookup"><span data-stu-id="34d2a-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET types.</span></span> <span data-ttu-id="34d2a-105">Para obter mais informações sobre arquivos de configuração, consulte [Esquema de arquivos de configuração](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="34d2a-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34d2a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="34d2a-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="34d2a-107">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="34d2a-107">Child Elements</span></span>  
  
|<span data-ttu-id="34d2a-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="34d2a-108">Element</span></span>|<span data-ttu-id="34d2a-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="34d2a-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34d2a-110">\<add> Elemento para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="34d2a-110">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)|<span data-ttu-id="34d2a-111">Adiciona tipos que são usados pela <xref:System.Xml.Serialization.XmlSchemaImporter> para criar mapeamentos.</span><span class="sxs-lookup"><span data-stu-id="34d2a-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="34d2a-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="34d2a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="34d2a-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="34d2a-113">Element</span></span>|<span data-ttu-id="34d2a-114">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="34d2a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34d2a-115">\<system.xml.serialization> Elementos</span><span class="sxs-lookup"><span data-stu-id="34d2a-115">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="34d2a-116">O elemento de nível superior para controlar a serialização XML.</span><span class="sxs-lookup"><span data-stu-id="34d2a-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="34d2a-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="34d2a-117">Example</span></span>  

 <span data-ttu-id="34d2a-118">O exemplo de código a seguir ilustra como adicionar tipos que são usados pelo <xref:System.Xml.Serialization.XmlSchemaImporter> ao mapear tipos XSD para tipos .net.</span><span class="sxs-lookup"><span data-stu-id="34d2a-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =
        "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34d2a-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="34d2a-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="34d2a-120">Esquema do arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="34d2a-120">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="34d2a-121">\<dateTimeSerialization> Elementos</span><span class="sxs-lookup"><span data-stu-id="34d2a-121">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="34d2a-122">\<add> Elemento para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="34d2a-122">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="34d2a-123">\<system.xml.serialization> Elementos</span><span class="sxs-lookup"><span data-stu-id="34d2a-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
