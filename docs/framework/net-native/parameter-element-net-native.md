---
title: <Parameter> (.NET Nativo)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
ms.openlocfilehash: 7e812ab60eb0a89eb868346733a8ea74e2f76d3e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287859"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="0830e-102">\<Parameter> (.NET Nativo)</span><span class="sxs-lookup"><span data-stu-id="0830e-102">\<Parameter> Element (.NET Native)</span></span>

<span data-ttu-id="0830e-103">Aplica a política de tempo de reflexão ao tipo do argumento passado para um método.</span><span class="sxs-lookup"><span data-stu-id="0830e-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0830e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0830e-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0830e-105">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0830e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0830e-106">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="0830e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0830e-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="0830e-107">Attributes</span></span>  
  
|<span data-ttu-id="0830e-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="0830e-108">Attribute</span></span>|<span data-ttu-id="0830e-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="0830e-109">Attribute type</span></span>|<span data-ttu-id="0830e-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="0830e-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0830e-111">Geral</span><span class="sxs-lookup"><span data-stu-id="0830e-111">General</span></span>|<span data-ttu-id="0830e-112">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="0830e-112">Required attribute.</span></span> <span data-ttu-id="0830e-113">O nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0830e-113">The parameter name.</span></span> <span data-ttu-id="0830e-114">Por exemplo, para a assinatura do método `String.CompareTo(Object value)`, o valor do atributo `Name` é "value".</span><span class="sxs-lookup"><span data-stu-id="0830e-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="0830e-115">Reflexão</span><span class="sxs-lookup"><span data-stu-id="0830e-115">Reflection</span></span>|<span data-ttu-id="0830e-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0830e-116">Optional attribute.</span></span> <span data-ttu-id="0830e-117">Controla o acesso de runtime a construtores para habilitar a ativação de instâncias.</span><span class="sxs-lookup"><span data-stu-id="0830e-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="0830e-118">Reflexão</span><span class="sxs-lookup"><span data-stu-id="0830e-118">Reflection</span></span>|<span data-ttu-id="0830e-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0830e-119">Optional attribute.</span></span> <span data-ttu-id="0830e-120">Controla a consulta para obter informações sobre elementos do programa, mas não permite qualquer acesso de runtime.</span><span class="sxs-lookup"><span data-stu-id="0830e-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="0830e-121">Reflexão</span><span class="sxs-lookup"><span data-stu-id="0830e-121">Reflection</span></span>|<span data-ttu-id="0830e-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0830e-122">Optional attribute.</span></span> <span data-ttu-id="0830e-123">Controla o acesso a todos os tipos de membro ao runtime, incluindo construtores, métodos, campos, propriedades e eventos, habilitando a programação dinâmica.</span><span class="sxs-lookup"><span data-stu-id="0830e-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="0830e-124">Serialização</span><span class="sxs-lookup"><span data-stu-id="0830e-124">Serialization</span></span>|<span data-ttu-id="0830e-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0830e-125">Optional attribute.</span></span> <span data-ttu-id="0830e-126">Controla o acesso ao runtime para construtores, campos e propriedades para habilitar a serialização e desserialização das instâncias por bibliotecas como o serializador Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="0830e-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="0830e-127">Serialização</span><span class="sxs-lookup"><span data-stu-id="0830e-127">Serialization</span></span>|<span data-ttu-id="0830e-128">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0830e-128">Optional attribute.</span></span> <span data-ttu-id="0830e-129">Controla a política de serialização que usa a classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0830e-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="0830e-130">Serialização</span><span class="sxs-lookup"><span data-stu-id="0830e-130">Serialization</span></span>|<span data-ttu-id="0830e-131">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0830e-131">Optional attribute.</span></span> <span data-ttu-id="0830e-132">Controla a política de serialização JSON que usa a classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0830e-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="0830e-133">Serialização</span><span class="sxs-lookup"><span data-stu-id="0830e-133">Serialization</span></span>|<span data-ttu-id="0830e-134">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0830e-134">Optional attribute.</span></span> <span data-ttu-id="0830e-135">Controla a política de serialização XML que usa a classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0830e-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="0830e-136">Interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="0830e-136">Interop</span></span>|<span data-ttu-id="0830e-137">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0830e-137">Optional attribute.</span></span> <span data-ttu-id="0830e-138">Controla a política de marshaling de tipos de referência do WinRT e COM.</span><span class="sxs-lookup"><span data-stu-id="0830e-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="0830e-139">Interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="0830e-139">Interop</span></span>|<span data-ttu-id="0830e-140">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0830e-140">Optional attribute.</span></span> <span data-ttu-id="0830e-141">Controla a diretiva de marshaling de tipos delegados como ponteiros de função para código nativo.</span><span class="sxs-lookup"><span data-stu-id="0830e-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="0830e-142">Interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="0830e-142">Interop</span></span>|<span data-ttu-id="0830e-143">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0830e-143">Optional attribute.</span></span> <span data-ttu-id="0830e-144">Controla a política de marshaling de tipos de valor para código nativo.</span><span class="sxs-lookup"><span data-stu-id="0830e-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0830e-145">Atributo de nome</span><span class="sxs-lookup"><span data-stu-id="0830e-145">Name attribute</span></span>  
  
|<span data-ttu-id="0830e-146">Valor</span><span class="sxs-lookup"><span data-stu-id="0830e-146">Value</span></span>|<span data-ttu-id="0830e-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="0830e-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0830e-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="0830e-148">*parameter_name*</span></span>|<span data-ttu-id="0830e-149">O nome do parâmetro de método aos quais a política é aplicada.</span><span class="sxs-lookup"><span data-stu-id="0830e-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="0830e-150">Por exemplo, para a assinatura do método `String.CompareTo(Object value)`, o valor do atributo `Name` é "value".</span><span class="sxs-lookup"><span data-stu-id="0830e-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0830e-151">Todos os outros atributos</span><span class="sxs-lookup"><span data-stu-id="0830e-151">All other attributes</span></span>  
  
|<span data-ttu-id="0830e-152">Valor</span><span class="sxs-lookup"><span data-stu-id="0830e-152">Value</span></span>|<span data-ttu-id="0830e-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="0830e-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0830e-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0830e-154">*policy_setting*</span></span>|<span data-ttu-id="0830e-155">A configuração a ser aplicada a este tipo de política.</span><span class="sxs-lookup"><span data-stu-id="0830e-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="0830e-156">Os valores possíveis são `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`.</span><span class="sxs-lookup"><span data-stu-id="0830e-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="0830e-157">Para obter mais informações, consulte [Configurações da política da diretiva de runtime](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0830e-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0830e-158">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0830e-158">Child Elements</span></span>  

 <span data-ttu-id="0830e-159">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0830e-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0830e-160">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0830e-160">Parent Elements</span></span>  
  
|<span data-ttu-id="0830e-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="0830e-161">Element</span></span>|<span data-ttu-id="0830e-162">Descrição</span><span class="sxs-lookup"><span data-stu-id="0830e-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="0830e-163">Aplica a política de reflexão de runtime a um construtor ou método.</span><span class="sxs-lookup"><span data-stu-id="0830e-163">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0830e-164">Comentários</span><span class="sxs-lookup"><span data-stu-id="0830e-164">Remarks</span></span>  

 <span data-ttu-id="0830e-165">O `<Parameter>` elemento é um filho do [\<Method>](method-element-net-native.md) elemento e é usado para aplicar a política a um parâmetro de método específico.</span><span class="sxs-lookup"><span data-stu-id="0830e-165">The `<Parameter>` element is a child of the [\<Method>](method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="0830e-166">O parâmetro de método específico é especificado pelo nome em vez de por tipo.</span><span class="sxs-lookup"><span data-stu-id="0830e-166">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="0830e-167">Pelo menos um atributo que representa um tipo de política, como `Activate` ou `Dynamic`, deve estar presente.</span><span class="sxs-lookup"><span data-stu-id="0830e-167">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0830e-168">Veja também</span><span class="sxs-lookup"><span data-stu-id="0830e-168">See also</span></span>

- [<span data-ttu-id="0830e-169">\<Method> Elementos</span><span class="sxs-lookup"><span data-stu-id="0830e-169">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="0830e-170">Referência do arquivo de configuração de diretivas do runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="0830e-170">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0830e-171">Configurações da política da diretiva de runtime</span><span class="sxs-lookup"><span data-stu-id="0830e-171">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="0830e-172">Elementos da diretiva de runtime</span><span class="sxs-lookup"><span data-stu-id="0830e-172">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
