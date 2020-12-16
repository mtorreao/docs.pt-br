---
title: Aviso de SYSLIB0004
description: Saiba mais sobre o obsoletions que gera SYSLIB0004 de aviso de tempo de compilação.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 03be8bb54f71f74ed94ee2c3f8489397ae1e99b5
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596430"
---
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a><span data-ttu-id="6f77b-103">SYSLIB0004: não há suporte para o recurso CER (região de execução restrita)</span><span class="sxs-lookup"><span data-stu-id="6f77b-103">SYSLIB0004: The constrained execution region (CER) feature is not supported</span></span>

<span data-ttu-id="6f77b-104">Há suporte para o recurso [cer (regiões de execução restrita)](../../../framework/performance/constrained-execution-regions.md) somente no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f77b-104">The [Constrained execution regions (CER)](../../../framework/performance/constrained-execution-regions.md) feature is supported only in .NET Framework.</span></span> <span data-ttu-id="6f77b-105">Assim, várias APIs relacionadas à CER são marcadas como obsoletas, começando no .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="6f77b-105">As such, various CER-related APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="6f77b-106">O uso dessas APIs gera aviso `SYSLIB0004` no momento da compilação.</span><span class="sxs-lookup"><span data-stu-id="6f77b-106">Using these APIs generates warning `SYSLIB0004` at compile time.</span></span>

<span data-ttu-id="6f77b-107">As seguintes APIs relacionadas a CER são obsoletas:</span><span class="sxs-lookup"><span data-stu-id="6f77b-107">The following CER-related APIs are obsolete:</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="6f77b-108">Soluções Alternativas</span><span class="sxs-lookup"><span data-stu-id="6f77b-108">Workarounds</span></span>

- <span data-ttu-id="6f77b-109">Se você aplicou um atributo CER a um método, remova o atributo.</span><span class="sxs-lookup"><span data-stu-id="6f77b-109">If you have applied a CER attribute to a method, remove the attribute.</span></span> <span data-ttu-id="6f77b-110">Esses atributos não têm nenhum efeito no .NET 5,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="6f77b-110">These attributes have no effect in .NET 5.0 and later versions.</span></span>

  ```csharp
  // REMOVE the attribute below.
  [ReliabilityContract(Consistency.WillNotCorruptState, Cer.Success)]
  public void DoSomething()
  {
  }

  // REMOVE the attribute below.
  [PrePrepareMethod]
  public void DoSomething()
  {
  }
  ```

- <span data-ttu-id="6f77b-111">Se você estiver chamando `RuntimeHelpers.ProbeForSufficientStack` ou `RuntimeHelpers.PrepareContractedDelegate` , remova a chamada.</span><span class="sxs-lookup"><span data-stu-id="6f77b-111">If you are calling `RuntimeHelpers.ProbeForSufficientStack` or `RuntimeHelpers.PrepareContractedDelegate`, remove the call.</span></span> <span data-ttu-id="6f77b-112">Essas chamadas não têm nenhum efeito no .NET 5,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="6f77b-112">These calls have no effect in .NET 5.0 and later versions.</span></span>

  ```csharp
  public void DoSomething()
  {
      // REMOVE the call below.
      RuntimeHelpers.ProbeForSufficientStack();

      // (Remainder of your method logic here.)
  }
  ```

- <span data-ttu-id="6f77b-113">Se você estiver chamando `RuntimeHelpers.PrepareConstrainedRegions` , remova a chamada.</span><span class="sxs-lookup"><span data-stu-id="6f77b-113">If you are calling `RuntimeHelpers.PrepareConstrainedRegions`, remove the call.</span></span> <span data-ttu-id="6f77b-114">Essa chamada não tem nenhum efeito no .NET 5,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="6f77b-114">This call has no effect in .NET 5.0 and later versions.</span></span>

  ```csharp
  public void DoSomething_Old()
  {
      // REMOVE the call below.
      RuntimeHelpers.PrepareConstrainedRegions();
      try
      {
          // try code
      }
      finally
      {
          // cleanup code
      }
  }

  public void DoSomething_Corrected()
  {
      // There is no call to PrepareConstrainedRegions. It's a normal try / finally block.

      try
      {
          // try code
      }
      finally
      {
          // cleanup code
      }
  }
  ```

- <span data-ttu-id="6f77b-115">Se você estiver chamando `RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup` , substitua a chamada por um bloco _try/catch/finally_ padrão.</span><span class="sxs-lookup"><span data-stu-id="6f77b-115">If you are calling `RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup`, replace the call with a standard _try / catch / finally_ block.</span></span>

  ```csharp
  // The sample below produces warning SYSLIB0004.
  public void DoSomething_Old()
  {
      RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(MyTryCode, MyCleanupCode, null);
  }
  public void MyTryCode(object state) { /* try code */ }
  public void MyCleanupCode(object state, bool exceptionThrown) { /* cleanup code */ }

  // The corrected sample below does not produce warning SYSLIB0004.
  public void DoSomething_Corrected()
  {
      try
      {
          // try code
      }
      catch (Exception ex)
      {
          // exception handling code
      }
      finally
      {
          // cleanup code
      }
  }
  ```

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="6f77b-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="6f77b-116">See also</span></span>

- [<span data-ttu-id="6f77b-117">Regiões de execução restrita</span><span class="sxs-lookup"><span data-stu-id="6f77b-117">Constrained execution regions</span></span>](../../../framework/performance/constrained-execution-regions.md)
