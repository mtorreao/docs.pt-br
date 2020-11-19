---
title: Criar um aplicativo de console .NET usando Visual Studio Code
description: Saiba como criar um aplicativo de console .NET usando Visual Studio Code e a CLI do .NET.
ms.date: 11/17/2020
ms.openlocfilehash: dbbdf88b0c84089249eb7e446c25eddc11543c1a
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915863"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-code"></a><span data-ttu-id="4ff42-103">Tutorial: criar um aplicativo de console .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4ff42-103">Tutorial: Create a .NET console application using Visual Studio Code</span></span>

<span data-ttu-id="4ff42-104">Este tutorial mostra como criar e executar um aplicativo de console .NET usando Visual Studio Code e a CLI do .NET.</span><span class="sxs-lookup"><span data-stu-id="4ff42-104">This tutorial shows how to create and run a .NET console application by using Visual Studio Code and the .NET CLI.</span></span> <span data-ttu-id="4ff42-105">Tarefas de projeto, como criar, compilar e executar um projeto, são feitas usando a CLI do .NET.</span><span class="sxs-lookup"><span data-stu-id="4ff42-105">Project tasks, such as creating, compiling, and running a project are done by using the .NET CLI.</span></span> <span data-ttu-id="4ff42-106">Você pode seguir este tutorial com um editor de código diferente e executar comandos em um terminal, se preferir.</span><span class="sxs-lookup"><span data-stu-id="4ff42-106">You can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4ff42-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4ff42-107">Prerequisites</span></span>

1. <span data-ttu-id="4ff42-108">[Visual Studio Code](https://code.visualstudio.com/) com a [extensão C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) instalada.</span><span class="sxs-lookup"><span data-stu-id="4ff42-108">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="4ff42-109">Para obter informações sobre como instalar extensões em Visual Studio Code, consulte [vs Code Marketplace de extensão](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="4ff42-109">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="4ff42-110">O [SDK do .net 5,0 ou posterior](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="4ff42-110">The [.NET 5.0 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="4ff42-111">Criar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="4ff42-111">Create the app</span></span>

<span data-ttu-id="4ff42-112">Crie um projeto de aplicativo de console .NET chamado "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="4ff42-112">Create a .NET console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="4ff42-113">Inicie o Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4ff42-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="4ff42-114">Selecione **arquivo**  >  **abrir pasta** (**arquivo**  >  **aberto...** no MacOS) no menu principal.</span><span class="sxs-lookup"><span data-stu-id="4ff42-114">Select **File** > **Open Folder** (**File** > **Open...** on macOS) from the main menu.</span></span>

1. <span data-ttu-id="4ff42-115">Na caixa de diálogo **abrir pasta** , crie uma pasta *HelloWorld* e clique em **Selecionar pasta** (**aberta** no MacOS).</span><span class="sxs-lookup"><span data-stu-id="4ff42-115">In the **Open Folder** dialog, create a *HelloWorld* folder and click **Select Folder** (**Open** on macOS).</span></span>

   <span data-ttu-id="4ff42-116">O nome da pasta torna-se o nome do projeto e o nome do namespace por padrão.</span><span class="sxs-lookup"><span data-stu-id="4ff42-116">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="4ff42-117">Você adicionará código posteriormente no tutorial que assume que o namespace do projeto é `HelloWorld` .</span><span class="sxs-lookup"><span data-stu-id="4ff42-117">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="4ff42-118">Abra o **terminal** no Visual Studio Code selecionando **Exibir**  >  **terminal** no menu principal.</span><span class="sxs-lookup"><span data-stu-id="4ff42-118">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="4ff42-119">O **terminal** é aberto com o prompt de comando na pasta *HelloWorld* .</span><span class="sxs-lookup"><span data-stu-id="4ff42-119">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="4ff42-120">No **terminal**, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4ff42-120">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new console
   ```

<span data-ttu-id="4ff42-121">O modelo cria um simples aplicativo “Olá, Mundo”.</span><span class="sxs-lookup"><span data-stu-id="4ff42-121">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="4ff42-122">Ele chama o <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> método para exibir " :::no-loc text="Hello World!"::: " na janela do console.</span><span class="sxs-lookup"><span data-stu-id="4ff42-122">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display ":::no-loc text="Hello World!":::" in the console window.</span></span>

<span data-ttu-id="4ff42-123">O código de modelo define uma classe, `Program` , com um único método, `Main` , que usa uma <xref:System.String> matriz como um argumento:</span><span class="sxs-lookup"><span data-stu-id="4ff42-123">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="4ff42-124">`Main` é o ponto de entrada do aplicativo, o método que é chamado automaticamente pelo runtime quando ele inicia o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4ff42-124">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="4ff42-125">Quaisquer argumentos de linha de comando fornecidos quando o aplicativo for iniciado estão disponíveis na matriz *args*.</span><span class="sxs-lookup"><span data-stu-id="4ff42-125">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="4ff42-126">Executar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="4ff42-126">Run the app</span></span>

<span data-ttu-id="4ff42-127">Execute o seguinte comando no **terminal**:</span><span class="sxs-lookup"><span data-stu-id="4ff42-127">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="4ff42-128">O programa exibe "Olá, Mundo!"</span><span class="sxs-lookup"><span data-stu-id="4ff42-128">The program displays "Hello World!"</span></span> <span data-ttu-id="4ff42-129">e termina.</span><span class="sxs-lookup"><span data-stu-id="4ff42-129">and ends.</span></span>

![O comando de execução dotnet](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="4ff42-131">Aprimorar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="4ff42-131">Enhance the app</span></span>

<span data-ttu-id="4ff42-132">Aprimore o aplicativo para solicitar ao usuário seu nome e exibi-lo junto com a data e hora.</span><span class="sxs-lookup"><span data-stu-id="4ff42-132">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="4ff42-133">Abra *Program.cs* clicando nele.</span><span class="sxs-lookup"><span data-stu-id="4ff42-133">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="4ff42-134">Na primeira vez que um arquivo do C# é aberto no Visual Studio Code, o [OmniSharp](https://www.omnisharp.net/) é carregado no editor.</span><span class="sxs-lookup"><span data-stu-id="4ff42-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Abra o arquivo Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="4ff42-136">Selecione **Sim** quando Visual Studio Code solicitar que você adicione os ativos ausentes para compilar e depurar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4ff42-136">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![Prompt para ativos ausentes](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="4ff42-138">Substitua o conteúdo do `Main` método em *Program.cs*, que é a linha que chama `Console.WriteLine` , com o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="4ff42-138">Replace the contents of the `Main` method in *Program.cs*, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="4ff42-139">Esse código exibe um prompt na janela do console e aguarda até que o usuário insira uma cadeia de caracteres seguida pela tecla <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="4ff42-139">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="4ff42-140">Ele armazena essa cadeia de caracteres em uma variável chamada `name` .</span><span class="sxs-lookup"><span data-stu-id="4ff42-140">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="4ff42-141">Ele também recupera o valor da propriedade <xref:System.DateTime.Now?displayProperty=nameWithType>, que contém a hora local atual e o atribui a uma variável chamada `date`.</span><span class="sxs-lookup"><span data-stu-id="4ff42-141">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="4ff42-142">E ele exibe esses valores na janela do console.</span><span class="sxs-lookup"><span data-stu-id="4ff42-142">And it displays these values in the console window.</span></span> <span data-ttu-id="4ff42-143">Por fim, ele exibe um prompt na janela do console e chama o <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> método para aguardar a entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="4ff42-143">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="4ff42-144">O `\n` representa um caractere de nova linha.</span><span class="sxs-lookup"><span data-stu-id="4ff42-144">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="4ff42-145">O cifrão ( `$` ) na frente de uma cadeia de caracteres permite que você coloque expressões como nomes de variáveis entre chaves na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4ff42-145">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="4ff42-146">O valor da expressão é inserido na cadeia de caracteres no lugar da expressão.</span><span class="sxs-lookup"><span data-stu-id="4ff42-146">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="4ff42-147">Essa sintaxe é conhecida como [cadeias de caracteres interpoladas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="4ff42-147">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="4ff42-148">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="4ff42-148">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4ff42-149">No Visual Studio Code, você precisa salvar explicitamente as alterações.</span><span class="sxs-lookup"><span data-stu-id="4ff42-149">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="4ff42-150">Ao contrário do Visual Studio, as alterações de arquivo não são salvas automaticamente quando você compila e executa um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4ff42-150">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="4ff42-151">Execute o programa novamente:</span><span class="sxs-lookup"><span data-stu-id="4ff42-151">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="4ff42-152">Responda ao prompt digitando um nome e pressionando a tecla <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="4ff42-152">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Janela do terminal com saída do programa modificada":::

1. <span data-ttu-id="4ff42-154">Pressione qualquer tecla para encerrar o programa.</span><span class="sxs-lookup"><span data-stu-id="4ff42-154">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ff42-155">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4ff42-155">Additional resources</span></span>

- [<span data-ttu-id="4ff42-156">Configurar o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4ff42-156">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a><span data-ttu-id="4ff42-157">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4ff42-157">Next steps</span></span>

<span data-ttu-id="4ff42-158">Neste tutorial, você criou um aplicativo de console .NET.</span><span class="sxs-lookup"><span data-stu-id="4ff42-158">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="4ff42-159">No próximo tutorial, você depurará o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4ff42-159">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4ff42-160">Depurar um aplicativo de console .NET usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4ff42-160">Debug a .NET console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
