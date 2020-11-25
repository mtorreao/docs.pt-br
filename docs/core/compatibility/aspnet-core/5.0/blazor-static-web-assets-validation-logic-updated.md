---
title: 'Alteração significativa: mais incrivelmente: lógica de validação atualizada para ativos da Web estáticos'
description: 'Saiba mais sobre as alterações significativas no ASP.NET Core 5,0 intitulados mais recentes: lógica de validação atualizada para ativos da Web estáticos'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f201818c0130739e8da4f42e7b1f3a1987f70d1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760376"
---
# <a name="blazor-updated-validation-logic-for-static-web-assets"></a><span data-ttu-id="b3bbc-103">Mais incrivelmente: lógica de validação atualizada para ativos da Web estáticos</span><span class="sxs-lookup"><span data-stu-id="b3bbc-103">Blazor: Updated validation logic for static web assets</span></span>

<span data-ttu-id="b3bbc-104">Houve um problema na validação de conflito para ativos da Web estáticos no ASP.NET Core 3,1 e no Webassembly 3,2 de mais.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-104">There was an issue in conflict validation for static web assets in ASP.NET Core 3.1 and Blazor WebAssembly 3.2.</span></span> <span data-ttu-id="b3bbc-105">O problema:</span><span class="sxs-lookup"><span data-stu-id="b3bbc-105">The issue:</span></span>

* <span data-ttu-id="b3bbc-106">Impedia a detecção adequada de conflitos entre os ativos do host e os ativos das bibliotecas de classe Razor (RCLs) e dos aplicativos Webassembly mais valiosos.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-106">Prevented proper conflict detection between the host assets and assets from Razor Class Libraries (RCLs) and Blazor WebAssembly apps.</span></span>
* <span data-ttu-id="b3bbc-107">Afeta principalmente os aplicativos Webassembly mais valiosos, já que, por padrão, os ativos da Web estáticos no RCLs são servidos sob o `_content/$(PackageId)` prefixo.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-107">Mostly affects Blazor WebAssembly apps, since by default, static web assets in RCLs are served under the `_content/$(PackageId)` prefix.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b3bbc-108">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="b3bbc-108">Version introduced</span></span>

<span data-ttu-id="b3bbc-109">5.0</span><span class="sxs-lookup"><span data-stu-id="b3bbc-109">5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="b3bbc-110">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="b3bbc-110">Old behavior</span></span>

<span data-ttu-id="b3bbc-111">Durante o desenvolvimento, os ativos da Web estáticos de um RCL podem ser silenciosamente substituídos por ativos de projeto de host na mesma caminho do host.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-111">During development, an RCL's static web assets could be silently overridden with host project assets on the same host path.</span></span> <span data-ttu-id="b3bbc-112">Considere um RCL que definiu um ativo estático da Web para ser servido em */folder/file.txt*.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-112">Consider an RCL that has defined a static web asset to be served at */folder/file.txt*.</span></span> <span data-ttu-id="b3bbc-113">Se o host colocou um arquivo em *wwwroot/pasta/file.txt*, o arquivo no servidor substituiu silenciosamente o arquivo no aplicativo Webassembly RCL ou mais novo.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-113">If the host placed a file at *wwwroot/folder/file.txt*, the file on the server silently overrode the file on the RCL or Blazor WebAssembly app.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="b3bbc-114">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="b3bbc-114">New behavior</span></span>

<span data-ttu-id="b3bbc-115">ASP.NET Core detecta corretamente quando esse problema ocorre.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-115">ASP.NET Core correctly detects when this issue happens.</span></span> <span data-ttu-id="b3bbc-116">Ele informa a você, o usuário, do conflito para que você possa executar a ação apropriada.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-116">It informs you, the user, of the conflict so that you can take the appropriate action.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b3bbc-117">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="b3bbc-117">Reason for change</span></span>

<span data-ttu-id="b3bbc-118">Os ativos da Web estáticos não devem ser substituíveis por arquivos no host *wwwroot* do projeto.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-118">Static web assets weren't intended to be overridable by files on the *wwwroot* host of the project.</span></span> <span data-ttu-id="b3bbc-119">Permitir a substituição desses arquivos pode levar a erros que são difíceis de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-119">Allowing for the overriding of those files could lead to errors that are difficult to diagnose.</span></span> <span data-ttu-id="b3bbc-120">O resultado pode ser alterações de comportamento indefinido em aplicativos publicados.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-120">The result could be undefined behavior changes in published apps.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b3bbc-121">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="b3bbc-121">Recommended action</span></span>

<span data-ttu-id="b3bbc-122">Por padrão, não há motivo para um arquivo RCL entrar em conflito com um arquivo no host.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-122">By default, there's no reason for an RCL file to conflict with a file on the host.</span></span> <span data-ttu-id="b3bbc-123">Os arquivos RCL são prefixados com `_content/${PackageId}` .</span><span class="sxs-lookup"><span data-stu-id="b3bbc-123">RCL files are prefixed with `_content/${PackageId}`.</span></span> <span data-ttu-id="b3bbc-124">Os arquivos Webassembly mais claros são colocados na raiz do espaço de URL do host, o que torna os conflitos mais fáceis.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-124">Blazor WebAssembly files are placed at the root of the host URL space, which makes conflicts easier.</span></span> <span data-ttu-id="b3bbc-125">Por exemplo, os aplicativos Webassembly mais poseriais contêm um arquivo *favicon. ico* que o host também pode incluir em sua pasta *wwwroot* .</span><span class="sxs-lookup"><span data-stu-id="b3bbc-125">For example, Blazor WebAssembly apps contain a *favicon.ico* file that the host might also include in its *wwwroot* folder.</span></span>

<span data-ttu-id="b3bbc-126">Se a origem do conflito for um arquivo RCL, isso geralmente significa que o código está copiando os ativos da biblioteca para a pasta *wwwroot* do projeto.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-126">If the conflict's source is an RCL file, it often means code is copying assets from the library into the project's *wwwroot* folder.</span></span> <span data-ttu-id="b3bbc-127">Escrever código para copiar arquivos anula um objetivo principal de ativos da Web estáticos.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-127">Writing code to copy files defeats a primary goal of static web assets.</span></span> <span data-ttu-id="b3bbc-128">Essa meta é fundamental para obter atualizações no navegador quando o conteúdo é atualizado sem a necessidade de disparar uma nova compilação.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-128">This goal is fundamental to get updates on the browser when the contents are updated without having to trigger a new compilation.</span></span>

<span data-ttu-id="b3bbc-129">Você pode optar por preservar esse comportamento e manter o arquivo no host.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-129">You may choose to preserve this behavior and maintain the file on the host.</span></span> <span data-ttu-id="b3bbc-130">Para fazer isso, remova o arquivo da lista de ativos da Web estáticos com um destino MSBuild personalizado.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-130">To do so, remove the file from the list of static web assets with a custom MSBuild target.</span></span>

<span data-ttu-id="b3bbc-131">Para usar o arquivo do RCL ou o arquivo do aplicativo Webassembly mais novo, em vez do arquivo do projeto host, remova o arquivo do projeto host.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-131">To use the RCL's file or the Blazor WebAssembly app's file instead of the host project's file, remove the file from the host project.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b3bbc-132">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="b3bbc-132">Affected APIs</span></span>

<span data-ttu-id="b3bbc-133">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b3bbc-133">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
