---
title: MDA marshaling
description: Examine o assistente de depuração gerenciada de marshaling (MDA), que é invocado se o CLR configurar informações de marshaling para um parâmetro de método ou um campo de estrutura.
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
ms.openlocfilehash: afe54a2104e05f8fad57c7cbba4988b013aff761
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271168"
---
# <a name="marshaling-mda"></a><span data-ttu-id="e64de-103">MDA marshaling</span><span class="sxs-lookup"><span data-stu-id="e64de-103">marshaling MDA</span></span>

<span data-ttu-id="e64de-104">O MDA (Assistente de Depuração Gerenciado) de `marshaling` é ativado quando o CLR define informações de marshaling para um parâmetro de método ou um campo de uma estrutura.</span><span class="sxs-lookup"><span data-stu-id="e64de-104">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="e64de-105">Esse MDA não funciona para assemblies compilados por JIT.</span><span class="sxs-lookup"><span data-stu-id="e64de-105">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e64de-106">Efeito sobre o runtime</span><span class="sxs-lookup"><span data-stu-id="e64de-106">Effect on the Runtime</span></span>  

 <span data-ttu-id="e64de-107">Esse MDA não tem efeito sobre o CLR.</span><span class="sxs-lookup"><span data-stu-id="e64de-107">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e64de-108">Saída</span><span class="sxs-lookup"><span data-stu-id="e64de-108">Output</span></span>  

 <span data-ttu-id="e64de-109">O MDA exibe o tipo do parâmetro ou campo nos contextos gerenciado e não gerenciado, bem como a estrutura ou o método que contém o tipo.</span><span class="sxs-lookup"><span data-stu-id="e64de-109">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="e64de-110">A seguir está um exemplo da saída de um campo:</span><span class="sxs-lookup"><span data-stu-id="e64de-110">The following is an example of the output for a field:</span></span>  
  
```output
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="e64de-111">Configuração</span><span class="sxs-lookup"><span data-stu-id="e64de-111">Configuration</span></span>  

 <span data-ttu-id="e64de-112">A configuração de MDA permite que você filtre as informações de marshaling relatadas com base no campo envolvido ou em nomes de método.</span><span class="sxs-lookup"><span data-stu-id="e64de-112">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="e64de-113">O exemplo a seguir mostra o uso dos elementos `methodFilter`, `fieldFilter` e `match` para especificar filtros.</span><span class="sxs-lookup"><span data-stu-id="e64de-113">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="e64de-114">A definição do `name` atributo como um asterisco ( \* ) corresponderá a tudo.</span><span class="sxs-lookup"><span data-stu-id="e64de-114">Setting the `name` attribute to an asterisk (\*) will match everything.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e64de-115">Veja também</span><span class="sxs-lookup"><span data-stu-id="e64de-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="e64de-116">Diagnosticando erros com assistentes de depuração gerenciados</span><span class="sxs-lookup"><span data-stu-id="e64de-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="e64de-117">Realizando marshaling de interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="e64de-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
