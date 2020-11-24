---
title: Elemento <xmlSerializer>
description: O <xmlSerializer> elemento especifica se uma verificação adicional de progresso do XmlSerializer é feita.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 6f368880c97a21dc3e9593ecb2319d265a1b8932
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676485"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="4959e-103">Elemento \<xmlSerializer></span><span class="sxs-lookup"><span data-stu-id="4959e-103">\<xmlSerializer> Element</span></span>

<span data-ttu-id="4959e-104">Especifica se uma verificação adicional de progresso do <xref:System.Xml.Serialization.XmlSerializer> é feita.</span><span class="sxs-lookup"><span data-stu-id="4959e-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a><span data-ttu-id="4959e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4959e-105">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4959e-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4959e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="4959e-107">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="4959e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4959e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="4959e-108">Attributes</span></span>  
  
|<span data-ttu-id="4959e-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="4959e-109">Attribute</span></span>|<span data-ttu-id="4959e-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="4959e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4959e-111">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="4959e-111">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="4959e-112">Especifica se o progresso do <xref:System.Xml.Serialization.XmlSerializer> é verificado.</span><span class="sxs-lookup"><span data-stu-id="4959e-112">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="4959e-113">Defina o atributo como "true" ou "false".</span><span class="sxs-lookup"><span data-stu-id="4959e-113">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="4959e-114">O padrão é "true".</span><span class="sxs-lookup"><span data-stu-id="4959e-114">The default is "true".</span></span>|  
|<span data-ttu-id="4959e-115">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="4959e-115">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="4959e-116">Especifica se o <xref:System.Xml.Serialization.XmlSerializer> usa a geração de serialização herdada que gera assemblies escrevendo código C# em um arquivo e, em seguida, compilando-o em um assembly.</span><span class="sxs-lookup"><span data-stu-id="4959e-116">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="4959e-117">O padrão é **false**.</span><span class="sxs-lookup"><span data-stu-id="4959e-117">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4959e-118">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="4959e-118">Child Elements</span></span>  

 <span data-ttu-id="4959e-119">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="4959e-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4959e-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="4959e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4959e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4959e-121">Element</span></span>|<span data-ttu-id="4959e-122">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4959e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4959e-123">\<system.xml.serialization> Elementos</span><span class="sxs-lookup"><span data-stu-id="4959e-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="4959e-124">Contém definições de configuração para as classes <xref:System.Xml.Serialization.XmlSerializer> e <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="4959e-124">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4959e-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="4959e-125">Remarks</span></span>  

 <span data-ttu-id="4959e-126">Por padrão, o <xref:System.Xml.Serialization.XmlSerializer> fornece uma camada adicional de segurança contra potenciais ataques de negação de serviço ao desserializar dados não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="4959e-126">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="4959e-127">Ele faz isso tentando detectar loops infinitos durante a desserialização.</span><span class="sxs-lookup"><span data-stu-id="4959e-127">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="4959e-128">Se uma condição desse tipo for detectada, uma exceção será gerada com a seguinte mensagem: “Erro interno: a desserialização não pôde avançar sobre o fluxo subjacente”.</span><span class="sxs-lookup"><span data-stu-id="4959e-128">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="4959e-129">Receber essa mensagem não necessariamente indica que um ataque de negação de serviço esteja em andamento.</span><span class="sxs-lookup"><span data-stu-id="4959e-129">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="4959e-130">Em algumas circunstâncias raras, o mecanismo de detecção de loop infinito produz um falso positivo e a exceção é gerada para uma mensagem de entrada legítima.</span><span class="sxs-lookup"><span data-stu-id="4959e-130">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="4959e-131">Se você achar que em seus aplicativos específicos mensagens legítimas estão sendo rejeitadas por essa camada extra de proteção, defina o atributo **checkDeserializeAdvances** como “false”.</span><span class="sxs-lookup"><span data-stu-id="4959e-131">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="4959e-132">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4959e-132">Example</span></span>  

 <span data-ttu-id="4959e-133">O exemplo de código a seguir define o atributo **checkDeserializeAdvances** como “false”.</span><span class="sxs-lookup"><span data-stu-id="4959e-133">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4959e-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="4959e-134">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="4959e-135">\<system.xml.serialization> Elementos</span><span class="sxs-lookup"><span data-stu-id="4959e-135">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="4959e-136">Serialização XML e SOAP</span><span class="sxs-lookup"><span data-stu-id="4959e-136">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
