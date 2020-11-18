---
title: Globalizando e localizando aplicativos do .NET
description: Saiba como desenvolver um aplicativo preparado para o mundo. Leia sobre globalização, revisão de possibilidade e localização no .NET.
ms.date: 06/08/2018
helpviewer_keywords:
- international applications [.NET]
- globalization [.NET], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
ms.openlocfilehash: 670a159844cfeb475b26c1d1aa85e7f09a95c21f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829850"
---
# <a name="globalizing-and-localizing-net-applications"></a><span data-ttu-id="ae2a1-104">Globalizando e localizando aplicativos do .NET</span><span class="sxs-lookup"><span data-stu-id="ae2a1-104">Globalizing and localizing .NET applications</span></span>

<span data-ttu-id="ae2a1-105">O desenvolvimento de um aplicativo que possa ser usado em todo o mundo, incluindo ser localizado em um ou mais idiomas, envolve três etapas: a globalização, a análise da possibilidade de localização e a localização em si.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-105">Developing a world-ready application, including an application that can be localized into one or more languages, involves three steps: globalization, localizability review, and localization.</span></span>

[<span data-ttu-id="ae2a1-106">Globalização</span><span class="sxs-lookup"><span data-stu-id="ae2a1-106">Globalization</span></span>](globalization.md)

<span data-ttu-id="ae2a1-107">Esta etapa envolve a criação e a codificação de um aplicativo que seja independente de cultura e idioma, bem como que ofereça suporte a interfaces de usuário localizadas e dados regionais para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-107">This step involves designing and coding an application that is culture-neutral and language-neutral, and that supports localized user interfaces and regional data for all users.</span></span> <span data-ttu-id="ae2a1-108">Ela envolve a tomada de decisões de design e de programação que não sejam baseadas em suposições para culturas específicas.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-108">It involves making design and programming decisions that are not based on culture-specific assumptions.</span></span> <span data-ttu-id="ae2a1-109">Mesmo quando um aplicativo globalizado não está localizado, ele foi criado e escrito para que possa ser localizado posteriormente em um ou mais idiomas com relativa facilidade.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-109">While a globalized application is not localized, it nevertheless is designed and written so that it can be subsequently localized into one or more languages with relative ease.</span></span>

[<span data-ttu-id="ae2a1-110">Revisão de localização</span><span class="sxs-lookup"><span data-stu-id="ae2a1-110">Localizability review</span></span>](localizability-review.md)

<span data-ttu-id="ae2a1-111">Essa etapa envolve a verificação do código e do design de um aplicativo para garantir que ele possa ser facilmente localizado e para identificar potenciais obstáculos à localização, bem como verificar se o código executável do aplicativo está separado de seus recursos.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-111">This step involves reviewing an application's code and design to ensure that it can be localized easily and to identify potential roadblocks for localization, and verifying that the application's executable code is separated from its resources.</span></span> <span data-ttu-id="ae2a1-112">Se a fase de globalização foi eficaz, a análise de capacidade de localização confirmará as opções de design e codificação feitas durante a globalização.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-112">If the globalization stage was effective, the localizability review will confirm the design and coding choices made during globalization.</span></span> <span data-ttu-id="ae2a1-113">O estágio de localizabilidade também pode identificar todos os problemas restantes para que o código-fonte do aplicativo não precise ser modificado durante o estágio de localização.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-113">The localizability stage may also identify any remaining issues so that an application's source code doesn't have to be modified during the localization stage.</span></span>

[<span data-ttu-id="ae2a1-114">Localização</span><span class="sxs-lookup"><span data-stu-id="ae2a1-114">Localization</span></span>](localization.md)

<span data-ttu-id="ae2a1-115">Essa etapa envolve a personalização de um aplicativo para culturas ou regiões específicas.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-115">This step involves customizing an application for specific cultures or regions.</span></span> <span data-ttu-id="ae2a1-116">Se as etapas de globalização e localizabilidade tiverem sido feitas corretamente, a localização consistirá principalmente na tradução da interface de usuário.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-116">If the globalization and localizability steps have been performed correctly, localization consists primarily of translating the user interface.</span></span>

<span data-ttu-id="ae2a1-117">Seguir estas três etapas oferece duas vantagens:</span><span class="sxs-lookup"><span data-stu-id="ae2a1-117">Following these three steps provides two advantages:</span></span>

- <span data-ttu-id="ae2a1-118">Libera você de ter que readaptar um aplicativo projetado para oferecer suporte a uma única cultura, como inglês dos EUA, para oferecer suporte a culturas adicionais.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-118">It frees you from having to retrofit an application that is designed to support a single culture, such as U.S. English, to support additional cultures.</span></span>

- <span data-ttu-id="ae2a1-119">Isso resulta em aplicativos localizados que são mais estáveis e possuem menos bugs.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-119">It results in localized applications that are more stable and have fewer bugs.</span></span>

<span data-ttu-id="ae2a1-120">O .NET fornece suporte abrangente ao desenvolvimento de aplicativos preparados para o mundo e localizados.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-120">.NET provides extensive support for the development of world-ready and localized applications.</span></span> <span data-ttu-id="ae2a1-121">Em particular, muitos membros de tipos na biblioteca de classes do .NET auxiliam na globalização ao retornarem valores que refletem as convenções da cultura do usuário atual ou de uma cultura específica.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-121">In particular, many type members in the .NET class library aid globalization by returning values that reflect the conventions of either the current user's culture or a specified culture.</span></span> <span data-ttu-id="ae2a1-122">Além disso, o .NET Framework dá suporte a assemblies satélites que facilitam o processo de localizar um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-122">Also, .NET supports satellite assemblies, which facilitate the process of localizing an application.</span></span>

<span data-ttu-id="ae2a1-123">Confira mais informações na [Documentação de globalização](/globalization/).</span><span class="sxs-lookup"><span data-stu-id="ae2a1-123">For additional information, see the [Globalization documentation](/globalization/).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ae2a1-124">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ae2a1-124">In this section</span></span>

[<span data-ttu-id="ae2a1-125">Globalização</span><span class="sxs-lookup"><span data-stu-id="ae2a1-125">Globalization</span></span>](globalization.md)

<span data-ttu-id="ae2a1-126">Discute o primeiro estágio da criação de um aplicativo pronto para o mundo, o que envolve o projeto e a codificação de um aplicativo independente de cultura e idioma.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-126">Discusses the first stage of creating a world-ready application, which involves designing and coding an application that is culture-neutral and language-neutral.</span></span>

[<span data-ttu-id="ae2a1-127">Globalização e ICU do .NET</span><span class="sxs-lookup"><span data-stu-id="ae2a1-127">.NET globalization and ICU</span></span>](globalization-icu.md)

<span data-ttu-id="ae2a1-128">Descreve como a globalização [do .NET usa componentes internacionais para Unicode (ICU)](http://site.icu-project.org/home).</span><span class="sxs-lookup"><span data-stu-id="ae2a1-128">Describes how .NET globalization uses [International Components for Unicode (ICU)](http://site.icu-project.org/home).</span></span>

[<span data-ttu-id="ae2a1-129">Revisão de localização</span><span class="sxs-lookup"><span data-stu-id="ae2a1-129">Localizability review</span></span>](localizability-review.md)

<span data-ttu-id="ae2a1-130">Discute o segundo estágio da criação de um aplicativo localizado, o que envolve a identificação de obstáculos potenciais à localização.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-130">Discusses the second stage of creating a localized application, which involves identifying potential roadblocks to localization.</span></span>

[<span data-ttu-id="ae2a1-131">Localização</span><span class="sxs-lookup"><span data-stu-id="ae2a1-131">Localization</span></span>](localization.md)

<span data-ttu-id="ae2a1-132">Discute o estágio final da criação de um aplicativo localizado, o que envolve a personalização da interface de usuário de um aplicativo para regiões ou culturas específicas.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-132">Discusses the final stage of creating a localized application, which involves customizing an application's user interface for specific regions or cultures.</span></span>

[<span data-ttu-id="ae2a1-133">Operações de cadeia de caracteres que não diferenciam culturas</span><span class="sxs-lookup"><span data-stu-id="ae2a1-133">Culture-insensitive string operations</span></span>](culture-insensitive-string-operations.md)

<span data-ttu-id="ae2a1-134">Descreve como usar métodos e classes do .NET sensíveis a culturas por padrão para obter resultados sem diferenciação de cultura.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-134">Describes how to use .NET methods and classes that are culture-sensitive by default to obtain culture-insensitive results.</span></span>

[<span data-ttu-id="ae2a1-135">Práticas recomendadas para o desenvolvimento de aplicativos prontos para o mundo</span><span class="sxs-lookup"><span data-stu-id="ae2a1-135">Best practices for developing world-ready applications</span></span>](best-practices-for-developing-world-ready-apps.md)

<span data-ttu-id="ae2a1-136">Descreve as práticas recomendadas a serem seguidas para globalização, localização e desenvolvimento de aplicativos ASP.NET prontos para o mundo.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-136">Describes the best practices to follow for globalization, localization, and developing world-ready ASP.NET applications.</span></span>

## <a name="reference"></a><span data-ttu-id="ae2a1-137">Referência</span><span class="sxs-lookup"><span data-stu-id="ae2a1-137">Reference</span></span>

- <span data-ttu-id="ae2a1-138">Namespace <xref:System.Globalization?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ae2a1-138"><xref:System.Globalization?displayProperty=nameWithType> namespace</span></span>

   <span data-ttu-id="ae2a1-139">Contém classes que definem informações relacionadas à cultura, incluindo idioma, país/região, calendários em uso, padrões de formato para datas, moeda, números e ordem de classificação para cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-139">Contains classes that define culture-related information, including the language, the country/region, the calendars in use, the format patterns for dates, currency, and numbers, and the sort order for strings.</span></span>

- <span data-ttu-id="ae2a1-140">Namespace <xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="ae2a1-140"><xref:System.Resources> namespace</span></span>

   <span data-ttu-id="ae2a1-141">Fornece classes para a criação, manipulação e utilização de recursos.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-141">Provides classes for creating, manipulating, and using resources.</span></span>

- <span data-ttu-id="ae2a1-142">Namespace <xref:System.Text></span><span class="sxs-lookup"><span data-stu-id="ae2a1-142"><xref:System.Text> namespace</span></span>

   <span data-ttu-id="ae2a1-143">Contém classes que representam ASCII, ANSI, Unicode e outras codificações de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-143">Contains classes representing ASCII, ANSI, Unicode, and other character encodings.</span></span>

- [<span data-ttu-id="ae2a1-144">Resgen.exe (gerador de arquivo de recurso)</span><span class="sxs-lookup"><span data-stu-id="ae2a1-144">Resgen.exe (Resource File Generator)</span></span>](../../framework/tools/resgen-exe-resource-file-generator.md)

   <span data-ttu-id="ae2a1-145">Descreve como usar Resgen.exe para converter arquivos .txt e XML (.resx) para arquivos .resources binários do Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-145">Describes how to use Resgen.exe to convert .txt files and XML-based resource format (.resx) files to common language runtime binary .resources files.</span></span>

- [<span data-ttu-id="ae2a1-146">Winres.exe (Windows Forms editor de recursos)</span><span class="sxs-lookup"><span data-stu-id="ae2a1-146">Winres.exe (Windows Forms Resource Editor)</span></span>](../../framework/tools/winres-exe-windows-forms-resource-editor.md)

   <span data-ttu-id="ae2a1-147">Descreve como usar Winres.exe para localizar formulários do Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ae2a1-147">Describes how to use Winres.exe to localize Windows Forms forms.</span></span>
