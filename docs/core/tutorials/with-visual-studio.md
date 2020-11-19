---
title: Criar um aplicativo de console .NET usando o Visual Studio
description: Saiba como criar um aplicativo de console .NET com C# ou Visual Basic usando o Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e395122e59f17ed66bbd9d83b01610993f663ce1
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915902"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio"></a><span data-ttu-id="6a0c9-103">Tutorial: criar um aplicativo de console .NET usando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6a0c9-103">Tutorial: Create a .NET console application using Visual Studio</span></span>

<span data-ttu-id="6a0c9-104">Este tutorial mostra como criar e executar um aplicativo de console .NET no Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-104">This tutorial shows how to create and run a .NET console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a0c9-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6a0c9-105">Prerequisites</span></span>

- <span data-ttu-id="6a0c9-106">[Visual Studio 2019 versão 16,8 ou uma versão posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) com a carga de trabalho de **desenvolvimento de plataforma cruzada do .NET Core** instalada.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-106">[Visual Studio 2019 version 16.8 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="6a0c9-107">O SDK do .NET 5,0 é instalado automaticamente quando você seleciona essa carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-107">The .NET 5.0 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="6a0c9-108">Para obter mais informações, consulte [instalar o SDK do .NET com o Visual Studio](../install/windows.md#install-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="6a0c9-108">For more information, see [Install the .NET SDK with Visual Studio](../install/windows.md#install-with-visual-studio).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="6a0c9-109">Criar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="6a0c9-109">Create the app</span></span>

<span data-ttu-id="6a0c9-110">Crie um projeto de aplicativo de console .NET chamado "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="6a0c9-110">Create a .NET console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="6a0c9-111">Inicie o Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-111">Start Visual Studio 2019.</span></span>

1. <span data-ttu-id="6a0c9-112">Selecione **ferramentas**  >  **Opções**  >  **Environment**  >  **recursos de visualização** de ambiente e, em seguida, selecione **Mostrar todos os modelos do .NET Core no novo projeto (requer reinicialização)**.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-112">Select **Tools** > **Options** > **Environment** > **Preview features**, and then select **Show all .NET Core templates in the New project (requires restart)**.</span></span>

   :::image type="content" source="media/with-visual-studio/dotnet-options.png" alt-text="Opção Mostrar todos os modelos do .NET":::

1. <span data-ttu-id="6a0c9-114">Feche e reabra o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-114">Close and reopen Visual Studio.</span></span>

1. <span data-ttu-id="6a0c9-115">Na página inicial, escolha **criar um novo projeto**.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-115">On the start page, choose **Create a new project**.</span></span>

   :::image type="content" source="./media/with-visual-studio/start-window.png" alt-text="Criar um novo botão de projeto selecionado na página inicial do Visual Studio":::

1. <span data-ttu-id="6a0c9-117">Na página **criar um novo projeto** , insira **console** na caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-117">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="6a0c9-118">Em seguida, escolha **C#** ou **Visual Basic** na lista idioma e, em seguida, escolha **todas as plataformas** na lista plataforma.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-118">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="6a0c9-119">Escolha o modelo de **aplicativo de console** e, em seguida, escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-119">Choose the **Console Application** template, and then choose **Next**.</span></span>

   :::image type="content" source="./media/with-visual-studio/create-new-project.png" alt-text="Criar uma nova janela de projeto com filtros selecionados":::

   > [!TIP]
   > <span data-ttu-id="6a0c9-121">Se você não vir os modelos .NET, provavelmente está faltando a carga de trabalho necessária.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-121">If you don't see the .NET templates, you're probably missing the required workload.</span></span> <span data-ttu-id="6a0c9-122">Na mensagem **não localizando o que você está procurando?** , escolha o link **instalar mais ferramentas e recursos** .</span><span class="sxs-lookup"><span data-stu-id="6a0c9-122">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="6a0c9-123">O Instalador do Visual Studio é aberto.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-123">The Visual Studio Installer opens.</span></span> <span data-ttu-id="6a0c9-124">Verifique se você tem a carga de trabalho de **desenvolvimento de plataforma cruzada do .NET Core** instalada.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-124">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

1. <span data-ttu-id="6a0c9-125">No diálogo **configurar seu novo projeto** , digite **HelloWorld** na caixa **nome do projeto** .</span><span class="sxs-lookup"><span data-stu-id="6a0c9-125">In the **Configure your new project** dialog,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="6a0c9-126">Em seguida, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-126">Then choose **Create**.</span></span>

   :::image type="content" source="./media/with-visual-studio/configure-new-project.png" alt-text="Configurar sua nova janela de projeto com os campos nome do projeto, local e nome da solução":::

1. <span data-ttu-id="6a0c9-128">Na caixa de diálogo **informações adicionais** , selecione **.NET 5,0 (atual)** e, em seguida, selecione **criar**.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-128">In the **Additional information** dialog, select **.NET 5.0 (Current)**, and then select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio/additional-info.png" alt-text="Caixa de diálogo Informações adicionais":::

<span data-ttu-id="6a0c9-130">O modelo cria um simples aplicativo “Olá, Mundo”.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="6a0c9-131">Ele chama o <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> método para exibir "Olá, mundo!"</span><span class="sxs-lookup"><span data-stu-id="6a0c9-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="6a0c9-132">na janela do console.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-132">in the console window.</span></span>

<span data-ttu-id="6a0c9-133">O código de modelo define uma classe, `Program` , com um único método, `Main` , que usa uma <xref:System.String> matriz como um argumento:</span><span class="sxs-lookup"><span data-stu-id="6a0c9-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

```vb
Imports System

Module Program
    Sub Main(args As String())
        Console.WriteLine("Hello World!")
    End Sub
End Module
```

<span data-ttu-id="6a0c9-134">`Main` é o ponto de entrada do aplicativo, o método que é chamado automaticamente pelo runtime quando ele inicia o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="6a0c9-135">Quaisquer argumentos de linha de comando fornecidos quando o aplicativo for iniciado estão disponíveis na matriz *args*.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-135">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="6a0c9-136">Se o idioma que você deseja usar não for mostrado, altere o seletor de idioma na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-136">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="6a0c9-137">Executar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="6a0c9-137">Run the app</span></span>

1. <span data-ttu-id="6a0c9-138">Pressione <kbd>Ctrl</kbd> + <kbd>F5</kbd> para executar o programa sem depuração.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-138">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

   <span data-ttu-id="6a0c9-139">Uma janela de console é aberta com o texto "Olá, Mundo!"</span><span class="sxs-lookup"><span data-stu-id="6a0c9-139">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="6a0c9-140">impresso na tela.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-140">printed on the screen.</span></span>

   :::image type="content" source="./media/with-visual-studio/hello-world-console.png" alt-text="Janela de console mostrando Hello World Press any key to continue":::

1. <span data-ttu-id="6a0c9-142">Pressione qualquer tecla para fechar a janela do console.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-142">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="6a0c9-143">Aprimorar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="6a0c9-143">Enhance the app</span></span>

<span data-ttu-id="6a0c9-144">Aprimore o aplicativo para solicitar ao usuário seu nome e exibi-lo junto com a data e hora.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-144">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="6a0c9-145">Em *Program.cs* ou *Program. vb*, substitua o conteúdo do `Main` método, que é a linha que chama `Console.WriteLine` , com o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="6a0c9-145">In *Program.cs* or *Program.vb*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   <span data-ttu-id="6a0c9-146">Esse código exibe um prompt na janela do console e aguarda até que o usuário insira uma cadeia de caracteres seguida pela tecla <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="6a0c9-146">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="6a0c9-147">Ele armazena essa cadeia de caracteres em uma variável chamada `name` .</span><span class="sxs-lookup"><span data-stu-id="6a0c9-147">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="6a0c9-148">Ele também recupera o valor da <xref:System.DateTime.Now?displayProperty=nameWithType> propriedade, que contém a hora local atual e a atribui a uma variável chamada `date` ( `currentDate` em Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6a0c9-148">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="6a0c9-149">E ele exibe esses valores na janela do console.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-149">And it displays these values in the console window.</span></span> <span data-ttu-id="6a0c9-150">Por fim, ele exibe um prompt na janela do console e chama o <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> método para aguardar a entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-150">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="6a0c9-151">O `\n` ( `vbCrLf` em Visual Basic) representa um caractere de nova linha.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-151">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="6a0c9-152">O cifrão ( `$` ) na frente de uma cadeia de caracteres permite que você coloque expressões como nomes de variáveis entre chaves na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-152">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="6a0c9-153">O valor da expressão é inserido na cadeia de caracteres no lugar da expressão.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-153">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="6a0c9-154">Essa sintaxe é conhecida como [cadeias de caracteres interpoladas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="6a0c9-154">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="6a0c9-155">Pressione <kbd>Ctrl</kbd> + <kbd>F5</kbd> para executar o programa sem depuração.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-155">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

1. <span data-ttu-id="6a0c9-156">Responda ao prompt digitando um nome e pressionando a tecla <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="6a0c9-156">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="./media/with-visual-studio/hello-world-update.png" alt-text="Janela de console com saída de programa modificada":::

1. <span data-ttu-id="6a0c9-158">Pressione qualquer tecla para fechar a janela do console.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-158">Press any key to close the console window.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a0c9-159">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6a0c9-159">Additional resources</span></span>

- [<span data-ttu-id="6a0c9-160">Versões atuais e versões de suporte a longo prazo</span><span class="sxs-lookup"><span data-stu-id="6a0c9-160">Current releases and long-term support releases</span></span>](../releases-and-support.md#net-core-and-net-5-version-lifecycles)

## <a name="next-steps"></a><span data-ttu-id="6a0c9-161">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="6a0c9-161">Next steps</span></span>

<span data-ttu-id="6a0c9-162">Neste tutorial, você criou um aplicativo de console .NET.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-162">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="6a0c9-163">No próximo tutorial, você depurará o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6a0c9-163">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6a0c9-164">Depurar um aplicativo de console .NET usando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6a0c9-164">Debug a .NET console application using Visual Studio</span></span>](debugging-with-visual-studio.md)
