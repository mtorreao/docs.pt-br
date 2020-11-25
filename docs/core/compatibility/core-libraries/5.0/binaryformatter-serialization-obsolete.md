---
title: 'Alteração significativa: os métodos de serialização BinaryFormatter são obsoletos e proibidos em aplicativos ASP.NET'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que os métodos serializar e desserializar em BinaryFormatter, Formatter e IFormatter são obsoletos.
ms.date: 11/01/2020
ms.openlocfilehash: 5807a7d4e6beab26b9848b803922396dd893075b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760401"
---
# <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a><span data-ttu-id="b10c1-103">Os métodos de serialização BinaryFormatter são obsoletos e proibidos em aplicativos ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b10c1-103">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>

<span data-ttu-id="b10c1-104">`Serialize` e `Deserialize` os métodos em <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> , <xref:System.Runtime.Serialization.Formatter> e <xref:System.Runtime.Serialization.IFormatter> agora são obsoletos como aviso.</span><span class="sxs-lookup"><span data-stu-id="b10c1-104">`Serialize` and `Deserialize` methods on <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter>, and <xref:System.Runtime.Serialization.IFormatter> are now obsolete as warning.</span></span> <span data-ttu-id="b10c1-105">Além disso, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> a serialização é proibida por padrão para aplicativos ASP.net.</span><span class="sxs-lookup"><span data-stu-id="b10c1-105">Additionally, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is prohibited by default for ASP.NET apps.</span></span>

## <a name="change-description"></a><span data-ttu-id="b10c1-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="b10c1-106">Change description</span></span>

<span data-ttu-id="b10c1-107">Devido a [vulnerabilidades de segurança](../../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) no <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> , os métodos a seguir agora são obsoletos e produzem um aviso de tempo de compilação com a ID `SYSLIB0011` .</span><span class="sxs-lookup"><span data-stu-id="b10c1-107">Due to [security vulnerabilities](../../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following methods are now obsolete and produce a compile-time warning with ID `SYSLIB0011`.</span></span> <span data-ttu-id="b10c1-108">Além disso, no ASP.NET Core 5,0 e em aplicativos posteriores, eles lançarão um <xref:System.NotSupportedException> , a menos que o aplicativo Web tenha reativado a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="b10c1-108">Additionally, in ASP.NET Core 5.0 and later apps, they will throw a <xref:System.NotSupportedException>, unless the web app has re-enabled <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> functionality.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

<span data-ttu-id="b10c1-109">Os seguintes métodos de serialização também são obsoletos e produzem aviso `SYSLIB0011` , mas não têm nenhuma alteração comportamental:</span><span class="sxs-lookup"><span data-stu-id="b10c1-109">The following serialization methods are also obsolete and produce warning `SYSLIB0011`, but have no behavioral changes:</span></span>

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="version-introduced"></a><span data-ttu-id="b10c1-110">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="b10c1-110">Version introduced</span></span>

<span data-ttu-id="b10c1-111">5.0</span><span class="sxs-lookup"><span data-stu-id="b10c1-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b10c1-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="b10c1-112">Reason for change</span></span>

<span data-ttu-id="b10c1-113">Esses métodos são marcados como obsoletos como parte de um esforço para o uso do vento <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> no ecossistema do .net.</span><span class="sxs-lookup"><span data-stu-id="b10c1-113">These methods are marked obsolete as part of an effort to wind down usage of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> within the .NET ecosystem.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b10c1-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="b10c1-114">Recommended action</span></span>

- <span data-ttu-id="b10c1-115">Pare <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> de usar no seu código.</span><span class="sxs-lookup"><span data-stu-id="b10c1-115">Stop using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in your code.</span></span> <span data-ttu-id="b10c1-116">Em vez disso, considere usar <xref:System.Text.Json.JsonSerializer> ou <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="b10c1-116">Instead, consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="b10c1-117">Para obter mais informações, consulte [Guia de segurança do BinaryFormatter](../../../../standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="b10c1-117">For more information, see [BinaryFormatter security guide](../../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

- <span data-ttu-id="b10c1-118">Você pode suprimir temporariamente o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> aviso de tempo de compilação, que é `SYSLIB0011` .</span><span class="sxs-lookup"><span data-stu-id="b10c1-118">You can temporarily suppress the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> compile-time warning, which is `SYSLIB0011`.</span></span> <span data-ttu-id="b10c1-119">Recomendamos que você avalie minuciosamente seu código em busca de riscos antes de escolher essa opção.</span><span class="sxs-lookup"><span data-stu-id="b10c1-119">We recommend that you thoroughly assess your code for risks before choosing this option.</span></span> <span data-ttu-id="b10c1-120">A maneira mais fácil de suprimir os avisos é envolver o site de chamada individual com `#pragma` diretivas.</span><span class="sxs-lookup"><span data-stu-id="b10c1-120">The easiest way to suppress the warnings is to surround the individual call site with `#pragma` directives.</span></span>

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  <span data-ttu-id="b10c1-121">Você também pode suprimir o aviso no arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="b10c1-121">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  <span data-ttu-id="b10c1-122">Se você suprimir o aviso no arquivo de projeto, o aviso será suprimido para todos os arquivos de código no projeto.</span><span class="sxs-lookup"><span data-stu-id="b10c1-122">If you suppress the warning in the project file, the warning is suppressed for all code files in the project.</span></span> <span data-ttu-id="b10c1-123">A supressão `SYSLIB0011` não elimina os avisos causados pelo uso de outras APIs obsoletas.</span><span class="sxs-lookup"><span data-stu-id="b10c1-123">Suppressing `SYSLIB0011` does not suppress warnings caused by using other obsolete APIs.</span></span>

- <span data-ttu-id="b10c1-124">Para continuar usando <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o em aplicativos ASP.net, você pode reabilitá-lo no arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="b10c1-124">To continue using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in ASP.NET apps, you can re-enable it in the project file.</span></span> <span data-ttu-id="b10c1-125">No entanto, é altamente recomendável não fazer isso.</span><span class="sxs-lookup"><span data-stu-id="b10c1-125">However, it's strongly recommended not to do this.</span></span> <span data-ttu-id="b10c1-126">Para obter mais informações, consulte [Guia de segurança do BinaryFormatter](../../../../standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="b10c1-126">For more information, see [BinaryFormatter security guide](../../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

<span data-ttu-id="b10c1-127">Para obter mais informações sobre as ações recomendadas, consulte [Resolvendo erros de BinaryFormatter obsoletion e de desativação](https://aka.ms/binaryformatter).</span><span class="sxs-lookup"><span data-stu-id="b10c1-127">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b10c1-128">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="b10c1-128">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET Core

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
