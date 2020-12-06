---
title: Eventos
description: 'Saiba como os eventos F # permitem associar chamadas de função a ações do usuário, que são importantes na programação de GUI.'
ms.date: 08/15/2020
ms.openlocfilehash: 17e0cc8840053bf24d5c69694fe94d544c44510d
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740335"
---
# <a name="events"></a><span data-ttu-id="cd6c4-103">Eventos</span><span class="sxs-lookup"><span data-stu-id="cd6c4-103">Events</span></span>

<span data-ttu-id="cd6c4-104">Eventos permitem que você associe chamadas de função a ações de usuário e são importantes na programação da GUI.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-104">Events enable you to associate function calls with user actions and are important in GUI programming.</span></span> <span data-ttu-id="cd6c4-105">Os eventos também podem ser disparados por seus aplicativos ou pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-105">Events can also be triggered by your applications or by the operating system.</span></span>

## <a name="handling-events"></a><span data-ttu-id="cd6c4-106">Tratando eventos</span><span class="sxs-lookup"><span data-stu-id="cd6c4-106">Handling Events</span></span>

<span data-ttu-id="cd6c4-107">Quando você usa uma biblioteca de GUI como o Windows Forms ou o Windows Presentation Foundation (WPF), grande parte do código em seu aplicativo é executado em resposta a eventos que são predefinidos pela biblioteca.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-107">When you use a GUI library like Windows Forms or Windows Presentation Foundation (WPF), much of the code in your application runs in response to events that are predefined by the library.</span></span> <span data-ttu-id="cd6c4-108">Esses eventos predefinidos são membros de classes da GUI como formulários e controles.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-108">These predefined events are members of GUI classes such as forms and controls.</span></span> <span data-ttu-id="cd6c4-109">Você pode adicionar comportamento personalizado a um evento preexistente, como o clique de botão, ao fazer referência ao evento de interesse nomeado específico (por exemplo, o evento `Click` da classe `Form`) e invocar o método `Add` como mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-109">You can add custom behavior to a preexisting event, such as a button click, by referencing the specific named event of interest (for example, the `Click` event of the `Form` class) and invoking the `Add` method, as shown in the following code.</span></span> <span data-ttu-id="cd6c4-110">Se você executar isso do F# Interativo, omita a chamada a `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-110">If you run this from F# Interactive, omit the call to `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

<span data-ttu-id="cd6c4-111">O tipo do método `Add` é `('a -> unit) -> unit`.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-111">The type of the `Add` method is `('a -> unit) -> unit`.</span></span> <span data-ttu-id="cd6c4-112">Portanto, o método do manipulador de eventos assume um parâmetro, normalmente os argumentos de evento, e retorna `unit`.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-112">Therefore, the event handler method takes one parameter, typically the event arguments, and returns `unit`.</span></span> <span data-ttu-id="cd6c4-113">O exemplo anterior mostra o manipulador de eventos como uma expressão lambda.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-113">The previous example shows the event handler as a lambda expression.</span></span> <span data-ttu-id="cd6c4-114">O manipulador de eventos também pode ser um valor de função como no exemplo de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-114">The event handler can also be a function value, as in the following code example.</span></span> <span data-ttu-id="cd6c4-115">O exemplo de código a seguir também mostra o uso de parâmetros do manipulador de eventos que fornecem informações específicas para o tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-115">The following code example also shows the use of the event handler parameters, which provide information specific to the type of event.</span></span> <span data-ttu-id="cd6c4-116">Para um evento `MouseMove`, o sistema passa um objeto `System.Windows.Forms.MouseEventArgs` que contém a posição `X` e `Y` do ponteiro.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-116">For a `MouseMove` event, the system passes a `System.Windows.Forms.MouseEventArgs` object, which contains the `X` and `Y` position of the pointer.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]

## <a name="creating-custom-events"></a><span data-ttu-id="cd6c4-117">Criando eventos personalizados</span><span class="sxs-lookup"><span data-stu-id="cd6c4-117">Creating Custom Events</span></span>

<span data-ttu-id="cd6c4-118">Os eventos f # são representados pelo tipo de [evento](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html) f #, que implementa a interface [IEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-ievent-1.html) .</span><span class="sxs-lookup"><span data-stu-id="cd6c4-118">F# events are represented by the F# [Event](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html) type, which implements the [IEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-ievent-1.html) interface.</span></span> <span data-ttu-id="cd6c4-119">`IEvent` é uma interface que combina a funcionalidade de duas outras interfaces `System.IObservable<'T>` e [IDelegateEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-idelegateevent-1.html).</span><span class="sxs-lookup"><span data-stu-id="cd6c4-119">`IEvent` is itself an interface that combines the functionality of two other interfaces, `System.IObservable<'T>` and [IDelegateEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-idelegateevent-1.html).</span></span> <span data-ttu-id="cd6c4-120">Portanto, `Event`s têm funcionalidade equivalente de delegados em outras linguagens, além da funcionalidade adicional de `IObservable` o que significa que os eventos de F# oferecem suporte à filtragem de eventos e ao uso de funções de primeira classe de F# e expressões lambda como manipuladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-120">Therefore, `Event`s have the equivalent functionality of delegates in other languages, plus the additional functionality from `IObservable`, which means that F# events support event filtering and using F# first-class functions and lambda expressions as event handlers.</span></span> <span data-ttu-id="cd6c4-121">Essa funcionalidade é fornecida no [módulo de evento](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html).</span><span class="sxs-lookup"><span data-stu-id="cd6c4-121">This functionality is provided in the [Event module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html).</span></span>

<span data-ttu-id="cd6c4-122">Para criar um evento em uma classe que atue como qualquer outro evento do .NET Framework, adicione à classe uma associação `let` que defina um `Event` como um campo em uma classe.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-122">To create an event on a class that acts just like any other .NET Framework event, add to the class a `let` binding that defines an `Event` as a field in a class.</span></span> <span data-ttu-id="cd6c4-123">Você pode especificar o tipo de argumento de evento desejado como o argumento de tipo ou deixá-lo em branco e fazer com que o compilador deduza o tipo apropriado.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-123">You can specify the desired event argument type as the type argument, or leave it blank and have the compiler infer the appropriate type.</span></span> <span data-ttu-id="cd6c4-124">Você também deve definir um membro de evento que exponha o evento como um evento de CLI.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-124">You also must define an event member that exposes the event as a CLI event.</span></span> <span data-ttu-id="cd6c4-125">Esse membro deve ter o atributo [CLIEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-clieventattribute.html) .</span><span class="sxs-lookup"><span data-stu-id="cd6c4-125">This member should have the [CLIEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-clieventattribute.html) attribute.</span></span> <span data-ttu-id="cd6c4-126">Ele é declarado como uma propriedade e sua implementação é apenas uma chamada para a propriedade [Publish](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html#Publish) do evento.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-126">It is declared like a property and its implementation is just a call to the [Publish](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html#Publish) property of the event.</span></span> <span data-ttu-id="cd6c4-127">Os usuários de sua classe podem usar o método `Add` do evento publicado para adicionar um manipulador.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-127">Users of your class can use the `Add` method of the published event to add a handler.</span></span> <span data-ttu-id="cd6c4-128">O argumento para o método `Add` pode ser uma expressão lambda.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-128">The argument for the `Add` method can be a lambda expression.</span></span> <span data-ttu-id="cd6c4-129">Você pode usar a propriedade `Trigger` do evento para gerar o evento, passando os argumentos à função do manipulador.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-129">You can use the `Trigger` property of the event to raise the event, passing the arguments to the handler function.</span></span> <span data-ttu-id="cd6c4-130">O exemplo de código a seguir ilustra isso.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-130">The following code example illustrates this.</span></span> <span data-ttu-id="cd6c4-131">Neste exemplo, o argumento do tipo inferido para o evento é uma tupla que representa os argumentos para a expressão lambda.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-131">In this example, the inferred type argument for the event is a tuple, which represents the arguments for the lambda expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

<span data-ttu-id="cd6c4-132">A saída é a seguinte.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-132">The output is as follows.</span></span>

```console
Event1 occurred! Object data: Hello World!
```

<span data-ttu-id="cd6c4-133">A funcionalidade adicional fornecida pelo módulo `Event` está ilustrada aqui.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-133">The additional functionality provided by the `Event` module is illustrated here.</span></span> <span data-ttu-id="cd6c4-134">O exemplo de código a seguir ilustra o uso básico de `Event.create` para criar um evento e um método de gatilho, adicionar dois manipuladores de eventos na forma de expressões lambda e disparar o evento para executar ambas as expressões lambda.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-134">The following code example illustrates the basic use of `Event.create` to create an event and a trigger method, add two event handlers in the form of lambda expressions, and then trigger the event to execute both lambda expressions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

<span data-ttu-id="cd6c4-135">A saída do código anterior está a seguir.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-135">The output of the previous code is as follows.</span></span>

```console
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a><span data-ttu-id="cd6c4-136">Processando fluxos de eventos</span><span class="sxs-lookup"><span data-stu-id="cd6c4-136">Processing Event Streams</span></span>

<span data-ttu-id="cd6c4-137">Em vez de apenas adicionar um manipulador de eventos para um evento usando a função [evento. Add](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html#add) , você pode usar as funções no `Event` módulo para processar fluxos de eventos de maneiras altamente personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-137">Instead of just adding an event handler for an event by using the [Event.add](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html#add) function, you can use the functions in the `Event` module to process streams of events in highly customized ways.</span></span> <span data-ttu-id="cd6c4-138">Para fazer isso, use a barra vertical e o sinal maior que (`|>`) junto com o evento como o primeiro valor em uma série de chamadas de função e funções do módulo `Event` como chamadas de função subsequentes.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-138">To do this, you use the forward pipe (`|>`) together with the event as the first value in a series of function calls, and the `Event` module functions as subsequent function calls.</span></span>

<span data-ttu-id="cd6c4-139">O exemplo de código a seguir mostra como configurar um evento em que o manipulador é chamado apenas em determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-139">The following code example shows how to set up an event for which the handler is only called under certain conditions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

<span data-ttu-id="cd6c4-140">O [módulo observável](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-observablemodule.html) contém funções semelhantes que operam em objetos observáveis.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-140">The [Observable module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-observablemodule.html) contains similar functions that operate on observable objects.</span></span> <span data-ttu-id="cd6c4-141">Objetos observáveis são semelhantes a eventos, mas apenas assinam eventos ativamente se eles mesmos estiverem sendo assinados.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-141">Observable objects are similar to events but only actively subscribe to events if they themselves are being subscribed to.</span></span>

## <a name="implementing-an-interface-event"></a><span data-ttu-id="cd6c4-142">Implementando um evento de interface</span><span class="sxs-lookup"><span data-stu-id="cd6c4-142">Implementing an Interface Event</span></span>

<span data-ttu-id="cd6c4-143">À medida em que desenvolve componentes de interface do usuário, você frequentemente começa ao criar um novo formulário ou um novo controle que herde de um formulário ou controle existente.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-143">As you develop UI components, you often start by creating a new form or a new control that inherits from an existing form or control.</span></span> <span data-ttu-id="cd6c4-144">Eventos são frequentemente definidos em uma interface e, nesse caso, você deve implementar a interface para implementar o evento.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-144">Events are frequently defined on an interface, and, in that case, you must implement the interface to implement the event.</span></span> <span data-ttu-id="cd6c4-145">A interface `System.ComponentModel.INotifyPropertyChanged` define um único evento `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`.</span><span class="sxs-lookup"><span data-stu-id="cd6c4-145">The `System.ComponentModel.INotifyPropertyChanged` interface defines a single `System.ComponentModel.INotifyPropertyChanged.PropertyChanged` event.</span></span> <span data-ttu-id="cd6c4-146">O código a seguir ilustra como implementar o evento que essa interface herdada definiu:</span><span class="sxs-lookup"><span data-stu-id="cd6c4-146">The following code illustrates how to implement the event that this inherited interface defined:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

type AppForm() as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
            this.Property2 <- "text3")

    // This property does not have the property-changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property-changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    // Expose the PropertyChanged event as a first class .NET event.
    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = propertyChanged.Publish.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = propertyChanged.Publish.RemoveHandler(handler)

    // This is the event-handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property {args.PropertyName} changed its value to {newValue}"

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
let inpc = appForm :> INotifyPropertyChanged
inpc.PropertyChanged.Add(appForm.OnPropertyChanged)
Application.Run(appForm)
```

<span data-ttu-id="cd6c4-147">Se você desejar conectar o evento no construtor, o código será um pouco mais complicado porque a conexão do evento deverá estar em um bloco `then` em um construtor adicional como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="cd6c4-147">If you want to hook up the event in the constructor, the code is a bit more complicated because the event hookup must be in a `then` block in an additional constructor, as in the following example:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

// Create a private constructor with a dummy argument so that the public
// constructor can have no arguments.
type AppForm private (dummy) as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
            this.Property2 <- "text3")

    // This property does not have the property changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = this.PropertyChanged.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = this.PropertyChanged.RemoveHandler(handler)

    // This is the event handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property {args.PropertyName} changed its value to {newValue}"

    new() as this =
        new AppForm(0)
        then
            let inpc = this :> INotifyPropertyChanged
            inpc.PropertyChanged.Add(this.OnPropertyChanged)

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
Application.Run(appForm)
```

## <a name="see-also"></a><span data-ttu-id="cd6c4-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="cd6c4-148">See also</span></span>

- [<span data-ttu-id="cd6c4-149">Membros</span><span class="sxs-lookup"><span data-stu-id="cd6c4-149">Members</span></span>](index.md)
- [<span data-ttu-id="cd6c4-150">Manipulando e acionando eventos</span><span class="sxs-lookup"><span data-stu-id="cd6c4-150">Handling and Raising Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="cd6c4-151">Expressões lambda: a `fun` palavra-chave</span><span class="sxs-lookup"><span data-stu-id="cd6c4-151">Lambda Expressions: The `fun` Keyword</span></span>](../functions/lambda-expressions-the-fun-keyword.md)
