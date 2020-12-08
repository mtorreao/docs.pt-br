---
title: Arquitetar aplicativos Web modernos com o ASP.NET Core e o Azure
description: Um guia que fornece diretrizes de ponta a ponta para a criação de aplicativos Web monolíticos usando o ASP.NET Core e o Azure.
author: ardalis
ms.author: wiwagn
ms.date: 12/07/2020
ms.openlocfilehash: 90d092b2269315e5b6734430e82cc7211324479b
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851289"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="413bd-103">Arquitetar Aplicativos Web Modernos com o ASP.NET Core e o Azure</span><span class="sxs-lookup"><span data-stu-id="413bd-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![Livro de folhas de rosto do guia de aplicativos Web do arquiteto moderno.](./media/index/web-application-guide-cover-image.png)

<span data-ttu-id="413bd-105">**Edição v 5.0** -atualizado para ASP.NET Core 5,0</span><span class="sxs-lookup"><span data-stu-id="413bd-105">**EDITION v5.0** - Updated to ASP.NET Core 5.0</span></span>

<span data-ttu-id="413bd-106">Consulte o [changelog](https://aka.ms/aspnet-ebook-changelog) para obter as atualizações do livro e as contribuições da Comunidade.</span><span class="sxs-lookup"><span data-stu-id="413bd-106">Refer [changelog](https://aka.ms/aspnet-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="413bd-107">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="413bd-107">PUBLISHED BY</span></span>

<span data-ttu-id="413bd-108">Divisão de Desenvolvedores Microsoft, equipes dos produtos .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="413bd-108">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="413bd-109">Uma divisão da Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="413bd-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="413bd-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="413bd-110">One Microsoft Way</span></span>

<span data-ttu-id="413bd-111">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="413bd-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="413bd-112">Copyright © 2020 da Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="413bd-112">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="413bd-113">Todos os direitos reservados.</span><span class="sxs-lookup"><span data-stu-id="413bd-113">All rights reserved.</span></span> <span data-ttu-id="413bd-114">Nenhuma parte do conteúdo deste guia pode ser reproduzida ou transmitida de nenhuma forma nem por nenhum meio sem a permissão por escrito do publicador.</span><span class="sxs-lookup"><span data-stu-id="413bd-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="413bd-115">Este livro é fornecido “no estado em que se encontra” e expressa os pontos de vista e as opiniões do autor.</span><span class="sxs-lookup"><span data-stu-id="413bd-115">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="413bd-116">Os pontos de vista, as opiniões e as informações expressos neste livro, incluindo URLs e outras referências a sites da Internet, podem ser alteradas sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="413bd-116">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="413bd-117"> Alguns exemplos aqui representados são fornecidos somente para fins de ilustração e são fictícios.</span><span class="sxs-lookup"><span data-stu-id="413bd-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="413bd-118">Nenhuma associação ou conexão real é intencional ou deve ser inferida.</span><span class="sxs-lookup"><span data-stu-id="413bd-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="413bd-119">A Microsoft e as marcas listadas em <https://www.microsoft.com> na página da Web "Marcas" são marcas comerciais do grupo de empresas Microsoft.</span><span class="sxs-lookup"><span data-stu-id="413bd-119">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="413bd-120">Mac e macOS são marcas comerciais da Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="413bd-120">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="413bd-121">O logotipo de redistribuição do Docker é uma marca registrada do Docker, Inc. usada pela permissão.</span><span class="sxs-lookup"><span data-stu-id="413bd-121">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="413bd-122">Todas as outras marcas e logotipos são propriedade de seus respectivos proprietários.</span><span class="sxs-lookup"><span data-stu-id="413bd-122">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="413bd-123">Autor:</span><span class="sxs-lookup"><span data-stu-id="413bd-123">Author:</span></span>

> <span data-ttu-id="413bd-124">**Steve "ardalis" Smith** – Arquiteto de software e instrutor – [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="413bd-124">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="413bd-125">Editores:</span><span class="sxs-lookup"><span data-stu-id="413bd-125">Editors:</span></span>

> <span data-ttu-id="413bd-126">**Maira Wenzel**</span><span class="sxs-lookup"><span data-stu-id="413bd-126">**Maira Wenzel**</span></span>

## <a name="action-links"></a><span data-ttu-id="413bd-127">Links de ação</span><span class="sxs-lookup"><span data-stu-id="413bd-127">Action links</span></span>

- <span data-ttu-id="413bd-128">Este livro eletrônico também está disponível em um formato PDF (somente versão em inglês) [Download](https://aka.ms/webappebook)</span><span class="sxs-lookup"><span data-stu-id="413bd-128">This e-book is also available in a PDF format (English version only) [Download](https://aka.ms/webappebook)</span></span>

- <span data-ttu-id="413bd-129">Clonar/bifurcar o aplicativo de referência [eShopOnWeb no GitHub](https://github.com/dotnet-architecture/eShopOnWeb)</span><span class="sxs-lookup"><span data-stu-id="413bd-129">Clone/Fork the reference application [eShopOnWeb on GitHub](https://github.com/dotnet-architecture/eShopOnWeb)</span></span>

## <a name="introduction"></a><span data-ttu-id="413bd-130">Introdução</span><span class="sxs-lookup"><span data-stu-id="413bd-130">Introduction</span></span>

<span data-ttu-id="413bd-131">O .NET 5 e o ASP.NET Core oferecem várias vantagens em relação ao desenvolvimento tradicional do .NET.</span><span class="sxs-lookup"><span data-stu-id="413bd-131">.NET 5 and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="413bd-132">Você deve usar o .NET 5 para seus aplicativos de servidor se alguns ou todos os itens a seguir forem importantes para o sucesso do seu aplicativo:</span><span class="sxs-lookup"><span data-stu-id="413bd-132">You should use .NET 5 for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="413bd-133">Suporte para plataforma cruzada.</span><span class="sxs-lookup"><span data-stu-id="413bd-133">Cross-platform support.</span></span>

- <span data-ttu-id="413bd-134">Uso de microsserviços.</span><span class="sxs-lookup"><span data-stu-id="413bd-134">Use of microservices.</span></span>

- <span data-ttu-id="413bd-135">Uso de contêineres do Docker.</span><span class="sxs-lookup"><span data-stu-id="413bd-135">Use of Docker containers.</span></span>

- <span data-ttu-id="413bd-136">Requisitos de alto desempenho e escalabilidade.</span><span class="sxs-lookup"><span data-stu-id="413bd-136">High performance and scalability requirements.</span></span>

- <span data-ttu-id="413bd-137">Controle de versão lado a lado para versões do .NET por aplicativo no mesmo servidor.</span><span class="sxs-lookup"><span data-stu-id="413bd-137">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="413bd-138">Os aplicativos .NET tradicionais podem e oferecem suporte a muitos desses requisitos, mas ASP.NET Core e o .NET 5 foram otimizados para oferecer suporte aprimorado para os cenários acima.</span><span class="sxs-lookup"><span data-stu-id="413bd-138">Traditional .NET applications can and do support many of these requirements, but ASP.NET Core and .NET 5 have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="413bd-139">Cada vez mais empresas estão optando por hospedar seus aplicativos Web na nuvem usando serviços como o Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="413bd-139">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="413bd-140">Considere hospedar seu aplicativo na nuvem se os seguintes itens forem importantes para seu aplicativo ou organização:</span><span class="sxs-lookup"><span data-stu-id="413bd-140">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="413bd-141">Investimento reduzido nos custos de data center (hardware, software, espaço, utilitários, gerenciamento de servidor, etc.)</span><span class="sxs-lookup"><span data-stu-id="413bd-141">Reduced investment in data center costs (hardware, software, space, utilities, server management, etc.)</span></span>

- <span data-ttu-id="413bd-142">Preços flexíveis (pague com base no uso, não pela capacidade ociosa).</span><span class="sxs-lookup"><span data-stu-id="413bd-142">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="413bd-143">Confiabilidade extrema.</span><span class="sxs-lookup"><span data-stu-id="413bd-143">Extreme reliability.</span></span>

- <span data-ttu-id="413bd-144">Melhoria na mobilidade de aplicativo: altere facilmente onde e como seu aplicativo é implantado.</span><span class="sxs-lookup"><span data-stu-id="413bd-144">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="413bd-145">Capacidade flexível: aumente ou reduza com base em necessidades reais.</span><span class="sxs-lookup"><span data-stu-id="413bd-145">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="413bd-146">A criação de aplicativos Web com o ASP.NET Core, hospedados no Azure, oferece várias vantagens competitivas em relação às alternativas tradicionais.</span><span class="sxs-lookup"><span data-stu-id="413bd-146">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="413bd-147">O ASP.NET Core é otimizado para práticas de desenvolvimento de aplicativos Web e cenários de hospedagem em nuvem modernos.</span><span class="sxs-lookup"><span data-stu-id="413bd-147">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="413bd-148">Neste guia, você aprenderá como arquitetar seus aplicativos ASP.NET Core para aproveitar melhor essas funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="413bd-148">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="version"></a><span data-ttu-id="413bd-149">Versão</span><span class="sxs-lookup"><span data-stu-id="413bd-149">Version</span></span>

<span data-ttu-id="413bd-150">Este guia foi revisado para cobrir a versão do **.net 5,0** junto com muitas atualizações adicionais relacionadas à mesma "onda" de tecnologias (isto é, Azure e tecnologias de terceiros adicionais) que coincidem no tempo com a versão 5,0 do .net.</span><span class="sxs-lookup"><span data-stu-id="413bd-150">This guide has been revised to cover **.NET 5.0** version along with many additional updates related to the same "wave" of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET 5.0 release.</span></span> <span data-ttu-id="413bd-151">É por isso que a versão do livro também foi atualizada para a versão **5,0**.</span><span class="sxs-lookup"><span data-stu-id="413bd-151">That's why the book version has also been updated to version **5.0**.</span></span>

## <a name="purpose"></a><span data-ttu-id="413bd-152">Finalidade</span><span class="sxs-lookup"><span data-stu-id="413bd-152">Purpose</span></span>

<span data-ttu-id="413bd-153">Este guia fornece orientação de ponta a ponta sobre a criação de aplicativos Web *monolíticos* usando o ASP.NET Core e o Azure.</span><span class="sxs-lookup"><span data-stu-id="413bd-153">This guide provides end-to-end guidance on building *monolithic* web applications using ASP.NET Core and Azure.</span></span> <span data-ttu-id="413bd-154">Nesse contexto, "monolítico" refere-se ao fato de que esses aplicativos são implantados como uma única unidade, não como uma coleção de serviços e aplicativos em interação.</span><span class="sxs-lookup"><span data-stu-id="413bd-154">In this context, "monolithic" refers to the fact that these applications are deployed as a single unit, not as a collection of interacting services and applications.</span></span>

<span data-ttu-id="413bd-155">Este guia é complementar aos ["_microserviços .net. Arquitetura para aplicativos .NET em contêineres_"](../microservices/index.md), que se concentram mais no Docker, em microservices e na implantação de contêineres para hospedar aplicativos corporativos.</span><span class="sxs-lookup"><span data-stu-id="413bd-155">This guide is complementary to ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices/index.md), which focuses more on Docker, microservices, and deployment of containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="413bd-156">Microsserviços do .NET.</span><span class="sxs-lookup"><span data-stu-id="413bd-156">.NET Microservices.</span></span> <span data-ttu-id="413bd-157">Arquitetura de aplicativos .NET em contêineres</span><span class="sxs-lookup"><span data-stu-id="413bd-157">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="413bd-158">**livro eletrônico**</span><span class="sxs-lookup"><span data-stu-id="413bd-158">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="413bd-159">**Aplicativo de exemplo**</span><span class="sxs-lookup"><span data-stu-id="413bd-159">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="413bd-160">Quem deve usar este guia</span><span class="sxs-lookup"><span data-stu-id="413bd-160">Who should use this guide</span></span>

<span data-ttu-id="413bd-161">O público-alvo principal deste guia são desenvolvedores, líderes de desenvolvimento e arquitetos interessados em compilar aplicativos Web modernos usando tecnologias e serviços da Microsoft na nuvem.</span><span class="sxs-lookup"><span data-stu-id="413bd-161">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="413bd-162">Um público-alvo secundário são os tomadores de decisões técnicas que já estão familiarizados com o ASP.NET ou com o Azure e estão buscando informações para saber se é interessante atualizar seus projetos novos ou existentes para o ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="413bd-162">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="413bd-163">Como você pode usar este guia</span><span class="sxs-lookup"><span data-stu-id="413bd-163">How you can use this guide</span></span>

<span data-ttu-id="413bd-164">Este guia foi condensado em um documento relativamente pequeno que se concentra na criação de aplicativos Web com as tecnologias modernas do .NET e o Azure.</span><span class="sxs-lookup"><span data-stu-id="413bd-164">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Azure.</span></span> <span data-ttu-id="413bd-165">Como tal, ele pode ser lido em sua totalidade para fornecer uma base de compreensão desses aplicativos e suas considerações técnicas.</span><span class="sxs-lookup"><span data-stu-id="413bd-165">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="413bd-166">O guia, junto com seu aplicativo de exemplo, também pode servir como um ponto de partida ou de referência.</span><span class="sxs-lookup"><span data-stu-id="413bd-166">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="413bd-167">Use o aplicativo de exemplo associado como um modelo para seus próprios aplicativos ou para ver como você poderia organizar os blocos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="413bd-167">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="413bd-168">Confira os princípios do guia, a cobertura das opções de arquitetura e de tecnologia e as considerações de decisões ao ponderar essas opções para seu próprio aplicativo.</span><span class="sxs-lookup"><span data-stu-id="413bd-168">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="413bd-169">Fique à vontade para encaminhar este guia para sua equipe para ajudar a garantir um entendimento comum dessas considerações e oportunidades.</span><span class="sxs-lookup"><span data-stu-id="413bd-169">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="413bd-170">Quando todas as pessoas trabalham com um conjunto comum de terminologia e de princípios subjacentes é mais fácil garantir a aplicação consistente dos padrões e das práticas de arquitetura.</span><span class="sxs-lookup"><span data-stu-id="413bd-170">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="413bd-171">Referências</span><span class="sxs-lookup"><span data-stu-id="413bd-171">References</span></span>

- <span data-ttu-id="413bd-172">**Escolhendo entre o .NET 5 e o .NET Framework para aplicativos de servidor**</span><span class="sxs-lookup"><span data-stu-id="413bd-172">**Choosing between .NET 5 and .NET Framework for server apps**</span></span>  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../../standard/choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="413bd-173">Próximo</span><span class="sxs-lookup"><span data-stu-id="413bd-173">Next</span></span>](modern-web-applications-characteristics.md)
