---
title: Estrutura do projeto para Blazor aplicativos
description: Saiba como as estruturas de projeto de ASP.NET Web Forms e Blazor projetos são comparadas.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 11/20/2020
ms.openlocfilehash: d91430eb654ee16934408bf064803b34ca700640
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509800"
---
# <a name="project-structure-for-no-locblazor-apps"></a><span data-ttu-id="94129-103">Estrutura do projeto para Blazor aplicativos</span><span class="sxs-lookup"><span data-stu-id="94129-103">Project structure for Blazor apps</span></span>

<span data-ttu-id="94129-104">Apesar das diferenças significativas na estrutura do projeto, ASP.NET Web Forms e Blazor Compartilhe muitos conceitos semelhantes.</span><span class="sxs-lookup"><span data-stu-id="94129-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="94129-105">Aqui, veremos a estrutura de um Blazor projeto e o comparamos a um projeto ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="94129-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="94129-106">Para criar seu primeiro Blazor aplicativo, siga as instruções nas [ Blazor etapas de introdução](/aspnet/core/blazor/get-started).</span><span class="sxs-lookup"><span data-stu-id="94129-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="94129-107">Você pode seguir as instruções para criar um Blazor aplicativo de servidor ou um Blazor WebAssembly aplicativo hospedado no ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="94129-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="94129-108">Exceto para a lógica específica do modelo de hospedagem, a maior parte do código em ambos os projetos é a mesma.</span><span class="sxs-lookup"><span data-stu-id="94129-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="94129-109">Arquivo de projeto</span><span class="sxs-lookup"><span data-stu-id="94129-109">Project file</span></span>

<span data-ttu-id="94129-110">Blazor Aplicativos de servidor são projetos .NET.</span><span class="sxs-lookup"><span data-stu-id="94129-110">Blazor Server apps are .NET projects.</span></span> <span data-ttu-id="94129-111">O arquivo de projeto para o Blazor aplicativo de servidor é quase tão simples quanto pode ser:</span><span class="sxs-lookup"><span data-stu-id="94129-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="94129-112">O arquivo de projeto para um Blazor WebAssembly aplicativo parece um pouco mais envolvido (números de versão exatas podem variar):</span><span class="sxs-lookup"><span data-stu-id="94129-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Components.WebAssembly" Version="5.0.0" />
    <PackageReference Include="Microsoft.AspNetCore.Components.WebAssembly.DevServer" Version="5.0.0" PrivateAssets="all" />
    <PackageReference Include="System.Net.Http.Json" Version="5.0.0" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="94129-113">BlazorWebAssemblyo projeto `Microsoft.NET.Sdk.BlazorWebAssembly` é direcionado em vez do `Microsoft.NET.Sdk.Web` SDK porque eles são executados no navegador em um WebAssembly tempo de execução do .net baseado em.</span><span class="sxs-lookup"><span data-stu-id="94129-113">Blazor WebAssembly project targets `Microsoft.NET.Sdk.BlazorWebAssembly` instead of `Microsoft.NET.Sdk.Web` sdk because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="94129-114">Você não pode instalar o .NET em um navegador da Web como você pode em um computador de servidor ou de desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="94129-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="94129-115">Consequentemente, o projeto faz referência à Blazor estrutura usando referências de pacote individuais.</span><span class="sxs-lookup"><span data-stu-id="94129-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="94129-116">Por comparação, um projeto ASP.NET Web Forms padrão inclui quase 300 linhas de XML em seu arquivo *. csproj* , a maior parte deles está listando explicitamente os vários arquivos de código e conteúdo no projeto.</span><span class="sxs-lookup"><span data-stu-id="94129-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="94129-117">Com o lançamento do `.NET 5` `Blazor Server` e do `Blazor WebAssembly` aplicativo, é possível compartilhar facilmente um tempo de execução unificado.</span><span class="sxs-lookup"><span data-stu-id="94129-117">With the release of `.NET 5` both `Blazor Server` and `Blazor WebAssembly` app can easily share one unified runtime.</span></span>

<span data-ttu-id="94129-118">Embora eles tenham suporte, as referências de assembly individuais são menos comuns em projetos .NET.</span><span class="sxs-lookup"><span data-stu-id="94129-118">Although they're supported, individual assembly references are less common in .NET projects.</span></span> <span data-ttu-id="94129-119">A maioria das dependências do projeto é tratada como referências de pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="94129-119">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="94129-120">Você só precisa referenciar as dependências de pacote de nível superior em projetos .NET.</span><span class="sxs-lookup"><span data-stu-id="94129-120">You only need to reference top-level package dependencies in .NET projects.</span></span> <span data-ttu-id="94129-121">Dependências transitivas são incluídas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="94129-121">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="94129-122">Em vez de usar o arquivo de *packages.config* normalmente encontrado em projetos de Web Forms de ASP.net para referenciar pacotes, as referências de pacote são adicionadas ao arquivo de projeto usando o `<PackageReference>` elemento.</span><span class="sxs-lookup"><span data-stu-id="94129-122">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="94129-123">Ponto de entrada</span><span class="sxs-lookup"><span data-stu-id="94129-123">Entry point</span></span>

<span data-ttu-id="94129-124">O Blazor ponto de entrada do aplicativo de servidor é definido no arquivo *Program.cs* , como você veria em um aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="94129-124">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="94129-125">Quando o aplicativo é executado, ele cria e executa uma instância de host Web usando padrões específicos para aplicativos Web.</span><span class="sxs-lookup"><span data-stu-id="94129-125">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="94129-126">O host da Web gerencia o Blazor ciclo de vida do aplicativo do servidor e configura os serviços de nível de host.</span><span class="sxs-lookup"><span data-stu-id="94129-126">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="94129-127">Exemplos desses serviços são configuração, registro em log, injeção de dependência e o servidor HTTP.</span><span class="sxs-lookup"><span data-stu-id="94129-127">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="94129-128">Esse código é basicamente clichê e, muitas vezes, permanece inalterado.</span><span class="sxs-lookup"><span data-stu-id="94129-128">This code is mostly boilerplate and is often left unchanged.</span></span>

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

<span data-ttu-id="94129-129">Blazoros WebAssembly aplicativos também definem um ponto de entrada em *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="94129-129">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="94129-130">O código parece um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="94129-130">The code looks slightly different.</span></span> <span data-ttu-id="94129-131">O código é semelhante, pois está configurando o host de aplicativo para fornecer os mesmos serviços de nível de host para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94129-131">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="94129-132">WebAssemblyNo entanto, o host de aplicativo não configura um servidor http porque ele é executado diretamente no navegador.</span><span class="sxs-lookup"><span data-stu-id="94129-132">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="94129-133">Blazor os aplicativos têm uma `Startup` classe em vez de um arquivo *global. asax* para definir a lógica de inicialização para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94129-133">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="94129-134">A `Startup` classe é usada para configurar o aplicativo e quaisquer serviços específicos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94129-134">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="94129-135">No Blazor aplicativo de servidor, a `Startup` classe é usada para configurar o ponto de extremidade para a conexão em tempo real usada pelo Blazor entre os navegadores cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="94129-135">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="94129-136">No Blazor WebAssembly aplicativo, a `Startup` classe define os componentes raiz para o aplicativo e onde eles devem ser renderizados.</span><span class="sxs-lookup"><span data-stu-id="94129-136">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="94129-137">Vamos dar uma olhada mais detalhada na `Startup` classe na seção de [inicialização do aplicativo](./app-startup.md) .</span><span class="sxs-lookup"><span data-stu-id="94129-137">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="94129-138">Arquivos estáticos</span><span class="sxs-lookup"><span data-stu-id="94129-138">Static files</span></span>

<span data-ttu-id="94129-139">Ao contrário dos projetos do ASP.NET Web Forms, nem todos os arquivos em um Blazor projeto podem ser solicitados como arquivos estáticos.</span><span class="sxs-lookup"><span data-stu-id="94129-139">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="94129-140">Somente os arquivos na pasta *wwwroot* são endereçáveis da Web.</span><span class="sxs-lookup"><span data-stu-id="94129-140">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="94129-141">Essa pasta é referida na "raiz da Web" do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94129-141">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="94129-142">Qualquer coisa fora da raiz da Web do aplicativo *não é* endereçável da Web.</span><span class="sxs-lookup"><span data-stu-id="94129-142">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="94129-143">Essa configuração fornece um nível adicional de segurança que impede a exposição acidental de arquivos de projeto na Web.</span><span class="sxs-lookup"><span data-stu-id="94129-143">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="94129-144">Configuração</span><span class="sxs-lookup"><span data-stu-id="94129-144">Configuration</span></span>

<span data-ttu-id="94129-145">A configuração no ASP.NET Web Forms aplicativos normalmente é manipulada usando um ou mais arquivos de *web.config* .</span><span class="sxs-lookup"><span data-stu-id="94129-145">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="94129-146">Blazor os aplicativos normalmente não têm *web.config* arquivos.</span><span class="sxs-lookup"><span data-stu-id="94129-146">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="94129-147">Se isso for feito, o arquivo será usado apenas para definir configurações específicas do IIS quando hospedado no IIS.</span><span class="sxs-lookup"><span data-stu-id="94129-147">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="94129-148">Em vez disso, Blazor os aplicativos de servidor usam as abstrações de configuração ASP.NET Core ( Blazor WebAssembly os aplicativos atualmente não dão suporte às mesmas abstrações de configuração, mas podem ser um recurso adicionado no futuro).</span><span class="sxs-lookup"><span data-stu-id="94129-148">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="94129-149">Por exemplo, o Blazor aplicativo de servidor padrão armazena algumas configurações no *appsettings.jsem*.</span><span class="sxs-lookup"><span data-stu-id="94129-149">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*"
}
```

<span data-ttu-id="94129-150">Aprenderemos mais sobre a configuração em projetos ASP.NET Core na seção de [configuração](./config.md) .</span><span class="sxs-lookup"><span data-stu-id="94129-150">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="94129-151">Componentes do Razor</span><span class="sxs-lookup"><span data-stu-id="94129-151">Razor components</span></span>

<span data-ttu-id="94129-152">A maioria dos arquivos em Blazor projetos são arquivos *. Razor* .</span><span class="sxs-lookup"><span data-stu-id="94129-152">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="94129-153">O Razor é uma linguagem de modelagem baseada em HTML e em C# que é usada para gerar dinamicamente a interface do usuário da Web.</span><span class="sxs-lookup"><span data-stu-id="94129-153">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="94129-154">Os arquivos *. Razor* definem componentes que compõem a interface do usuário do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94129-154">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="94129-155">Para a maior parte, os componentes são idênticos para o Blazor servidor e os Blazor WebAssembly aplicativos.</span><span class="sxs-lookup"><span data-stu-id="94129-155">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="94129-156">Os componentes no Blazor são análogos aos controles de usuário no ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="94129-156">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="94129-157">Cada arquivo de componente do Razor é compilado em uma classe do .NET quando o projeto é compilado.</span><span class="sxs-lookup"><span data-stu-id="94129-157">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="94129-158">A classe gerada captura o estado do componente, a lógica de renderização, os métodos de ciclo de vida, os manipuladores de eventos e outras lógicas.</span><span class="sxs-lookup"><span data-stu-id="94129-158">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="94129-159">Vamos examinar os componentes de criação na seção [criando componentes Blazor de interface do usuário reutilizáveis](./components.md) .</span><span class="sxs-lookup"><span data-stu-id="94129-159">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="94129-160">Os arquivos *_Imports. Razor* não são arquivos de componente do Razor.</span><span class="sxs-lookup"><span data-stu-id="94129-160">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="94129-161">Em vez disso, eles definem um conjunto de diretivas do Razor para importar para outros arquivos *. Razor* dentro da mesma pasta e em suas subpastas.</span><span class="sxs-lookup"><span data-stu-id="94129-161">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="94129-162">Por exemplo, um arquivo *_Imports. Razor* é uma maneira convencional de adicionar `using` diretivas para namespaces comumente usados:</span><span class="sxs-lookup"><span data-stu-id="94129-162">For example, a *_Imports.razor* file is a conventional way to add `using` directives for commonly used namespaces:</span></span>

```razor
@using System.Net.Http
@using Microsoft.AspNetCore.Authorization
@using Microsoft.AspNetCore.Components.Authorization
@using Microsoft.AspNetCore.Components.Forms
@using Microsoft.AspNetCore.Components.Routing
@using Microsoft.AspNetCore.Components.Web
@using Microsoft.JSInterop
@using BlazorApp1
@using BlazorApp1.Shared
```

## <a name="pages"></a><span data-ttu-id="94129-163">Páginas</span><span class="sxs-lookup"><span data-stu-id="94129-163">Pages</span></span>

<span data-ttu-id="94129-164">Onde estão as páginas nos Blazor aplicativos?</span><span class="sxs-lookup"><span data-stu-id="94129-164">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="94129-165">Blazor não define uma extensão de arquivo separada para páginas endereçáveis, como os arquivos *. aspx* em ASP.NET Web Forms aplicativos.</span><span class="sxs-lookup"><span data-stu-id="94129-165">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="94129-166">Em vez disso, as páginas são definidas por meio da atribuição de rotas a componentes.</span><span class="sxs-lookup"><span data-stu-id="94129-166">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="94129-167">Uma rota é normalmente atribuída usando a `@page` diretiva Razor.</span><span class="sxs-lookup"><span data-stu-id="94129-167">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="94129-168">Por exemplo, o `Counter` componente criado no arquivo *pages/Counter. Razor* define a seguinte rota:</span><span class="sxs-lookup"><span data-stu-id="94129-168">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="94129-169">O roteamento no Blazor é tratado pelo lado do cliente, não no servidor.</span><span class="sxs-lookup"><span data-stu-id="94129-169">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="94129-170">À medida que o usuário navega no navegador, Blazor intercepta a navegação e, em seguida, renderiza o componente com a rota correspondente.</span><span class="sxs-lookup"><span data-stu-id="94129-170">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="94129-171">As rotas de componentes não são inferidas no momento pelo local do arquivo do componente como estão com páginas *. aspx* .</span><span class="sxs-lookup"><span data-stu-id="94129-171">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="94129-172">Esse recurso pode ser adicionado no futuro.</span><span class="sxs-lookup"><span data-stu-id="94129-172">This feature may be added in the future.</span></span> <span data-ttu-id="94129-173">Cada rota deve ser especificada explicitamente no componente.</span><span class="sxs-lookup"><span data-stu-id="94129-173">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="94129-174">O armazenamento de componentes roteáveis em uma pasta de *páginas* não tem significado especial e é puramente uma convenção.</span><span class="sxs-lookup"><span data-stu-id="94129-174">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="94129-175">Veremos mais detalhadamente no roteamento no Blazor na seção [páginas, roteamento e layouts](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="94129-175">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="94129-176">Layout</span><span class="sxs-lookup"><span data-stu-id="94129-176">Layout</span></span>

<span data-ttu-id="94129-177">No ASP.NET Web Forms aplicativos, um layout de página comum é manipulado usando páginas mestras (*site. Master*).</span><span class="sxs-lookup"><span data-stu-id="94129-177">In ASP.NET Web Forms apps, a common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="94129-178">Em Blazor aplicativos, o layout da página é manipulado usando componentes de layout (*Shared/MainLayout. Razor*).</span><span class="sxs-lookup"><span data-stu-id="94129-178">In Blazor apps, the page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="94129-179">Os componentes de layout serão discutidos em mais detalhes na seção [página, roteamento e layouts](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="94129-179">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-no-locblazor"></a><span data-ttu-id="94129-180">Inicialização Blazor</span><span class="sxs-lookup"><span data-stu-id="94129-180">Bootstrap Blazor</span></span>

<span data-ttu-id="94129-181">Para inicializar Blazor , o aplicativo deve:</span><span class="sxs-lookup"><span data-stu-id="94129-181">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="94129-182">Especifique o local na página em que o componente raiz (*app. Razor*) deve ser renderizado.</span><span class="sxs-lookup"><span data-stu-id="94129-182">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="94129-183">Adicione o Blazor script de estrutura correspondente.</span><span class="sxs-lookup"><span data-stu-id="94129-183">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="94129-184">No Blazor aplicativo de servidor, a página host do componente raiz é definida no arquivo *_Host. cshtml* .</span><span class="sxs-lookup"><span data-stu-id="94129-184">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="94129-185">Esse arquivo define uma página Razor, não um componente.</span><span class="sxs-lookup"><span data-stu-id="94129-185">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="94129-186">Razor Pages usar sintaxe Razor para definir uma página endereçável do servidor, muito parecida com uma página *. aspx* .</span><span class="sxs-lookup"><span data-stu-id="94129-186">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="94129-187">O `Html.RenderComponentAsync<TComponent>(RenderMode)` método é usado para definir onde um componente de nível raiz deve ser renderizado.</span><span class="sxs-lookup"><span data-stu-id="94129-187">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="94129-188">A `RenderMode` opção indica a maneira como o componente deve ser renderizado.</span><span class="sxs-lookup"><span data-stu-id="94129-188">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="94129-189">A tabela a seguir descreve as opções com suporte `RenderMode` .</span><span class="sxs-lookup"><span data-stu-id="94129-189">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="94129-190">Opção</span><span class="sxs-lookup"><span data-stu-id="94129-190">Option</span></span>                        |<span data-ttu-id="94129-191">Descrição</span><span class="sxs-lookup"><span data-stu-id="94129-191">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="94129-192">Renderizado interativamente quando uma conexão com o navegador é estabelecida</span><span class="sxs-lookup"><span data-stu-id="94129-192">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="94129-193">Primeiro renderizado e, em seguida, renderizado interativamente</span><span class="sxs-lookup"><span data-stu-id="94129-193">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="94129-194">Renderizado como conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="94129-194">Rendered as static content</span></span>|

<span data-ttu-id="94129-195">A referência de script para *_framework/blazor.server.js* estabelece a conexão em tempo real com o servidor e, em seguida, lida com todas as interações do usuário e as atualizações da interface de usuário.</span><span class="sxs-lookup"><span data-stu-id="94129-195">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

```razor
@page "/"
@namespace BlazorApp1.Pages
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BlazorApp1</title>
    <base href="~/" />
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>
        @(await Html.RenderComponentAsync<App>(RenderMode.ServerPrerendered))
    </app>

    <script src="_framework/blazor.server.js"></script>
</body>
</html>
```

<span data-ttu-id="94129-196">No Blazor WebAssembly aplicativo, a página host é um arquivo HTML estático simples em *wwwroot/index.html*.</span><span class="sxs-lookup"><span data-stu-id="94129-196">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="94129-197">O `<div>` elemento com ID chamado `app` é usado para indicar onde o componente raiz deve ser renderizado.</span><span class="sxs-lookup"><span data-stu-id="94129-197">The `<div>` element with id named `app` is used to indicate where the root component should be rendered.</span></span>

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/app.css" rel="stylesheet" />
    <link href="blazor-web.styles.css" rel="stylesheet" />
</head>

<body>
    <div id="app">Loading...</div>

    <div id="blazor-error-ui">
        An unhandled error has occurred.
        <a href="" class="reload">Reload</a>
        <a class="dismiss">🗙</a>
    </div>
    <script src="_framework/blazor.webassembly.js"></script>
</body>

</html>

```

<span data-ttu-id="94129-198">O componente raiz a ser renderizado é configurado no método do aplicativo `Program.Main` com a flexibilidade para registrar diferentes serviços por meio da injeção de dependência. Você pode consultar adicionar serviços a um aplicativo no [ Blazor WebAssembly ](https://docs.microsoft.com/aspnet/core/blazor/fundamentals/dependency-injection?view=aspnetcore-5.0#blazor-webassembly)</span><span class="sxs-lookup"><span data-stu-id="94129-198">The root component to render is configured in the app's `Program.Main` method with the flexibility to register different services through dependency injection.You can refer add services to an app in [Blazor WebAssembly](https://docs.microsoft.com/aspnet/core/blazor/fundamentals/dependency-injection?view=aspnetcore-5.0#blazor-webassembly)</span></span>

```csharp
public class Program
{
    public static async Task Main(string[] args)
    {
        var builder = WebAssemblyHostBuilder.CreateDefault(args);
        builder.RootComponents.Add<App>("#app");

        ....
        ....
    }
}
```

## <a name="build-output"></a><span data-ttu-id="94129-199">Saída do build</span><span class="sxs-lookup"><span data-stu-id="94129-199">Build output</span></span>

<span data-ttu-id="94129-200">Quando um Blazor projeto é compilado, todos os arquivos de código e componente do Razor são compilados em um único assembly.</span><span class="sxs-lookup"><span data-stu-id="94129-200">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="94129-201">Diferentemente do ASP.NET Web Forms projetos, Blazor o não dá suporte à compilação em tempo de execução da lógica da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="94129-201">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="94129-202">Executar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="94129-202">Run the app</span></span>

<span data-ttu-id="94129-203">Para executar o Blazor aplicativo de servidor, pressione `F5` no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="94129-203">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="94129-204">Blazor os aplicativos não oferecem suporte à compilação em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="94129-204">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="94129-205">Para ver os resultados das alterações de marcação de código e de componente, recompile e reinicie o aplicativo com o depurador anexado.</span><span class="sxs-lookup"><span data-stu-id="94129-205">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="94129-206">Se você executar sem o depurador anexado ( `Ctrl+F5` ), o Visual Studio inspecionará as alterações de arquivo e reiniciará o aplicativo conforme as alterações forem feitas.</span><span class="sxs-lookup"><span data-stu-id="94129-206">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="94129-207">Você atualiza manualmente o navegador conforme as alterações são feitas.</span><span class="sxs-lookup"><span data-stu-id="94129-207">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="94129-208">Para executar o Blazor WebAssembly aplicativo, escolha uma das seguintes abordagens:</span><span class="sxs-lookup"><span data-stu-id="94129-208">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="94129-209">Execute o projeto do cliente diretamente usando o servidor de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="94129-209">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="94129-210">Execute o projeto de servidor ao hospedar o aplicativo com ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="94129-210">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="94129-211">BlazorWebAssemblyos aplicativos podem ser depurados no navegador e no Visual Studio. consulte [ASP.NET Core Blazor WebAssembly de depuração](/aspnet/core/blazor/debug) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="94129-211">Blazor WebAssembly apps can be debugged in both browser and Visual Studio.See [Debug ASP.NET Core Blazor WebAssembly](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="94129-212">[Anterior](hosting-models.md) 
> [Avançar](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="94129-212">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
