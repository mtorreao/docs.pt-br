---
title: Análise de código no .NET
titleSuffix: ''
description: Saiba mais sobre a análise de código-fonte no SDK do .NET.
ms.date: 08/22/2020
ms.topic: overview
ms.custom: updateeachrelease
helpviewer_keywords:
- code analysis
- code analyzers
ms.openlocfilehash: ca3a9cb914befbc8e0982070b818b27ee3143793
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "96585543"
---
# <a name="overview-of-net-source-code-analysis"></a>Visão geral da análise de código-fonte do .NET

Os analisadores do .NET Compiler Platform (Roslyn) inspecionam código em C# ou no Visual Basic em busca de problemas de estilo e de qualidade. Do .NET 5.0 em diante, esses analisadores estão incluídos no SDK do .NET. (Anteriormente, você instalou analisadores de qualidade de código como um [pacote NuGet](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers)e analisadores de estilo de código foram instalados com o Visual Studio.)

- [Análise de qualidade de código (regras "CAxxxx")](#code-quality-analysis)
- [Análise de estilo de código (regras "IDExxxx")](#code-style-analysis)

Se violações de regra forem encontradas por um analisador, elas serão relatadas como uma sugestão, aviso ou erro, dependendo de como cada regra é [configurada](configuration-options.md). Violações de análise de código aparecem com o prefixo "CA" ou "IDE" para diferenciá-las dos erros do compilador.

> [!TIP]
>
> - Você também pode instalar analisadores de terceiros, como [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/), [analisadores de xUnit](https://www.nuget.org/packages/xunit.analyzers/)e o [analisador de sonar](https://www.nuget.org/packages/SonarAnalyzer.CSharp/).
> - Se você estiver usando o Visual Studio, muitas regras do analisador têm *correções de código* associadas que você pode aplicar para corrigir o problema. As correções de código são mostradas no menu de ícones de lâmpada.

## <a name="code-quality-analysis"></a>Análise de qualidade de código

_As regras de análise de qualidade de código ("AC")_ inspecionam seu código em C# ou Visual Basic para fins de segurança, desempenho, design e outros problemas. A análise é habilitada, por padrão, para projetos direcionados ao .NET 5,0 ou posterior. Você pode habilitar a análise de código em projetos direcionados a versões anteriores do .NET definindo a propriedade [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) como `true` . Você também pode desabilitar a análise de código para seu projeto definindo `EnableNETAnalyzers` como `false` .

> [!TIP]
> No Visual Studio, você pode habilitar ou desabilitar a análise de código usando o projeto janela Propriedades. Para acessar o projeto janela Propriedades, clique com o botão direito do mouse em um projeto dentro de Gerenciador de Soluções e selecione **Propriedades**. Em seguida, selecione a guia **análise de código** e marque ou desmarque a caixa de seleção para **habilitar os analisadores .net**.

### <a name="enabled-rules"></a>Regras habilitadas

As regras a seguir estão habilitadas, por padrão, no .NET 5,0 Preview 8.

| ID do diagnóstico | Categoria | Severidade | Descrição |
| - | - | - | - |
| [CA1416](/visualstudio/code-quality/ca1416) | Interoperabilidade | Aviso | Analisador de compatibilidade de plataforma |
| [CA1417](/visualstudio/code-quality/ca1417) | Interoperabilidade | Aviso | Não usar `OutAttribute` em parâmetros de cadeia de caracteres para P/Invokes |
| [CA1831](/visualstudio/code-quality/ca1831) | Desempenho | Aviso | Use `AsSpan` em vez de indexadores baseados em intervalo para cadeia de caracteres quando apropriado |
| [CA2013](/visualstudio/code-quality/ca2013) | Confiabilidade | Aviso | Não usar `ReferenceEquals` com tipos de valor |
| [CA2014](/visualstudio/code-quality/ca2014) | Confiabilidade | Aviso | Não usar `stackalloc` em loops |
| [CA2015](/visualstudio/code-quality/ca2015) | Confiabilidade | Aviso | Não defina finalizadores para tipos derivados de <xref:System.Buffers.MemoryManager%601> |
| [CA2200](/visualstudio/code-quality/ca2200) | Uso | Aviso | Relançar para preservar detalhes da pilha
| [CA2247](/visualstudio/code-quality/ca2247) | Uso | Aviso | O argumento passado para o Construtor TaskCompletionSource deve ser <xref:System.Threading.Tasks.TaskCreationOptions> enum em vez de <xref:System.Threading.Tasks.TaskContinuationOptions> |

Você pode alterar a severidade dessas regras para desabilitá-las ou promovê-las para erros.

Para obter uma lista completa das regras de qualidade de código disponíveis, consulte [regras de qualidade de código](quality-rules/index.md).

### <a name="enable-additional-rules"></a>Habilitar regras adicionais

A partir do .NET 5,0 RC2, o SDK do .NET é fornecido com todas as [regras de qualidade de código "CA"](/visualstudio/code-quality/code-analysis-for-managed-code-warnings). Para obter uma lista completa das regras incluídas em cada versão do SDK do .NET, consulte [versões do analisador](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).

#### <a name="default-analysis-mode"></a>Modo de análise padrão

No modo de análise padrão, algumas regras são [habilitadas por padrão](#enabled-rules) como avisos de compilação. Algumas outras regras são habilitadas por padrão apenas como sugestões de IDE do Visual Studio com correções de código correspondentes. As regras restantes são desabilitadas por padrão. A [lista completa de regras](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md) inclui a severidade padrão de cada regra e se a regra está ou não habilitada por padrão no modo de análise padrão.

#### <a name="custom-analysis-mode"></a>Modo de análise personalizada

Você pode [configurar regras de análise de código](configuration-options.md) para habilitar ou desabilitar uma regra individual ou uma categoria de regras. Além disso, você pode usar a propriedade [analysismode](../../core/project-sdk/msbuild-props.md#analysismode) para alternar para um dos seguintes modos de análise personalizados:

- Modo _agressivo_ ou _de recusa_ : todas as regras são habilitadas por padrão como avisos de compilação. Você pode [recusar](configuration-options.md) seletivamente as regras individuais para desabilitá-las.
- Modo _conservador_ ou _opt-in_ : todas as regras são desabilitadas por padrão. Você pode [optar](configuration-options.md) seletivamente por regras individuais para habilitá-las.

### <a name="treat-warnings-as-errors"></a>Tratar avisos como erros

Se você usar o `-warnaserror` sinalizador ao compilar seus projetos, todos os avisos de análise de código também serão tratados como erros. Se você não quiser que os avisos de qualidade de código (CAxxxx) sejam tratados como erros em presença de `-warnaserror` , você poderá definir a `CodeAnalysisTreatWarningsAsErrors` Propriedade do MSBuild como `false` no arquivo do projeto.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

Você ainda verá quaisquer avisos de análise de código, mas eles não interromperão sua compilação.

### <a name="latest-updates"></a>Atualizações mais recentes

Por padrão, você obterá as regras de análise de código mais recentes e as severidades de regra padrão ao atualizar para versões mais recentes do SDK do .NET. Se você não quiser esse comportamento, por exemplo, se quiser garantir que nenhuma regra nova seja habilitada ou desabilitada, você poderá substituí-la de uma das seguintes maneiras:

- Defina a `AnalysisLevel` Propriedade MSBuild com um valor específico para bloquear os avisos para esse conjunto. Ao atualizar para um SDK mais recente, você ainda obterá correções de bug para esses avisos, mas nenhum aviso novo será habilitado e nenhum aviso existente será desabilitado. Por exemplo, para bloquear o conjunto de regras para as que acompanham a versão 5,0 do SDK do .NET, adicione a seguinte entrada ao arquivo de projeto.

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > O valor padrão da `AnalysisLevel` propriedade é `latest` , o que significa que você sempre Obtém as últimas regras de análise de código à medida que passa para versões mais recentes do SDK do .net.

  Para obter mais informações e ver uma lista de possíveis valores, consulte [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel).

- Instale o [pacote NuGet Microsoft. CodeAnalysis. Netanalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) para desassociar atualizações de regra das atualizações do SDK do .net. A instalação do pacote desativa os analisadores internos do SDK e gera um aviso de compilação se o SDK contiver uma versão de assembly do analisador mais recente do que a do pacote NuGet.

## <a name="code-style-analysis"></a>Análise de estilo de código

A [análise do estilo de código](/visualstudio/ide/editorconfig-code-style-settings-reference) (regras "IDExxxx") permite que você defina e mantenha o estilo de código consistente em sua codebase. A seguir estão as configurações padrão:

- Compilação de linha de comando: a análise de estilo de código está desabilitada, por padrão, para todos os projetos .NET em compilações de linha de comando.
- Visual Studio: a análise de estilo de código está habilitada, por padrão, para todos os projetos .NET dentro do Visual Studio como [ações rápidas de refatoração de código](/visualstudio/ide/code-generation-in-visual-studio).

Iniciando o .NET 5,0 RC2, você pode habilitar a análise de estilo de código no Build, tanto na linha de comando quanto dentro do Visual Studio. Violações de estilo de código aparecem como avisos ou erros com um prefixo "IDE". Isso permite que você imponha estilos de código consistentes no momento da compilação.

> [!NOTE]
> O recurso de análise de estilo de código é experimental e pode mudar entre as versões do .NET 5 e do .NET 6.

Etapas para habilitar a análise do estilo de código na compilação:

1. Defina a propriedade [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) do MSBuild como `true` .

1. Em um arquivo *. editorconfig* , [Configure](configuration-options.md) cada regra de estilo de código "IDE" que você deseja executar na compilação como um aviso ou um erro. Por exemplo:

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   Como alternativa, você pode configurar a categoria "estilo" inteira para ser um aviso ou erro, por padrão, e, em seguida, desativar seletivamente as regras que você não deseja executar na compilação. Por exemplo:

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

## <a name="suppress-a-warning"></a>Suprimir um aviso

Para suprimir uma violação de regra, defina a opção de severidade para essa ID de regra como `none` em um arquivo EditorConfig. Por exemplo:

```ini
dotnet_diagnostic.CA1822.severity = none
```

O Visual Studio fornece maneiras adicionais de suprimir avisos das regras de análise de código. Para obter mais informações, consulte [suprimir violações](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).

Para obter mais informações sobre severidades de regra, consulte [Configurar a severidade da regra](configuration-options.md#severity-level).

## <a name="see-also"></a>Confira também

- [Referência da regra de análise de qualidade de código](quality-rules/index.md)
- [Referência da regra de análise de estilo de código](style-rules/index.md)
- [Análise de código no Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview)
- [SDK da Plataforma do Compilador .NET](../../csharp/roslyn-sdk/index.md)
- [Tutorial: escrever seu primeiro analisador e correção de código](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
