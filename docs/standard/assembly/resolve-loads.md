---
title: Resolver carregamentos de assembly
description: Este artigo descreve o evento .NET AppDomain. AssemblyResolve. Use esse evento para aplicativos que exigem controle sobre o carregamento de assembly.
ms.date: 12/15/2020
helpviewer_keywords:
- assemblies [.NET], resolving loads
- application domains, loading assemblies
- resolving assembly loads
- assemblies [.NET], loading
- application domains, resolving assembly loads
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 63545db31a4290ce933da45c0957dfdb2a00701c
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593858"
---
# <a name="resolve-assembly-loads"></a><span data-ttu-id="01c5e-104">Resolver carregamentos de assembly</span><span class="sxs-lookup"><span data-stu-id="01c5e-104">Resolve assembly loads</span></span>

<span data-ttu-id="01c5e-105">O .NET fornece o <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento para aplicativos que exigem maior controle sobre o carregamento de assembly.</span><span class="sxs-lookup"><span data-stu-id="01c5e-105">.NET provides the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event for applications that require greater control over assembly loading.</span></span> <span data-ttu-id="01c5e-106">Ao tratar esse evento, seu aplicativo pode carregar um assembly no contexto de carga de fora dos caminhos normais de investigação, selecionar qual das várias versões de assembly carregar, emitir um assembly dinâmico e retorná-lo, etc.</span><span class="sxs-lookup"><span data-stu-id="01c5e-106">By handling this event, your application can load an assembly into the load context from outside the normal probing paths, select which of several assembly versions to load, emit a dynamic assembly and return it, and so on.</span></span> <span data-ttu-id="01c5e-107">Este tópico fornece orientação para a manipulação do evento <xref:System.AppDomain.AssemblyResolve>.</span><span class="sxs-lookup"><span data-stu-id="01c5e-107">This topic provides guidance for handling the <xref:System.AppDomain.AssemblyResolve> event.</span></span>

> [!NOTE]
> <span data-ttu-id="01c5e-108">Para resolver carregamentos de assembly no contexto de somente reflexão, use o evento <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="01c5e-108">For resolving assembly loads in the reflection-only context, use the <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType> event instead.</span></span>

## <a name="how-the-assemblyresolve-event-works"></a><span data-ttu-id="01c5e-109">Como o evento AssemblyResolve funciona</span><span class="sxs-lookup"><span data-stu-id="01c5e-109">How the AssemblyResolve event works</span></span>

<span data-ttu-id="01c5e-110">Quando você registra um manipulador para o evento <xref:System.AppDomain.AssemblyResolve>, o manipulador é invocado sempre que o runtime falha ao se associar a um assembly por nome.</span><span class="sxs-lookup"><span data-stu-id="01c5e-110">When you register a handler for the <xref:System.AppDomain.AssemblyResolve> event, the handler is invoked whenever the runtime fails to bind to an assembly by name.</span></span> <span data-ttu-id="01c5e-111">Por exemplo, chamar os seguintes métodos usando o código do usuário pode fazer com que o evento <xref:System.AppDomain.AssemblyResolve> seja gerado:</span><span class="sxs-lookup"><span data-stu-id="01c5e-111">For example, calling the following methods from user code can cause the <xref:System.AppDomain.AssemblyResolve> event to be raised:</span></span>

- <span data-ttu-id="01c5e-112">Uma sobrecarga de método <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> ou uma sobrecarga de método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> cujo primeiro argumento é uma cadeia de caracteres que representa o nome de exibição do assembly a ser carregado (ou seja, a cadeia de caracteres retornada pela propriedade <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="01c5e-112">An <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method overload or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overload whose first argument is a string that represents the display name of the assembly to load (that is, the string returned by the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property).</span></span>

- <span data-ttu-id="01c5e-113">Uma sobrecarga de método <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> ou uma sobrecarga de método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> cujo primeiro argumento é um objeto <xref:System.Reflection.AssemblyName> que identifica o assembly a ser carregado.</span><span class="sxs-lookup"><span data-stu-id="01c5e-113">An <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method overload or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overload whose first argument is an <xref:System.Reflection.AssemblyName> object that identifies the assembly to load.</span></span>

- <span data-ttu-id="01c5e-114">Uma sobrecarga de método <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="01c5e-114">An <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> method overload.</span></span>

- <span data-ttu-id="01c5e-115">Uma sobrecarga de método <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> ou <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> que cria uma instância de um objeto em outro domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="01c5e-115">An <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> method overload that instantiates an object in another application domain.</span></span>

## <a name="what-the-event-handler-does"></a><span data-ttu-id="01c5e-116">O que o manipulador de eventos faz</span><span class="sxs-lookup"><span data-stu-id="01c5e-116">What the event handler does</span></span>

<span data-ttu-id="01c5e-117">O manipulador do evento <xref:System.AppDomain.AssemblyResolve> recebe o nome de exibição do assembly a ser carregado na propriedade <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="01c5e-117">The handler for the <xref:System.AppDomain.AssemblyResolve> event receives the display name of the assembly to be loaded, in the <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="01c5e-118">Se o manipulador não reconhecer o nome do assembly, ele retornará `null` (C#), `Nothing` (Visual Basic) ou `nullptr` (Visual C++).</span><span class="sxs-lookup"><span data-stu-id="01c5e-118">If the handler does not recognize the assembly name, it returns `null` (C#), `Nothing` (Visual Basic), or `nullptr` (Visual C++).</span></span>

<span data-ttu-id="01c5e-119">Se o manipulador reconhecer o nome do assembly, ele poderá carregar e retornar um assembly que atende à solicitação.</span><span class="sxs-lookup"><span data-stu-id="01c5e-119">If the handler recognizes the assembly name, it can load and return an assembly that satisfies the request.</span></span> <span data-ttu-id="01c5e-120">A lista a seguir descreve alguns cenários de exemplo.</span><span class="sxs-lookup"><span data-stu-id="01c5e-120">The following list describes some sample scenarios.</span></span>

- <span data-ttu-id="01c5e-121">Se o manipulador conhecer o local de uma versão do assembly, ele poderá carregar o assembly usando o método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> ou <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> e poderá retornar o assembly carregado se tiver êxito.</span><span class="sxs-lookup"><span data-stu-id="01c5e-121">If the handler knows the location of a version of the assembly, it can load the assembly by using the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> method, and can return the loaded assembly if successful.</span></span>

- <span data-ttu-id="01c5e-122">Se o manipulador tiver acesso a um banco de dados de assemblies armazenados como matrizes de bytes, ele poderá carregar uma matriz de bytes usando uma das sobrecargas do método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> que usa uma matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="01c5e-122">If the handler has access to a database of assemblies stored as byte arrays, it can load a byte array by using one of the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overloads that take a byte array.</span></span>

- <span data-ttu-id="01c5e-123">O manipulador pode gerar um assembly dinâmico e retorná-lo.</span><span class="sxs-lookup"><span data-stu-id="01c5e-123">The handler can generate a dynamic assembly and return it.</span></span>

> [!NOTE]
> <span data-ttu-id="01c5e-124">O manipulador deve carregar o assembly no contexto de carga, no contexto de carga ou sem contexto.</span><span class="sxs-lookup"><span data-stu-id="01c5e-124">The handler must load the assembly into the load-from context, into the load context, or without context.</span></span> <span data-ttu-id="01c5e-125">Se o manipulador carregar o assembly no contexto somente de reflexão usando o <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> método ou, a tentativa de carregamento que gerou o <xref:System.AppDomain.AssemblyResolve> evento falhará.</span><span class="sxs-lookup"><span data-stu-id="01c5e-125">If the handler loads the assembly into the reflection-only context by using the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> method, the load attempt that raised the <xref:System.AppDomain.AssemblyResolve> event fails.</span></span>

<span data-ttu-id="01c5e-126">É responsabilidade do manipulador de eventos retornar um assembly adequado.</span><span class="sxs-lookup"><span data-stu-id="01c5e-126">It is the responsibility of the event handler to return a suitable assembly.</span></span> <span data-ttu-id="01c5e-127">O manipulador pode analisar o nome de exibição do assembly solicitado passando o valor da propriedade <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> para o construtor <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="01c5e-127">The handler can parse the display name of the requested assembly by passing the <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> property value to the <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29> constructor.</span></span> <span data-ttu-id="01c5e-128">A partir do .NET Framework 4, o manipulador pode usar a propriedade <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> para determinar se a solicitação atual é uma dependência de outro assembly.</span><span class="sxs-lookup"><span data-stu-id="01c5e-128">Beginning with the .NET Framework 4, the handler can use the <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property to determine whether the current request is a dependency of another assembly.</span></span> <span data-ttu-id="01c5e-129">Essas informações podem ajudar a identificar um assembly que atenderá à dependência.</span><span class="sxs-lookup"><span data-stu-id="01c5e-129">This information can help identify an assembly that will satisfy the dependency.</span></span>

<span data-ttu-id="01c5e-130">O manipulador de eventos pode retornar uma versão diferente do assembly do que a versão que foi solicitada.</span><span class="sxs-lookup"><span data-stu-id="01c5e-130">The event handler can return a different version of the assembly than the version that was requested.</span></span>

<span data-ttu-id="01c5e-131">Na maioria dos casos, o assembly que é retornado pelo manipulador aparece no contexto de carga, independentemente do contexto em que o manipulador o carrega.</span><span class="sxs-lookup"><span data-stu-id="01c5e-131">In most cases, the assembly that is returned by the handler appears in the load context, regardless of the context the handler loads it into.</span></span> <span data-ttu-id="01c5e-132">Por exemplo, se o manipulador usar o método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> para carregar um assembly no contexto de origem de carga, o assembly aparecerá no contexto de carga quando o manipulador o retornar.</span><span class="sxs-lookup"><span data-stu-id="01c5e-132">For example, if the handler uses the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method to load an assembly into the load-from context, the assembly appears in the load context when the handler returns it.</span></span> <span data-ttu-id="01c5e-133">No entanto, no seguinte caso, o assembly aparece sem contexto quando o manipulador o retorna:</span><span class="sxs-lookup"><span data-stu-id="01c5e-133">However, in the following case the assembly appears without context when the handler returns it:</span></span>

- <span data-ttu-id="01c5e-134">O manipulador carrega um assembly sem contexto.</span><span class="sxs-lookup"><span data-stu-id="01c5e-134">The handler loads an assembly without context.</span></span>

- <span data-ttu-id="01c5e-135">A propriedade <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> não é nula.</span><span class="sxs-lookup"><span data-stu-id="01c5e-135">The <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property is not null.</span></span>

- <span data-ttu-id="01c5e-136">O assembly solicitante (ou seja, o assembly que é retornado pela propriedade <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>) foi carregado sem contexto.</span><span class="sxs-lookup"><span data-stu-id="01c5e-136">The requesting assembly (that is, the assembly that is returned by the <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property) was loaded without context.</span></span>

<span data-ttu-id="01c5e-137">Para obter informações sobre os contextos, consulte a sobrecarga de método <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="01c5e-137">For information about contexts, see the <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType> method overload.</span></span>

<span data-ttu-id="01c5e-138">Várias versões do mesmo assembly podem ser carregadas no mesmo domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="01c5e-138">Multiple versions of the same assembly can be loaded into the same application domain.</span></span> <span data-ttu-id="01c5e-139">Essa prática não é recomendada, pois ela pode levar a problemas de atribuição de tipo.</span><span class="sxs-lookup"><span data-stu-id="01c5e-139">This practice is not recommended, because it can lead to type assignment problems.</span></span> <span data-ttu-id="01c5e-140">Consulte [práticas recomendadas para o carregamento de assembly](../../framework/deployment/best-practices-for-assembly-loading.md).</span><span class="sxs-lookup"><span data-stu-id="01c5e-140">See [Best practices for assembly loading](../../framework/deployment/best-practices-for-assembly-loading.md).</span></span>

## <a name="what-the-event-handler-should-not-do"></a><span data-ttu-id="01c5e-141">O que o manipulador de eventos não deve fazer</span><span class="sxs-lookup"><span data-stu-id="01c5e-141">What the event handler should not do</span></span>

<span data-ttu-id="01c5e-142">A regra principal para tratamento do evento <xref:System.AppDomain.AssemblyResolve> é que você não deve tentar retornar um assembly que não reconhece.</span><span class="sxs-lookup"><span data-stu-id="01c5e-142">The primary rule for handling the <xref:System.AppDomain.AssemblyResolve> event is that you should not try to return an assembly you do not recognize.</span></span> <span data-ttu-id="01c5e-143">Ao escrever o manipulador, você deve saber quais assemblies podem fazer com que o evento seja acionado.</span><span class="sxs-lookup"><span data-stu-id="01c5e-143">When you write the handler, you should know which assemblies might cause the event to be raised.</span></span> <span data-ttu-id="01c5e-144">O manipulador deve retornar nulo para outros assemblies.</span><span class="sxs-lookup"><span data-stu-id="01c5e-144">Your handler should return null for other assemblies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01c5e-145">Começando com o .NET Framework 4, o evento <xref:System.AppDomain.AssemblyResolve> é gerado para assemblies satélite.</span><span class="sxs-lookup"><span data-stu-id="01c5e-145">Beginning with the .NET Framework 4, the <xref:System.AppDomain.AssemblyResolve> event is raised for satellite assemblies.</span></span> <span data-ttu-id="01c5e-146">Essa alteração afeta um manipulador de eventos que foi escrito para uma versão anterior do .NET Framework, se o manipulador tenta resolver todas as solicitações de carga do assembly.</span><span class="sxs-lookup"><span data-stu-id="01c5e-146">This change affects an event handler that was written for an earlier version of the .NET Framework, if the handler tries to resolve all assembly load requests.</span></span> <span data-ttu-id="01c5e-147">Manipuladores de eventos que ignoram assemblies que eles não reconhecem não são afetados por essa alteração: eles retornam `null` e mecanismos de fallback normais são seguidos.</span><span class="sxs-lookup"><span data-stu-id="01c5e-147">Event handlers that ignore assemblies they do not recognize are not affected by this change: They return `null`, and normal fallback mechanisms are followed.</span></span>

<span data-ttu-id="01c5e-148">Ao carregar um assembly, o manipulador de eventos não deve usar nenhuma das sobrecargas de método <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> ou <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> que possam fazer com que o evento <xref:System.AppDomain.AssemblyResolve> seja gerado recursivamente, pois isso poderia levar a um excedente de pilha.</span><span class="sxs-lookup"><span data-stu-id="01c5e-148">When loading an assembly, the event handler must not use any of the <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overloads that can cause the <xref:System.AppDomain.AssemblyResolve> event to be raised recursively, because this can lead to a stack overflow.</span></span> <span data-ttu-id="01c5e-149">(Consulte a lista fornecida anteriormente neste tópico.) Isso acontece mesmo que você forneça tratamento de exceção para a solicitação de carregamento, porque nenhuma exceção é lançada até que todos os manipuladores de eventos tenham retornado.</span><span class="sxs-lookup"><span data-stu-id="01c5e-149">(See the list provided earlier in this topic.) This happens even if you provide exception handling for the load request, because no exception is thrown until all event handlers have returned.</span></span> <span data-ttu-id="01c5e-150">Desse modo, o seguinte código resultará em um excedente de pilha se `MyAssembly` não for encontrado:</span><span class="sxs-lookup"><span data-stu-id="01c5e-150">Thus, the following code results in a stack overflow if `MyAssembly` is not found:</span></span>

```csharp
using System;
using System.Reflection;

class BadExample
{
    static void Main()
    {
        AppDomain ad = AppDomain.CreateDomain("Test");
        ad.AssemblyResolve += MyHandler;

        try
        {
            object obj = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType");
        }
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static Assembly MyHandler(object source, ResolveEventArgs e)
    {
        Console.WriteLine("Resolving {0}", e.Name);
        // DO NOT DO THIS: This causes a StackOverflowException
        return Assembly.Load(e.Name);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```vb
Imports System.Reflection

Class BadExample

    Shared Sub Main()

        Dim ad As AppDomain = AppDomain.CreateDomain("Test")
        AddHandler ad.AssemblyResolve, AddressOf MyHandler

        Try
            Dim obj As object = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType")
        Catch ex As Exception
            Console.WriteLine(ex.Message)
        End Try
    End Sub

    Shared Function MyHandler(ByVal source As Object, _
                              ByVal e As ResolveEventArgs) As Assembly
        Console.WriteLine("Resolving {0}", e.Name)
        // DO NOT DO THIS: This causes a StackOverflowException
        Return Assembly.Load(e.Name)
    End Function
End Class

' This example produces output similar to the following:
'
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'...
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'
'Process is terminated due to StackOverflowException.
```

```cpp
using namespace System;
using namespace System::Reflection;

ref class Example
{
internal:
    static Assembly^ MyHandler(Object^ source, ResolveEventArgs^ e)
    {
        Console::WriteLine("Resolving {0}", e->Name);
        // DO NOT DO THIS: This causes a StackOverflowException
        return Assembly::Load(e->Name);
    }
};

void main()
{
    AppDomain^ ad = AppDomain::CreateDomain("Test");
    ad->AssemblyResolve += gcnew ResolveEventHandler(&Example::MyHandler);

    try
    {
        Object^ obj = ad->CreateInstanceAndUnwrap(
            "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
            "MyType");
    }
    catch (Exception^ ex)
    {
        Console::WriteLine(ex->Message);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
*/
```

### <a name="the-correct-way-to-handle-assemblyresolve"></a><span data-ttu-id="01c5e-151">A maneira correta de lidar com AssemblyResolve</span><span class="sxs-lookup"><span data-stu-id="01c5e-151">The correct way to handle AssemblyResolve</span></span>

<span data-ttu-id="01c5e-152">Ao resolver assemblies do manipulador de <xref:System.AppDomain.AssemblyResolve> eventos, um <xref:System.StackOverflowException> será gerado eventualmente se o manipulador usar as chamadas de <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> método ou.</span><span class="sxs-lookup"><span data-stu-id="01c5e-152">When resolving assemblies from the <xref:System.AppDomain.AssemblyResolve> event handler, a <xref:System.StackOverflowException> will eventually be thrown if the handler uses the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method calls.</span></span> <span data-ttu-id="01c5e-153">Em vez disso, use <xref:System.Reflection.Assembly.LoadFile%2A> <xref:System.Reflection.Assembly.LoadFrom%2A> métodos ou, pois eles não geram o `AssemblyResolve` evento.</span><span class="sxs-lookup"><span data-stu-id="01c5e-153">Instead, use <xref:System.Reflection.Assembly.LoadFile%2A> or <xref:System.Reflection.Assembly.LoadFrom%2A> methods, as they do not raise the `AssemblyResolve` event.</span></span>

<span data-ttu-id="01c5e-154">Imagine que `MyAssembly.dll` está localizado próximo ao assembly em execução, em um local conhecido, ele pode ser resolvido usando `Assembly.LoadFile` o caminho fornecido para o assembly.</span><span class="sxs-lookup"><span data-stu-id="01c5e-154">Imagine that `MyAssembly.dll` is located near the executing assembly, in a known location, it can be resolved using `Assembly.LoadFile` given the path to the assembly.</span></span>

```csharp
using System;
using System.IO;
using System.Reflection;

class CorrectExample
{
    static void Main()
    {
        AppDomain ad = AppDomain.CreateDomain("Test");
        ad.AssemblyResolve += MyHandler;

        try
        {
            object obj = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType");
        }
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static Assembly MyHandler(object source, ResolveEventArgs e)
    {
        Console.WriteLine("Resolving {0}", e.Name);

        var path = Path.GetFullPath("../../MyAssembly.dll");
        return Assembly.LoadFile(path);
     }
}
```

```vb
Imports System.IO
Imports System.Reflection

Class CorrectExample

    Shared Sub Main()

        Dim ad As AppDomain = AppDomain.CreateDomain("Test")
        AddHandler ad.AssemblyResolve, AddressOf MyHandler

        Try
            Dim obj As Object = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType")
        Catch ex As Exception
            Console.WriteLine(ex.Message)
        End Try
    End Sub

    Shared Function MyHandler(ByVal source As Object,
                              ByVal e As ResolveEventArgs) As Assembly
        Console.WriteLine("Resolving {0}", e.Name)

        Dim fullPath = Path.GetFullPath("../../MyAssembly.dll")
        Return Assembly.LoadFile(fullPath)
    End Function
End Class
```

```cpp
using namespace System;
using namespace System::IO;
using namespace System::Reflection;

ref class Example
{
internal:
    static Assembly^ MyHandler(Object^ source, ResolveEventArgs^ e)
    {
        Console::WriteLine("Resolving {0}", e->Name);

        String^ fullPath = Path::GetFullPath("../../MyAssembly.dll");
        return Assembly::LoadFile(fullPath);
    }
};

void main()
{
    AppDomain^ ad = AppDomain::CreateDomain("Test");
    ad->AssemblyResolve += gcnew ResolveEventHandler(&Example::MyHandler);

    try
    {
        Object^ obj = ad->CreateInstanceAndUnwrap(
            "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
            "MyType");
    }
    catch (Exception^ ex)
    {
        Console::WriteLine(ex->Message);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="01c5e-155">Confira também</span><span class="sxs-lookup"><span data-stu-id="01c5e-155">See also</span></span>

- [<span data-ttu-id="01c5e-156">Práticas recomendadas para o carregamento de assembly</span><span class="sxs-lookup"><span data-stu-id="01c5e-156">Best practices for assembly loading</span></span>](../../framework/deployment/best-practices-for-assembly-loading.md)
- [<span data-ttu-id="01c5e-157">Usar domínios de aplicativo</span><span class="sxs-lookup"><span data-stu-id="01c5e-157">Use application domains</span></span>](../../framework/app-domains/use.md)
