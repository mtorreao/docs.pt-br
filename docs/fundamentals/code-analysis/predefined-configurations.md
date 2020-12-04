---
title: Arquivos de configuração predefinidos (análise de código)
description: Saiba como usar editorconfig predefinidos e arquivos de conjunto de regras para direcionar tipos específicos de análise de código.
ms.date: 09/24/2020
ms.topic: conceptual
ms.openlocfilehash: 4937dcab1183fa3f63be4afc71627a7c7c08c6bd
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "96585036"
---
# <a name="predefined-configuration-files"></a><span data-ttu-id="257d0-103">Arquivos de configuração predefinidos</span><span class="sxs-lookup"><span data-stu-id="257d0-103">Predefined configuration files</span></span>

<span data-ttu-id="257d0-104">Os arquivos de [conjunto de regras](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) e EditorConfig predefinidos estão disponíveis para facilitar e facilitar a habilitação de uma categoria de regras de qualidade de código, como segurança ou regras de design.</span><span class="sxs-lookup"><span data-stu-id="257d0-104">Predefined EditorConfig and [rule set](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) files are available that make it quick and easy to enable a category of code quality rules, such as security or design rules.</span></span> <span data-ttu-id="257d0-105">Ao habilitar uma categoria específica de regras, você pode identificar problemas direcionados e condições específicas.</span><span class="sxs-lookup"><span data-stu-id="257d0-105">By enabling a specific category of rules, you can identify targeted issues and specific conditions.</span></span> <span data-ttu-id="257d0-106">Para acessar esses arquivos predefinidos, instale o pacote analisador NuGet do [Microsoft. CodeAnalysis. Netanalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) .</span><span class="sxs-lookup"><span data-stu-id="257d0-106">To access these predefined files, install the [Microsoft.CodeAnalysis.NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) NuGet analyzer package.</span></span>

<span data-ttu-id="257d0-107">[Microsoft. CodeAnalysis. Netanalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) inclui arquivos EditorConfig predefinidos e conjuntos de regras para as seguintes categorias de regra:</span><span class="sxs-lookup"><span data-stu-id="257d0-107">[Microsoft.CodeAnalysis.NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) includes predefined EditorConfig files and rule sets for the following rule categories:</span></span>

- <span data-ttu-id="257d0-108">Todas as regras</span><span class="sxs-lookup"><span data-stu-id="257d0-108">All rules</span></span>
- <span data-ttu-id="257d0-109">Fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="257d0-109">Dataflow</span></span>
- <span data-ttu-id="257d0-110">Design</span><span class="sxs-lookup"><span data-stu-id="257d0-110">Design</span></span>
- <span data-ttu-id="257d0-111">Documentação</span><span class="sxs-lookup"><span data-stu-id="257d0-111">Documentation</span></span>
- <span data-ttu-id="257d0-112">Globalização</span><span class="sxs-lookup"><span data-stu-id="257d0-112">Globalization</span></span>
- <span data-ttu-id="257d0-113">Interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="257d0-113">Interoperability</span></span>
- <span data-ttu-id="257d0-114">Facilidade de manutenção</span><span class="sxs-lookup"><span data-stu-id="257d0-114">Maintainability</span></span>
- <span data-ttu-id="257d0-115">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="257d0-115">Naming</span></span>
- <span data-ttu-id="257d0-116">Desempenho</span><span class="sxs-lookup"><span data-stu-id="257d0-116">Performance</span></span>
- <span data-ttu-id="257d0-117">Portado do FxCop</span><span class="sxs-lookup"><span data-stu-id="257d0-117">Ported from FxCop</span></span>
- <span data-ttu-id="257d0-118">Confiabilidade</span><span class="sxs-lookup"><span data-stu-id="257d0-118">Reliability</span></span>
- <span data-ttu-id="257d0-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="257d0-119">Security</span></span>
- <span data-ttu-id="257d0-120">Uso</span><span class="sxs-lookup"><span data-stu-id="257d0-120">Usage</span></span>

<span data-ttu-id="257d0-121">Cada uma dessas categorias de regras tem um EditorConfig ou um arquivo de conjunto de regras para:</span><span class="sxs-lookup"><span data-stu-id="257d0-121">Each of those categories of rules has an EditorConfig or rule set file to:</span></span>

- <span data-ttu-id="257d0-122">Habilitar todas as regras na categoria (e desabilitar todas as outras regras)</span><span class="sxs-lookup"><span data-stu-id="257d0-122">Enable all the rules in the category (and disable all other rules)</span></span>
- <span data-ttu-id="257d0-123">Usar a severidade padrão de cada regra e habilitada por configuração padrão (e desabilitar todas as outras regras)</span><span class="sxs-lookup"><span data-stu-id="257d0-123">Use each rule's default severity and enabled by default setting (and disable all other rules)</span></span>

> [!TIP]
> <span data-ttu-id="257d0-124">A categoria "todas as regras" tem um EditorConfig adicional ou um arquivo de conjunto de regras para desabilitar todas as regras.</span><span class="sxs-lookup"><span data-stu-id="257d0-124">The "all rules" category has an additional EditorConfig or rule set file to disable all rules.</span></span> <span data-ttu-id="257d0-125">Use esse arquivo para eliminar rapidamente qualquer erro ou aviso do analisador em um projeto.</span><span class="sxs-lookup"><span data-stu-id="257d0-125">Use this file to quickly get rid of any analyzer warnings or errors in a project.</span></span>

## <a name="predefined-editorconfig-files"></a><span data-ttu-id="257d0-126">Arquivos EditorConfig predefinidos</span><span class="sxs-lookup"><span data-stu-id="257d0-126">Predefined EditorConfig files</span></span>

<span data-ttu-id="257d0-127">Os arquivos EditorConfig predefinidos para o pacote do analisador Microsoft. CodeAnalysis. netanalyzers estão localizados no subdiretório *EditorConfig* do qual o pacote NuGet foi instalado.</span><span class="sxs-lookup"><span data-stu-id="257d0-127">The predefined EditorConfig files for the Microsoft.CodeAnalysis.NetAnalyzers analyzer package are located in the *editorconfig* subdirectory of where the NuGet package was installed.</span></span> <span data-ttu-id="257d0-128">Por exemplo, o arquivo EditorConfig para habilitar todas as regras de segurança está localizado em *EditorConfig/SecurityRulesEnabled/. EditorConfig*.</span><span class="sxs-lookup"><span data-stu-id="257d0-128">For example, the EditorConfig file to enable all security rules is located at *editorconfig/SecurityRulesEnabled/.editorconfig*.</span></span>

<span data-ttu-id="257d0-129">Copie o arquivo *. editorconfig* escolhido para o diretório raiz do projeto.</span><span class="sxs-lookup"><span data-stu-id="257d0-129">Copy the chosen *.editorconfig* file to your project's root directory.</span></span>

## <a name="predefined-rule-sets"></a><span data-ttu-id="257d0-130">Conjuntos de regras predefinidas</span><span class="sxs-lookup"><span data-stu-id="257d0-130">Predefined rule sets</span></span>

<span data-ttu-id="257d0-131">Os arquivos de conjunto de regras predefinidos para o pacote do analisador Microsoft. CodeAnalysis. netanalyzers estão localizados no subdiretório *RuleSets* de onde o pacote NuGet foi instalado.</span><span class="sxs-lookup"><span data-stu-id="257d0-131">The predefined rule set files for the Microsoft.CodeAnalysis.NetAnalyzers analyzer package are located in the *rulesets* subdirectory of where the NuGet package was installed.</span></span> <span data-ttu-id="257d0-132">Por exemplo, o arquivo de conjunto de regras para habilitar todas as regras de segurança está localizado em *RuleSets/SecurityRulesEnabled. RuleSet*.</span><span class="sxs-lookup"><span data-stu-id="257d0-132">For example, the rule set file to enable all security rules is located at *rulesets/SecurityRulesEnabled.ruleset*.</span></span> <span data-ttu-id="257d0-133">Copie um ou mais conjuntos de regras e cole-os no diretório que contém o projeto.</span><span class="sxs-lookup"><span data-stu-id="257d0-133">Copy one or more of the rule sets and paste them in the directory that contains your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="257d0-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="257d0-134">See also</span></span>

- [<span data-ttu-id="257d0-135">Configuração do analisador</span><span class="sxs-lookup"><span data-stu-id="257d0-135">Analyzer configuration</span></span>](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [<span data-ttu-id="257d0-136">Opções de regra de estilo de código .NET para EditorConfig</span><span class="sxs-lookup"><span data-stu-id="257d0-136">.NET code style rule options for EditorConfig</span></span>](code-style-rule-options.md)
