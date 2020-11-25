---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032290"
---
### <a name="logging-debuglogger-class-made-internal"></a><span data-ttu-id="ac81a-101">Log: classe DebugLogger criada internamente</span><span class="sxs-lookup"><span data-stu-id="ac81a-101">Logging: DebugLogger class made internal</span></span>

<span data-ttu-id="ac81a-102">Antes do ASP.NET Core 3,0, o `DebugLogger` modificador de acesso foi `public` .</span><span class="sxs-lookup"><span data-stu-id="ac81a-102">Prior to ASP.NET Core 3.0, `DebugLogger`'s access modifier was `public`.</span></span> <span data-ttu-id="ac81a-103">No ASP.NET Core 3,0, o modificador de acesso foi alterado para `internal` .</span><span class="sxs-lookup"><span data-stu-id="ac81a-103">In ASP.NET Core 3.0, the access modifier changed to `internal`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ac81a-104">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="ac81a-104">Version introduced</span></span>

<span data-ttu-id="ac81a-105">3.0</span><span class="sxs-lookup"><span data-stu-id="ac81a-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ac81a-106">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="ac81a-106">Reason for change</span></span>

<span data-ttu-id="ac81a-107">A alteração está sendo feita para:</span><span class="sxs-lookup"><span data-stu-id="ac81a-107">The change is being made to:</span></span>

* <span data-ttu-id="ac81a-108">Impor consistência com outras implementações de agente, como `ConsoleLogger` .</span><span class="sxs-lookup"><span data-stu-id="ac81a-108">Enforce consistency with other logger implementations such as `ConsoleLogger`.</span></span>
* <span data-ttu-id="ac81a-109">Reduza a superfície da API.</span><span class="sxs-lookup"><span data-stu-id="ac81a-109">Reduce the API surface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ac81a-110">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="ac81a-110">Recommended action</span></span>

<span data-ttu-id="ac81a-111">Use o <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` método de extensão para habilitar o log de depuração.</span><span class="sxs-lookup"><span data-stu-id="ac81a-111">Use the <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` extension method to enable debug logging.</span></span> <span data-ttu-id="ac81a-112"><xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> também é ainda `public` no caso de o serviço precisar ser registrado manualmente.</span><span class="sxs-lookup"><span data-stu-id="ac81a-112"><xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> is also still `public` in the event the service needs to be registered manually.</span></span>

#### <a name="category"></a><span data-ttu-id="ac81a-113">Categoria</span><span class="sxs-lookup"><span data-stu-id="ac81a-113">Category</span></span>

<span data-ttu-id="ac81a-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ac81a-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ac81a-115">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="ac81a-115">Affected APIs</span></span>

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
