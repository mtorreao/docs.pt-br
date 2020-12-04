---
title: Criar um aplicativo de console .NET usando Visual Studio para Mac
description: Saiba como criar um aplicativo de console .NET usando Visual Studio para Mac.
ms.date: 11/30/2020
ms.openlocfilehash: 1351b06eec32cd8d3d9d44926655405fe2246f58
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599480"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="272a4-103">Tutorial: criar um aplicativo de console .NET usando o Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="272a4-103">Tutorial: Create a .NET console application using Visual Studio for Mac</span></span>

<span data-ttu-id="272a4-104">Este tutorial mostra como criar e executar um aplicativo de console .NET usando Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="272a4-104">This tutorial shows how to create and run a .NET console application using Visual Studio for Mac.</span></span>

> [!NOTE]
> <span data-ttu-id="272a4-105">Seus comentários são muito importantes.</span><span class="sxs-lookup"><span data-stu-id="272a4-105">Your feedback is highly valued.</span></span> <span data-ttu-id="272a4-106">Há duas maneiras de enviar comentários à equipe de desenvolvimento no Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="272a4-106">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="272a4-107">Em Visual Studio para Mac, selecione **ajuda** para  >  **relatar um problema** no menu ou **relatar um problema** na tela de boas-vindas, que abrirá uma janela para o arquivamento de um relatório de bug.</span><span class="sxs-lookup"><span data-stu-id="272a4-107">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="272a4-108">Você pode acompanhar seus comentários no portal [Developer Community (Comunidade do Desenvolvedor)](https://aka.ms/feedback/report?space=41).</span><span class="sxs-lookup"><span data-stu-id="272a4-108">You can track your feedback in the [Developer Community](https://aka.ms/feedback/report?space=41) portal.</span></span>
> * <span data-ttu-id="272a4-109">Para fazer uma sugestão, selecione **ajuda**  >  **fornecer uma sugestão** no menu ou **forneça uma sugestão** na tela de boas-vindas, que levará você para a [página da Web do Visual Studio para Mac Developer Community](https://aka.ms/feedback/suggest?space=41).</span><span class="sxs-lookup"><span data-stu-id="272a4-109">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://aka.ms/feedback/suggest?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="272a4-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="272a4-110">Prerequisites</span></span>

* <span data-ttu-id="272a4-111">[Visual Studio para Mac versão 8,8 ou posterior](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="272a4-111">[Visual Studio for Mac version 8.8 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="272a4-112">Selecione a opção para instalar o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="272a4-112">Select the option to install .NET Core.</span></span> <span data-ttu-id="272a4-113">A instalação do Xamarin é opcional para o desenvolvimento do .NET.</span><span class="sxs-lookup"><span data-stu-id="272a4-113">Installing Xamarin is optional for .NET development.</span></span> <span data-ttu-id="272a4-114">Para obter mais informações, consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="272a4-114">For more information, see the following resources:</span></span>

  * <span data-ttu-id="272a4-115">[Tutorial: instalar o Visual Studio para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="272a4-115">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="272a4-116">[Versões do MacOS com suporte](../install/windows.md).</span><span class="sxs-lookup"><span data-stu-id="272a4-116">[Supported macOS versions](../install/windows.md).</span></span>
  * <span data-ttu-id="272a4-117">[Versões do .NET com suporte pelo Visual Studio para Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="272a4-117">[.NET versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="272a4-118">Crie o aplicativo</span><span class="sxs-lookup"><span data-stu-id="272a4-118">Create the app</span></span>

1. <span data-ttu-id="272a4-119">Iniciar Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="272a4-119">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="272a4-120">Selecione **novo** na janela iniciar.</span><span class="sxs-lookup"><span data-stu-id="272a4-120">Select **New** in the start window.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="O botão Novo na tela de Boas-vindas do Visual Studio para Mac":::

1. <span data-ttu-id="272a4-122">Na caixa de diálogo **novo projeto** , selecione **aplicativo** no nó **Web e console** .</span><span class="sxs-lookup"><span data-stu-id="272a4-122">In the **New Project** dialog, select **App** under the **Web and Console** node.</span></span> <span data-ttu-id="272a4-123">Selecione o modelo de **aplicativo de console** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="272a4-123">Select the **Console Application** template, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Lista de modelos de novo projeto":::

1. <span data-ttu-id="272a4-125">Na lista suspensa **estrutura de destino** da caixa de diálogo **configurar seu novo aplicativo de console** , selecione **.NET 5,0** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="272a4-125">In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET 5.0**, and select **Next**.</span></span>

1. <span data-ttu-id="272a4-126">Digite "HelloWorld" para o **nome do projeto** e selecione **criar**.</span><span class="sxs-lookup"><span data-stu-id="272a4-126">Type "HelloWorld" for the **Project Name**, and select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Configurar a caixa de diálogo Novo Aplicativo de Console":::

<span data-ttu-id="272a4-128">O modelo cria um simples aplicativo “Olá, Mundo”.</span><span class="sxs-lookup"><span data-stu-id="272a4-128">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="272a4-129">Ele chama o <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> método para exibir "Olá, mundo!"</span><span class="sxs-lookup"><span data-stu-id="272a4-129">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="272a4-130">na janela do terminal.</span><span class="sxs-lookup"><span data-stu-id="272a4-130">in the terminal window.</span></span>

<span data-ttu-id="272a4-131">O código de modelo define uma classe, `Program` , com um único método, `Main` , que usa uma <xref:System.String> matriz como um argumento:</span><span class="sxs-lookup"><span data-stu-id="272a4-131">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="272a4-132">`Main` é o ponto de entrada do aplicativo, o método que é chamado automaticamente pelo runtime quando ele inicia o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="272a4-132">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="272a4-133">Todos os argumentos de linha de comando fornecidos quando o aplicativo é iniciado estão disponíveis na `args` matriz.</span><span class="sxs-lookup"><span data-stu-id="272a4-133">Any command-line arguments supplied when the application is launched are available in the `args` array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="272a4-134">Execute o aplicativo</span><span class="sxs-lookup"><span data-stu-id="272a4-134">Run the app</span></span>

1. <span data-ttu-id="272a4-135">Pressione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd> + <kbd>comando</kbd>Option + <kbd>Enter</kbd>) para executar o aplicativo sem depuração.</span><span class="sxs-lookup"><span data-stu-id="272a4-135">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="O terminal mostra Olá, Mundo!":::

1. <span data-ttu-id="272a4-137">Feche a janela do **terminal** .</span><span class="sxs-lookup"><span data-stu-id="272a4-137">Close the **Terminal** window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="272a4-138">Aprimorar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="272a4-138">Enhance the app</span></span>

<span data-ttu-id="272a4-139">Aprimore o aplicativo para solicitar ao usuário seu nome e exibi-lo junto com a data e hora.</span><span class="sxs-lookup"><span data-stu-id="272a4-139">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="272a4-140">No *Program.cs*, substitua o conteúdo do `Main` método, que é a linha que chama `Console.WriteLine` , com o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="272a4-140">In *Program.cs*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="272a4-141">Esse código exibe um prompt na janela do console e aguarda até que o usuário insira uma cadeia de caracteres seguida pela tecla <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="272a4-141">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key.</span></span> <span data-ttu-id="272a4-142">Ele armazena essa cadeia de caracteres em uma variável chamada `name` .</span><span class="sxs-lookup"><span data-stu-id="272a4-142">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="272a4-143">Ele também recupera o valor da propriedade <xref:System.DateTime.Now?displayProperty=nameWithType>, que contém a hora local atual e o atribui a uma variável chamada `date`.</span><span class="sxs-lookup"><span data-stu-id="272a4-143">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="272a4-144">E ele exibe esses valores na janela do console.</span><span class="sxs-lookup"><span data-stu-id="272a4-144">And it displays these values in the console window.</span></span> <span data-ttu-id="272a4-145">Por fim, ele exibe um prompt na janela do console e chama o <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> método para aguardar a entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="272a4-145">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="272a4-146">O `\n` representa um caractere de nova linha.</span><span class="sxs-lookup"><span data-stu-id="272a4-146">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="272a4-147">O cifrão ( `$` ) na frente de uma cadeia de caracteres permite que você coloque expressões como nomes de variáveis entre chaves na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="272a4-147">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="272a4-148">O valor da expressão é inserido na cadeia de caracteres no lugar da expressão.</span><span class="sxs-lookup"><span data-stu-id="272a4-148">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="272a4-149">Essa sintaxe é conhecida como [cadeias de caracteres interpoladas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="272a4-149">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="272a4-150">Pressione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd> + <kbd>comando</kbd>Option + <kbd>Enter</kbd>) para executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="272a4-150">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.</span></span>

1. <span data-ttu-id="272a4-151">Responda ao prompt digitando um nome e pressionando <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="272a4-151">Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Terminal mostra a saída de programa modificada":::

1. <span data-ttu-id="272a4-153">Feche o terminal.</span><span class="sxs-lookup"><span data-stu-id="272a4-153">Close the terminal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="272a4-154">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="272a4-154">Next steps</span></span>

<span data-ttu-id="272a4-155">Neste tutorial, você criou um aplicativo de console .NET.</span><span class="sxs-lookup"><span data-stu-id="272a4-155">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="272a4-156">No próximo tutorial, você depurará o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="272a4-156">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="272a4-157">Depurar um aplicativo de console .NET usando Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="272a4-157">Debug a .NET console application using Visual Studio for Mac</span></span>](debugging-with-visual-studio-mac.md)
