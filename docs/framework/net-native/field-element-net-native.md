---
title: <Field> (.NET Nativo)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
ms.openlocfilehash: e63dc293c42aa620b7f7ac15fc0454bc603b9dde
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251042"
---
# <a name="field-element-net-native"></a><span data-ttu-id="acb91-102">\<Field> (.NET Nativo)</span><span class="sxs-lookup"><span data-stu-id="acb91-102">\<Field> Element (.NET Native)</span></span>

<span data-ttu-id="acb91-103">Aplica a política de reflexão do runtime a um campo.</span><span class="sxs-lookup"><span data-stu-id="acb91-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb91-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="acb91-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acb91-105">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="acb91-105">Attributes and Elements</span></span>  

 <span data-ttu-id="acb91-106">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="acb91-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acb91-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="acb91-107">Attributes</span></span>  
  
|<span data-ttu-id="acb91-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="acb91-108">Attribute</span></span>|<span data-ttu-id="acb91-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="acb91-109">Attribute type</span></span>|<span data-ttu-id="acb91-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="acb91-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="acb91-111">Geral</span><span class="sxs-lookup"><span data-stu-id="acb91-111">General</span></span>|<span data-ttu-id="acb91-112">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="acb91-112">Required attribute.</span></span> <span data-ttu-id="acb91-113">Especifica o nome do campo.</span><span class="sxs-lookup"><span data-stu-id="acb91-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="acb91-114">Reflexão</span><span class="sxs-lookup"><span data-stu-id="acb91-114">Reflection</span></span>|<span data-ttu-id="acb91-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="acb91-115">Optional attribute.</span></span> <span data-ttu-id="acb91-116">Controla consultas para obter informações sobre o campo ou para enumerá-lo, mas não permite qualquer acesso dinâmico no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="acb91-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="acb91-117">Reflexão</span><span class="sxs-lookup"><span data-stu-id="acb91-117">Reflection</span></span>|<span data-ttu-id="acb91-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="acb91-118">Optional attribute.</span></span> <span data-ttu-id="acb91-119">Controla o acesso do runtime ao campo para habilitar programação dinâmica.</span><span class="sxs-lookup"><span data-stu-id="acb91-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="acb91-120">Essa política garante que um campo pode ser definido ou recuperado dinamicamente no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="acb91-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="acb91-121">Serialização</span><span class="sxs-lookup"><span data-stu-id="acb91-121">Serialization</span></span>|<span data-ttu-id="acb91-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="acb91-122">Optional attribute.</span></span> <span data-ttu-id="acb91-123">Controla o acesso do runtime a um campo para habilitar as instâncias de tipo a serem serializadas por bibliotecas como o serializador Newtonsoft JSON ou a ser usado para a associação de dados.</span><span class="sxs-lookup"><span data-stu-id="acb91-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="acb91-124">Atributo de nome</span><span class="sxs-lookup"><span data-stu-id="acb91-124">Name attribute</span></span>  
  
|<span data-ttu-id="acb91-125">Valor</span><span class="sxs-lookup"><span data-stu-id="acb91-125">Value</span></span>|<span data-ttu-id="acb91-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="acb91-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acb91-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="acb91-127">*method_name*</span></span>|<span data-ttu-id="acb91-128">O nome do campo.</span><span class="sxs-lookup"><span data-stu-id="acb91-128">The field name.</span></span> <span data-ttu-id="acb91-129">O tipo do campo é definido pelo [\<Type>](type-element-net-native.md) elemento pai ou [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="acb91-129">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="acb91-130">Todos os outros atributos</span><span class="sxs-lookup"><span data-stu-id="acb91-130">All other attributes</span></span>  
  
|<span data-ttu-id="acb91-131">Valor</span><span class="sxs-lookup"><span data-stu-id="acb91-131">Value</span></span>|<span data-ttu-id="acb91-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="acb91-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acb91-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="acb91-133">*policy_setting*</span></span>|<span data-ttu-id="acb91-134">A configuração a ser aplicada a este tipo de política para o campo.</span><span class="sxs-lookup"><span data-stu-id="acb91-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="acb91-135">Os valores possíveis são `Auto`, `Excluded`, `Included` e `Required`.</span><span class="sxs-lookup"><span data-stu-id="acb91-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="acb91-136">Para obter mais informações, consulte [Configurações da política da diretiva de runtime](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="acb91-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acb91-137">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="acb91-137">Child Elements</span></span>  

 <span data-ttu-id="acb91-138">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="acb91-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acb91-139">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="acb91-139">Parent Elements</span></span>  
  
|<span data-ttu-id="acb91-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="acb91-140">Element</span></span>|<span data-ttu-id="acb91-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="acb91-141">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="acb91-142">Aplica a política de reflexão a um tipo e todos os seus membros.</span><span class="sxs-lookup"><span data-stu-id="acb91-142">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="acb91-143">Aplica a política de reflexão a um tipo genérico construído e todos os seus membros.</span><span class="sxs-lookup"><span data-stu-id="acb91-143">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acb91-144">Comentários</span><span class="sxs-lookup"><span data-stu-id="acb91-144">Remarks</span></span>  

 <span data-ttu-id="acb91-145">Se a política do campo não for definida explicitamente, ele herdará a política de runtime do seu elemento pai.</span><span class="sxs-lookup"><span data-stu-id="acb91-145">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb91-146">Veja também</span><span class="sxs-lookup"><span data-stu-id="acb91-146">See also</span></span>

- [<span data-ttu-id="acb91-147">Elementos da diretiva de runtime</span><span class="sxs-lookup"><span data-stu-id="acb91-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="acb91-148">Referência do arquivo de configuração de diretivas do runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="acb91-148">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="acb91-149">Configurações da política da diretiva de runtime</span><span class="sxs-lookup"><span data-stu-id="acb91-149">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
