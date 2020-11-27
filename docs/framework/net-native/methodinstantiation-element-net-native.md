---
title: <MethodInstantiation> (.NET Nativo)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
ms.openlocfilehash: e247db05f8442d4fcfddbf03b5eb8955b8ff425a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250951"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="2feed-102">\<MethodInstantiation> (.NET Nativo)</span><span class="sxs-lookup"><span data-stu-id="2feed-102">\<MethodInstantiation> Element (.NET Native)</span></span>

<span data-ttu-id="2feed-103">Aplica a política de reflexão de runtime a um método genérico construído.</span><span class="sxs-lookup"><span data-stu-id="2feed-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2feed-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2feed-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2feed-105">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2feed-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2feed-106">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="2feed-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2feed-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="2feed-107">Attributes</span></span>  
  
|<span data-ttu-id="2feed-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="2feed-108">Attribute</span></span>|<span data-ttu-id="2feed-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="2feed-109">Attribute type</span></span>|<span data-ttu-id="2feed-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="2feed-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="2feed-111">Geral</span><span class="sxs-lookup"><span data-stu-id="2feed-111">General</span></span>|<span data-ttu-id="2feed-112">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="2feed-112">Required attribute.</span></span> <span data-ttu-id="2feed-113">Especifica o nome do método.</span><span class="sxs-lookup"><span data-stu-id="2feed-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="2feed-114">Geral</span><span class="sxs-lookup"><span data-stu-id="2feed-114">General</span></span>|<span data-ttu-id="2feed-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2feed-115">Optional attribute.</span></span> <span data-ttu-id="2feed-116">Especifica os parâmetros nomeados do método.</span><span class="sxs-lookup"><span data-stu-id="2feed-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="2feed-117">Vários parâmetros nomeados são separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2feed-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="2feed-118">O atributo `Signature` é usado para diferenciar métodos sobrecarregados.</span><span class="sxs-lookup"><span data-stu-id="2feed-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="2feed-119">Geral</span><span class="sxs-lookup"><span data-stu-id="2feed-119">General</span></span>|<span data-ttu-id="2feed-120">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="2feed-120">Required attribute.</span></span> <span data-ttu-id="2feed-121">Especifica os argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="2feed-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="2feed-122">Se houver vários parâmetros, eles são separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2feed-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="2feed-123">Reflexão</span><span class="sxs-lookup"><span data-stu-id="2feed-123">Reflection</span></span>|<span data-ttu-id="2feed-124">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2feed-124">Optional attribute.</span></span> <span data-ttu-id="2feed-125">Controla consultas para obter informações sobre o método ou para enumerá-lo, mas não permite qualquer invocação dinâmica no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="2feed-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="2feed-126">Reflexão</span><span class="sxs-lookup"><span data-stu-id="2feed-126">Reflection</span></span>|<span data-ttu-id="2feed-127">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2feed-127">Optional attribute.</span></span> <span data-ttu-id="2feed-128">Controla o acesso do runtime a um construtor ou método para habilitar a programação dinâmica.</span><span class="sxs-lookup"><span data-stu-id="2feed-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="2feed-129">Essa política garante que um membro pode ser invocado dinamicamente no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="2feed-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="2feed-130">Atributo de nome</span><span class="sxs-lookup"><span data-stu-id="2feed-130">Name attribute</span></span>  
  
|<span data-ttu-id="2feed-131">Valor</span><span class="sxs-lookup"><span data-stu-id="2feed-131">Value</span></span>|<span data-ttu-id="2feed-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="2feed-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2feed-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="2feed-133">*method_name*</span></span>|<span data-ttu-id="2feed-134">O nome do método.</span><span class="sxs-lookup"><span data-stu-id="2feed-134">The method name.</span></span> <span data-ttu-id="2feed-135">O tipo do método é definido pelo [\<Type>](type-element-net-native.md) elemento pai ou [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="2feed-135">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="2feed-136">Atributo de assinatura</span><span class="sxs-lookup"><span data-stu-id="2feed-136">Signature attribute</span></span>  
  
|<span data-ttu-id="2feed-137">Valor</span><span class="sxs-lookup"><span data-stu-id="2feed-137">Value</span></span>|<span data-ttu-id="2feed-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="2feed-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2feed-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="2feed-139">*method_signature*</span></span>|<span data-ttu-id="2feed-140">Especifica os parâmetros nomeados do método.</span><span class="sxs-lookup"><span data-stu-id="2feed-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="2feed-141">Se vários parâmetros estiverem presentes, eles são separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2feed-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="2feed-142">Atributo de argumentos</span><span class="sxs-lookup"><span data-stu-id="2feed-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="2feed-143">Valor</span><span class="sxs-lookup"><span data-stu-id="2feed-143">Value</span></span>|<span data-ttu-id="2feed-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="2feed-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2feed-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="2feed-145">*method_arguments*</span></span>|<span data-ttu-id="2feed-146">Especifica os argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="2feed-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="2feed-147">Se houver vários parâmetros, eles são separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2feed-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="2feed-148">Cada argumento deve conter o nome do tipo totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="2feed-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="2feed-149">Todos os outros atributos</span><span class="sxs-lookup"><span data-stu-id="2feed-149">All other attributes</span></span>  
  
|<span data-ttu-id="2feed-150">Valor</span><span class="sxs-lookup"><span data-stu-id="2feed-150">Value</span></span>|<span data-ttu-id="2feed-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="2feed-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2feed-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="2feed-152">*policy_setting*</span></span>|<span data-ttu-id="2feed-153">A configuração a ser aplicada a este tipo de política para o método.</span><span class="sxs-lookup"><span data-stu-id="2feed-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="2feed-154">Os valores possíveis são `Auto`, `Excluded`, `Included` e `Required`.</span><span class="sxs-lookup"><span data-stu-id="2feed-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="2feed-155">Para obter mais informações, consulte [Configurações da política da diretiva de runtime](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2feed-155">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2feed-156">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2feed-156">Child Elements</span></span>  

 <span data-ttu-id="2feed-157">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2feed-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2feed-158">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2feed-158">Parent Elements</span></span>  
  
|<span data-ttu-id="2feed-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="2feed-159">Element</span></span>|<span data-ttu-id="2feed-160">Descrição</span><span class="sxs-lookup"><span data-stu-id="2feed-160">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="2feed-161">Aplica a política de reflexão a um tipo e todos os seus membros.</span><span class="sxs-lookup"><span data-stu-id="2feed-161">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="2feed-162">Aplica a política de reflexão a um tipo genérico construído e todos os seus membros.</span><span class="sxs-lookup"><span data-stu-id="2feed-162">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2feed-163">Comentários</span><span class="sxs-lookup"><span data-stu-id="2feed-163">Remarks</span></span>  

 <span data-ttu-id="2feed-164">O elemento `<MethodInstantiation>` substitui a política de reflexão de runtime do seu método genérico aberto correspondente.</span><span class="sxs-lookup"><span data-stu-id="2feed-164">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2feed-165">Veja também</span><span class="sxs-lookup"><span data-stu-id="2feed-165">See also</span></span>

- [<span data-ttu-id="2feed-166">Referência do arquivo de configuração de diretivas do runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="2feed-166">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="2feed-167">Elementos da diretiva de runtime</span><span class="sxs-lookup"><span data-stu-id="2feed-167">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="2feed-168">Configurações da política da diretiva de runtime</span><span class="sxs-lookup"><span data-stu-id="2feed-168">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="2feed-169">\<Method> Elementos</span><span class="sxs-lookup"><span data-stu-id="2feed-169">\<Method> Element</span></span>](method-element-net-native.md)
