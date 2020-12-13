---
title: Programação assíncrona
description: 'Saiba como o F # fornece suporte limpo para assincronia com base em um modelo de programação de nível de linguagem derivado dos principais conceitos de programação funcional.'
ms.date: 08/15/2020
ms.openlocfilehash: 8bf8d6987187377cc1f44e77141b5d70d873f849
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366810"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="fc0a1-103">Programação assíncrona em F\#</span><span class="sxs-lookup"><span data-stu-id="fc0a1-103">Async programming in F\#</span></span>

<span data-ttu-id="fc0a1-104">A programação assíncrona é um mecanismo essencial para aplicativos modernos por vários motivos.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="fc0a1-105">Há dois casos de uso primários que a maioria dos desenvolvedores encontrará:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="fc0a1-106">Apresentar um processo de servidor que pode atender a um número significativo de solicitações de entrada simultâneas, minimizando os recursos do sistema ocupados enquanto o processamento da solicitação aguarda entradas de sistemas ou serviços externos a esse processo</span><span class="sxs-lookup"><span data-stu-id="fc0a1-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="fc0a1-107">Manutenção de uma interface do usuário responsiva ou thread principal ao progredir o trabalho em segundo plano simultaneamente</span><span class="sxs-lookup"><span data-stu-id="fc0a1-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="fc0a1-108">Embora o trabalho em segundo plano geralmente envolva a utilização de vários threads, é importante considerar os conceitos de assincronia e multithreading separadamente.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="fc0a1-109">Na verdade, eles são preocupações separadas e um não implica o outro.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="fc0a1-110">Este artigo descreve os conceitos separados em mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-110">This article describes the separate concepts in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="fc0a1-111">Assincronia definida</span><span class="sxs-lookup"><span data-stu-id="fc0a1-111">Asynchrony defined</span></span>

<span data-ttu-id="fc0a1-112">O ponto anterior – que a assincronia é independente da utilização de vários threads-vale a pena explicar um pouco mais.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="fc0a1-113">Há três conceitos que às vezes são relacionados, mas estritamente independentes um do outro:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="fc0a1-114">Corrente Quando vários cálculos são executados em períodos de tempo sobrepostos.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="fc0a1-115">Paralelismo Quando vários cálculos ou várias partes de uma única computação são executados exatamente ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="fc0a1-116">Sincronismo Quando um ou mais cálculos podem ser executados separadamente do fluxo do programa principal.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="fc0a1-117">Todos os três são conceitos ortogonal, mas podem ser facilmente conplanados, especialmente quando eles são usados juntos.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="fc0a1-118">Por exemplo, talvez seja necessário executar várias Computações assíncronas em paralelo.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="fc0a1-119">Essa relação não significa que o paralelismo ou a assincronia implicam um ao outro.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-119">This relationship does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="fc0a1-120">Se você considerar o etymology da palavra "Asynchronous", há duas partes envolvidas:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="fc0a1-121">"a", significando "não".</span><span class="sxs-lookup"><span data-stu-id="fc0a1-121">"a", meaning "not".</span></span>
- <span data-ttu-id="fc0a1-122">"síncrono", significando "ao mesmo tempo".</span><span class="sxs-lookup"><span data-stu-id="fc0a1-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="fc0a1-123">Ao reunir esses dois termos, você verá que "assíncrono" significa "não ao mesmo tempo".</span><span class="sxs-lookup"><span data-stu-id="fc0a1-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="fc0a1-124">Pronto!</span><span class="sxs-lookup"><span data-stu-id="fc0a1-124">That's it!</span></span> <span data-ttu-id="fc0a1-125">Não há implicação de simultaneidade ou paralelismo nessa definição.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="fc0a1-126">Isso também é verdade na prática.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-126">This is also true in practice.</span></span>

<span data-ttu-id="fc0a1-127">Em termos práticos, cálculos assíncronos em F # são agendados para execução independente do fluxo do programa principal.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="fc0a1-128">Essa execução independente não implica em simultaneidade ou paralelismo, nem significa que uma computação sempre ocorre em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-128">This independent execution doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="fc0a1-129">Na verdade, as Computações assíncronas podem até mesmo executar de forma síncrona, dependendo da natureza da computação e do ambiente em que a computação está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="fc0a1-130">O principal argumento que você deve ter é que as Computações assíncronas são independentes do fluxo do programa principal.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="fc0a1-131">Embora haja algumas garantias sobre quando ou como uma computação assíncrona é executada, há algumas abordagens para orquestrar e agendá-las.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="fc0a1-132">O restante deste artigo explora os principais conceitos de assincronia F # e como usar os tipos, funções e expressões criados no F #.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="fc0a1-133">Conceitos fundamentais</span><span class="sxs-lookup"><span data-stu-id="fc0a1-133">Core concepts</span></span>

<span data-ttu-id="fc0a1-134">No F #, a programação assíncrona é centralizada em cerca de três conceitos principais:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="fc0a1-135">O `Async<'T>` tipo, que representa uma computação assíncrona combinável.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="fc0a1-136">As `Async` funções de módulo, que permitem agendar trabalho assíncrono, compor Computações assíncronas e transformar resultados assíncronos.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="fc0a1-137">A `async { }` [expressão de computação](../../language-reference/computation-expressions.md), que fornece uma sintaxe conveniente para criar e controlar cálculos assíncronos.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="fc0a1-138">Você pode ver esses três conceitos no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-138">You can see these three concepts in the following example:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn $"File {fileName} has %d{bytes.Length} bytes"
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

<span data-ttu-id="fc0a1-139">No exemplo, a `printTotalFileBytes` função é do tipo `string -> Async<unit>` .</span><span class="sxs-lookup"><span data-stu-id="fc0a1-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="fc0a1-140">Chamar a função não executa realmente a computação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="fc0a1-141">Em vez disso, retorna um `Async<unit>` que atua como uma *especificação* do trabalho que deve ser executado de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="fc0a1-142">Ele chama `Async.AwaitTask` seu corpo, que converte o resultado de <xref:System.IO.File.ReadAllBytesAsync%2A> para um tipo apropriado.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="fc0a1-143">Outra linha importante é a chamada para `Async.RunSynchronously` .</span><span class="sxs-lookup"><span data-stu-id="fc0a1-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="fc0a1-144">Esse é um dos módulos assíncronos que iniciam funções que você precisará chamar se quiser realmente executar uma computação assíncrona em F #.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="fc0a1-145">Essa é uma diferença fundamental com o estilo de programação C#/Visual Basic `async` .</span><span class="sxs-lookup"><span data-stu-id="fc0a1-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="fc0a1-146">No F #, as Computações assíncronas podem ser consideradas como **tarefas frias**.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="fc0a1-147">Eles devem ser iniciados explicitamente para realmente executar.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="fc0a1-148">Isso tem algumas vantagens, pois permite combinar e sequenciar trabalho assíncrono muito mais facilmente do que em C# ou Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="fc0a1-149">Combinar Computações assíncronas</span><span class="sxs-lookup"><span data-stu-id="fc0a1-149">Combine asynchronous computations</span></span>

<span data-ttu-id="fc0a1-150">Aqui está um exemplo que se baseia no anterior combinando cálculos:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-150">Here is an example that builds upon the previous one by combining computations:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn $"File {fileName} has %d{bytes.Length} bytes"
    }

[<EntryPoint>]
let main argv =
    argv
    |> Seq.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

<span data-ttu-id="fc0a1-151">Como você pode ver, a `main` função tem muito mais alguns elementos.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-151">As you can see, the `main` function has quite a few more elements.</span></span> <span data-ttu-id="fc0a1-152">Conceitualmente, ele faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="fc0a1-153">Transforme os argumentos de linha de comando em uma sequência de `Async<unit>` cálculos com `Seq.map` .</span><span class="sxs-lookup"><span data-stu-id="fc0a1-153">Transform the command-line arguments into a sequence of `Async<unit>` computations with `Seq.map`.</span></span>
2. <span data-ttu-id="fc0a1-154">Crie um `Async<'T[]>` que agenda e executa os `printTotalFileBytes` cálculos em paralelo quando ele é executado.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="fc0a1-155">Crie um `Async<unit>` que executará a computação paralela e ignore seu resultado (que é um `unit[]` ).</span><span class="sxs-lookup"><span data-stu-id="fc0a1-155">Create an `Async<unit>` that will run the parallel computation and ignore its result (which is a `unit[]`).</span></span>
4. <span data-ttu-id="fc0a1-156">Execute explicitamente a computação composta geral com `Async.RunSynchronously` , bloqueando até que seja concluída.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-156">Explicitly run the overall composed computation with `Async.RunSynchronously`, blocking until it completes.</span></span>

<span data-ttu-id="fc0a1-157">Quando esse programa é executado, `printTotalFileBytes` é executado em paralelo para cada argumento de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="fc0a1-158">Como as Computações assíncronas são executadas independentemente do fluxo do programa, não há nenhuma ordem definida na qual elas imprimem suas informações e concluam a execução.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-158">Because asynchronous computations execute independently of program flow, there is no defined order in which they print their information and finish executing.</span></span> <span data-ttu-id="fc0a1-159">Os cálculos serão agendados em paralelo, mas a ordem de execução não será garantida.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="fc0a1-160">Computações assíncronas de sequência</span><span class="sxs-lookup"><span data-stu-id="fc0a1-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="fc0a1-161">Como `Async<'T>` o é uma especificação de trabalho em vez de uma tarefa já em execução, você pode executar transformações mais complexas facilmente.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="fc0a1-162">Aqui está um exemplo que sequencia um conjunto de Computações assíncronas para que eles executem um após o outro.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn $"File {fileName} has %d{bytes.Length} bytes"
    }

[<EntryPoint>]
let main argv =
    argv
    |> Seq.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="fc0a1-163">Isso agendará `printTotalFileBytes` para ser executado na ordem dos elementos em `argv` vez de agendá-los em paralelo.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="fc0a1-164">Como cada operação sucessiva não será agendada até a conclusão da execução da computação anterior, os cálculos serão seqüenciados de modo que não haja sobreposição na execução.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-164">Because each successive operation will not be scheduled until after the preceding computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="fc0a1-165">Funções de módulo assíncrono importantes</span><span class="sxs-lookup"><span data-stu-id="fc0a1-165">Important Async module functions</span></span>

<span data-ttu-id="fc0a1-166">Ao escrever código assíncrono em F #, você geralmente interage com uma estrutura que lida com o agendamento de cálculos para você.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-166">When you write async code in F#, you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="fc0a1-167">No entanto, esse não é sempre o caso, portanto, é bom entender as várias funções que podem ser usadas para agendar o trabalho assíncrono.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-167">However, this is not always the case, so it is good to understand the various functions that can be used to schedule asynchronous work.</span></span>

<span data-ttu-id="fc0a1-168">Como os cálculos assíncronos F # são uma _especificação_ de trabalho em vez de uma representação de trabalho que já está em execução, eles devem ser iniciados explicitamente com uma função inicial.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="fc0a1-169">Há muitos [métodos de início assíncrono](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#section0) que são úteis em diferentes contextos.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-169">There are many [Async starting methods](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#section0) that are helpful in different contexts.</span></span> <span data-ttu-id="fc0a1-170">A seção a seguir descreve algumas das funções iniciais mais comuns.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="fc0a1-171">Async. StartChild</span><span class="sxs-lookup"><span data-stu-id="fc0a1-171">Async.StartChild</span></span>

<span data-ttu-id="fc0a1-172">Inicia uma computação filho em uma computação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="fc0a1-173">Isso permite que vários cálculos assíncronos sejam executados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="fc0a1-174">A computação filho compartilha um token de cancelamento com a computação pai.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="fc0a1-175">Se o cálculo pai for cancelado, o cálculo filho também será cancelado.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="fc0a1-176">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-176">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="fc0a1-177">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-177">When to use:</span></span>

- <span data-ttu-id="fc0a1-178">Quando você deseja executar várias Computações assíncronas simultaneamente em vez de uma de cada vez, mas elas não são agendadas em paralelo.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="fc0a1-179">Quando você quiser vincular o tempo de vida de uma computação filho ao de um cálculo pai.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="fc0a1-180">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-180">What to watch out for:</span></span>

- <span data-ttu-id="fc0a1-181">Iniciar vários cálculos com `Async.StartChild` não é o mesmo que agendá-los em paralelo.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="fc0a1-182">Se você quiser agendar cálculos em paralelo, use `Async.Parallel` .</span><span class="sxs-lookup"><span data-stu-id="fc0a1-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="fc0a1-183">Cancelar um cálculo pai irá disparar o cancelamento de todos os cálculos filho iniciados.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="fc0a1-184">Async. StartImmediate</span><span class="sxs-lookup"><span data-stu-id="fc0a1-184">Async.StartImmediate</span></span>

<span data-ttu-id="fc0a1-185">Executa uma computação assíncrona, começando imediatamente no thread do sistema operacional atual.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="fc0a1-186">Isso será útil se você precisar atualizar algo no thread de chamada durante o cálculo.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="fc0a1-187">Por exemplo, se uma computação assíncrona precisar atualizar uma interface do usuário (como atualizar uma barra de progresso), `Async.StartImmediate` deverá ser usada.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="fc0a1-188">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-188">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="fc0a1-189">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-189">When to use:</span></span>

- <span data-ttu-id="fc0a1-190">Quando você precisa atualizar algo no thread de chamada no meio de uma computação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="fc0a1-191">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-191">What to watch out for:</span></span>

- <span data-ttu-id="fc0a1-192">O código na computação assíncrona será executado em qualquer thread em que ele esteja agendado.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="fc0a1-193">Isso pode ser problemático se esse thread for, de alguma forma, confidencial, como um thread de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="fc0a1-194">Nesses casos, `Async.StartImmediate` provavelmente é inadequado usar.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="fc0a1-195">Async. StartAsTask</span><span class="sxs-lookup"><span data-stu-id="fc0a1-195">Async.StartAsTask</span></span>

<span data-ttu-id="fc0a1-196">Executa uma computação no pool de threads.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="fc0a1-197">Retorna um <xref:System.Threading.Tasks.Task%601> que será concluído no estado correspondente depois que o cálculo for encerrado (produz o resultado, gera uma exceção ou é cancelado).</span><span class="sxs-lookup"><span data-stu-id="fc0a1-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="fc0a1-198">Se nenhum token de cancelamento for fornecido, o token de cancelamento padrão será usado.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="fc0a1-199">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-199">Signature:</span></span>

```fsharp
computation: Async<'T> * taskCreationOptions: ?TaskCreationOptions * cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="fc0a1-200">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-200">When to use:</span></span>

- <span data-ttu-id="fc0a1-201">Quando você precisa chamar uma API do .NET que produz um <xref:System.Threading.Tasks.Task%601> para representar o resultado de uma computação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-201">When you need to call into a .NET API that yields a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="fc0a1-202">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-202">What to watch out for:</span></span>

- <span data-ttu-id="fc0a1-203">Essa chamada irá alocar um `Task` objeto adicional, o que pode aumentar a sobrecarga se for usado com frequência.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="fc0a1-204">Async. Parallel</span><span class="sxs-lookup"><span data-stu-id="fc0a1-204">Async.Parallel</span></span>

<span data-ttu-id="fc0a1-205">Agenda uma sequência de Computações assíncronas a serem executadas em paralelo, produzindo uma matriz de resultados na ordem em que foram fornecidas.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-205">Schedules a sequence of asynchronous computations to be executed in parallel, yielding an array of results in the order they were supplied.</span></span> <span data-ttu-id="fc0a1-206">O grau de paralelismo pode ser, opcionalmente, ajustado/limitado, especificando o `maxDegreeOfParallelism` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreeOfParallelism` parameter.</span></span>

<span data-ttu-id="fc0a1-207">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> * ?maxDegreeOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="fc0a1-208">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-208">When to use it:</span></span>

- <span data-ttu-id="fc0a1-209">Se você precisar executar um conjunto de cálculos ao mesmo tempo e não tiver nenhuma dependência em sua ordem de execução.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="fc0a1-210">Se você não precisar de resultados de cálculos agendados em paralelo até que todos tenham sido concluídos.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="fc0a1-211">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-211">What to watch out for:</span></span>

- <span data-ttu-id="fc0a1-212">Você só pode acessar a matriz resultante de valores depois que todos os cálculos forem concluídos.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="fc0a1-213">As computações serão executadas sempre que acabarem sendo agendadas.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-213">Computations will be run whenever they end up getting scheduled.</span></span> <span data-ttu-id="fc0a1-214">Esse comportamento significa que você não pode contar com a ordem de sua execução.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-214">This behavior means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="fc0a1-215">Async. Sequential</span><span class="sxs-lookup"><span data-stu-id="fc0a1-215">Async.Sequential</span></span>

<span data-ttu-id="fc0a1-216">Agenda uma sequência de Computações assíncronas a serem executadas na ordem em que são passadas.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="fc0a1-217">O primeiro cálculo será executado e, em seguida, o próximo e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="fc0a1-218">Nenhum cálculo será executado em paralelo.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="fc0a1-219">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="fc0a1-220">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-220">When to use it:</span></span>

- <span data-ttu-id="fc0a1-221">Se você precisar executar vários cálculos na ordem.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="fc0a1-222">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-222">What to watch out for:</span></span>

- <span data-ttu-id="fc0a1-223">Você só pode acessar a matriz resultante de valores depois que todos os cálculos forem concluídos.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="fc0a1-224">As computações serão executadas na ordem em que são passadas para essa função, o que pode significar que mais tempo decorrerá antes que os resultados sejam retornados.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="fc0a1-225">Async. AwaitTask</span><span class="sxs-lookup"><span data-stu-id="fc0a1-225">Async.AwaitTask</span></span>

<span data-ttu-id="fc0a1-226">Retorna uma computação assíncrona que aguarda o determinado <xref:System.Threading.Tasks.Task%601> a ser concluído e retorna seu resultado como um `Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="fc0a1-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="fc0a1-227">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-227">Signature:</span></span>

```fsharp
task: Task<'T> -> Async<'T>
```

<span data-ttu-id="fc0a1-228">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-228">When to use:</span></span>

- <span data-ttu-id="fc0a1-229">Quando você está consumindo uma API do .NET que retorna um <xref:System.Threading.Tasks.Task%601> dentro de uma computação assíncrona em F #.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="fc0a1-230">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-230">What to watch out for:</span></span>

- <span data-ttu-id="fc0a1-231">As exceções são encapsuladas <xref:System.AggregateException> seguindo a Convenção da biblioteca de tarefas paralelas; esse comportamento é diferente de como a F # Async geralmente faz a superfície de exceções.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library; this behavior is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="fc0a1-232">Async. catch</span><span class="sxs-lookup"><span data-stu-id="fc0a1-232">Async.Catch</span></span>

<span data-ttu-id="fc0a1-233">Cria uma computação assíncrona que executa um determinado `Async<'T>` , retornando um `Async<Choice<'T, exn>>` .</span><span class="sxs-lookup"><span data-stu-id="fc0a1-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="fc0a1-234">Se o determinado for `Async<'T>` concluído com êxito, um `Choice1Of2` será retornado com o valor resultante.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="fc0a1-235">Se uma exceção for lançada antes de ser concluída, um `Choice2of2` será retornado com a exceção gerada.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="fc0a1-236">Se ele for usado em uma computação assíncrona que, por sua vez, é composto por muitos cálculos, e um desses cálculos gera uma exceção, a computação que englobará o cálculo será totalmente interrompida.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="fc0a1-237">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="fc0a1-238">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-238">When to use:</span></span>

- <span data-ttu-id="fc0a1-239">Quando você estiver executando um trabalho assíncrono que pode falhar com uma exceção e você deseja tratar essa exceção no chamador.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="fc0a1-240">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-240">What to watch out for:</span></span>

- <span data-ttu-id="fc0a1-241">Ao usar Computações assíncronas combinadas ou sequenciadas, a computação abrangerá completamente se um de seus cálculos "internos" gerar uma exceção.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="fc0a1-242">Async. ignore</span><span class="sxs-lookup"><span data-stu-id="fc0a1-242">Async.Ignore</span></span>

<span data-ttu-id="fc0a1-243">Cria uma computação assíncrona que executa a computação fornecida, mas descarta seu resultado.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-243">Creates an asynchronous computation that runs the given computation but drops its result.</span></span>

<span data-ttu-id="fc0a1-244">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="fc0a1-245">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-245">When to use:</span></span>

- <span data-ttu-id="fc0a1-246">Quando você tem uma computação assíncrona cujo resultado não é necessário.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="fc0a1-247">Isso é análogo à `ignore` função de código não assíncrono.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-247">This is analogous to the `ignore` function for non-asynchronous code.</span></span>

<span data-ttu-id="fc0a1-248">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-248">What to watch out for:</span></span>

- <span data-ttu-id="fc0a1-249">Se você precisar usar `Async.Ignore` o porque deseja usar `Async.Start` ou outra função que exija `Async<unit>` o, considere se descartar o resultado está ok.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-249">If you must use `Async.Ignore` because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay.</span></span> <span data-ttu-id="fc0a1-250">Evite descartar os resultados apenas para se ajustar a uma assinatura de tipo.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-250">Avoid discarding results just to fit a type signature.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="fc0a1-251">Async. RunSynchronously</span><span class="sxs-lookup"><span data-stu-id="fc0a1-251">Async.RunSynchronously</span></span>

<span data-ttu-id="fc0a1-252">Executa uma computação assíncrona e aguarda seu resultado no thread de chamada.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="fc0a1-253">Propaga uma exceção caso a computação gere uma.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-253">Propagates an exception should the computation yield one.</span></span> <span data-ttu-id="fc0a1-254">Esta chamada está bloqueando.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-254">This call is blocking.</span></span>

<span data-ttu-id="fc0a1-255">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-255">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int * cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="fc0a1-256">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-256">When to use it:</span></span>

- <span data-ttu-id="fc0a1-257">Se você precisar dele, use-o apenas uma vez em um aplicativo-no ponto de entrada para um executável.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-257">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="fc0a1-258">Quando você não se importa com o desempenho e deseja executar um conjunto de outras operações assíncronas de uma vez.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-258">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="fc0a1-259">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-259">What to watch out for:</span></span>

- <span data-ttu-id="fc0a1-260">A chamada `Async.RunSynchronously` bloqueia o thread de chamada até que a execução seja concluída.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-260">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="fc0a1-261">Async. Start</span><span class="sxs-lookup"><span data-stu-id="fc0a1-261">Async.Start</span></span>

<span data-ttu-id="fc0a1-262">Inicia uma computação assíncrona que retorna `unit` no pool de threads.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-262">Starts an asynchronous computation that returns `unit` in the thread pool.</span></span> <span data-ttu-id="fc0a1-263">Não aguarda sua conclusão e/ou observa um resultado de exceção.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-263">Doesn't wait for its completion and/or observe an exception outcome.</span></span> <span data-ttu-id="fc0a1-264">Cálculos aninhados iniciados com `Async.Start` são iniciados independentemente do cálculo pai que os chamou; seu tempo de vida não está vinculado a nenhum cálculo pai.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-264">Nested computations started with `Async.Start` are started independently of the parent computation that called them; their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="fc0a1-265">Se o cálculo pai for cancelado, nenhum cálculo filho será cancelado.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-265">If the parent computation is canceled, no child computations are canceled.</span></span>

<span data-ttu-id="fc0a1-266">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-266">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="fc0a1-267">Use somente quando:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-267">Use only when:</span></span>

- <span data-ttu-id="fc0a1-268">Você tem uma computação assíncrona que não produz um resultado e/ou requer o processamento de um.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="fc0a1-269">Você não precisa saber quando uma computação assíncrona é concluída.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="fc0a1-270">Você não se importa com o thread em que uma computação assíncrona é executada.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="fc0a1-271">Você não precisa estar atento ou relatar exceções resultantes da execução.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-271">You don't have any need to be aware of or report exceptions resulting from the execution.</span></span>

<span data-ttu-id="fc0a1-272">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-272">What to watch out for:</span></span>

- <span data-ttu-id="fc0a1-273">Exceções geradas por computações iniciadas com `Async.Start` não são propagadas para o chamador.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="fc0a1-274">A pilha de chamadas será completamente desbobinada.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="fc0a1-275">Qualquer trabalho (como chamada `printfn` ) iniciado com `Async.Start` não fará com que o efeito aconteça no thread principal da execução de um programa.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-275">Any work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="fc0a1-276">Interoperar com o .NET</span><span class="sxs-lookup"><span data-stu-id="fc0a1-276">Interoperate with .NET</span></span>

<span data-ttu-id="fc0a1-277">Você pode estar trabalhando com uma biblioteca .NET ou codebase C# que usa programação assíncrona de estilo [Async/Await](../../../standard/async.md).</span><span class="sxs-lookup"><span data-stu-id="fc0a1-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="fc0a1-278">Como o C# e a maioria das bibliotecas do .NET usam os <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task> tipos e como suas abstrações principais em vez de `Async<'T>` , você deve cruzar um limite entre essas duas abordagens para assincronia.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="fc0a1-279">Como trabalhar com o .NET Async e `Task<T>`</span><span class="sxs-lookup"><span data-stu-id="fc0a1-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="fc0a1-280">Trabalhar com bibliotecas assíncronas .NET e bases de código que usam <xref:System.Threading.Tasks.Task%601> (ou seja, Computações assíncronas com valores de retorno) é simples e tem suporte interno com F #.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="fc0a1-281">Você pode usar a `Async.AwaitTask` função para aguardar uma computação assíncrona do .net:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="fc0a1-282">Você pode usar a `Async.StartAsTask` função para passar uma computação assíncrona para um chamador do .net:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="fc0a1-283">Como trabalhar com o .NET Async e `Task`</span><span class="sxs-lookup"><span data-stu-id="fc0a1-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="fc0a1-284">Para trabalhar com APIs que usam <xref:System.Threading.Tasks.Task> (ou seja, Computações assíncronas do .NET que não retornam um valor), talvez seja necessário adicionar uma função adicional que converterá um `Async<'T>` para um <xref:System.Threading.Tasks.Task> :</span><span class="sxs-lookup"><span data-stu-id="fc0a1-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="fc0a1-285">Já existe um `Async.AwaitTask` que aceita uma <xref:System.Threading.Tasks.Task> entrada as.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="fc0a1-286">Com isso e a função definida anteriormente `startTaskFromAsyncUnit` , você pode iniciar e esperar <xref:System.Threading.Tasks.Task> tipos de uma computação Async de F #.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="fc0a1-287">Relação com multithreading</span><span class="sxs-lookup"><span data-stu-id="fc0a1-287">Relationship to multi-threading</span></span>

<span data-ttu-id="fc0a1-288">Embora o Threading seja mencionado em todo este artigo, há duas coisas importantes a serem lembradas:</span><span class="sxs-lookup"><span data-stu-id="fc0a1-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="fc0a1-289">Não há afinidade entre uma computação assíncrona e um thread, a menos que seja explicitamente iniciado no thread atual.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="fc0a1-290">A programação assíncrona em F # não é uma abstração para multithreading.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="fc0a1-291">Por exemplo, uma computação pode ser realmente executada no thread do chamador, dependendo da natureza do trabalho.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="fc0a1-292">Uma computação também poderia "saltar" entre threads, emprestando-os por um pequeno tempo para fazer um trabalho útil entre períodos de "espera" (como quando uma chamada de rede está em trânsito).</span><span class="sxs-lookup"><span data-stu-id="fc0a1-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="fc0a1-293">Embora o F # forneça algumas capacidades para iniciar uma computação assíncrona no thread atual (ou não explicitamente no thread atual), a assincronia geralmente não está associada a uma estratégia de Threading específica.</span><span class="sxs-lookup"><span data-stu-id="fc0a1-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc0a1-294">Veja também</span><span class="sxs-lookup"><span data-stu-id="fc0a1-294">See also</span></span>

- [<span data-ttu-id="fc0a1-295">O modelo de programação assíncrona F #</span><span class="sxs-lookup"><span data-stu-id="fc0a1-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="fc0a1-296">Guia assíncrono F # do Jet. com</span><span class="sxs-lookup"><span data-stu-id="fc0a1-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="fc0a1-297">F # para o guia de programação assíncrona de lucros e diversão</span><span class="sxs-lookup"><span data-stu-id="fc0a1-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="fc0a1-298">Async em C# e F #: armadilhas assíncronas em C #</span><span class="sxs-lookup"><span data-stu-id="fc0a1-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
