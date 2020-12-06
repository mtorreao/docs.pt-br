---
title: Programação assíncrona
description: 'Saiba como o F # fornece suporte limpo para assincronia com base em um modelo de programação de nível de linguagem derivado dos principais conceitos de programação funcional.'
ms.date: 08/15/2020
ms.openlocfilehash: 04b397ddbfb468aa3bc4ee245175d3ec9bdedb50
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739321"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="4deba-103">Programação assíncrona em F\#</span><span class="sxs-lookup"><span data-stu-id="4deba-103">Async programming in F\#</span></span>

<span data-ttu-id="4deba-104">A programação assíncrona é um mecanismo essencial para aplicativos modernos por vários motivos.</span><span class="sxs-lookup"><span data-stu-id="4deba-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="4deba-105">Há dois casos de uso primários que a maioria dos desenvolvedores encontrará:</span><span class="sxs-lookup"><span data-stu-id="4deba-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="4deba-106">Apresentar um processo de servidor que pode atender a um número significativo de solicitações de entrada simultâneas, minimizando os recursos do sistema ocupados enquanto o processamento da solicitação aguarda entradas de sistemas ou serviços externos a esse processo</span><span class="sxs-lookup"><span data-stu-id="4deba-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="4deba-107">Manutenção de uma interface do usuário responsiva ou thread principal ao progredir o trabalho em segundo plano simultaneamente</span><span class="sxs-lookup"><span data-stu-id="4deba-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="4deba-108">Embora o trabalho em segundo plano geralmente envolva a utilização de vários threads, é importante considerar os conceitos de assincronia e multithreading separadamente.</span><span class="sxs-lookup"><span data-stu-id="4deba-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="4deba-109">Na verdade, eles são preocupações separadas e um não implica o outro.</span><span class="sxs-lookup"><span data-stu-id="4deba-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="4deba-110">Este artigo descreve os conceitos separados em mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="4deba-110">This article describes the separate concepts in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="4deba-111">Assincronia definida</span><span class="sxs-lookup"><span data-stu-id="4deba-111">Asynchrony defined</span></span>

<span data-ttu-id="4deba-112">O ponto anterior – que a assincronia é independente da utilização de vários threads-vale a pena explicar um pouco mais.</span><span class="sxs-lookup"><span data-stu-id="4deba-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="4deba-113">Há três conceitos que às vezes são relacionados, mas estritamente independentes um do outro:</span><span class="sxs-lookup"><span data-stu-id="4deba-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="4deba-114">Corrente Quando vários cálculos são executados em períodos de tempo sobrepostos.</span><span class="sxs-lookup"><span data-stu-id="4deba-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="4deba-115">Paralelismo Quando vários cálculos ou várias partes de uma única computação são executados exatamente ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="4deba-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="4deba-116">Sincronismo Quando um ou mais cálculos podem ser executados separadamente do fluxo do programa principal.</span><span class="sxs-lookup"><span data-stu-id="4deba-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="4deba-117">Todos os três são conceitos ortogonal, mas podem ser facilmente conplanados, especialmente quando eles são usados juntos.</span><span class="sxs-lookup"><span data-stu-id="4deba-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="4deba-118">Por exemplo, talvez seja necessário executar várias Computações assíncronas em paralelo.</span><span class="sxs-lookup"><span data-stu-id="4deba-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="4deba-119">Essa relação não significa que o paralelismo ou a assincronia implicam um ao outro.</span><span class="sxs-lookup"><span data-stu-id="4deba-119">This relationship does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="4deba-120">Se você considerar o etymology da palavra "Asynchronous", há duas partes envolvidas:</span><span class="sxs-lookup"><span data-stu-id="4deba-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="4deba-121">"a", significando "não".</span><span class="sxs-lookup"><span data-stu-id="4deba-121">"a", meaning "not".</span></span>
- <span data-ttu-id="4deba-122">"síncrono", significando "ao mesmo tempo".</span><span class="sxs-lookup"><span data-stu-id="4deba-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="4deba-123">Ao reunir esses dois termos, você verá que "assíncrono" significa "não ao mesmo tempo".</span><span class="sxs-lookup"><span data-stu-id="4deba-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="4deba-124">Pronto!</span><span class="sxs-lookup"><span data-stu-id="4deba-124">That's it!</span></span> <span data-ttu-id="4deba-125">Não há implicação de simultaneidade ou paralelismo nessa definição.</span><span class="sxs-lookup"><span data-stu-id="4deba-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="4deba-126">Isso também é verdade na prática.</span><span class="sxs-lookup"><span data-stu-id="4deba-126">This is also true in practice.</span></span>

<span data-ttu-id="4deba-127">Em termos práticos, cálculos assíncronos em F # são agendados para execução independente do fluxo do programa principal.</span><span class="sxs-lookup"><span data-stu-id="4deba-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="4deba-128">Essa execução independente não implica em simultaneidade ou paralelismo, nem significa que uma computação sempre ocorre em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4deba-128">This independent execution doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="4deba-129">Na verdade, as Computações assíncronas podem até mesmo executar de forma síncrona, dependendo da natureza da computação e do ambiente em que a computação está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="4deba-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="4deba-130">O principal argumento que você deve ter é que as Computações assíncronas são independentes do fluxo do programa principal.</span><span class="sxs-lookup"><span data-stu-id="4deba-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="4deba-131">Embora haja algumas garantias sobre quando ou como uma computação assíncrona é executada, há algumas abordagens para orquestrar e agendá-las.</span><span class="sxs-lookup"><span data-stu-id="4deba-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="4deba-132">O restante deste artigo explora os principais conceitos de assincronia F # e como usar os tipos, funções e expressões criados no F #.</span><span class="sxs-lookup"><span data-stu-id="4deba-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="4deba-133">Conceitos fundamentais</span><span class="sxs-lookup"><span data-stu-id="4deba-133">Core concepts</span></span>

<span data-ttu-id="4deba-134">No F #, a programação assíncrona é centralizada em cerca de três conceitos principais:</span><span class="sxs-lookup"><span data-stu-id="4deba-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="4deba-135">O `Async<'T>` tipo, que representa uma computação assíncrona combinável.</span><span class="sxs-lookup"><span data-stu-id="4deba-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="4deba-136">As `Async` funções de módulo, que permitem agendar trabalho assíncrono, compor Computações assíncronas e transformar resultados assíncronos.</span><span class="sxs-lookup"><span data-stu-id="4deba-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="4deba-137">A `async { }` [expressão de computação](../../language-reference/computation-expressions.md), que fornece uma sintaxe conveniente para criar e controlar cálculos assíncronos.</span><span class="sxs-lookup"><span data-stu-id="4deba-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="4deba-138">Você pode ver esses três conceitos no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4deba-138">You can see these three concepts in the following example:</span></span>

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

<span data-ttu-id="4deba-139">No exemplo, a `printTotalFileBytes` função é do tipo `string -> Async<unit>` .</span><span class="sxs-lookup"><span data-stu-id="4deba-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="4deba-140">Chamar a função não executa realmente a computação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="4deba-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="4deba-141">Em vez disso, retorna um `Async<unit>` que atua como uma *especificação* do trabalho que deve ser executado de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="4deba-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="4deba-142">Ele chama `Async.AwaitTask` seu corpo, que converte o resultado de <xref:System.IO.File.ReadAllBytesAsync%2A> para um tipo apropriado.</span><span class="sxs-lookup"><span data-stu-id="4deba-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="4deba-143">Outra linha importante é a chamada para `Async.RunSynchronously` .</span><span class="sxs-lookup"><span data-stu-id="4deba-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="4deba-144">Esse é um dos módulos assíncronos que iniciam funções que você precisará chamar se quiser realmente executar uma computação assíncrona em F #.</span><span class="sxs-lookup"><span data-stu-id="4deba-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="4deba-145">Essa é uma diferença fundamental com o estilo de programação C#/Visual Basic `async` .</span><span class="sxs-lookup"><span data-stu-id="4deba-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="4deba-146">No F #, as Computações assíncronas podem ser consideradas como **tarefas frias**.</span><span class="sxs-lookup"><span data-stu-id="4deba-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="4deba-147">Eles devem ser iniciados explicitamente para realmente executar.</span><span class="sxs-lookup"><span data-stu-id="4deba-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="4deba-148">Isso tem algumas vantagens, pois permite combinar e sequenciar trabalho assíncrono muito mais facilmente do que em C# ou Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4deba-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="4deba-149">Combinar Computações assíncronas</span><span class="sxs-lookup"><span data-stu-id="4deba-149">Combine asynchronous computations</span></span>

<span data-ttu-id="4deba-150">Aqui está um exemplo que se baseia no anterior combinando cálculos:</span><span class="sxs-lookup"><span data-stu-id="4deba-150">Here is an example that builds upon the previous one by combining computations:</span></span>

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
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

<span data-ttu-id="4deba-151">Como você pode ver, a `main` função tem muito mais algumas chamadas feitas.</span><span class="sxs-lookup"><span data-stu-id="4deba-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="4deba-152">Conceitualmente, ele faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4deba-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="4deba-153">Transforme os argumentos de linha de comando em `Async<unit>` cálculos com `Array.map` .</span><span class="sxs-lookup"><span data-stu-id="4deba-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="4deba-154">Crie um `Async<'T[]>` que agenda e executa os `printTotalFileBytes` cálculos em paralelo quando ele é executado.</span><span class="sxs-lookup"><span data-stu-id="4deba-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="4deba-155">Crie um `Async<unit>` que irá executar a computação paralela e ignorar seu resultado.</span><span class="sxs-lookup"><span data-stu-id="4deba-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="4deba-156">Execute explicitamente a última computação com `Async.RunSynchronously` e bloqueie até que ela seja concluída.</span><span class="sxs-lookup"><span data-stu-id="4deba-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it completes.</span></span>

<span data-ttu-id="4deba-157">Quando esse programa é executado, `printTotalFileBytes` é executado em paralelo para cada argumento de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="4deba-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="4deba-158">Como as Computações assíncronas são executadas independentemente do fluxo do programa, não há nenhuma ordem na qual elas imprimem suas informações e concluam a execução.</span><span class="sxs-lookup"><span data-stu-id="4deba-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="4deba-159">Os cálculos serão agendados em paralelo, mas a ordem de execução não será garantida.</span><span class="sxs-lookup"><span data-stu-id="4deba-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="4deba-160">Computações assíncronas de sequência</span><span class="sxs-lookup"><span data-stu-id="4deba-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="4deba-161">Como `Async<'T>` o é uma especificação de trabalho em vez de uma tarefa já em execução, você pode executar transformações mais complexas facilmente.</span><span class="sxs-lookup"><span data-stu-id="4deba-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="4deba-162">Aqui está um exemplo que sequencia um conjunto de Computações assíncronas para que eles executem um após o outro.</span><span class="sxs-lookup"><span data-stu-id="4deba-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

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
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="4deba-163">Isso agendará `printTotalFileBytes` para ser executado na ordem dos elementos em `argv` vez de agendá-los em paralelo.</span><span class="sxs-lookup"><span data-stu-id="4deba-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="4deba-164">Como o próximo item não será agendado até que a execução da última computação seja concluída, os cálculos serão seqüenciados de modo que não haja sobreposição na execução.</span><span class="sxs-lookup"><span data-stu-id="4deba-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="4deba-165">Funções de módulo assíncrono importantes</span><span class="sxs-lookup"><span data-stu-id="4deba-165">Important Async module functions</span></span>

<span data-ttu-id="4deba-166">Ao escrever código assíncrono em F #, você geralmente interage com uma estrutura que lida com o agendamento de cálculos para você.</span><span class="sxs-lookup"><span data-stu-id="4deba-166">When you write async code in F#, you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="4deba-167">No entanto, esse não é sempre o caso, portanto, é bom aprender as várias funções iniciais para agendar o trabalho assíncrono.</span><span class="sxs-lookup"><span data-stu-id="4deba-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="4deba-168">Como os cálculos assíncronos F # são uma _especificação_ de trabalho em vez de uma representação de trabalho que já está em execução, eles devem ser iniciados explicitamente com uma função inicial.</span><span class="sxs-lookup"><span data-stu-id="4deba-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="4deba-169">Há muitos [métodos de início assíncrono](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#section0) que são úteis em diferentes contextos.</span><span class="sxs-lookup"><span data-stu-id="4deba-169">There are many [Async starting methods](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#section0) that are helpful in different contexts.</span></span> <span data-ttu-id="4deba-170">A seção a seguir descreve algumas das funções iniciais mais comuns.</span><span class="sxs-lookup"><span data-stu-id="4deba-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="4deba-171">Async. StartChild</span><span class="sxs-lookup"><span data-stu-id="4deba-171">Async.StartChild</span></span>

<span data-ttu-id="4deba-172">Inicia uma computação filho em uma computação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="4deba-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="4deba-173">Isso permite que vários cálculos assíncronos sejam executados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="4deba-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="4deba-174">A computação filho compartilha um token de cancelamento com a computação pai.</span><span class="sxs-lookup"><span data-stu-id="4deba-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="4deba-175">Se o cálculo pai for cancelado, o cálculo filho também será cancelado.</span><span class="sxs-lookup"><span data-stu-id="4deba-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="4deba-176">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="4deba-176">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="4deba-177">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="4deba-177">When to use:</span></span>

- <span data-ttu-id="4deba-178">Quando você deseja executar várias Computações assíncronas simultaneamente em vez de uma de cada vez, mas elas não são agendadas em paralelo.</span><span class="sxs-lookup"><span data-stu-id="4deba-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="4deba-179">Quando você quiser vincular o tempo de vida de uma computação filho ao de um cálculo pai.</span><span class="sxs-lookup"><span data-stu-id="4deba-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="4deba-180">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="4deba-180">What to watch out for:</span></span>

- <span data-ttu-id="4deba-181">Iniciar vários cálculos com `Async.StartChild` não é o mesmo que agendá-los em paralelo.</span><span class="sxs-lookup"><span data-stu-id="4deba-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="4deba-182">Se você quiser agendar cálculos em paralelo, use `Async.Parallel` .</span><span class="sxs-lookup"><span data-stu-id="4deba-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="4deba-183">Cancelar um cálculo pai irá disparar o cancelamento de todos os cálculos filho iniciados.</span><span class="sxs-lookup"><span data-stu-id="4deba-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="4deba-184">Async. StartImmediate</span><span class="sxs-lookup"><span data-stu-id="4deba-184">Async.StartImmediate</span></span>

<span data-ttu-id="4deba-185">Executa uma computação assíncrona, começando imediatamente no thread do sistema operacional atual.</span><span class="sxs-lookup"><span data-stu-id="4deba-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="4deba-186">Isso será útil se você precisar atualizar algo no thread de chamada durante o cálculo.</span><span class="sxs-lookup"><span data-stu-id="4deba-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="4deba-187">Por exemplo, se uma computação assíncrona precisar atualizar uma interface do usuário (como atualizar uma barra de progresso), `Async.StartImmediate` deverá ser usada.</span><span class="sxs-lookup"><span data-stu-id="4deba-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="4deba-188">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="4deba-188">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="4deba-189">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="4deba-189">When to use:</span></span>

- <span data-ttu-id="4deba-190">Quando você precisa atualizar algo no thread de chamada no meio de uma computação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="4deba-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="4deba-191">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="4deba-191">What to watch out for:</span></span>

- <span data-ttu-id="4deba-192">O código na computação assíncrona será executado em qualquer thread em que ele esteja agendado.</span><span class="sxs-lookup"><span data-stu-id="4deba-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="4deba-193">Isso pode ser problemático se esse thread for, de alguma forma, confidencial, como um thread de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="4deba-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="4deba-194">Nesses casos, `Async.StartImmediate` provavelmente é inadequado usar.</span><span class="sxs-lookup"><span data-stu-id="4deba-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="4deba-195">Async. StartAsTask</span><span class="sxs-lookup"><span data-stu-id="4deba-195">Async.StartAsTask</span></span>

<span data-ttu-id="4deba-196">Executa uma computação no pool de threads.</span><span class="sxs-lookup"><span data-stu-id="4deba-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="4deba-197">Retorna um <xref:System.Threading.Tasks.Task%601> que será concluído no estado correspondente depois que o cálculo for encerrado (produz o resultado, gera uma exceção ou é cancelado).</span><span class="sxs-lookup"><span data-stu-id="4deba-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="4deba-198">Se nenhum token de cancelamento for fornecido, o token de cancelamento padrão será usado.</span><span class="sxs-lookup"><span data-stu-id="4deba-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="4deba-199">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="4deba-199">Signature:</span></span>

```fsharp
computation: Async<'T> * taskCreationOptions: ?TaskCreationOptions * cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="4deba-200">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="4deba-200">When to use:</span></span>

- <span data-ttu-id="4deba-201">Quando você precisa chamar uma API do .NET que espera um <xref:System.Threading.Tasks.Task%601> para representar o resultado de uma computação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="4deba-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="4deba-202">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="4deba-202">What to watch out for:</span></span>

- <span data-ttu-id="4deba-203">Essa chamada irá alocar um `Task` objeto adicional, o que pode aumentar a sobrecarga se for usado com frequência.</span><span class="sxs-lookup"><span data-stu-id="4deba-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="4deba-204">Async. Parallel</span><span class="sxs-lookup"><span data-stu-id="4deba-204">Async.Parallel</span></span>

<span data-ttu-id="4deba-205">Agenda uma sequência de Computações assíncronas a serem executadas em paralelo.</span><span class="sxs-lookup"><span data-stu-id="4deba-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="4deba-206">O grau de paralelismo pode ser, opcionalmente, ajustado/limitado, especificando o `maxDegreesOfParallelism` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4deba-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="4deba-207">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="4deba-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> * ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="4deba-208">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="4deba-208">When to use it:</span></span>

- <span data-ttu-id="4deba-209">Se você precisar executar um conjunto de cálculos ao mesmo tempo e não tiver nenhuma dependência em sua ordem de execução.</span><span class="sxs-lookup"><span data-stu-id="4deba-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="4deba-210">Se você não precisar de resultados de cálculos agendados em paralelo até que todos tenham sido concluídos.</span><span class="sxs-lookup"><span data-stu-id="4deba-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="4deba-211">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="4deba-211">What to watch out for:</span></span>

- <span data-ttu-id="4deba-212">Você só pode acessar a matriz resultante de valores depois que todos os cálculos forem concluídos.</span><span class="sxs-lookup"><span data-stu-id="4deba-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="4deba-213">As computações serão executadas sempre que acabarem sendo agendadas.</span><span class="sxs-lookup"><span data-stu-id="4deba-213">Computations will be run whenever they end up getting scheduled.</span></span> <span data-ttu-id="4deba-214">Esse comportamento significa que você não pode contar com a ordem de sua execução.</span><span class="sxs-lookup"><span data-stu-id="4deba-214">This behavior means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="4deba-215">Async. Sequential</span><span class="sxs-lookup"><span data-stu-id="4deba-215">Async.Sequential</span></span>

<span data-ttu-id="4deba-216">Agenda uma sequência de Computações assíncronas a serem executadas na ordem em que são passadas.</span><span class="sxs-lookup"><span data-stu-id="4deba-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="4deba-217">O primeiro cálculo será executado e, em seguida, o próximo e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="4deba-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="4deba-218">Nenhum cálculo será executado em paralelo.</span><span class="sxs-lookup"><span data-stu-id="4deba-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="4deba-219">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="4deba-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="4deba-220">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="4deba-220">When to use it:</span></span>

- <span data-ttu-id="4deba-221">Se você precisar executar vários cálculos na ordem.</span><span class="sxs-lookup"><span data-stu-id="4deba-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="4deba-222">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="4deba-222">What to watch out for:</span></span>

- <span data-ttu-id="4deba-223">Você só pode acessar a matriz resultante de valores depois que todos os cálculos forem concluídos.</span><span class="sxs-lookup"><span data-stu-id="4deba-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="4deba-224">As computações serão executadas na ordem em que são passadas para essa função, o que pode significar que mais tempo decorrerá antes que os resultados sejam retornados.</span><span class="sxs-lookup"><span data-stu-id="4deba-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="4deba-225">Async. AwaitTask</span><span class="sxs-lookup"><span data-stu-id="4deba-225">Async.AwaitTask</span></span>

<span data-ttu-id="4deba-226">Retorna uma computação assíncrona que aguarda o determinado <xref:System.Threading.Tasks.Task%601> a ser concluído e retorna seu resultado como um `Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="4deba-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="4deba-227">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="4deba-227">Signature:</span></span>

```fsharp
task: Task<'T> -> Async<'T>
```

<span data-ttu-id="4deba-228">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="4deba-228">When to use:</span></span>

- <span data-ttu-id="4deba-229">Quando você está consumindo uma API do .NET que retorna um <xref:System.Threading.Tasks.Task%601> dentro de uma computação assíncrona em F #.</span><span class="sxs-lookup"><span data-stu-id="4deba-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="4deba-230">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="4deba-230">What to watch out for:</span></span>

- <span data-ttu-id="4deba-231">As exceções são encapsuladas em <xref:System.AggregateException> seguindo a Convenção da biblioteca de tarefas paralelas, e esse comportamento é diferente de como a F # Async geralmente faz a superfície de exceções.</span><span class="sxs-lookup"><span data-stu-id="4deba-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this behavior is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="4deba-232">Async. catch</span><span class="sxs-lookup"><span data-stu-id="4deba-232">Async.Catch</span></span>

<span data-ttu-id="4deba-233">Cria uma computação assíncrona que executa um determinado `Async<'T>` , retornando um `Async<Choice<'T, exn>>` .</span><span class="sxs-lookup"><span data-stu-id="4deba-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="4deba-234">Se o determinado for `Async<'T>` concluído com êxito, um `Choice1Of2` será retornado com o valor resultante.</span><span class="sxs-lookup"><span data-stu-id="4deba-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="4deba-235">Se uma exceção for lançada antes de ser concluída, um `Choice2of2` será retornado com a exceção gerada.</span><span class="sxs-lookup"><span data-stu-id="4deba-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="4deba-236">Se ele for usado em uma computação assíncrona que, por sua vez, é composto por muitos cálculos, e um desses cálculos gera uma exceção, a computação que englobará o cálculo será totalmente interrompida.</span><span class="sxs-lookup"><span data-stu-id="4deba-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="4deba-237">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="4deba-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="4deba-238">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="4deba-238">When to use:</span></span>

- <span data-ttu-id="4deba-239">Quando você estiver executando um trabalho assíncrono que pode falhar com uma exceção e você deseja tratar essa exceção no chamador.</span><span class="sxs-lookup"><span data-stu-id="4deba-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="4deba-240">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="4deba-240">What to watch out for:</span></span>

- <span data-ttu-id="4deba-241">Ao usar Computações assíncronas combinadas ou sequenciadas, a computação abrangerá completamente se um de seus cálculos "internos" gerar uma exceção.</span><span class="sxs-lookup"><span data-stu-id="4deba-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="4deba-242">Async. ignore</span><span class="sxs-lookup"><span data-stu-id="4deba-242">Async.Ignore</span></span>

<span data-ttu-id="4deba-243">Cria uma computação assíncrona que executa a computação específica e ignora seu resultado.</span><span class="sxs-lookup"><span data-stu-id="4deba-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="4deba-244">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="4deba-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="4deba-245">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="4deba-245">When to use:</span></span>

- <span data-ttu-id="4deba-246">Quando você tem uma computação assíncrona cujo resultado não é necessário.</span><span class="sxs-lookup"><span data-stu-id="4deba-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="4deba-247">Isso é análogo ao `ignore` código para código não assíncrono.</span><span class="sxs-lookup"><span data-stu-id="4deba-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="4deba-248">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="4deba-248">What to watch out for:</span></span>

- <span data-ttu-id="4deba-249">Se você precisar usar `Async.Ignore` o porque deseja usar `Async.Start` ou outra função que exija `Async<unit>` o, considere se descartar o resultado está ok.</span><span class="sxs-lookup"><span data-stu-id="4deba-249">If you must use `Async.Ignore` because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay.</span></span> <span data-ttu-id="4deba-250">Evite descartar os resultados apenas para se ajustar a uma assinatura de tipo.</span><span class="sxs-lookup"><span data-stu-id="4deba-250">Avoid discarding results just to fit a type signature.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="4deba-251">Async. RunSynchronously</span><span class="sxs-lookup"><span data-stu-id="4deba-251">Async.RunSynchronously</span></span>

<span data-ttu-id="4deba-252">Executa uma computação assíncrona e aguarda seu resultado no thread de chamada.</span><span class="sxs-lookup"><span data-stu-id="4deba-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="4deba-253">Esta chamada está bloqueando.</span><span class="sxs-lookup"><span data-stu-id="4deba-253">This call is blocking.</span></span>

<span data-ttu-id="4deba-254">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="4deba-254">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int * cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="4deba-255">Quando usar:</span><span class="sxs-lookup"><span data-stu-id="4deba-255">When to use it:</span></span>

- <span data-ttu-id="4deba-256">Se você precisar dele, use-o apenas uma vez em um aplicativo-no ponto de entrada para um executável.</span><span class="sxs-lookup"><span data-stu-id="4deba-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="4deba-257">Quando você não se importa com o desempenho e deseja executar um conjunto de outras operações assíncronas de uma vez.</span><span class="sxs-lookup"><span data-stu-id="4deba-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="4deba-258">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="4deba-258">What to watch out for:</span></span>

- <span data-ttu-id="4deba-259">A chamada `Async.RunSynchronously` bloqueia o thread de chamada até que a execução seja concluída.</span><span class="sxs-lookup"><span data-stu-id="4deba-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="4deba-260">Async. Start</span><span class="sxs-lookup"><span data-stu-id="4deba-260">Async.Start</span></span>

<span data-ttu-id="4deba-261">Inicia uma computação assíncrona no pool de threads que o retorna `unit` .</span><span class="sxs-lookup"><span data-stu-id="4deba-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="4deba-262">Não aguarda seu resultado.</span><span class="sxs-lookup"><span data-stu-id="4deba-262">Doesn't wait for its result.</span></span> <span data-ttu-id="4deba-263">Cálculos aninhados iniciados com `Async.Start` são iniciados independentemente do cálculo pai que os chamou.</span><span class="sxs-lookup"><span data-stu-id="4deba-263">Nested computations started with `Async.Start` are started independently of the parent computation that called them.</span></span> <span data-ttu-id="4deba-264">Seu tempo de vida não está vinculado a nenhum cálculo pai.</span><span class="sxs-lookup"><span data-stu-id="4deba-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="4deba-265">Se o cálculo pai for cancelado, nenhum cálculo filho será cancelado.</span><span class="sxs-lookup"><span data-stu-id="4deba-265">If the parent computation is canceled, no child computations are canceled.</span></span>

<span data-ttu-id="4deba-266">Assinatura:</span><span class="sxs-lookup"><span data-stu-id="4deba-266">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="4deba-267">Use somente quando:</span><span class="sxs-lookup"><span data-stu-id="4deba-267">Use only when:</span></span>

- <span data-ttu-id="4deba-268">Você tem uma computação assíncrona que não produz um resultado e/ou requer o processamento de um.</span><span class="sxs-lookup"><span data-stu-id="4deba-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="4deba-269">Você não precisa saber quando uma computação assíncrona é concluída.</span><span class="sxs-lookup"><span data-stu-id="4deba-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="4deba-270">Você não se importa com o thread em que uma computação assíncrona é executada.</span><span class="sxs-lookup"><span data-stu-id="4deba-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="4deba-271">Você não precisa estar atento ou relatar exceções resultantes da tarefa.</span><span class="sxs-lookup"><span data-stu-id="4deba-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="4deba-272">O que deve ser observado:</span><span class="sxs-lookup"><span data-stu-id="4deba-272">What to watch out for:</span></span>

- <span data-ttu-id="4deba-273">Exceções geradas por computações iniciadas com `Async.Start` não são propagadas para o chamador.</span><span class="sxs-lookup"><span data-stu-id="4deba-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="4deba-274">A pilha de chamadas será completamente desbobinada.</span><span class="sxs-lookup"><span data-stu-id="4deba-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="4deba-275">Qualquer trabalho (como chamada `printfn` ) iniciado com `Async.Start` não fará com que o efeito aconteça no thread principal da execução de um programa.</span><span class="sxs-lookup"><span data-stu-id="4deba-275">Any work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="4deba-276">Interoperar com o .NET</span><span class="sxs-lookup"><span data-stu-id="4deba-276">Interoperate with .NET</span></span>

<span data-ttu-id="4deba-277">Você pode estar trabalhando com uma biblioteca .NET ou codebase C# que usa programação assíncrona de estilo [Async/Await](../../../standard/async.md).</span><span class="sxs-lookup"><span data-stu-id="4deba-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="4deba-278">Como o C# e a maioria das bibliotecas do .NET usam os <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task> tipos e como suas abstrações principais em vez de `Async<'T>` , você deve cruzar um limite entre essas duas abordagens para assincronia.</span><span class="sxs-lookup"><span data-stu-id="4deba-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="4deba-279">Como trabalhar com o .NET Async e `Task<T>`</span><span class="sxs-lookup"><span data-stu-id="4deba-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="4deba-280">Trabalhar com bibliotecas assíncronas .NET e bases de código que usam <xref:System.Threading.Tasks.Task%601> (ou seja, Computações assíncronas com valores de retorno) é simples e tem suporte interno com F #.</span><span class="sxs-lookup"><span data-stu-id="4deba-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="4deba-281">Você pode usar a `Async.AwaitTask` função para aguardar uma computação assíncrona do .net:</span><span class="sxs-lookup"><span data-stu-id="4deba-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="4deba-282">Você pode usar a `Async.StartAsTask` função para passar uma computação assíncrona para um chamador do .net:</span><span class="sxs-lookup"><span data-stu-id="4deba-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="4deba-283">Como trabalhar com o .NET Async e `Task`</span><span class="sxs-lookup"><span data-stu-id="4deba-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="4deba-284">Para trabalhar com APIs que usam <xref:System.Threading.Tasks.Task> (ou seja, Computações assíncronas do .NET que não retornam um valor), talvez seja necessário adicionar uma função adicional que converterá um `Async<'T>` para um <xref:System.Threading.Tasks.Task> :</span><span class="sxs-lookup"><span data-stu-id="4deba-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="4deba-285">Já existe um `Async.AwaitTask` que aceita uma <xref:System.Threading.Tasks.Task> entrada as.</span><span class="sxs-lookup"><span data-stu-id="4deba-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="4deba-286">Com isso e a função definida anteriormente `startTaskFromAsyncUnit` , você pode iniciar e esperar <xref:System.Threading.Tasks.Task> tipos de uma computação Async de F #.</span><span class="sxs-lookup"><span data-stu-id="4deba-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="4deba-287">Relação com multithreading</span><span class="sxs-lookup"><span data-stu-id="4deba-287">Relationship to multi-threading</span></span>

<span data-ttu-id="4deba-288">Embora o Threading seja mencionado em todo este artigo, há duas coisas importantes a serem lembradas:</span><span class="sxs-lookup"><span data-stu-id="4deba-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="4deba-289">Não há afinidade entre uma computação assíncrona e um thread, a menos que seja explicitamente iniciado no thread atual.</span><span class="sxs-lookup"><span data-stu-id="4deba-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="4deba-290">A programação assíncrona em F # não é uma abstração para multithreading.</span><span class="sxs-lookup"><span data-stu-id="4deba-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="4deba-291">Por exemplo, uma computação pode ser realmente executada no thread do chamador, dependendo da natureza do trabalho.</span><span class="sxs-lookup"><span data-stu-id="4deba-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="4deba-292">Uma computação também poderia "saltar" entre threads, emprestando-os por um pequeno tempo para fazer um trabalho útil entre períodos de "espera" (como quando uma chamada de rede está em trânsito).</span><span class="sxs-lookup"><span data-stu-id="4deba-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="4deba-293">Embora o F # forneça algumas capacidades para iniciar uma computação assíncrona no thread atual (ou não explicitamente no thread atual), a assincronia geralmente não está associada a uma estratégia de Threading específica.</span><span class="sxs-lookup"><span data-stu-id="4deba-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="4deba-294">Confira também</span><span class="sxs-lookup"><span data-stu-id="4deba-294">See also</span></span>

- [<span data-ttu-id="4deba-295">O modelo de programação assíncrona F #</span><span class="sxs-lookup"><span data-stu-id="4deba-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="4deba-296">Guia assíncrono F # do Jet. com</span><span class="sxs-lookup"><span data-stu-id="4deba-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="4deba-297">F # para o guia de programação assíncrona de lucros e diversão</span><span class="sxs-lookup"><span data-stu-id="4deba-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="4deba-298">Async em C# e F #: armadilhas assíncronas em C #</span><span class="sxs-lookup"><span data-stu-id="4deba-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
