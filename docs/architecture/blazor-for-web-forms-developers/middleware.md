---
title: Módulos, manipuladores e middleware
description: Saiba mais sobre como lidar com solicitações HTTP com módulos, manipuladores e middleware.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 10/11/2019
ms.openlocfilehash: dbb0a94b0401d58139c024fd8ca3e00353a19efa
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678037"
---
# <a name="modules-handlers-and-middleware"></a><span data-ttu-id="53991-103">Módulos, manipuladores e middleware</span><span class="sxs-lookup"><span data-stu-id="53991-103">Modules, handlers, and middleware</span></span>

<span data-ttu-id="53991-104">Um aplicativo ASP.NET Core é criado com base em uma série de *middleware*.</span><span class="sxs-lookup"><span data-stu-id="53991-104">An ASP.NET Core app is built upon a series of *middleware*.</span></span> <span data-ttu-id="53991-105">O middleware é manipuladores que são organizados em um pipeline para lidar com solicitações e respostas.</span><span class="sxs-lookup"><span data-stu-id="53991-105">Middleware is handlers that are arranged into a pipeline to handle requests and responses.</span></span> <span data-ttu-id="53991-106">Em um aplicativo Web Forms, manipuladores e módulos HTTP resolvem problemas semelhantes.</span><span class="sxs-lookup"><span data-stu-id="53991-106">In a Web Forms app, HTTP handlers and modules solve similar problems.</span></span> <span data-ttu-id="53991-107">Em ASP.NET Core, módulos, manipuladores, *global.asax.cs* e o ciclo de vida do aplicativo são substituídos por middleware.</span><span class="sxs-lookup"><span data-stu-id="53991-107">In ASP.NET Core, modules, handlers, *Global.asax.cs*, and the app life cycle are replaced with middleware.</span></span> <span data-ttu-id="53991-108">Neste capítulo, você aprenderá sobre o middleware no contexto de um Blazor aplicativo.</span><span class="sxs-lookup"><span data-stu-id="53991-108">In this chapter, you'll learn about middleware in the context of a Blazor app.</span></span>

## <a name="overview"></a><span data-ttu-id="53991-109">Visão geral</span><span class="sxs-lookup"><span data-stu-id="53991-109">Overview</span></span>

<span data-ttu-id="53991-110">O pipeline de solicitação do ASP.NET Core consiste em uma sequência de delegados de solicitação, chamados um após o outro.</span><span class="sxs-lookup"><span data-stu-id="53991-110">The ASP.NET Core request pipeline consists of a sequence of request delegates, called one after the other.</span></span> <span data-ttu-id="53991-111">O diagrama a seguir demonstra o conceito.</span><span class="sxs-lookup"><span data-stu-id="53991-111">The following diagram demonstrates the concept.</span></span> <span data-ttu-id="53991-112">O thread de execução segue as setas pretas.</span><span class="sxs-lookup"><span data-stu-id="53991-112">The thread of execution follows the black arrows.</span></span>

![pipeline](media/middleware/request-delegate-pipeline.png)

<span data-ttu-id="53991-114">O diagrama anterior não tem um conceito de eventos de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="53991-114">The preceding diagram lacks a concept of lifecycle events.</span></span> <span data-ttu-id="53991-115">Esse conceito é fundamental para como as solicitações de Web Forms ASP.NET são tratadas.</span><span class="sxs-lookup"><span data-stu-id="53991-115">This concept is foundational to how ASP.NET Web Forms requests are handled.</span></span> <span data-ttu-id="53991-116">Esse sistema torna mais fácil motivo de qual processo está ocorrendo e permite que o middleware seja inserido em qualquer ponto.</span><span class="sxs-lookup"><span data-stu-id="53991-116">This system makes it easier to reason about what process is occurring and allows middleware to be inserted at any point.</span></span> <span data-ttu-id="53991-117">O middleware é executado na ordem em que é adicionado ao pipeline de solicitação.</span><span class="sxs-lookup"><span data-stu-id="53991-117">Middleware executes in the order in which it's added to the request pipeline.</span></span> <span data-ttu-id="53991-118">Eles também são adicionados no código em vez de arquivos de configuração, geralmente em *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="53991-118">They're also added in code instead of configuration files, usually in *Startup.cs*.</span></span>

## <a name="katana"></a><span data-ttu-id="53991-119">Katana</span><span class="sxs-lookup"><span data-stu-id="53991-119">Katana</span></span>

<span data-ttu-id="53991-120">Os leitores familiarizados com o Katana se sentirão confortáveis em ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="53991-120">Readers familiar with Katana will feel comfortable in ASP.NET Core.</span></span> <span data-ttu-id="53991-121">Na verdade, Katana é uma estrutura da qual ASP.NET Core deriva.</span><span class="sxs-lookup"><span data-stu-id="53991-121">In fact, Katana is a framework from which ASP.NET Core derives.</span></span> <span data-ttu-id="53991-122">Ele apresentou middleware semelhante e padrões de pipeline para ASP.NET 4. x.</span><span class="sxs-lookup"><span data-stu-id="53991-122">It introduced similar middleware and pipeline patterns for ASP.NET 4.x.</span></span> <span data-ttu-id="53991-123">O middleware projetado para Katana pode ser adaptado para funcionar com o pipeline de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="53991-123">Middleware designed for Katana can be adapted to work with the ASP.NET Core pipeline.</span></span>

## <a name="common-middleware"></a><span data-ttu-id="53991-124">Middleware comum</span><span class="sxs-lookup"><span data-stu-id="53991-124">Common middleware</span></span>

<span data-ttu-id="53991-125">O ASP.NET 4. x inclui muitos módulos.</span><span class="sxs-lookup"><span data-stu-id="53991-125">ASP.NET 4.x includes many modules.</span></span> <span data-ttu-id="53991-126">De maneira semelhante, ASP.NET Core também tem muitos componentes de middleware disponíveis.</span><span class="sxs-lookup"><span data-stu-id="53991-126">In a similar fashion, ASP.NET Core has many middleware components available as well.</span></span> <span data-ttu-id="53991-127">Os módulos do IIS podem ser usados em alguns casos com ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="53991-127">IIS modules may be used in some cases with ASP.NET Core.</span></span> <span data-ttu-id="53991-128">Em outros casos, o middleware nativo ASP.NET Core pode estar disponível.</span><span class="sxs-lookup"><span data-stu-id="53991-128">In other cases, native ASP.NET Core middleware may be available.</span></span>

<span data-ttu-id="53991-129">A tabela a seguir lista os componentes e middleware de substituição no ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="53991-129">The following table lists replacement middleware and components in ASP.NET Core.</span></span>

|<span data-ttu-id="53991-130">Módulo</span><span class="sxs-lookup"><span data-stu-id="53991-130">Module</span></span>                 |<span data-ttu-id="53991-131">Módulo ASP.NET 4. x</span><span class="sxs-lookup"><span data-stu-id="53991-131">ASP.NET 4.x module</span></span>           |<span data-ttu-id="53991-132">Opção ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="53991-132">ASP.NET Core option</span></span>|
|-----------------------|-----------------------------|-------------------|
|<span data-ttu-id="53991-133">Erros de HTTP</span><span class="sxs-lookup"><span data-stu-id="53991-133">HTTP errors</span></span>            |`CustomErrorModule`          |[<span data-ttu-id="53991-134">Middleware de páginas de código de status</span><span class="sxs-lookup"><span data-stu-id="53991-134">Status Code Pages Middleware</span></span>](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|<span data-ttu-id="53991-135">Documento padrão</span><span class="sxs-lookup"><span data-stu-id="53991-135">Default document</span></span>       |`DefaultDocumentModule`      |[<span data-ttu-id="53991-136">Middleware de arquivos padrão</span><span class="sxs-lookup"><span data-stu-id="53991-136">Default Files Middleware</span></span>](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|<span data-ttu-id="53991-137">Pesquisa no diretório</span><span class="sxs-lookup"><span data-stu-id="53991-137">Directory browsing</span></span>     |`DirectoryListingModule`     |[<span data-ttu-id="53991-138">Middleware de navegação no diretório</span><span class="sxs-lookup"><span data-stu-id="53991-138">Directory Browsing Middleware</span></span>](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|<span data-ttu-id="53991-139">Compactação dinâmica</span><span class="sxs-lookup"><span data-stu-id="53991-139">Dynamic compression</span></span>    |`DynamicCompressionModule`   |[<span data-ttu-id="53991-140">Middleware de compactação de resposta</span><span class="sxs-lookup"><span data-stu-id="53991-140">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="53991-141">Rastreamento de solicitações com falha</span><span class="sxs-lookup"><span data-stu-id="53991-141">Failed requests tracing</span></span>|`FailedRequestsTracingModule`|[<span data-ttu-id="53991-142">Log de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="53991-142">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|<span data-ttu-id="53991-143">Cache de arquivos</span><span class="sxs-lookup"><span data-stu-id="53991-143">File caching</span></span>           |`FileCacheModule`            |[<span data-ttu-id="53991-144">Middleware de cache de resposta</span><span class="sxs-lookup"><span data-stu-id="53991-144">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="53991-145">Cache HTTP</span><span class="sxs-lookup"><span data-stu-id="53991-145">HTTP caching</span></span>           |`HttpCacheModule`            |[<span data-ttu-id="53991-146">Middleware de cache de resposta</span><span class="sxs-lookup"><span data-stu-id="53991-146">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="53991-147">Log de FTP</span><span class="sxs-lookup"><span data-stu-id="53991-147">HTTP logging</span></span>           |`HttpLoggingModule`          |[<span data-ttu-id="53991-148">Log de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="53991-148">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index)|
|<span data-ttu-id="53991-149">Redirecionamento HTTP</span><span class="sxs-lookup"><span data-stu-id="53991-149">HTTP redirection</span></span>       |`HttpRedirectionModule`      |[<span data-ttu-id="53991-150">Middleware de regravação de URL</span><span class="sxs-lookup"><span data-stu-id="53991-150">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="53991-151">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="53991-151">ISAPI filters</span></span>          |`IsapiFilterModule`          |[<span data-ttu-id="53991-152">Middleware</span><span class="sxs-lookup"><span data-stu-id="53991-152">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="53991-153">ISAPI</span><span class="sxs-lookup"><span data-stu-id="53991-153">ISAPI</span></span>                  |`IsapiModule`                |[<span data-ttu-id="53991-154">Middleware</span><span class="sxs-lookup"><span data-stu-id="53991-154">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="53991-155">Filtragem de solicitações</span><span class="sxs-lookup"><span data-stu-id="53991-155">Request filtering</span></span>      |`RequestFilteringModule`     |[<span data-ttu-id="53991-156">Irule usando de middleware de regravação de URL</span><span class="sxs-lookup"><span data-stu-id="53991-156">URL Rewriting Middleware IRule</span></span>](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|<span data-ttu-id="53991-157">Regravação de URL&#8224;</span><span class="sxs-lookup"><span data-stu-id="53991-157">URL rewriting&#8224;</span></span>   |`RewriteModule`              |[<span data-ttu-id="53991-158">Middleware de regravação de URL</span><span class="sxs-lookup"><span data-stu-id="53991-158">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="53991-159">Compactação estática</span><span class="sxs-lookup"><span data-stu-id="53991-159">Static compression</span></span>     |`StaticCompressionModule`    |[<span data-ttu-id="53991-160">Middleware de compactação de resposta</span><span class="sxs-lookup"><span data-stu-id="53991-160">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="53991-161">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="53991-161">Static content</span></span>         |`StaticFileModule`           |[<span data-ttu-id="53991-162">Middleware de arquivos estáticos</span><span class="sxs-lookup"><span data-stu-id="53991-162">Static File Middleware</span></span>](/aspnet/core/fundamentals/static-files)|
|<span data-ttu-id="53991-163">Autorização de URL</span><span class="sxs-lookup"><span data-stu-id="53991-163">URL authorization</span></span>      |`UrlAuthorizationModule`     |[<span data-ttu-id="53991-164">Identidade do ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="53991-164">ASP.NET Core Identity</span></span>](/aspnet/core/security/authentication/identity)|

<span data-ttu-id="53991-165">Essa lista não é exaustiva, mas deve dar uma ideia de qual mapeamento existe entre as duas estruturas.</span><span class="sxs-lookup"><span data-stu-id="53991-165">This list isn't exhaustive but should give an idea of what mapping exists between the two frameworks.</span></span> <span data-ttu-id="53991-166">Para obter uma lista mais detalhada, consulte [módulos do IIS com ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).</span><span class="sxs-lookup"><span data-stu-id="53991-166">For a more detailed list, see [IIS modules with ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).</span></span>

## <a name="custom-middleware"></a><span data-ttu-id="53991-167">Middleware personalizado</span><span class="sxs-lookup"><span data-stu-id="53991-167">Custom middleware</span></span>

<span data-ttu-id="53991-168">O middleware interno pode não lidar com todos os cenários necessários para um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="53991-168">Built-in middleware may not handle all scenarios needed for an app.</span></span> <span data-ttu-id="53991-169">Nesses casos, faz sentido criar seu próprio middleware.</span><span class="sxs-lookup"><span data-stu-id="53991-169">In such cases, it makes sense to create your own middleware.</span></span> <span data-ttu-id="53991-170">Há várias maneiras de definir o middleware, com o mais simples de ser um simples delegado.</span><span class="sxs-lookup"><span data-stu-id="53991-170">There are multiple ways of defining middleware, with the simplest being a simple delegate.</span></span> <span data-ttu-id="53991-171">Considere o seguinte middleware, que aceita uma solicitação de cultura de uma cadeia de caracteres de consulta:</span><span class="sxs-lookup"><span data-stu-id="53991-171">Consider the following middleware, which accepts a culture request from a query string:</span></span>

```csharp
public class Startup
{
    public void Configure(IApplicationBuilder app)
    {
        app.Use(async (context, next) =>
        {
            var cultureQuery = context.Request.Query["culture"];

            if (!string.IsNullOrWhiteSpace(cultureQuery))
            {
                var culture = new CultureInfo(cultureQuery);

                CultureInfo.CurrentCulture = culture;
                CultureInfo.CurrentUICulture = culture;
            }

            // Call the next delegate/middleware in the pipeline
            await next();
        });

        app.Run(async (context) =>
            await context.Response.WriteAsync(
                $"Hello {CultureInfo.CurrentCulture.DisplayName}"));
    }
}
```

<span data-ttu-id="53991-172">O middleware também pode ser definido como uma classe implementando a `IMiddleware` interface ou seguindo a Convenção de middleware.</span><span class="sxs-lookup"><span data-stu-id="53991-172">Middleware can also be defined as class, either by implementing the `IMiddleware` interface or by following middleware convention.</span></span> <span data-ttu-id="53991-173">Para obter mais informações, consulte [Write custom ASP.NET Core middleware](/aspnet/core/fundamentals/middleware/write).</span><span class="sxs-lookup"><span data-stu-id="53991-173">For more information, see [Write custom ASP.NET Core middleware](/aspnet/core/fundamentals/middleware/write).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="53991-174">[Anterior](data.md) 
> [Avançar](config.md)</span><span class="sxs-lookup"><span data-stu-id="53991-174">[Previous](data.md)
[Next](config.md)</span></span>
