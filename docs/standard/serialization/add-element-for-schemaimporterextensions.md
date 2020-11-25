---
title: Elemento <add> para <schemaImporterExtensions>
description: O <add> elemento Adiciona tipos usados pela classe XmlSchemaImporter para mapear tipos XSD para tipos .net.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: b8a0775e9d33d59606b1150aa9a1b3b1026d4b0b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726438"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="ef314-103">Elemento \<add> para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ef314-103">\<add> Element for \<schemaImporterExtensions></span></span>

<span data-ttu-id="ef314-104">Adiciona tipos usados pelo <xref:System.Xml.Serialization.XmlSchemaImporter> para mapear tipos XSD para tipos .net.</span><span class="sxs-lookup"><span data-stu-id="ef314-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET types.</span></span> <span data-ttu-id="ef314-105">Para obter mais informações sobre arquivos de configuração, consulte [Esquema de arquivos de configuração](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="ef314-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
\<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a><span data-ttu-id="ef314-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ef314-106">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef314-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ef314-107">Attributes and Elements</span></span>  

 <span data-ttu-id="ef314-108">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="ef314-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef314-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ef314-109">Attributes</span></span>  
  
|<span data-ttu-id="ef314-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="ef314-110">Attribute</span></span>|<span data-ttu-id="ef314-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="ef314-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef314-112">**name**</span><span class="sxs-lookup"><span data-stu-id="ef314-112">**name**</span></span>|<span data-ttu-id="ef314-113">Um nome simples que é usado para localizar a instância.</span><span class="sxs-lookup"><span data-stu-id="ef314-113">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="ef314-114">**tipo**</span><span class="sxs-lookup"><span data-stu-id="ef314-114">**type**</span></span>|<span data-ttu-id="ef314-115">Obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="ef314-115">Required.</span></span> <span data-ttu-id="ef314-116">Especifica a classe de extensão de esquema para adicionar.</span><span class="sxs-lookup"><span data-stu-id="ef314-116">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="ef314-117">O valor de atributo **type** deve ser uma linha e incluir o nome do tipo totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="ef314-117">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="ef314-118">Quando o assembly é colocado no GAC (cache de assembly global), ele também deve incluir a versão, cultura e token de chave pública do assembly assinado.</span><span class="sxs-lookup"><span data-stu-id="ef314-118">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef314-119">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ef314-119">Child Elements</span></span>  

 <span data-ttu-id="ef314-120">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ef314-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef314-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ef314-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ef314-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef314-122">Element</span></span>|<span data-ttu-id="ef314-123">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="ef314-123">Description</span></span>|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|<span data-ttu-id="ef314-124">Contém tipos que são usados pela <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="ef314-124">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ef314-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ef314-125">Example</span></span>  

 <span data-ttu-id="ef314-126">O exemplo de código a seguir adiciona um tipo de extensão que o XmlSchemaImporter pode usar ao mapear tipos.</span><span class="sxs-lookup"><span data-stu-id="ef314-126">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
       PublicKeyToken=b03f5f7f11d50a3a" />
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef314-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="ef314-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="ef314-128">\<system.xml.serialization> Elementos</span><span class="sxs-lookup"><span data-stu-id="ef314-128">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="ef314-129">\<schemaImporterExtensions> Elementos</span><span class="sxs-lookup"><span data-stu-id="ef314-129">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
