---
title: ASP.NET Core gRPC para desenvolvedores do WCF – gRPC para desenvolvedores do WCF
description: Introdução à criação de serviços gRPCs no ASP.NET Core 5,0 para desenvolvedores do WCF
ms.date: 01/06/2021
ms.openlocfilehash: 26cce6bb784c08a5b59623ff5882fcf2fbb9e9ac
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970187"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="ccc4f-103">ASP.NET Core gRPC para desenvolvedores do WCF</span><span class="sxs-lookup"><span data-stu-id="ccc4f-103">ASP.NET Core gRPC for WCF Developers</span></span>

![imagem da capa](./media/cover.png)

<span data-ttu-id="ccc4f-105">Edição v 1.0.1-atualizado para ASP.NET Core 5,0</span><span class="sxs-lookup"><span data-stu-id="ccc4f-105">EDITION v1.0.1 - Updated to ASP.NET Core 5.0</span></span>

<span data-ttu-id="ccc4f-106">Consulte o [changelog](https://aka.ms/grpc-ebook-changelog) para obter as atualizações do livro e as contribuições da Comunidade.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-106">Refer [changelog](https://aka.ms/grpc-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="ccc4f-107">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="ccc4f-107">PUBLISHED BY</span></span>

<span data-ttu-id="ccc4f-108">Divisão de Desenvolvedores Microsoft, equipes dos produtos .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ccc4f-108">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="ccc4f-109">Uma divisão da Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="ccc4f-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="ccc4f-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="ccc4f-110">One Microsoft Way</span></span>

<span data-ttu-id="ccc4f-111">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="ccc4f-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="ccc4f-112">Copyright © 2021 da Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="ccc4f-112">Copyright © 2021 by Microsoft Corporation</span></span>

<span data-ttu-id="ccc4f-113">Todos os direitos reservados.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-113">All rights reserved.</span></span> <span data-ttu-id="ccc4f-114">Nenhuma parte do conteúdo deste guia pode ser reproduzida ou transmitida de nenhuma forma nem por nenhum meio sem a permissão por escrito do publicador.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="ccc4f-115">Este livro é fornecido “no estado em que se encontra” e expressa os pontos de vista e as opiniões do autor.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-115">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="ccc4f-116">Os pontos de vista, as opiniões e as informações expressos neste guia, incluindo URLs e outras referências a sites da Internet, podem ser alteradas sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-116">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="ccc4f-117"> Alguns exemplos aqui representados são fornecidos somente para fins de ilustração e são fictícios.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="ccc4f-118">Nenhuma associação ou conexão real é intencional ou deve ser inferida.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="ccc4f-119">A Microsoft e as marcas listadas em <https://www.microsoft.com> na página da Web "Marcas" são marcas comerciais do grupo de empresas Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-119">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="ccc4f-120">O logotipo de redistribuição do Docker é uma marca registrada do Docker, Inc. usada pela permissão.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="ccc4f-121">Todas as outras marcas e logotipos são propriedade de seus respectivos proprietários.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="ccc4f-122">Autores:</span><span class="sxs-lookup"><span data-stu-id="ccc4f-122">Authors:</span></span>

> <span data-ttu-id="ccc4f-123">**Mark** diretor técnico de Rendle – [recódigo Visual](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="ccc4f-123">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="ccc4f-124">**Miranda Steiner** – autor técnico</span><span class="sxs-lookup"><span data-stu-id="ccc4f-124">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="ccc4f-125">Editor:</span><span class="sxs-lookup"><span data-stu-id="ccc4f-125">Editor:</span></span>

> <span data-ttu-id="ccc4f-126">**Maira Wenzel** -Sr. Content Developer-Microsoft</span><span class="sxs-lookup"><span data-stu-id="ccc4f-126">**Maira Wenzel** - Sr. Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="ccc4f-127">Introdução</span><span class="sxs-lookup"><span data-stu-id="ccc4f-127">Introduction</span></span>

<span data-ttu-id="ccc4f-128">o gRPC é uma estrutura moderna para a criação de serviços em rede e aplicativos distribuídos.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-128">gRPC is a modern framework for building networked services and distributed applications.</span></span> <span data-ttu-id="ccc4f-129">Imagine o desempenho das associações NetTCP do Windows Communication Foundation (WCF), combinadas com a interoperabilidade entre plataformas do SOAP.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-129">Imagine the performance of Windows Communication Foundation (WCF) NetTCP bindings, combined with the cross-platform interoperability of SOAP.</span></span> <span data-ttu-id="ccc4f-130">o gRPC se baseia no HTTP/2 e no protocolo de codificação de mensagens Protobuf para fornecer comunicação de alto desempenho e baixa largura de banda entre aplicativos e serviços.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-130">gRPC builds on HTTP/2 and the Protobuf message-encoding protocol to provide high performance, low-bandwidth communication between applications and services.</span></span> <span data-ttu-id="ccc4f-131">Ele dá suporte à geração de código de servidor e cliente nas linguagens e plataformas de programação mais populares, incluindo .NET, Java, Python, Node.js, Go e C++.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-131">It supports server and client code generation across most popular programming languages and platforms, including .NET, Java, Python, Node.js, Go, and C++.</span></span> <span data-ttu-id="ccc4f-132">Com o suporte de primeira classe para gRPC no ASP.NET Core 5,0, juntamente com as ferramentas e bibliotecas existentes do gRPC para .NET Framework 4. x, é uma excelente alternativa ao WCF para equipes de desenvolvimento que buscam adotar o .NET em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-132">With the first-class support for gRPC in ASP.NET Core 5.0, alongside the existing gRPC tools and libraries for .NET Framework 4.x, it's an excellent alternative to WCF for development teams looking to adopt .NET in their organizations.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="ccc4f-133">Quem deve usar este guia</span><span class="sxs-lookup"><span data-stu-id="ccc4f-133">Who should use this guide</span></span>

<span data-ttu-id="ccc4f-134">Este guia foi escrito para desenvolvedores que trabalham em .NET Framework ou .NET que usavam o WCF anteriormente e que estão buscando migrar seus aplicativos para um ambiente de RPC moderno para .NET Core 3,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-134">This guide was written for developers working in .NET Framework or .NET who have previously used WCF, and who are seeking to migrate their applications to a modern RPC environment for .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="ccc4f-135">Mais geralmente, se você estiver atualizando ou considerando a atualização para o .NET 5 e quiser usar as ferramentas internas do gRPC, este guia também será útil.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-135">More generally, if you are upgrading, or considering upgrading, to .NET 5, and you want to use the built-in gRPC tools, this guide is also useful.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="ccc4f-136">Como você pode usar este guia</span><span class="sxs-lookup"><span data-stu-id="ccc4f-136">How you can use this guide</span></span>

<span data-ttu-id="ccc4f-137">Esta é uma breve introdução à criação de serviços gRPCs no ASP.NET Core 5,0, com referência específica ao WCF como uma plataforma análoga.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-137">This is a short introduction to building gRPC Services in ASP.NET Core 5.0, with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="ccc4f-138">Ele explica os princípios de gRPC, relacionando cada conceito aos recursos equivalentes do WCF e oferece orientação para migrar um aplicativo WCF existente para o gRPC.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-138">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="ccc4f-139">Ele também é útil para desenvolvedores que têm experiência com o WCF e procuram aprender a gRPC para criar novos serviços.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-139">It's also useful for developers who have experience with WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="ccc4f-140">Você pode usar os aplicativos de exemplo como um modelo ou referência para seus próprios projetos e você é livre para copiar e reutilizar o código do livro ou de seus exemplos.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-140">You can use the sample applications as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="ccc4f-141">Fique à vontade para encaminhar este guia para sua equipe para ajudar a garantir um entendimento comum dessas considerações e oportunidades.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-141">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="ccc4f-142">Ter todos trabalhando em um conjunto comum de termos e princípios subjacentes ajuda a garantir a aplicação consistente de práticas e padrões de arquitetura.</span><span class="sxs-lookup"><span data-stu-id="ccc4f-142">Having everybody working from a common set of terms and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="ccc4f-143">Referências</span><span class="sxs-lookup"><span data-stu-id="ccc4f-143">References</span></span>

- <span data-ttu-id="ccc4f-144">**site do gRPC**
  <https://grpc.io></span><span class="sxs-lookup"><span data-stu-id="ccc4f-144">**gRPC website**
<https://grpc.io></span></span>
- <span data-ttu-id="ccc4f-145">**Escolhendo entre o .NET 5 e o .NET Framework para aplicativos de servidor**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="ccc4f-145">**Choosing between .NET 5 and .NET Framework for server apps**
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="ccc4f-146">Próximo</span><span class="sxs-lookup"><span data-stu-id="ccc4f-146">Next</span></span>](introduction.md)
