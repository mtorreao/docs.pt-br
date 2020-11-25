---
title: 'Alteração significativa: Propriedades obsoletas em ConsoleLoggerOptions'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que o tipo ConsoleLoggerFormat e algumas propriedades em ConsoleLoggerOptions agora são obsoletos.
ms.date: 11/01/2020
ms.openlocfilehash: e38ba3bda371c713a8b2cb4cda8b4c585dac29f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760496"
---
# <a name="obsolete-properties-on-consoleloggeroptions"></a><span data-ttu-id="87a5e-103">Propriedades obsoletas em ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="87a5e-103">Obsolete properties on ConsoleLoggerOptions</span></span>

<span data-ttu-id="87a5e-104">O <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> tipo e algumas propriedades em <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> agora estão obsoletos.</span><span class="sxs-lookup"><span data-stu-id="87a5e-104">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and some properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are now obsolete.</span></span>

## <a name="change-description"></a><span data-ttu-id="87a5e-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="87a5e-105">Change description</span></span>

<span data-ttu-id="87a5e-106">A partir do .NET 5,0, o <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> tipo e várias propriedades <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> são obsoletos.</span><span class="sxs-lookup"><span data-stu-id="87a5e-106">Starting in .NET 5.0, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and several properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are obsolete.</span></span> <span data-ttu-id="87a5e-107">As propriedades obsoletas são:</span><span class="sxs-lookup"><span data-stu-id="87a5e-107">The obsolete properties are:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

<span data-ttu-id="87a5e-108">Com a introdução de novos formatadores, essas propriedades agora estão disponíveis nos formatadores individuais.</span><span class="sxs-lookup"><span data-stu-id="87a5e-108">With the introduction of new formatters, these properties are now available on the individual formatters.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="87a5e-109">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="87a5e-109">Reason for change</span></span>

<span data-ttu-id="87a5e-110">A <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> propriedade é um tipo de enumeração, que não pode representar um formatador personalizado.</span><span class="sxs-lookup"><span data-stu-id="87a5e-110">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> property is an enumeration type, which cannot represent a custom formatter.</span></span>

<span data-ttu-id="87a5e-111">As propriedades restantes foram definidas <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> e aplicadas a ambos os formatos internos para logs do console.</span><span class="sxs-lookup"><span data-stu-id="87a5e-111">The remaining properties were set on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> and applied to both of the built-in formats for console logs.</span></span> <span data-ttu-id="87a5e-112">No entanto, com a introdução de uma nova API de formatador, faz mais sentido para que a formatação seja representada nas opções específicas do formatador.</span><span class="sxs-lookup"><span data-stu-id="87a5e-112">However, with the introduction of a new formatter API, it makes more sense for formatting to be represented on the formatter-specific options.</span></span> <span data-ttu-id="87a5e-113">Essa alteração fornece melhor separação entre os formatadores do agente e do agente de log.</span><span class="sxs-lookup"><span data-stu-id="87a5e-113">This change provides better separation between the logger and logger formatters.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="87a5e-114">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="87a5e-114">Version introduced</span></span>

<span data-ttu-id="87a5e-115">5.0</span><span class="sxs-lookup"><span data-stu-id="87a5e-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="87a5e-116">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="87a5e-116">Recommended action</span></span>

- <span data-ttu-id="87a5e-117">Use a nova <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> propriedade no lugar da <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> propriedade.</span><span class="sxs-lookup"><span data-stu-id="87a5e-117">Use the new <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> property in place of the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="87a5e-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="87a5e-118">For example:</span></span>

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  <span data-ttu-id="87a5e-119">Há várias diferenças entre <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> e <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> :</span><span class="sxs-lookup"><span data-stu-id="87a5e-119">There are several differences between <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span></span>

  - <span data-ttu-id="87a5e-120"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> tem apenas duas opções possíveis: `Default` e `Systemd` .</span><span class="sxs-lookup"><span data-stu-id="87a5e-120"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> has only two possible options: `Default` and `Systemd`.</span></span>
  - <span data-ttu-id="87a5e-121"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> não diferencia maiúsculas de minúsculas e pode ser qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="87a5e-121"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> is case insensitive and can be any string.</span></span> <span data-ttu-id="87a5e-122">Os nomes internos reservados são `Simple` , `Systemd` e `Json` (.NET 5,0 e posterior).</span><span class="sxs-lookup"><span data-stu-id="87a5e-122">The reserved, built-in names are `Simple`, `Systemd`, and `Json` (.NET 5.0 and later).</span></span>
  - <span data-ttu-id="87a5e-123">`"Format": "Systemd"` mapeia para `"FormatterName": "Systemd"` .</span><span class="sxs-lookup"><span data-stu-id="87a5e-123">`"Format": "Systemd"` maps to `"FormatterName": "Systemd"`.</span></span>
  - <span data-ttu-id="87a5e-124">`"Format": "Default"` mapeia para `"FormatterName": "Simple"` .</span><span class="sxs-lookup"><span data-stu-id="87a5e-124">`"Format": "Default"` maps to `"FormatterName": "Simple"`.</span></span>

- <span data-ttu-id="87a5e-125">Para as <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors> <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes> Propriedades,, e <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat> <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> , use a propriedade correspondente nos <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions> tipos novo, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions> ou <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> .</span><span class="sxs-lookup"><span data-stu-id="87a5e-125">For the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat>, and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> properties, use the corresponding property on the new <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions>, or <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> types instead.</span></span> <span data-ttu-id="87a5e-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="87a5e-126">For example:</span></span>

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

<span data-ttu-id="87a5e-127">Os dois trechos de código JSON a seguir mostram como o arquivo de configuração é alterado.</span><span class="sxs-lookup"><span data-stu-id="87a5e-127">The following two JSON snippets show how the configuration file changes.</span></span> <span data-ttu-id="87a5e-128">Arquivo de configuração antigo:</span><span class="sxs-lookup"><span data-stu-id="87a5e-128">Old configuration file:</span></span>

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "Format": "Systemd",
      "IncludeScopes": true,
      "TimestampFormat": "HH:mm:ss",
      "UseUtcTimestamp": true
    }
  },
  "AllowedHosts": "*"
}
```

<span data-ttu-id="87a5e-129">Novo arquivo de configuração:</span><span class="sxs-lookup"><span data-stu-id="87a5e-129">New configuration file:</span></span>

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "FormatterName": "Systemd",
      "FormatterOptions": {
        "IncludeScopes": true,
        "TimestampFormat": "HH:mm:ss",
        "UseUtcTimestamp": true
      }
    }
  },
  "AllowedHosts": "*"
}
```

## <a name="affected-apis"></a><span data-ttu-id="87a5e-130">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="87a5e-130">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET

### Affected APIs

- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format`

-->
