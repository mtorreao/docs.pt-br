---
title: Criar uma biblioteca de classes .NET usando Visual Studio para Mac
description: Saiba como criar uma biblioteca de classes .NET usando Visual Studio para Mac.
ms.date: 11/30/2020
ms.openlocfilehash: 1b6b26de06d18d505fa6dde3ff9779a3dab3f1e6
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599285"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio-for-mac"></a><span data-ttu-id="4c378-103">Tutorial: criar uma biblioteca de classes do .NET usando Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="4c378-103">Tutorial: Create a .NET class library using Visual Studio for Mac</span></span>

<span data-ttu-id="4c378-104">Neste tutorial, você cria uma biblioteca de classes que contém um único método de manipulação de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4c378-104">In this tutorial, you create a class library that contains a single string-handling method.</span></span>

<span data-ttu-id="4c378-105">Uma *biblioteca de classes* define tipos e métodos que são chamados por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4c378-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="4c378-106">Se a biblioteca tiver como destino .NET Standard 2,0, ela poderá ser chamada por qualquer implementação do .NET (incluindo .NET Framework) que ofereça suporte a .NET Standard 2,0.</span><span class="sxs-lookup"><span data-stu-id="4c378-106">If the library targets .NET Standard 2.0, it can be called by any .NET implementation (including .NET Framework) that supports .NET Standard 2.0.</span></span> <span data-ttu-id="4c378-107">Se a biblioteca tiver como destino o .NET 5, ela poderá ser chamada por qualquer aplicativo que tenha como destino o .NET 5.</span><span class="sxs-lookup"><span data-stu-id="4c378-107">If the library targets .NET 5, it can be called by any application that targets .NET 5.</span></span> <span data-ttu-id="4c378-108">Este tutorial mostra como direcionar o .NET 5.</span><span class="sxs-lookup"><span data-stu-id="4c378-108">This tutorial shows how to target .NET 5.</span></span>

> [!NOTE]
> <span data-ttu-id="4c378-109">Seus comentários são muito importantes.</span><span class="sxs-lookup"><span data-stu-id="4c378-109">Your feedback is highly valued.</span></span> <span data-ttu-id="4c378-110">Há duas maneiras de enviar comentários à equipe de desenvolvimento no Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="4c378-110">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> - <span data-ttu-id="4c378-111">Em Visual Studio para Mac, selecione **ajuda**  >  **relatar um problema** no menu ou **relatar um problema** na tela de boas-vindas, que abre uma janela para o arquivamento de um relatório de bug.</span><span class="sxs-lookup"><span data-stu-id="4c378-111">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="4c378-112">Você pode acompanhar seus comentários no portal [Developer Community (Comunidade do Desenvolvedor)](https://aka.ms/feedback/report?space=41).</span><span class="sxs-lookup"><span data-stu-id="4c378-112">You can track your feedback in the [Developer Community](https://aka.ms/feedback/report?space=41) portal.</span></span>
> - <span data-ttu-id="4c378-113">Para fazer uma sugestão, selecione **ajuda**  >  **fornecer uma sugestão** no menu ou **forneça uma sugestão** na tela de boas-vindas, que leva você para a [página da Web do Visual Studio para Mac Developer Community](https://aka.ms/feedback/suggest?space=41).</span><span class="sxs-lookup"><span data-stu-id="4c378-113">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac Developer Community webpage](https://aka.ms/feedback/suggest?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c378-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4c378-114">Prerequisites</span></span>

* <span data-ttu-id="4c378-115">[Instale Visual Studio para Mac versão 8,8 ou posterior](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="4c378-115">[Install Visual Studio for Mac version 8.8 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="4c378-116">Selecione a opção para instalar o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c378-116">Select the option to install .NET Core.</span></span> <span data-ttu-id="4c378-117">A instalação do Xamarin é opcional para o desenvolvimento do .NET.</span><span class="sxs-lookup"><span data-stu-id="4c378-117">Installing Xamarin is optional for .NET development.</span></span> <span data-ttu-id="4c378-118">Para obter mais informações, consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="4c378-118">For more information, see the following resources:</span></span>

  * <span data-ttu-id="4c378-119">[Tutorial: instalar o Visual Studio para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="4c378-119">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="4c378-120">[Versões do MacOS com suporte](../install/macos.md).</span><span class="sxs-lookup"><span data-stu-id="4c378-120">[Supported macOS versions](../install/macos.md).</span></span>
  * <span data-ttu-id="4c378-121">[Versões do .NET com suporte pelo Visual Studio para Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="4c378-121">[.NET versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-a-solution-with-a-class-library-project"></a><span data-ttu-id="4c378-122">Criar uma solução com um projeto de biblioteca de classes</span><span class="sxs-lookup"><span data-stu-id="4c378-122">Create a solution with a class library project</span></span>

<span data-ttu-id="4c378-123">Uma solução do Visual Studio serve como um contêiner para um ou mais projetos.</span><span class="sxs-lookup"><span data-stu-id="4c378-123">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="4c378-124">Crie uma solução e um projeto de biblioteca de classes na solução.</span><span class="sxs-lookup"><span data-stu-id="4c378-124">Create a solution and a class library project in the solution.</span></span> <span data-ttu-id="4c378-125">Você adicionará mais projetos relacionados à mesma solução posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4c378-125">You'll add additional, related projects to the same solution later.</span></span>

1. <span data-ttu-id="4c378-126">Iniciar Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="4c378-126">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="4c378-127">Na janela iniciar, selecione **novo projeto**.</span><span class="sxs-lookup"><span data-stu-id="4c378-127">In the start window, select **New Project**.</span></span>

1. <span data-ttu-id="4c378-128">Na caixa de diálogo **escolher um modelo para o novo projeto** , selecione **Web e** biblioteca de classes da biblioteca de console  >  **Library**  >  **Class Library** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4c378-128">In the **Choose a template for your new project** dialog select **Web and Console** > **Library** > **Class Library**, and then select **Next**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Caixa de diálogo Novo Projeto":::

1. <span data-ttu-id="4c378-130">Na caixa de diálogo **configurar sua nova biblioteca de classes** , escolha **.NET 5,0** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4c378-130">In the **Configure your new Class Library** dialog, choose **.NET 5.0**, and select **Next**.</span></span>

1. <span data-ttu-id="4c378-131">Nomeie o projeto "StringLibrary" e a solução "ClassLibraryProjects".</span><span class="sxs-lookup"><span data-stu-id="4c378-131">Name the project "StringLibrary" and the solution "ClassLibraryProjects".</span></span> <span data-ttu-id="4c378-132">Deixe **criar um diretório de projeto dentro do diretório de solução** selecionado.</span><span class="sxs-lookup"><span data-stu-id="4c378-132">Leave **Create a project directory within the solution directory** selected.</span></span> <span data-ttu-id="4c378-133">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4c378-133">Select **Create**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Opções da caixa de diálogo Novo projeto do Visual Studio para Mac":::

1. <span data-ttu-id="4c378-135">No menu principal, selecione **Exibir**  >  **solução** e selecione o ícone de encaixe para manter o pad aberto.</span><span class="sxs-lookup"><span data-stu-id="4c378-135">From the main menu, select **View** > **Solution**, and select the dock icon to keep the pad open.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="Ícone de encaixe para o painel de solução":::

1. <span data-ttu-id="4c378-137">No painel de **solução** , expanda o `StringLibrary` nó para revelar o arquivo de classe fornecido pelo modelo, *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="4c378-137">In the **Solution** pad, expand the `StringLibrary` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="4c378-138"><kbd>Ctrl</kbd>-clique no arquivo, selecione **renomear** no menu de contexto e renomeie o arquivo para *StringLibrary.cs*.</span><span class="sxs-lookup"><span data-stu-id="4c378-138"><kbd>ctrl</kbd>-click the file, select **Rename** from the context menu, and rename the file to *StringLibrary.cs*.</span></span> <span data-ttu-id="4c378-139">Abra o arquivo e substitua o conteúdo pelo código a seguir:</span><span class="sxs-lookup"><span data-stu-id="4c378-139">Open the file and replace the contents with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. <span data-ttu-id="4c378-140">Pressione <kbd>⌘</kbd><kbd>S</kbd> (<kbd>Command</kbd> + <kbd>s</kbd>) para salvar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="4c378-140">Press <kbd>⌘</kbd><kbd>S</kbd> (<kbd>command</kbd>+<kbd>S</kbd>) to save the file.</span></span>

1. <span data-ttu-id="4c378-141">Selecione **Erros** na margem da parte inferior da janela do IDE para abrir o painel **Erros**.</span><span class="sxs-lookup"><span data-stu-id="4c378-141">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="4c378-142">Selecione o botão **Compilar Saída**.</span><span class="sxs-lookup"><span data-stu-id="4c378-142">Select the **Build Output** button.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="Margem inferior do IDE do Visual Studio para Mac mostrando o botão Erros":::

1. <span data-ttu-id="4c378-144">Selecione **Compilar**  >  **compilar tudo** no menu.</span><span class="sxs-lookup"><span data-stu-id="4c378-144">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="4c378-145">A solução é compilada.</span><span class="sxs-lookup"><span data-stu-id="4c378-145">The solution builds.</span></span> <span data-ttu-id="4c378-146">O painel de saída da compilação mostra que a compilação foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="4c378-146">The build output panel shows that the build is successful.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="Painel de saída do Build do Visual Studio do painel Erros com a mensagem Build bem-sucedido":::

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="4c378-148">Adicionar um aplicativo de console à solução</span><span class="sxs-lookup"><span data-stu-id="4c378-148">Add a console app to the solution</span></span>

<span data-ttu-id="4c378-149">Adicione um aplicativo de console que usa a biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="4c378-149">Add a console application that uses the class library.</span></span> <span data-ttu-id="4c378-150">O aplicativo solicitará que o usuário insira uma cadeia de caracteres e relate se a cadeia de caracteres começa com um caractere maiúsculo.</span><span class="sxs-lookup"><span data-stu-id="4c378-150">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="4c378-151">No painel de **solução** , <kbd>pressione CTRL +</kbd>clique na `ClassLibraryProjects` solução.</span><span class="sxs-lookup"><span data-stu-id="4c378-151">In the **Solution** pad, <kbd>ctrl</kbd>-click the `ClassLibraryProjects` solution.</span></span> <span data-ttu-id="4c378-152">Adicione um novo projeto de **aplicativo de console** selecionando o modelo nos modelos de aplicativo **Web e de console**  >  **App** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4c378-152">Add a new **Console Application** project by selecting the template from the **Web and Console** > **App** templates, and select **Next**.</span></span>

1. <span data-ttu-id="4c378-153">Selecione **.net 5,0** como a **estrutura de destino** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4c378-153">Select **.NET 5.0** as the **Target Framework** and select **Next**.</span></span>

1. <span data-ttu-id="4c378-154">Nomeie a **demonstração** do projeto.</span><span class="sxs-lookup"><span data-stu-id="4c378-154">Name the project **ShowCase**.</span></span> <span data-ttu-id="4c378-155">Selecione **Criar** para criar o projeto na solução.</span><span class="sxs-lookup"><span data-stu-id="4c378-155">Select **Create** to create the project in the solution.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="Adicionar projeto de demonstração":::

1. <span data-ttu-id="4c378-157">Abra o arquivo *Program.cs* .</span><span class="sxs-lookup"><span data-stu-id="4c378-157">Open the *Program.cs* file.</span></span> <span data-ttu-id="4c378-158">Substitua o código pelo código a seguir:</span><span class="sxs-lookup"><span data-stu-id="4c378-158">Replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="4c378-159">O programa solicita que o usuário insira uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4c378-159">The program prompts the user to enter a string.</span></span> <span data-ttu-id="4c378-160">Ele indica se a cadeia de caracteres começa com um caractere maiúsculo.</span><span class="sxs-lookup"><span data-stu-id="4c378-160">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="4c378-161">Se o usuário pressionar a tecla <kbd>Enter</kbd> sem inserir uma cadeia de caracteres, o aplicativo será encerrado e a janela do console será fechada.</span><span class="sxs-lookup"><span data-stu-id="4c378-161">If the user presses the <kbd>enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

   <span data-ttu-id="4c378-162">O código usa a variável `row` ​​para manter uma contagem do número de linhas de dados gravadas na janela do console.</span><span class="sxs-lookup"><span data-stu-id="4c378-162">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="4c378-163">Sempre que for maior ou igual a 25, o código limpará a janela do console e exibirá uma mensagem para o usuário.</span><span class="sxs-lookup"><span data-stu-id="4c378-163">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="4c378-164">Adicionar uma referência ao projeto</span><span class="sxs-lookup"><span data-stu-id="4c378-164">Add a project reference</span></span>

<span data-ttu-id="4c378-165">Inicialmente, o novo projeto de aplicativo de console não tem acesso à biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="4c378-165">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="4c378-166">Para permitir que ele chame métodos na biblioteca de classes, crie uma referência de projeto para o projeto de biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="4c378-166">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="4c378-167">No painel **soluções** , <kbd>pressione CTRL</kbd>e clique no nó **dependências** do novo projeto de **demonstração** .</span><span class="sxs-lookup"><span data-stu-id="4c378-167">In the **Solutions** pad, <kbd>ctrl</kbd>-click the **Dependencies** node of the new **ShowCase** project.</span></span> <span data-ttu-id="4c378-168">No menu de contexto, selecione **Adicionar referência**.</span><span class="sxs-lookup"><span data-stu-id="4c378-168">In the context menu, select **Add Reference**.</span></span>

1. <span data-ttu-id="4c378-169">Na caixa de diálogo **referências** , selecione **StringLibrary** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c378-169">In the **References** dialog, select **StringLibrary** and select **OK**.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="4c378-170">Execute o aplicativo</span><span class="sxs-lookup"><span data-stu-id="4c378-170">Run the app</span></span>

1. <span data-ttu-id="4c378-171"><kbd>Ctrl</kbd>-clique no projeto de **demonstração** e selecione **Executar projeto** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="4c378-171"><kbd>ctrl</kbd>-click the **ShowCase** project and select **Run project** from the context menu.</span></span>

1. <span data-ttu-id="4c378-172">Experimente o programa digitando cadeias de caracteres e pressionando <kbd>Enter</kbd>e pressione <kbd>Enter</kbd> para sair.</span><span class="sxs-lookup"><span data-stu-id="4c378-172">Try out the program by entering strings and pressing <kbd>enter</kbd>, then press <kbd>enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="Janela do console do Visual Studio para Mac mostrando o aplicativo em execução":::

## <a name="additional-resources"></a><span data-ttu-id="4c378-174">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4c378-174">Additional resources</span></span>

* [<span data-ttu-id="4c378-175">Desenvolver bibliotecas com a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="4c378-175">Develop libraries with the .NET CLI</span></span>](libraries.md)
* [<span data-ttu-id="4c378-176">Notas sobre a versão do Visual Studio 2019 para Mac</span><span class="sxs-lookup"><span data-stu-id="4c378-176">Visual Studio 2019 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2019-mac-relnotes)
* <span data-ttu-id="4c378-177">[.Net Standard versões e plataformas às quais eles dão suporte](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="4c378-177">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4c378-178">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4c378-178">Next steps</span></span>

<span data-ttu-id="4c378-179">Neste tutorial, você criou uma solução e um projeto de biblioteca e adicionou um projeto de aplicativo de console que usa a biblioteca do.</span><span class="sxs-lookup"><span data-stu-id="4c378-179">In this tutorial, you created a solution and a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="4c378-180">No próximo tutorial, você adicionará um projeto de teste de unidade à solução.</span><span class="sxs-lookup"><span data-stu-id="4c378-180">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4c378-181">Testar uma biblioteca de classes .NET usando Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="4c378-181">Test a .NET class library using Visual Studio for Mac</span></span>](testing-library-with-visual-studio-mac.md)
