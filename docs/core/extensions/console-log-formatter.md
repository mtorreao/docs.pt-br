---
title: Formatação de log de console
description: Saiba como usar a formatação de log de console disponível ou implementar a formatação de log personalizada para seus aplicativos .NET.
author: IEvangelist
ms.author: dapine
ms.date: 12/17/2020
ms.openlocfilehash: 0ec8fc2018febe4273aa646d1682be197933f925
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700815"
---
# <a name="console-log-formatting"></a><span data-ttu-id="aafbb-103">Formatação de log de console</span><span class="sxs-lookup"><span data-stu-id="aafbb-103">Console log formatting</span></span>

<span data-ttu-id="aafbb-104">No .NET 5, o suporte à formatação personalizada foi adicionado aos logs do console no `Microsoft.Extensions.Logging.Console` namespace.</span><span class="sxs-lookup"><span data-stu-id="aafbb-104">In .NET 5, support for custom formatting was added to console logs in the `Microsoft.Extensions.Logging.Console` namespace.</span></span> <span data-ttu-id="aafbb-105">Há três opções de formatação predefinidas disponíveis: [`Simple`](#simple) , [`Systemd`](#systemd) e [`Json`](#json) .</span><span class="sxs-lookup"><span data-stu-id="aafbb-105">There are three predefined formatting options available: [`Simple`](#simple), [`Systemd`](#systemd), and [`Json`](#json).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aafbb-106">Anteriormente, a <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> Enumeração permitia selecionar o formato de log desejado, legível por humanos, que era o `Default` , ou linha única, também conhecido como `Systemd` .</span><span class="sxs-lookup"><span data-stu-id="aafbb-106">Previously, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> enum allowed for selecting the desired log format, either human readable which was the `Default`, or single line which is also known as `Systemd`.</span></span> <span data-ttu-id="aafbb-107">No entanto, elas **não** eram personalizáveis e agora estão preteridas.</span><span class="sxs-lookup"><span data-stu-id="aafbb-107">However, these were **not** customizable, and are now deprecated.</span></span>

<span data-ttu-id="aafbb-108">Neste artigo, você aprenderá sobre os formatadores de log do console.</span><span class="sxs-lookup"><span data-stu-id="aafbb-108">In this article, you will learn about console log formatters.</span></span> <span data-ttu-id="aafbb-109">O código-fonte de exemplo demonstra como:</span><span class="sxs-lookup"><span data-stu-id="aafbb-109">The sample source code demonstrates how to:</span></span>

- <span data-ttu-id="aafbb-110">Registrar um novo formatador</span><span class="sxs-lookup"><span data-stu-id="aafbb-110">Register a new formatter</span></span>
- <span data-ttu-id="aafbb-111">Selecione um formatador registrado para usar</span><span class="sxs-lookup"><span data-stu-id="aafbb-111">Select a registered formatter to use</span></span>
  - <span data-ttu-id="aafbb-112">Por meio de código ou [configuração](configuration.md)</span><span class="sxs-lookup"><span data-stu-id="aafbb-112">Either through code, or [configuration](configuration.md)</span></span>
- <span data-ttu-id="aafbb-113">Implementar um formatador personalizado</span><span class="sxs-lookup"><span data-stu-id="aafbb-113">Implement a custom formatter</span></span>
  - <span data-ttu-id="aafbb-114">Atualizar configuração via <xref:Microsoft.Extensions.Options.IOptionsMonitor%601></span><span class="sxs-lookup"><span data-stu-id="aafbb-114">Update configuration via <xref:Microsoft.Extensions.Options.IOptionsMonitor%601></span></span>
  - <span data-ttu-id="aafbb-115">Habilitar formatação de cor personalizada</span><span class="sxs-lookup"><span data-stu-id="aafbb-115">Enable custom color formatting</span></span>

## <a name="register-formatter"></a><span data-ttu-id="aafbb-116">Registrar formatador</span><span class="sxs-lookup"><span data-stu-id="aafbb-116">Register formatter</span></span>

<span data-ttu-id="aafbb-117">O [ `Console` provedor de log](logging-providers.md#console) tem vários formatadores predefinidos e expõe a capacidade de criar seu próprio formatador personalizado.</span><span class="sxs-lookup"><span data-stu-id="aafbb-117">The [`Console` logging provider](logging-providers.md#console) has several predefined formatters, and exposes the ability to author your own custom formatter.</span></span> <span data-ttu-id="aafbb-118">Para registrar qualquer um dos formatadores disponíveis, use o `Add{Type}Console` método de extensão correspondente:</span><span class="sxs-lookup"><span data-stu-id="aafbb-118">To register any of the available formatters, use the corresponding `Add{Type}Console` extension method:</span></span>

| <span data-ttu-id="aafbb-119">Tipos disponíveis</span><span class="sxs-lookup"><span data-stu-id="aafbb-119">Available types</span></span> | <span data-ttu-id="aafbb-120">Método para registrar tipo</span><span class="sxs-lookup"><span data-stu-id="aafbb-120">Method to register type</span></span> |
|--|--|
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddJsonConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSimpleConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSystemdConsole%2A?displayProperty=nameWithType> |

### <a name="simple"></a><span data-ttu-id="aafbb-121">Simples</span><span class="sxs-lookup"><span data-stu-id="aafbb-121">Simple</span></span>

<span data-ttu-id="aafbb-122">Para usar o `Simple` formatador do console, registre-o com `AddSimpleConsole` :</span><span class="sxs-lookup"><span data-stu-id="aafbb-122">To use the `Simple` console formatter, register it with `AddSimpleConsole`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-simple/Program.cs" highlight="11-16":::

<span data-ttu-id="aafbb-123">No código-fonte de exemplo anterior, o <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> formatador foi registrado.</span><span class="sxs-lookup"><span data-stu-id="aafbb-123">In the preceding sample source code, the <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> formatter was registered.</span></span> <span data-ttu-id="aafbb-124">Ele fornece aos logs a capacidade de não apenas encapsular informações como tempo e nível de log em cada mensagem de log, mas também permite a inserção de cor ANSI e o recuo de mensagens.</span><span class="sxs-lookup"><span data-stu-id="aafbb-124">It provides logs with the ability to not only wrap information such as time and log level in each log message, but also allows for ANSI color embedding and indentation of messages.</span></span>

### <a name="systemd"></a><span data-ttu-id="aafbb-125">Systemd</span><span class="sxs-lookup"><span data-stu-id="aafbb-125">Systemd</span></span>

<span data-ttu-id="aafbb-126">O <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> agente do console do:</span><span class="sxs-lookup"><span data-stu-id="aafbb-126">The <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> console logger:</span></span>

- <span data-ttu-id="aafbb-127">Usa o formato e as severidades do nível de log "syslog"</span><span class="sxs-lookup"><span data-stu-id="aafbb-127">Uses the "Syslog" log level format and severities</span></span>
- <span data-ttu-id="aafbb-128">Não **formata mensagens** com cores</span><span class="sxs-lookup"><span data-stu-id="aafbb-128">Does **not** format messages with colors</span></span>
- <span data-ttu-id="aafbb-129">Sempre registra mensagens em uma única linha</span><span class="sxs-lookup"><span data-stu-id="aafbb-129">Always logs messages in a single line</span></span>

<span data-ttu-id="aafbb-130">Isso é normalmente útil para contêineres, que geralmente fazem uso de `Systemd` log de console.</span><span class="sxs-lookup"><span data-stu-id="aafbb-130">This is commonly useful for containers, which often make use of `Systemd` console logging.</span></span> <span data-ttu-id="aafbb-131">Com o .NET 5, o `Simple` agente de log do console também permite uma versão compactada que registra em uma única linha, além de permitir a desabilitação de cores, conforme mostrado em um exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="aafbb-131">With .NET 5, the `Simple` console logger also enables a compact version that logs in a single line, and also allows for disabling colors as shown in an earlier sample.</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-systemd/Program.cs" highlight="11-15":::

### <a name="json"></a><span data-ttu-id="aafbb-132">Json</span><span class="sxs-lookup"><span data-stu-id="aafbb-132">Json</span></span>

<span data-ttu-id="aafbb-133">Para gravar logs em um formato JSON, o `Json` formatador do console é usado.</span><span class="sxs-lookup"><span data-stu-id="aafbb-133">To write logs in a JSON format, the `Json` console formatter is used.</span></span> <span data-ttu-id="aafbb-134">O código-fonte de exemplo mostra como um aplicativo ASP.NET Core pode registrá-lo.</span><span class="sxs-lookup"><span data-stu-id="aafbb-134">The sample source code shows how an ASP.NET Core app might register it.</span></span> <span data-ttu-id="aafbb-135">Usando o `webapp` modelo, crie um novo aplicativo ASP.NET Core com o [novo comando dotnet](../tools/dotnet-new.md) :</span><span class="sxs-lookup"><span data-stu-id="aafbb-135">Using the `webapp` template, create a new ASP.NET Core app with the [dotnet new](../tools/dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new webapp -o Console.ExampleFormatters.Json
```

<span data-ttu-id="aafbb-136">Ao executar o aplicativo, usando o código de modelo, você obtém o formato de log padrão abaixo:</span><span class="sxs-lookup"><span data-stu-id="aafbb-136">When running the app, using the template code, you get the default log format below:</span></span>

```
info: Microsoft.Hosting.Lifetime[0]
      Now listening on: https://localhost:5001
```

<span data-ttu-id="aafbb-137">Por padrão, o `Simple` formatador de log do console é selecionado com a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="aafbb-137">By default, the `Simple` console log formatter is selected with default configuration.</span></span> <span data-ttu-id="aafbb-138">Você altera isso chamando `AddJsonConsole` no *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="aafbb-138">You change this by calling `AddJsonConsole` in the *Program.cs*:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-json/Program.cs" highlight="17-26":::

<span data-ttu-id="aafbb-139">Execute o aplicativo novamente, com a alteração acima, a mensagem de log agora está formatada como JSON:</span><span class="sxs-lookup"><span data-stu-id="aafbb-139">Run the app again, with the above change, the log message is now formatted as JSON:</span></span>

:::code language="json" source="snippets/logging/console-formatter-json/example-output.json":::

> [!TIP]
> <span data-ttu-id="aafbb-140">O `Json` formatador do console, por padrão, registra cada mensagem em uma única linha.</span><span class="sxs-lookup"><span data-stu-id="aafbb-140">The `Json` console formatter, by default, logs each message in a single line.</span></span> <span data-ttu-id="aafbb-141">Para torná-lo mais legível ao configurar o formatador, defina <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType> como `true` .</span><span class="sxs-lookup"><span data-stu-id="aafbb-141">In order to make it more readable while configuring the formatter, set <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType> to `true`.</span></span>

## <a name="set-formatter-with-configuration"></a><span data-ttu-id="aafbb-142">Definir formatador com configuração</span><span class="sxs-lookup"><span data-stu-id="aafbb-142">Set formatter with configuration</span></span>

<span data-ttu-id="aafbb-143">Os exemplos anteriores mostraram como registrar um formatador programaticamente.</span><span class="sxs-lookup"><span data-stu-id="aafbb-143">The previous samples have shown how to register a formatter programmatically.</span></span> <span data-ttu-id="aafbb-144">Como alternativa, isso pode ser feito com a [configuração](configuration.md).</span><span class="sxs-lookup"><span data-stu-id="aafbb-144">Alternatively, this can be done with [configuration](configuration.md).</span></span> <span data-ttu-id="aafbb-145">Considere o código-fonte do aplicativo Web anterior, se você atualizar o *appsettings.jsno* arquivo em vez de chamar `ConfigureLogging` no arquivo *Program.cs* , poderá obter o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="aafbb-145">Consider the previous web application sample source code, if you update the *appsettings.json* file rather than calling `ConfigureLogging` in the *Program.cs* file, you could get the same outcome.</span></span> <span data-ttu-id="aafbb-146">O `appsettings.json` arquivo atualizado configuraria o formatador da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="aafbb-146">The updated `appsettings.json` file would configure the formatter as follows:</span></span>

:::code language="json" source="snippets/logging/console-formatter-json/appsettings.json" highlight="14-23":::

<span data-ttu-id="aafbb-147">Os dois valores de chave que precisam ser definidos são `"FormatterName"` e `"FormatterOptions"` .</span><span class="sxs-lookup"><span data-stu-id="aafbb-147">The two key values that need to be set are `"FormatterName"` and `"FormatterOptions"`.</span></span> <span data-ttu-id="aafbb-148">Se um formatador com o valor definido para `"FormatterName"` já estiver registrado, esse formatador será selecionado e suas propriedades poderão ser configuradas desde que sejam fornecidas como uma chave dentro do `"FormatterOptions"` nó.</span><span class="sxs-lookup"><span data-stu-id="aafbb-148">If a formatter with the value set for `"FormatterName"` is already registered, that formatter is selected, and its properties can be configured as long as they are provided as a key inside the `"FormatterOptions"` node.</span></span> <span data-ttu-id="aafbb-149">Os nomes de formatadores predefinidos são reservados em <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames> :</span><span class="sxs-lookup"><span data-stu-id="aafbb-149">The predefined formatter names are reserved under <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames>:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>

## <a name="implement-a-custom-formatter"></a><span data-ttu-id="aafbb-150">Implementar um formatador personalizado</span><span class="sxs-lookup"><span data-stu-id="aafbb-150">Implement a custom formatter</span></span>

<span data-ttu-id="aafbb-151">Para implementar um formatador personalizado, você precisa:</span><span class="sxs-lookup"><span data-stu-id="aafbb-151">To implement a custom formatter, you need to:</span></span>

- <span data-ttu-id="aafbb-152">Criar uma subclasse de <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter> , representa seu formatador personalizado</span><span class="sxs-lookup"><span data-stu-id="aafbb-152">Create a subclass of <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter>, this represents your custom formatter</span></span>
- <span data-ttu-id="aafbb-153">Registrar seu formatador personalizado com</span><span class="sxs-lookup"><span data-stu-id="aafbb-153">Register your custom formatter with</span></span>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsole%2A?displayProperty=nameWithType>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsoleFormatter%60%602(Microsoft.Extensions.Logging.ILoggingBuilder,System.Action{%60%601})?displayProperty=nameWithType>

<span data-ttu-id="aafbb-154">Crie um método de extensão para lidar com isso para você:</span><span class="sxs-lookup"><span data-stu-id="aafbb-154">Create an extension method to handle this for you:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/ConsoleLoggerExtensions.cs" highlight="11-12":::

<span data-ttu-id="aafbb-155">Os `CustomOptions` são definidos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="aafbb-155">The `CustomOptions` are defined as follows:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomOptions.cs":::

<span data-ttu-id="aafbb-156">No código anterior, as opções são uma subclasse de <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions> .</span><span class="sxs-lookup"><span data-stu-id="aafbb-156">In the preceding code, the options are a subclass of <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>.</span></span>

<span data-ttu-id="aafbb-157">A `AddConsoleFormatter` API:</span><span class="sxs-lookup"><span data-stu-id="aafbb-157">The `AddConsoleFormatter` API:</span></span>

- <span data-ttu-id="aafbb-158">Registra uma subclasse de `ConsoleFormatter`</span><span class="sxs-lookup"><span data-stu-id="aafbb-158">Registers a subclass of `ConsoleFormatter`</span></span>
- <span data-ttu-id="aafbb-159">Configuração de identificadores:</span><span class="sxs-lookup"><span data-stu-id="aafbb-159">Handles configuration:</span></span>
  - <span data-ttu-id="aafbb-160">Usa um token de alteração para sincronizar atualizações, com base no [padrão de opções](options.md)e na interface [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601)</span><span class="sxs-lookup"><span data-stu-id="aafbb-160">Uses a change token to synchronize updates, based on the [options pattern](options.md), and the [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601) interface</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/Program.cs" highlight="11-12":::

<span data-ttu-id="aafbb-161">Defina uma `CustomerFormatter` subclasse de `ConsoleFormatter` :</span><span class="sxs-lookup"><span data-stu-id="aafbb-161">Define a `CustomerFormatter` subclass of `ConsoleFormatter`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomFormatter.cs" highlight="24-45":::

<span data-ttu-id="aafbb-162">A `CustomFormatter.Write<TState>` API anterior determina qual texto é encapsulado em torno de cada mensagem de log.</span><span class="sxs-lookup"><span data-stu-id="aafbb-162">The preceding `CustomFormatter.Write<TState>` API dictates what text gets wrapped around each log message.</span></span> <span data-ttu-id="aafbb-163">Um padrão `ConsoleFormatter` deve ser capaz de encapsular escopos, carimbos de data/hora e nível de severidade de logs no mínimo.</span><span class="sxs-lookup"><span data-stu-id="aafbb-163">A standard `ConsoleFormatter` should be able to wrap around scopes, time stamps, and severity level of logs at a minimum.</span></span> <span data-ttu-id="aafbb-164">Além disso, você pode codificar as cores ANSI nas mensagens de log e também fornecer recuos desejados.</span><span class="sxs-lookup"><span data-stu-id="aafbb-164">Additionally, you can encode ANSI colors in the log messages, and provide desired indentations as well.</span></span> <span data-ttu-id="aafbb-165">A implementação do não `CustomFormatter.Write<TState>` tem esses recursos.</span><span class="sxs-lookup"><span data-stu-id="aafbb-165">The implementation of the `CustomFormatter.Write<TState>` lacks these capabilities.</span></span>

<span data-ttu-id="aafbb-166">Para inspiração ao personalizar ainda mais a formatação, consulte as implementações existentes no `Microsoft.Extensions.Logging.Console` namespace:</span><span class="sxs-lookup"><span data-stu-id="aafbb-166">For inspiration on further customizing formatting, see the existing implementations in the `Microsoft.Extensions.Logging.Console` namespace:</span></span>

- <span data-ttu-id="aafbb-167">[SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs).</span><span class="sxs-lookup"><span data-stu-id="aafbb-167">[SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs).</span></span>
- [<span data-ttu-id="aafbb-168">SystemdConsoleFormatter</span><span class="sxs-lookup"><span data-stu-id="aafbb-168">SystemdConsoleFormatter</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SystemdConsoleFormatter.cs)
- [<span data-ttu-id="aafbb-169">JsonConsoleFormatter</span><span class="sxs-lookup"><span data-stu-id="aafbb-169">JsonConsoleFormatter</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/JsonConsoleFormatter.cs)

## <a name="implement-custom-color-formatting"></a><span data-ttu-id="aafbb-170">Implementar a formatação de cor personalizada</span><span class="sxs-lookup"><span data-stu-id="aafbb-170">Implement custom color formatting</span></span>

<span data-ttu-id="aafbb-171">Para habilitar corretamente os recursos de cores em seu formatador de log personalizado, você pode estender o, <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> pois ele tem uma <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> propriedade que pode ser útil para habilitar cores em logs.</span><span class="sxs-lookup"><span data-stu-id="aafbb-171">In order to properly enable color capabilities in your custom logging formatter, you can extend the <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> as it has a <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> property that can be useful for enabling colors in logs.</span></span>

<span data-ttu-id="aafbb-172">Crie um `CustomColorOptions` que derive de `SimpleConsoleFormatterOptions` :</span><span class="sxs-lookup"><span data-stu-id="aafbb-172">Create a `CustomColorOptions` that derives from `SimpleConsoleFormatterOptions`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorOptions.cs" highlight="5":::

<span data-ttu-id="aafbb-173">Em seguida, escreva alguns métodos de extensão em uma `TextWriterExtensions` classe que permitem incorporar convenientemente as cores codificadas ANSI em mensagens de log formatadas:</span><span class="sxs-lookup"><span data-stu-id="aafbb-173">Next, write some extension methods in a `TextWriterExtensions` class that allow for conveniently embedding ANSI coded colors within formatted log messages:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/TextWriterExtensions.cs":::

<span data-ttu-id="aafbb-174">Um formatador de cor personalizado que manipula a aplicação de cores personalizadas pode ser definido da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="aafbb-174">A custom color formatter that handles applying custom colors could be defined as follows:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorFormatter.cs" highlight="15-18,52-65":::

<span data-ttu-id="aafbb-175">Quando você executar o aplicativo, os logs mostrarão a `CustomPrefix` mensagem na cor verde quando `FormatterOptions.ColorBehavior` for `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="aafbb-175">When you run the application, the logs will show the `CustomPrefix` message in the color green when `FormatterOptions.ColorBehavior` is `Enabled`.</span></span>

> [!NOTE]
> <span data-ttu-id="aafbb-176">Quando <xref:Microsoft.Extensions.Logging.Console.LoggerColorBehavior> é `Disabled` , as mensagens de log _não_ interpretam códigos de cores ANSI inseridos nas mensagens de log.</span><span class="sxs-lookup"><span data-stu-id="aafbb-176">When <xref:Microsoft.Extensions.Logging.Console.LoggerColorBehavior> is `Disabled`, log messages do _not_ interpret embedded ANSI color codes within log messages.</span></span> <span data-ttu-id="aafbb-177">Em vez disso, eles geram a mensagem bruta.</span><span class="sxs-lookup"><span data-stu-id="aafbb-177">Instead, they output the raw message.</span></span> <span data-ttu-id="aafbb-178">Considere o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="aafbb-178">For example, consider the following:</span></span>
>
> ```csharp
> logger.LogInformation("Random log \x1B[42mwith green background\x1B[49m message");
> ```
>
> <span data-ttu-id="aafbb-179">Isso produziria a cadeia de caracteres textual e _não_ é colorido.</span><span class="sxs-lookup"><span data-stu-id="aafbb-179">This would output the verbatim string, and it is _not_ colorized.</span></span>
>
> ```output
> Random log \x1B[42mwith green background\x1B[49m message
> ```

## <a name="see-also"></a><span data-ttu-id="aafbb-180">Veja também</span><span class="sxs-lookup"><span data-stu-id="aafbb-180">See also</span></span>

- [<span data-ttu-id="aafbb-181">Registro em log no .NET</span><span class="sxs-lookup"><span data-stu-id="aafbb-181">Logging in .NET</span></span>](logging.md)
- [<span data-ttu-id="aafbb-182">Implementar um provedor de log personalizado no .NET</span><span class="sxs-lookup"><span data-stu-id="aafbb-182">Implement a custom logging provider in .NET</span></span>](custom-logging-provider.md)
- [<span data-ttu-id="aafbb-183">Registro em log de alto desempenho no .NET</span><span class="sxs-lookup"><span data-stu-id="aafbb-183">High-performance logging in .NET</span></span>](high-performance-logging.md)
