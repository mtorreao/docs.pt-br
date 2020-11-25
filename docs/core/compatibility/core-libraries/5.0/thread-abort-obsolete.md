---
title: 'Alteração significativa: thread. Abort está obsoleto'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que as APIs thread. Abort estão obsoletas.
ms.date: 11/01/2020
ms.openlocfilehash: 6d7dfce8fda393bfd88c9b4cf0c59d53942cee25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760330"
---
# <a name="threadabort-is-obsolete"></a><span data-ttu-id="3186a-103">Thread. Abort é obsoleto</span><span class="sxs-lookup"><span data-stu-id="3186a-103">Thread.Abort is obsolete</span></span>

<span data-ttu-id="3186a-104">As <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs estão obsoletas.</span><span class="sxs-lookup"><span data-stu-id="3186a-104">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="3186a-105">Os projetos que se destinam ao .NET 5,0 ou uma versão posterior encontrarão um aviso de tempo de compilação `SYSLIB0006` se esses métodos forem chamados.</span><span class="sxs-lookup"><span data-stu-id="3186a-105">Projects that target .NET 5.0 or a later version will encounter compile-time warning `SYSLIB0006` if these methods are called.</span></span>

## <a name="change-description"></a><span data-ttu-id="3186a-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="3186a-106">Change description</span></span>

<span data-ttu-id="3186a-107">Anteriormente, as chamadas para <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> não produziram avisos de tempo de compilação, no entanto, o método lançou um <xref:System.PlatformNotSupportedException> em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="3186a-107">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="3186a-108">A partir do .NET 5,0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> é marcado como obsoleto como aviso.</span><span class="sxs-lookup"><span data-stu-id="3186a-108">Starting in .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="3186a-109">Chamar esse método produz o aviso do compilador `SYSLIB0006` .</span><span class="sxs-lookup"><span data-stu-id="3186a-109">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="3186a-110">A implementação do método permanece inalterada e continua lançando um <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="3186a-110">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="3186a-111">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="3186a-111">Reason for change</span></span>

<span data-ttu-id="3186a-112">Considerando que <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> o sempre lança um <xref:System.PlatformNotSupportedException> em todas as implementações do .net, exceto .NET Framework, <xref:System.ObsoleteAttribute> foi adicionado ao método para chamar a atenção para locais onde ele é chamado.</span><span class="sxs-lookup"><span data-stu-id="3186a-112">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="3186a-113">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="3186a-113">Version introduced</span></span>

<span data-ttu-id="3186a-114">5.0</span><span class="sxs-lookup"><span data-stu-id="3186a-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="3186a-115">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="3186a-115">Recommended action</span></span>

- <span data-ttu-id="3186a-116">Use um <xref:System.Threading.CancellationToken> para anular o processamento de uma unidade de trabalho em vez de chamar <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3186a-116">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3186a-117">O exemplo a seguir ilustra o uso de <xref:System.Threading.CancellationToken> .</span><span class="sxs-lookup"><span data-stu-id="3186a-117">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

  ```csharp
  void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
  {
      if (QueryIsMoreWorkPending())
      {
          // If the CancellationToken is marked as "needs to cancel",
          // this will throw the appropriate exception.
          cancellationToken.ThrowIfCancellationRequested();

          WorkItem work = DequeueWorkItem();
          ProcessWorkItem(work);
      }
  }
  ```

  <span data-ttu-id="3186a-118">Para saber mais, confira [Cancelamento em threads gerenciados](../../../../standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="3186a-118">For more information, see [Cancellation in managed threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="3186a-119">Para suprimir o aviso de tempo de compilação, suprime o código de aviso `SYSLIB0006` .</span><span class="sxs-lookup"><span data-stu-id="3186a-119">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="3186a-120">O código de aviso é específico para <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> e a supressão dele não elimina outros avisos de obsoletion em seu código.</span><span class="sxs-lookup"><span data-stu-id="3186a-120">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="3186a-121">No entanto, recomendamos que você remova <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> as chamadas para, em vez de suprimir o aviso.</span><span class="sxs-lookup"><span data-stu-id="3186a-121">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="3186a-122">Você também pode suprimir o aviso no arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="3186a-122">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

## <a name="affected-apis"></a><span data-ttu-id="3186a-123">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="3186a-123">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
