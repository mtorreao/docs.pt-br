---
title: Visão geral das bibliotecas de tempo de execução
description: Saiba o que está incluído na seção bibliotecas de tempo de execução do Sumário.
author: tdykstra
ms.date: 11/12/2020
ms.openlocfilehash: 5a8f888e1778553e2968277738cfef5134f11589
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687890"
---
# <a name="runtime-libraries-overview"></a><span data-ttu-id="4fedc-103">Visão geral das bibliotecas de tempo de execução</span><span class="sxs-lookup"><span data-stu-id="4fedc-103">Runtime libraries overview</span></span>

<span data-ttu-id="4fedc-104">O [tempo de execução do .net](../core/introduction.md#sdk-and-runtimes), que é instalado em um computador para uso por [aplicativos dependentes da estrutura](../core/introduction.md#deployment-models), tem um conjunto padrão de bibliotecas de classes, conhecido como bibliotecas de tempo de [execução](glossary.md#runtime), [bibliotecas de estruturas](glossary.md#framework-libraries)ou a [BCL (biblioteca de classes base)](glossary.md#bcl).</span><span class="sxs-lookup"><span data-stu-id="4fedc-104">The [.NET runtime](../core/introduction.md#sdk-and-runtimes), which is installed on a machine for use by [framework-dependent apps](../core/introduction.md#deployment-models), has an expansive standard set of class libraries, known as [runtime libraries](glossary.md#runtime), [framework libraries](glossary.md#framework-libraries), or the [base class library (BCL)](glossary.md#bcl).</span></span> <span data-ttu-id="4fedc-105">Além disso, há extensões para as bibliotecas de tempo de execução, fornecidas em pacotes NuGet.</span><span class="sxs-lookup"><span data-stu-id="4fedc-105">In addition, there are extensions to the runtime libraries, provided in NuGet packages.</span></span>

<span data-ttu-id="4fedc-106">Essas bibliotecas fornecem implementações para muitos tipos, algoritmos e funcionalidades de utilitário específicos de aplicativos e gerais.</span><span class="sxs-lookup"><span data-stu-id="4fedc-106">These libraries provide implementations for many general and app-specific types, algorithms, and utility functionality.</span></span>

## <a name="runtime-libraries"></a><span data-ttu-id="4fedc-107">Bibliotecas de runtime</span><span class="sxs-lookup"><span data-stu-id="4fedc-107">Runtime libraries</span></span>

<span data-ttu-id="4fedc-108">Essas bibliotecas fornecem os tipos básicos e a funcionalidade do utilitário e são a base de todas as outras bibliotecas de classes do .NET.</span><span class="sxs-lookup"><span data-stu-id="4fedc-108">These libraries provide the foundational types and utility functionality and are the base of all other .NET class libraries.</span></span> <span data-ttu-id="4fedc-109">Um exemplo é a <xref:System.String?displayProperty=nameWithType> classe, que fornece APIs para trabalhar com cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4fedc-109">An example is the <xref:System.String?displayProperty=nameWithType> class, which provides APIs for working with strings.</span></span> <span data-ttu-id="4fedc-110">Outro exemplo são as [bibliotecas de serialização](serialization/index.md).</span><span class="sxs-lookup"><span data-stu-id="4fedc-110">Another example is the [serialization libraries](serialization/index.md).</span></span>

## <a name="extensions-to-the-runtime-libraries"></a><span data-ttu-id="4fedc-111">Extensões para as bibliotecas de tempo de execução</span><span class="sxs-lookup"><span data-stu-id="4fedc-111">Extensions to the runtime libraries</span></span>

<span data-ttu-id="4fedc-112">Algumas bibliotecas são fornecidas em pacotes NuGet em vez de incluídos na [estrutura compartilhada](glossary.md#shared-framework)do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="4fedc-112">Some libraries are provided in NuGet packages rather than included in the runtime's [shared framework](glossary.md#shared-framework).</span></span> <span data-ttu-id="4fedc-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4fedc-113">For example:</span></span>

* [<span data-ttu-id="4fedc-114">Logging</span><span class="sxs-lookup"><span data-stu-id="4fedc-114">Logging</span></span>](../core/extensions/logging.md)
* [<span data-ttu-id="4fedc-115">Injeção de dependência</span><span class="sxs-lookup"><span data-stu-id="4fedc-115">Dependency injection</span></span>](../core/extensions/dependency-injection.md)
* [<span data-ttu-id="4fedc-116">Configuration</span><span class="sxs-lookup"><span data-stu-id="4fedc-116">Configuration</span></span>](../core/extensions/configuration.md)

## <a name="see-also"></a><span data-ttu-id="4fedc-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4fedc-117">See also</span></span>

* [<span data-ttu-id="4fedc-118">Introdução ao .NET</span><span class="sxs-lookup"><span data-stu-id="4fedc-118">Introduction to .NET</span></span>](../core/introduction.md)
* [<span data-ttu-id="4fedc-119">Instalar o SDK ou tempo de execução do .NET</span><span class="sxs-lookup"><span data-stu-id="4fedc-119">Install .NET SDK or runtime</span></span>](../core/install/index.yml)
* [<span data-ttu-id="4fedc-120">Selecione o SDK .NET ou a versão de tempo de execução instalada para usar</span><span class="sxs-lookup"><span data-stu-id="4fedc-120">Select the installed .NET SDK or runtime version to use</span></span>](../core/versions/selection.md)
* [<span data-ttu-id="4fedc-121">Publicar aplicativos dependentes da estrutura</span><span class="sxs-lookup"><span data-stu-id="4fedc-121">Publish framework-dependent apps</span></span>](../core/deploying/index.md#publish-framework-dependent)
