---
description: -Nullable (opções do compilador C#)
title: -Nullable (opções do compilador C#)
author: IEvangelist
ms.author: dapine
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 68857d0cb4d0cd1177506e0b7ce897d2cfc3aa5b
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099218"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="d29c2-103">-Nullable (opções do compilador C#)</span><span class="sxs-lookup"><span data-stu-id="d29c2-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="d29c2-104">A opção **-Nullable** permite que você especifique o contexto anulável.</span><span class="sxs-lookup"><span data-stu-id="d29c2-104">The **-nullable** option lets you specify the nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="d29c2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d29c2-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="d29c2-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d29c2-106">Arguments</span></span>

<span data-ttu-id="d29c2-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d29c2-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="d29c2-108">Especificar `+` , ou **-Nullable**, faz com que o compilador habilite o contexto anulável.</span><span class="sxs-lookup"><span data-stu-id="d29c2-108">Specifying `+`, or **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="d29c2-109">Especificando `-` , que estará em vigor se você não especificar **-Nullable**, desabilitará o contexto anulável.</span><span class="sxs-lookup"><span data-stu-id="d29c2-109">Specifying `-`, which is in effect if you don't specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="d29c2-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="d29c2-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="d29c2-111">Especifica a opção de contexto anulável.</span><span class="sxs-lookup"><span data-stu-id="d29c2-111">Specifies the nullable context option.</span></span> <span data-ttu-id="d29c2-112">Semelhante a `+` ou `-` , para habilitar e desabilitar, mas permite mais granularidade da especificidade de contexto anulável.</span><span class="sxs-lookup"><span data-stu-id="d29c2-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="d29c2-113">O `enable` argumento, que está em vigor, como se você especificar **-Nullable**, habilita o contexto anulável.</span><span class="sxs-lookup"><span data-stu-id="d29c2-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="d29c2-114">Especificar `disable` desabilitará o contexto anulável.</span><span class="sxs-lookup"><span data-stu-id="d29c2-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="d29c2-115">Ao fornecer o `warnings` argumento, **-Nullable: Warnings**, o contexto de aviso anulável é habilitado.</span><span class="sxs-lookup"><span data-stu-id="d29c2-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="d29c2-116">Ao especificar o `annotations` argumento, **-Nullable: Annotations**, o contexto de anotação anulável é habilitado.</span><span class="sxs-lookup"><span data-stu-id="d29c2-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="d29c2-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="d29c2-117">Remarks</span></span>

<span data-ttu-id="d29c2-118">A análise de fluxo é usada para inferir a nulidade das variáveis no código executável.</span><span class="sxs-lookup"><span data-stu-id="d29c2-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="d29c2-119">A nulidade inferida de uma variável é independente da nulidade declarada da variável.</span><span class="sxs-lookup"><span data-stu-id="d29c2-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="d29c2-120">As chamadas de método são analisadas mesmo quando são omitidas condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="d29c2-120">Method calls are analyzed even when they're conditionally omitted.</span></span> <span data-ttu-id="d29c2-121">Por exemplo, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> no modo de versão.</span><span class="sxs-lookup"><span data-stu-id="d29c2-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="d29c2-122">A invocação de métodos anotados com os seguintes atributos também afetará a análise do fluxo:</span><span class="sxs-lookup"><span data-stu-id="d29c2-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="d29c2-123">Pré-condições simples: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> e <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="d29c2-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="d29c2-124">Pós-condições simples: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> e <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="d29c2-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="d29c2-125">Pós-condições condicionais: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> e <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="d29c2-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="d29c2-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (por exemplo, `DoesNotReturnIf(false)` para <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> ) e <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="d29c2-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="d29c2-127">Pós-condições do membro: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> e <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="d29c2-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d29c2-128">O contexto anulável global não se aplica a arquivos de código gerados.</span><span class="sxs-lookup"><span data-stu-id="d29c2-128">The global nullable context does not apply for generated code files.</span></span> <span data-ttu-id="d29c2-129">Independentemente dessa configuração, o contexto anulável é *desabilitado* para qualquer arquivo de origem marcado como gerado.</span><span class="sxs-lookup"><span data-stu-id="d29c2-129">Regardless of this setting, the nullable context is *disabled* for any source file marked as generated.</span></span> <span data-ttu-id="d29c2-130">Há quatro maneiras de um arquivo ser marcado como gerado:</span><span class="sxs-lookup"><span data-stu-id="d29c2-130">There are four ways a file is marked as generated:</span></span>
>
> 1. <span data-ttu-id="d29c2-131">Em. editorconfig, especifique `generated_code = true` em uma seção que se aplica a esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="d29c2-131">In the .editorconfig, specify `generated_code = true` in a section that applies to that file.</span></span>
> 1. <span data-ttu-id="d29c2-132">Put `<auto-generated>` ou `<auto-generated/>` em um comentário na parte superior do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d29c2-132">Put `<auto-generated>` or `<auto-generated/>` in a comment at the top of the file.</span></span> <span data-ttu-id="d29c2-133">Ele pode estar em qualquer linha nesse comentário, mas o bloco de comentário deve ser o primeiro elemento no arquivo.</span><span class="sxs-lookup"><span data-stu-id="d29c2-133">It can be on any line in that comment, but the comment block must be the first element in the file.</span></span>
> 1. <span data-ttu-id="d29c2-134">Inicie o nome do arquivo com *TemporaryGeneratedFile_*</span><span class="sxs-lookup"><span data-stu-id="d29c2-134">Start the file name with *TemporaryGeneratedFile_*</span></span>
> 1. <span data-ttu-id="d29c2-135">Termine o nome do arquivo com *. designer.cs*, *. generated.cs*, *. g.cs* ou *. g.i.cs*.</span><span class="sxs-lookup"><span data-stu-id="d29c2-135">End the file name with *.designer.cs*, *.generated.cs*, *.g.cs*, or *.g.i.cs*.</span></span>
>
> <span data-ttu-id="d29c2-136">Os geradores podem optar por usar a [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) diretiva de pré-processador.</span><span class="sxs-lookup"><span data-stu-id="d29c2-136">Generators can opt-in using the [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) preprocessor directive.</span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="d29c2-137">Para definir essa opção de compilador em um projeto</span><span class="sxs-lookup"><span data-stu-id="d29c2-137">To set this compiler option in a project</span></span>

<span data-ttu-id="d29c2-138">Edite o arquivo *. csproj* para adicionar a `<Nullable>` marca em uma `Project/PropertyGroup` hierarquia:</span><span class="sxs-lookup"><span data-stu-id="d29c2-138">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="d29c2-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="d29c2-139">See also</span></span>

- [<span data-ttu-id="d29c2-140">Opções do compilador de C#</span><span class="sxs-lookup"><span data-stu-id="d29c2-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="d29c2-141">`#nullable` Diretiva de pré-processador</span><span class="sxs-lookup"><span data-stu-id="d29c2-141">`#nullable` preprocessor directive</span></span>](../preprocessor-directives/preprocessor-nullable.md)
- [<span data-ttu-id="d29c2-142">Tipos de referência anuláveis</span><span class="sxs-lookup"><span data-stu-id="d29c2-142">Nullable reference types</span></span>](../../nullable-references.md)
