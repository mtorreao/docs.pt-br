---
title: Criar uma biblioteca de classes .NET usando Visual Studio Code
description: Saiba como criar uma biblioteca de classes .NET usando Visual Studio Code.
ms.date: 11/18/2020
ms.openlocfilehash: 4473163b76060623b364d7dabf7366c3575e3dcd
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599493"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio-code"></a><span data-ttu-id="10ffb-103">Tutorial: criar uma biblioteca de classes do .NET usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="10ffb-103">Tutorial: Create a .NET class library using Visual Studio Code</span></span>

<span data-ttu-id="10ffb-104">Neste tutorial, você cria uma biblioteca de utilitário simples que contém um único método de manipulação de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="10ffb-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span>

<span data-ttu-id="10ffb-105">Uma *biblioteca de classes* define tipos e métodos que são chamados por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="10ffb-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="10ffb-106">Se a biblioteca tiver como destino .NET Standard 2,0, ela poderá ser chamada por qualquer implementação do .NET (incluindo .NET Framework) que ofereça suporte a .NET Standard 2,0.</span><span class="sxs-lookup"><span data-stu-id="10ffb-106">If the library targets .NET Standard 2.0, it can be called by any .NET implementation (including .NET Framework) that supports .NET Standard 2.0.</span></span> <span data-ttu-id="10ffb-107">Se a biblioteca tiver como destino o .NET 5, ela poderá ser chamada por qualquer aplicativo que tenha como destino o .NET 5.</span><span class="sxs-lookup"><span data-stu-id="10ffb-107">If the library targets .NET 5, it can be called by any application that targets .NET 5.</span></span> <span data-ttu-id="10ffb-108">Este tutorial mostra como direcionar o .NET 5.</span><span class="sxs-lookup"><span data-stu-id="10ffb-108">This tutorial shows how to target .NET 5.</span></span>

<span data-ttu-id="10ffb-109">Ao criar uma biblioteca de classes, você pode distribuí-la como um componente de terceiros ou como um componente agrupado com um ou mais aplicativos.</span><span class="sxs-lookup"><span data-stu-id="10ffb-109">When you create a class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10ffb-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="10ffb-110">Prerequisites</span></span>

1. <span data-ttu-id="10ffb-111">[Visual Studio Code](https://code.visualstudio.com/) com a [extensão C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) instalada.</span><span class="sxs-lookup"><span data-stu-id="10ffb-111">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="10ffb-112">Para obter informações sobre como instalar extensões em Visual Studio Code, consulte [vs Code Marketplace de extensão](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="10ffb-112">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="10ffb-113">O [SDK do .net 5,0 ou posterior](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="10ffb-113">The [.NET 5.0 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="10ffb-114">Criar uma solução</span><span class="sxs-lookup"><span data-stu-id="10ffb-114">Create a solution</span></span>

<span data-ttu-id="10ffb-115">Comece criando uma solução em branco para colocar o projeto de biblioteca de classes no.</span><span class="sxs-lookup"><span data-stu-id="10ffb-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="10ffb-116">Uma solução serve como um contêiner para um ou mais projetos.</span><span class="sxs-lookup"><span data-stu-id="10ffb-116">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="10ffb-117">Você adicionará mais projetos relacionados à mesma solução.</span><span class="sxs-lookup"><span data-stu-id="10ffb-117">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="10ffb-118">Inicie o Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="10ffb-118">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="10ffb-119">Selecione **arquivo**  >  **abrir pasta** (**abrir...** no MacOS) no menu principal</span><span class="sxs-lookup"><span data-stu-id="10ffb-119">Select **File** > **Open Folder** (**Open...** on macOS) from the main menu</span></span>

1. <span data-ttu-id="10ffb-120">Na caixa de diálogo **abrir pasta** , crie uma pasta *ClassLibraryProjects* e clique em **Selecionar pasta** (**aberta** no MacOS).</span><span class="sxs-lookup"><span data-stu-id="10ffb-120">In the **Open Folder** dialog, create a *ClassLibraryProjects* folder and click **Select Folder** (**Open** on macOS).</span></span>

1. <span data-ttu-id="10ffb-121">Abra o **terminal** no Visual Studio Code selecionando **Exibir**  >  **terminal** no menu principal.</span><span class="sxs-lookup"><span data-stu-id="10ffb-121">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="10ffb-122">O **terminal** é aberto com o prompt de comando na pasta *ClassLibraryProjects* .</span><span class="sxs-lookup"><span data-stu-id="10ffb-122">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="10ffb-123">No **terminal**, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="10ffb-123">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="10ffb-124">A saída do terminal é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="10ffb-124">The terminal output looks like the following example:</span></span>

   ```output
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="10ffb-125">Criar um projeto de biblioteca de classes</span><span class="sxs-lookup"><span data-stu-id="10ffb-125">Create a class library project</span></span>

<span data-ttu-id="10ffb-126">Adicione um novo projeto de biblioteca de classes .NET chamado "StringLibrary" à solução.</span><span class="sxs-lookup"><span data-stu-id="10ffb-126">Add a new .NET class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="10ffb-127">No terminal, execute o seguinte comando para criar o projeto de biblioteca:</span><span class="sxs-lookup"><span data-stu-id="10ffb-127">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="10ffb-128">O `-o` `--output` comando ou especifica o local para posicionar a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="10ffb-128">The `-o` or `--output` command specifies the location to place the generated output.</span></span>

   <span data-ttu-id="10ffb-129">A saída do terminal é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="10ffb-129">The terminal output looks like the following example:</span></span>

   ```output
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj (in 328 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="10ffb-130">Execute o seguinte comando para adicionar o projeto de biblioteca à solução:</span><span class="sxs-lookup"><span data-stu-id="10ffb-130">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="10ffb-131">A saída do terminal é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="10ffb-131">The terminal output looks like the following example:</span></span>

   ```output
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="10ffb-132">Verifique se a biblioteca tem como destino o .NET 5.</span><span class="sxs-lookup"><span data-stu-id="10ffb-132">Check to make sure that the library targets .NET 5.</span></span> <span data-ttu-id="10ffb-133">No **Explorer**, abra *StringLibrary/StringLibrary. csproj*.</span><span class="sxs-lookup"><span data-stu-id="10ffb-133">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="10ffb-134">O `TargetFramework` elemento mostra que o projeto tem como alvo o .net 5,0.</span><span class="sxs-lookup"><span data-stu-id="10ffb-134">The `TargetFramework` element shows that the project targets .NET 5.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>net5.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="10ffb-135">Abra *Class1.cs* e substitua o código pelo código a seguir.</span><span class="sxs-lookup"><span data-stu-id="10ffb-135">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="10ffb-136">A biblioteca de classes, `UtilityLibraries.StringLibrary` , contém um método chamado `StartsWithUpper` .</span><span class="sxs-lookup"><span data-stu-id="10ffb-136">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="10ffb-137">Esse método retorna um <xref:System.Boolean> valor que indica se a instância atual da cadeia de caracteres começa com um caractere maiúsculo.</span><span class="sxs-lookup"><span data-stu-id="10ffb-137">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="10ffb-138">O padrão Unicode distingue caracteres maiúsculos de caracteres minúsculos.</span><span class="sxs-lookup"><span data-stu-id="10ffb-138">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="10ffb-139">O método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> retornará `true` se um caractere for maiúsculo.</span><span class="sxs-lookup"><span data-stu-id="10ffb-139">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="10ffb-140">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="10ffb-140">Save the file.</span></span>

1. <span data-ttu-id="10ffb-141">Execute o comando a seguir para compilar a solução e verificar se o projeto é compilado sem erros.</span><span class="sxs-lookup"><span data-stu-id="10ffb-141">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="10ffb-142">A saída do terminal é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="10ffb-142">The terminal output looks like the following example:</span></span>

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\net5.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="10ffb-143">Adicionar um aplicativo de console à solução</span><span class="sxs-lookup"><span data-stu-id="10ffb-143">Add a console app to the solution</span></span>

<span data-ttu-id="10ffb-144">Adicione um aplicativo de console que usa a biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="10ffb-144">Add a console application that uses the class library.</span></span> <span data-ttu-id="10ffb-145">O aplicativo solicitará que o usuário insira uma cadeia de caracteres e relate se a cadeia de caracteres começa com um caractere maiúsculo.</span><span class="sxs-lookup"><span data-stu-id="10ffb-145">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="10ffb-146">No terminal, execute o seguinte comando para criar o projeto de aplicativo de console:</span><span class="sxs-lookup"><span data-stu-id="10ffb-146">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="10ffb-147">A saída do terminal é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="10ffb-147">The terminal output looks like the following example:</span></span>

   ```output
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj (in 210 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="10ffb-148">Execute o seguinte comando para adicionar o projeto de aplicativo de console à solução:</span><span class="sxs-lookup"><span data-stu-id="10ffb-148">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="10ffb-149">A saída do terminal é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="10ffb-149">The terminal output looks like the following example:</span></span>

   ```output
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="10ffb-150">Abra o *Showcase/Program. cs* e substitua todo o código pelo código a seguir.</span><span class="sxs-lookup"><span data-stu-id="10ffb-150">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="10ffb-151">O código usa a variável `row` ​​para manter uma contagem do número de linhas de dados gravadas na janela do console.</span><span class="sxs-lookup"><span data-stu-id="10ffb-151">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="10ffb-152">Sempre que for maior ou igual a 25, o código limpará a janela do console e exibirá uma mensagem para o usuário.</span><span class="sxs-lookup"><span data-stu-id="10ffb-152">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="10ffb-153">O programa solicita que o usuário insira uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="10ffb-153">The program prompts the user to enter a string.</span></span> <span data-ttu-id="10ffb-154">Ele indica se a cadeia de caracteres começa com um caractere maiúsculo.</span><span class="sxs-lookup"><span data-stu-id="10ffb-154">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="10ffb-155">Se o usuário pressionar a tecla <kbd>Enter</kbd> sem inserir uma cadeia de caracteres, o aplicativo será encerrado e a janela do console será fechada.</span><span class="sxs-lookup"><span data-stu-id="10ffb-155">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="10ffb-156">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="10ffb-156">Save your changes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="10ffb-157">Adicionar uma referência ao projeto</span><span class="sxs-lookup"><span data-stu-id="10ffb-157">Add a project reference</span></span>

<span data-ttu-id="10ffb-158">Inicialmente, o novo projeto de aplicativo de console não tem acesso à biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="10ffb-158">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="10ffb-159">Para permitir que ele chame métodos na biblioteca de classes, crie uma referência de projeto para o projeto de biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="10ffb-159">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="10ffb-160">Execute o comando a seguir:</span><span class="sxs-lookup"><span data-stu-id="10ffb-160">Run the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="10ffb-161">A saída do terminal é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="10ffb-161">The terminal output looks like the following example:</span></span>

   ```output
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a><span data-ttu-id="10ffb-162">Execute o aplicativo</span><span class="sxs-lookup"><span data-stu-id="10ffb-162">Run the app</span></span>

1. <span data-ttu-id="10ffb-163">Execute o seguinte comando no terminal:</span><span class="sxs-lookup"><span data-stu-id="10ffb-163">Run the following command in the terminal:</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="10ffb-164">Experimente o programa digitando cadeias de caracteres e pressionando <kbd>Enter</kbd>e pressione <kbd>Enter</kbd> para sair.</span><span class="sxs-lookup"><span data-stu-id="10ffb-164">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="10ffb-165">A saída do terminal é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="10ffb-165">The terminal output looks like the following example:</span></span>

   ```output
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   a string that starts with a lowercase letter
   Input: a string that starts with a lowercase letter
   Begins with uppercase? : No
   ```

## <a name="additional-resources"></a><span data-ttu-id="10ffb-166">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="10ffb-166">Additional resources</span></span>

* [<span data-ttu-id="10ffb-167">Desenvolver bibliotecas com a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="10ffb-167">Develop libraries with the .NET CLI</span></span>](libraries.md)
* <span data-ttu-id="10ffb-168">[.Net Standard versões e plataformas às quais eles dão suporte](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="10ffb-168">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="10ffb-169">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="10ffb-169">Next steps</span></span>

<span data-ttu-id="10ffb-170">Neste tutorial, você criou uma solução, adicionou um projeto de biblioteca e adicionou um projeto de aplicativo de console que usa a biblioteca do.</span><span class="sxs-lookup"><span data-stu-id="10ffb-170">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="10ffb-171">No próximo tutorial, você adicionará um projeto de teste de unidade à solução.</span><span class="sxs-lookup"><span data-stu-id="10ffb-171">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="10ffb-172">Testar uma biblioteca de classes .NET com .NET usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="10ffb-172">Test a .NET class library with .NET using Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
