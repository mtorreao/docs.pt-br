---
title: 'Introdução ao F # no Visual Studio para Mac'
description: 'Saiba como usar F # com Visual Studio para Mac.'
ms.date: 07/03/2018
ms.openlocfilehash: d2ad24ad18bb31419b39508f2cf555c82fbe2e0b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437997"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="71dc7-103">Introdução ao F # no Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="71dc7-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="71dc7-104">O F # e as ferramentas de Visual F# têm suporte no IDE do Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="71dc7-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="71dc7-105">Verifique se você tem [Visual Studio para Mac instalado](install-fsharp.md#install-f-with-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="71dc7-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="71dc7-106">Criando um aplicativo de console</span><span class="sxs-lookup"><span data-stu-id="71dc7-106">Creating a console application</span></span>

<span data-ttu-id="71dc7-107">Um dos projetos mais básicos no Visual Studio para Mac é o aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="71dc7-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="71dc7-108">Veja como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="71dc7-108">Here's how to do it.</span></span>  <span data-ttu-id="71dc7-109">Quando Visual Studio para Mac estiver aberto:</span><span class="sxs-lookup"><span data-stu-id="71dc7-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="71dc7-110">No menu **arquivo** , aponte para **nova solução**.</span><span class="sxs-lookup"><span data-stu-id="71dc7-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="71dc7-111">Na caixa de diálogo novo projeto, há dois modelos diferentes para o aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="71dc7-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="71dc7-112">Há um em outro-> .NET que tem como alvo o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="71dc7-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="71dc7-113">O outro modelo está em .NET Core – > aplicativo que tem como alvo o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="71dc7-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="71dc7-114">O modelo deve funcionar para a finalidade deste artigo.</span><span class="sxs-lookup"><span data-stu-id="71dc7-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="71dc7-115">Em aplicativo de console, altere C# para F # se necessário.</span><span class="sxs-lookup"><span data-stu-id="71dc7-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="71dc7-116">Escolha o botão **Avançar** para prosseguir!</span><span class="sxs-lookup"><span data-stu-id="71dc7-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="71dc7-117">Dê um nome ao projeto e escolha as opções desejadas para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="71dc7-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="71dc7-118">Observe, no painel de visualização, o lado da tela que mostrará a estrutura de diretório que será criada com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="71dc7-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="71dc7-119">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="71dc7-119">Click **Create**.</span></span>  <span data-ttu-id="71dc7-120">Agora você deve ver um projeto F # na Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="71dc7-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="71dc7-121">Escrevendo seu código</span><span class="sxs-lookup"><span data-stu-id="71dc7-121">Writing your code</span></span>

<span data-ttu-id="71dc7-122">Vamos começar escrevendo um pouco de código primeiro.</span><span class="sxs-lookup"><span data-stu-id="71dc7-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="71dc7-123">Verifique se o `Program.fs` arquivo está aberto e, em seguida, substitua seu conteúdo pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="71dc7-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="71dc7-124">No exemplo de código anterior, `square` foi definida uma função que recebe uma entrada chamada `x` e a multiplica por si só.</span><span class="sxs-lookup"><span data-stu-id="71dc7-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="71dc7-125">Como o F # usa a [inferência de tipos](../language-reference/type-inference.md), o tipo de `x` não precisa ser especificado.</span><span class="sxs-lookup"><span data-stu-id="71dc7-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="71dc7-126">O compilador F # compreende os tipos em que a multiplicação é válida e atribuirá um tipo a `x` com base em como `square` é chamado.</span><span class="sxs-lookup"><span data-stu-id="71dc7-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="71dc7-127">Se você passar `square` o mouse, verá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="71dc7-127">If you hover over `square`, you should see the following:</span></span>

```console
val square: x:int -> int
```

<span data-ttu-id="71dc7-128">Isso é o que é conhecido como assinatura do tipo da função.</span><span class="sxs-lookup"><span data-stu-id="71dc7-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="71dc7-129">Ele pode ser lido da seguinte maneira: "Square é uma função que recebe um inteiro chamado x e produz um inteiro".</span><span class="sxs-lookup"><span data-stu-id="71dc7-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="71dc7-130">Observe que o compilador define por hora o tipo do `square` como `int` – isso ocorre porque a multiplicação não é genérica em *todos os* tipos, mas sim em um conjunto fechado de tipos.</span><span class="sxs-lookup"><span data-stu-id="71dc7-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="71dc7-131">O compilador do F# escolheu `int` neste caso, mas ajustará a assinatura de tipo se você chamar `square` com um tipo de entrada diferente, como um `float`.</span><span class="sxs-lookup"><span data-stu-id="71dc7-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="71dc7-132">Outra função, `main` , é definida, que é decorada com o `EntryPoint` atributo para informar ao compilador F # que a execução do programa deve iniciar lá.</span><span class="sxs-lookup"><span data-stu-id="71dc7-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="71dc7-133">Ele segue a mesma convenção que outras [linguagens de programação em estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), em que argumentos de linha de comando podem ser passados para essa função e um código inteiro é retornado (normalmente `0` ).</span><span class="sxs-lookup"><span data-stu-id="71dc7-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="71dc7-134">É nessa função que chamamos a `square` função com um argumento de `12` .</span><span class="sxs-lookup"><span data-stu-id="71dc7-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="71dc7-135">Em seguida, o compilador F # atribui o tipo de `square` a `int -> int` (ou seja, uma função que usa um `int` e produz um `int` ).</span><span class="sxs-lookup"><span data-stu-id="71dc7-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="71dc7-136">A chamada para `printfn` é uma função de impressão formatada que usa uma cadeia de caracteres de formato, semelhante a linguagens de programação em estilo C, parâmetros que correspondem àquelas especificadas na cadeia de caracteres de formato e, em seguida, imprime o resultado e uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="71dc7-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="71dc7-137">Como executar código</span><span class="sxs-lookup"><span data-stu-id="71dc7-137">Running your code</span></span>

<span data-ttu-id="71dc7-138">Você pode executar o código e ver os resultados clicando em **executar** no menu de nível superior e, em seguida, **Iniciar sem depuração**.</span><span class="sxs-lookup"><span data-stu-id="71dc7-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="71dc7-139">Isso executará o programa sem depuração e permitirá que você veja os resultados.</span><span class="sxs-lookup"><span data-stu-id="71dc7-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="71dc7-140">Agora você deve ver o seguinte impresso na janela do console que Visual Studio para Mac exibida:</span><span class="sxs-lookup"><span data-stu-id="71dc7-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="71dc7-141">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="71dc7-141">Congratulations!</span></span>  <span data-ttu-id="71dc7-142">Você criou seu primeiro projeto em F # no Visual Studio para Mac, escreveu uma função F # imprimiu os resultados da chamada dessa função e executa o projeto para ver alguns resultados.</span><span class="sxs-lookup"><span data-stu-id="71dc7-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="71dc7-143">Usando F# Interativo</span><span class="sxs-lookup"><span data-stu-id="71dc7-143">Using F# Interactive</span></span>

<span data-ttu-id="71dc7-144">Um dos melhores recursos das ferramentas de Visual F# no Visual Studio para Mac é a janela F# Interativo.</span><span class="sxs-lookup"><span data-stu-id="71dc7-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="71dc7-145">Ele permite que você envie código para um processo no qual você pode chamar esse código e ver o resultado interativamente.</span><span class="sxs-lookup"><span data-stu-id="71dc7-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="71dc7-146">Para começar a usá-lo, realce a `square` função definida em seu código.</span><span class="sxs-lookup"><span data-stu-id="71dc7-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="71dc7-147">Em seguida, clique em **Editar** no menu de nível superior.</span><span class="sxs-lookup"><span data-stu-id="71dc7-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="71dc7-148">Em seguida, selecione **Enviar seleção para F# interativo**.</span><span class="sxs-lookup"><span data-stu-id="71dc7-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="71dc7-149">Isso executa o código na janela de F# Interativo.</span><span class="sxs-lookup"><span data-stu-id="71dc7-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="71dc7-150">Como alternativa, você pode clicar com o botão direito do mouse na seleção e escolher **Enviar seleção para F# interativo**.</span><span class="sxs-lookup"><span data-stu-id="71dc7-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="71dc7-151">Você deve ver a janela F# Interativo aparecer com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="71dc7-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```console
>

val square : x:int -> int

>
```

<span data-ttu-id="71dc7-152">Isso mostra a mesma assinatura de função para a `square` função, que você viu anteriormente ao passar o mouse sobre a função.</span><span class="sxs-lookup"><span data-stu-id="71dc7-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="71dc7-153">Como `square` agora está definido no processo de F# interativo, você pode chamá-lo com valores diferentes:</span><span class="sxs-lookup"><span data-stu-id="71dc7-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="71dc7-154">Isso executa a função, associa o resultado a um novo nome `it` e exibe o tipo e o valor de `it` .</span><span class="sxs-lookup"><span data-stu-id="71dc7-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="71dc7-155">Observe que você deve encerrar cada linha com `;;` .</span><span class="sxs-lookup"><span data-stu-id="71dc7-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="71dc7-156">É assim que F# Interativo sabe quando sua chamada de função é concluída.</span><span class="sxs-lookup"><span data-stu-id="71dc7-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="71dc7-157">Você também pode definir novas funções no F# Interativo:</span><span class="sxs-lookup"><span data-stu-id="71dc7-157">You can also define new functions in F# Interactive:</span></span>

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="71dc7-158">O acima define uma nova função, `isOdd` , que usa um `int` e verifica se ele é estranho!</span><span class="sxs-lookup"><span data-stu-id="71dc7-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="71dc7-159">Você pode chamar essa função para ver o que ela retorna com entradas diferentes.</span><span class="sxs-lookup"><span data-stu-id="71dc7-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="71dc7-160">Você pode chamar funções em chamadas de função:</span><span class="sxs-lookup"><span data-stu-id="71dc7-160">You can call functions within function calls:</span></span>

```console
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="71dc7-161">Você também pode usar o [operador de encaminhamento de pipe](../language-reference/symbol-and-operator-reference/index.md) para canalizar o valor nas duas funções:</span><span class="sxs-lookup"><span data-stu-id="71dc7-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="71dc7-162">O operador de encaminhamento de pipe e muito mais, são abordados em Tutoriais posteriores.</span><span class="sxs-lookup"><span data-stu-id="71dc7-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="71dc7-163">Isso é apenas uma visão do que você pode fazer com F# Interativo.</span><span class="sxs-lookup"><span data-stu-id="71dc7-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="71dc7-164">Para saber mais, confira [programação interativa com F #](../tools/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="71dc7-164">To learn more, check out [Interactive Programming with F#](../tools/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="71dc7-165">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="71dc7-165">Next steps</span></span>

<span data-ttu-id="71dc7-166">Se você ainda não fez isso, confira o [Tour do f #](../tour.md), que aborda alguns dos principais recursos da linguagem F #.</span><span class="sxs-lookup"><span data-stu-id="71dc7-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="71dc7-167">Ele fornecerá uma visão geral de alguns dos recursos do F # e fornecerá amplos exemplos de código que você pode copiar para Visual Studio para Mac e executar.</span><span class="sxs-lookup"><span data-stu-id="71dc7-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="71dc7-168">Também há alguns ótimos recursos externos que você pode usar, demonstrados no [guia F #](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="71dc7-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.yml).</span></span>

## <a name="see-also"></a><span data-ttu-id="71dc7-169">Confira também</span><span class="sxs-lookup"><span data-stu-id="71dc7-169">See also</span></span>

- [<span data-ttu-id="71dc7-170">Guia do F#</span><span class="sxs-lookup"><span data-stu-id="71dc7-170">F# guide</span></span>](../index.yml)
- [<span data-ttu-id="71dc7-171">Tour do F#</span><span class="sxs-lookup"><span data-stu-id="71dc7-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="71dc7-172">Referência da linguagem F#</span><span class="sxs-lookup"><span data-stu-id="71dc7-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="71dc7-173">Inferência de tipos</span><span class="sxs-lookup"><span data-stu-id="71dc7-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="71dc7-174">Referência de símbolo e operador</span><span class="sxs-lookup"><span data-stu-id="71dc7-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
