---
title: Elementos da diretiva de runtime
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: 96bce89c02ad17d1b30eda66237f69a15123dcd3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250795"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="c6b17-102">Elementos da diretiva de runtime</span><span class="sxs-lookup"><span data-stu-id="c6b17-102">Runtime Directive Elements</span></span>

<span data-ttu-id="c6b17-103">O formato do arquivo de diretivas (rd.xml) do runtime suporta os seguintes elementos de diretiva de runtime.</span><span class="sxs-lookup"><span data-stu-id="c6b17-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="c6b17-104">Consulte a [Referência do arquivo de configuração (rd.xml) de diretivas de runtime](runtime-directives-rd-xml-configuration-file-reference.md) para uma representação hierárquica.</span><span class="sxs-lookup"><span data-stu-id="c6b17-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [\<Application>](application-element-net-native.md)  
 <span data-ttu-id="c6b17-105">Aplica a política de reflexão de runtime a todos os tipos usados pelo aplicativo e serve como um contêiner para tipos amplos de aplicativos e membros de tipo cujos metadados estão disponíveis para reflexão no runtime.</span><span class="sxs-lookup"><span data-stu-id="c6b17-105">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="c6b17-106">Este é um filho do [\<Directives>](directives-element-net-native.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c6b17-106">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [\<Assembly>](assembly-element-net-native.md)  
 <span data-ttu-id="c6b17-107">Aplica a política de runtime a todos os tipos em um assembly.</span><span class="sxs-lookup"><span data-stu-id="c6b17-107">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="c6b17-108">Esse é um filho dos [\<Application>](application-element-net-native.md) elementos e [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b17-108">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="c6b17-109">Se a diretiva que o contém [\<Type>](type-element-net-native.md) for um atributo, o aplicará a política de tempo de execução a elementos de código aos quais esse atributo será aplicado.</span><span class="sxs-lookup"><span data-stu-id="c6b17-109">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [\<Directives>](directives-element-net-native.md)  
 <span data-ttu-id="c6b17-110">O elemento raiz em cada arquivo de diretivas de tempo de execução para .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c6b17-110">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="c6b17-111">Seus elementos filho são [\<Application>](application-element-net-native.md) e [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b17-111">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [\<Event>](event-element-net-native.md)  
 <span data-ttu-id="c6b17-112">Aplica a política de runtime a um evento.</span><span class="sxs-lookup"><span data-stu-id="c6b17-112">Applies runtime policy to an event.</span></span> <span data-ttu-id="c6b17-113">Esse é um filho dos [\<Type>](type-element-net-native.md) elementos e [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b17-113">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Field>](field-element-net-native.md)  
 <span data-ttu-id="c6b17-114">Aplica a política de runtime a um campo.</span><span class="sxs-lookup"><span data-stu-id="c6b17-114">Applies runtime policy to a field.</span></span> <span data-ttu-id="c6b17-115">Esse é um filho dos [\<Type>](type-element-net-native.md) elementos e [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b17-115">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 <span data-ttu-id="c6b17-116">Aplica a política de runtime ao tipo de parâmetro de um tipo ou método genérico.</span><span class="sxs-lookup"><span data-stu-id="c6b17-116">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 <span data-ttu-id="c6b17-117">Aplica a política de runtime a um tipo, se ela tiver sido aplicada ao tipo ou método recipiente.</span><span class="sxs-lookup"><span data-stu-id="c6b17-117">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [\<Library>](library-element-net-native.md)  
 <span data-ttu-id="c6b17-118">Aplica a política de runtime a todos os tipos em um assembly.</span><span class="sxs-lookup"><span data-stu-id="c6b17-118">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="c6b17-119">Esse é um filho dos [\<Application>](application-element-net-native.md) elementos e [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b17-119">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<Method>](method-element-net-native.md)  
 <span data-ttu-id="c6b17-120">Aplica a política de runtime a um método.</span><span class="sxs-lookup"><span data-stu-id="c6b17-120">Applies runtime policy to a method.</span></span> <span data-ttu-id="c6b17-121">Esse é um filho dos [\<Type>](type-element-net-native.md) elementos e [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b17-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="c6b17-122">Aplica a diretiva de runtime para um método genérico construído.</span><span class="sxs-lookup"><span data-stu-id="c6b17-122">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="c6b17-123">Esse é um filho dos [\<Type>](type-element-net-native.md) elementos e [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b17-123">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Namespace>](namespace-element-net-native.md)  
 <span data-ttu-id="c6b17-124">Aplica a política de runtime a todos os tipos em um namespace.</span><span class="sxs-lookup"><span data-stu-id="c6b17-124">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [\<Parameter>](parameter-element-net-native.md)  
 <span data-ttu-id="c6b17-125">Aplica a política de runtime ao tipo do argumento passado para um método.</span><span class="sxs-lookup"><span data-stu-id="c6b17-125">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [\<Property>](property-element-net-native.md)  
 <span data-ttu-id="c6b17-126">Aplica a política de runtime a uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="c6b17-126">Applies runtime policy to a property.</span></span> <span data-ttu-id="c6b17-127">Esse é um filho dos [\<Type>](type-element-net-native.md) elementos e [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b17-127">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 <span data-ttu-id="c6b17-128">Aplica a política de runtime a todas as classes herdadas do tipo recipiente.</span><span class="sxs-lookup"><span data-stu-id="c6b17-128">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [\<Type>](type-element-net-native.md)  
 <span data-ttu-id="c6b17-129">Aplica a política de runtime a um tipo.</span><span class="sxs-lookup"><span data-stu-id="c6b17-129">Applies runtime policy to a type.</span></span>  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="c6b17-130">Aplica a política de runtime a um tipo genérico construído.</span><span class="sxs-lookup"><span data-stu-id="c6b17-130">Applies runtime policy to a constructed generic type.</span></span>  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 <span data-ttu-id="c6b17-131">Aplica a política de runtime ao tipo representado por um argumento <xref:System.Type> passado para um método.</span><span class="sxs-lookup"><span data-stu-id="c6b17-131">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6b17-132">Veja também</span><span class="sxs-lookup"><span data-stu-id="c6b17-132">See also</span></span>

- [<span data-ttu-id="c6b17-133">Referência do arquivo de configuração rd.xml</span><span class="sxs-lookup"><span data-stu-id="c6b17-133">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
