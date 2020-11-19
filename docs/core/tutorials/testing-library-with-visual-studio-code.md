---
title: Testar uma biblioteca de classes .NET usando Visual Studio Code
description: Saiba como usar Visual Studio Code e a CLI do .NET para criar e executar um projeto de teste de unidade para uma biblioteca de classes .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 4528bd203ae03988a1d1d80a7e904e94e68c1d04
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915850"
---
# <a name="tutorial-test-a-net-class-library-using-visual-studio-code"></a><span data-ttu-id="1bd9b-103">Tutorial: testar uma biblioteca de classes .NET usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1bd9b-103">Tutorial: Test a .NET class library using Visual Studio Code</span></span>

<span data-ttu-id="1bd9b-104">Este tutorial mostra como automatizar o teste de unidade adicionando um projeto de teste a uma solução.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-104">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1bd9b-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1bd9b-105">Prerequisites</span></span>

- <span data-ttu-id="1bd9b-106">Este tutorial funciona com a solução que você cria em [criar uma biblioteca de classes .NET usando Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="1bd9b-106">This tutorial works with the solution that you create in [Create a .NET class library using Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="1bd9b-107">Crie um projeto de teste de unidade</span><span class="sxs-lookup"><span data-stu-id="1bd9b-107">Create a unit test project</span></span>

<span data-ttu-id="1bd9b-108">As unidade de teste fornecem testes de software automatizados durante o desenvolvimento e a publicação.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-108">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="1bd9b-109">A estrutura de teste que você usa neste tutorial é MSTest.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-109">The testing framework that you use in this tutorial is MSTest.</span></span> <span data-ttu-id="1bd9b-110">[MSTest](https://github.com/Microsoft/testfx-docs) é uma das três estruturas de teste que você pode escolher.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="1bd9b-111">Os outros são [xUnit](https://xunit.net/) e [NUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="1bd9b-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="1bd9b-112">Inicie o Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-112">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="1bd9b-113">Abra a `ClassLibraryProjects` solução que você criou em [criar uma biblioteca de classes .net usando Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="1bd9b-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET class library using Visual Studio Code](library-with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="1bd9b-114">Crie um projeto de teste de unidade chamado "StringLibraryTest".</span><span class="sxs-lookup"><span data-stu-id="1bd9b-114">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="1bd9b-115">O modelo de projeto cria um arquivo UnitTest1.cs com o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-115">The project template creates a UnitTest1.cs file with the following code:</span></span>

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

   namespace StringLibraryTest
   {
       [TestClass]
       public class UnitTest1
       {
           [TestMethod]
           public void TestMethod1()
           {
           }
       }
   }
   ```

   <span data-ttu-id="1bd9b-116">O código-fonte criado pelo modelo de teste de unidade faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-116">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="1bd9b-117">Ele importa o namespace <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contém os tipos usados para o teste de unidade.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-117">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="1bd9b-118">Ele aplica o atributo<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> à classe `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-118">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="1bd9b-119">Ele aplica o <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> atributo a ser definido `TestMethod1` .</span><span class="sxs-lookup"><span data-stu-id="1bd9b-119">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="1bd9b-120">Cada método marcado com [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) em uma classe de teste marcada com [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) é executado automaticamente quando o teste de unidade é executado.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-120">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="1bd9b-121">Adicione o projeto de teste à solução.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-121">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

## <a name="add-a-project-reference"></a><span data-ttu-id="1bd9b-122">Adicionar uma referência ao projeto</span><span class="sxs-lookup"><span data-stu-id="1bd9b-122">Add a project reference</span></span>

<span data-ttu-id="1bd9b-123">Para que o projeto de teste funcione com a `StringLibrary` classe, adicione uma referência no `StringLibraryTest` projeto ao `StringLibrary` projeto.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-123">For the test project to work with the `StringLibrary` class, add a reference in the `StringLibraryTest` project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="1bd9b-124">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-124">Run the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="1bd9b-125">Adicionar e executar métodos de teste de unidade</span><span class="sxs-lookup"><span data-stu-id="1bd9b-125">Add and run unit test methods</span></span>

<span data-ttu-id="1bd9b-126">Quando o Visual Studio executa um teste de unidade, ele executa cada método marcado com o <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> atributo em uma classe marcada com o  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-126">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="1bd9b-127">Um método de teste termina quando a primeira falha é encontrada ou quando todos os testes contidos no método foram bem-sucedidos.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-127">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="1bd9b-128">Os testes mais comuns chamam membros da classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-128">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="1bd9b-129">Muitos métodos assert incluem pelo menos dois parâmetros, um deles é o resultado esperado do teste, e o outro é o resultado real do teste.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-129">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="1bd9b-130">Alguns dos `Assert` métodos chamados mais frequentemente da classe são mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-130">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="1bd9b-131">Métodos assert</span><span class="sxs-lookup"><span data-stu-id="1bd9b-131">Assert methods</span></span>     | <span data-ttu-id="1bd9b-132">Função</span><span class="sxs-lookup"><span data-stu-id="1bd9b-132">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="1bd9b-133">Verifica se os dois valores ou objetos são iguais.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-133">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="1bd9b-134">A declaração falhará se os valores ou objetos não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-134">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="1bd9b-135">Verifica se duas variáveis de objeto se referem ao mesmo objeto.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-135">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="1bd9b-136">A assert falhará se as variáveis se referirem a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-136">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="1bd9b-137">Verifica se uma condição é `false`.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-137">Verifies that a condition is `false`.</span></span> <span data-ttu-id="1bd9b-138">O assert falhará se a condição for `true`.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-138">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="1bd9b-139">Verifica se um objeto não está `null` .</span><span class="sxs-lookup"><span data-stu-id="1bd9b-139">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="1bd9b-140">A assert falhará se o objeto for `null`.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-140">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="1bd9b-141">Você também pode usar o <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> método em um método de teste para indicar o tipo de exceção que ele deve lançar.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-141">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="1bd9b-142">O teste falhará se a exceção especificada não for lançada.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-142">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="1bd9b-143">Ao testar o método `StringLibrary.StartsWithUpper`, você quer fornecer um número de cadeias de caracteres que comecem com um caractere maiúsculo.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-143">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="1bd9b-144">Você espera que o método retorne `true` nesses casos, para que possa chamar o método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-144">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1bd9b-145">Da mesma forma, você deseja fornecer um número de cadeias de caracteres que comecem com algo diferente de um caractere maiúsculo.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-145">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="1bd9b-146">Você espera que o método retorne `false` nesses casos, para que possa chamar o método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-146">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1bd9b-147">Como o método de biblioteca lida com cadeias de caracteres, você também deseja certificar-se de que ele manipula com êxito uma [cadeia de caracteres vazia ( `String.Empty` )](xref:System.String.Empty) e uma `null` cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-147">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="1bd9b-148">Uma cadeia de caracteres vazia é aquela que não tem caracteres e cujo número <xref:System.String.Length> é 0.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-148">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="1bd9b-149">Uma `null` cadeia de caracteres é aquela que não foi inicializada.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-149">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="1bd9b-150">Você pode chamar `StartsWithUpper` diretamente como um método estático e passar um único <xref:System.String> argumento.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-150">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="1bd9b-151">Ou você pode chamar `StartsWithUpper` como um método de extensão em uma `string` variável atribuída a `null` .</span><span class="sxs-lookup"><span data-stu-id="1bd9b-151">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="1bd9b-152">Você definirá três métodos, cada um deles chamará um <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> método para cada elemento em uma matriz de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-152">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="1bd9b-153">Você chamará uma sobrecarga de método que permite especificar uma mensagem de erro a ser exibida em caso de falha de teste.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-153">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="1bd9b-154">A mensagem identifica a cadeia de caracteres que causou a falha.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-154">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="1bd9b-155">Para criar os métodos de teste:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-155">To create the test methods:</span></span>

1. <span data-ttu-id="1bd9b-156">Abra *StringLibraryTest/UnitTest1. cs* e substitua todo o código pelo código a seguir.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-156">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="1bd9b-157">O teste de caracteres maiúsculos no `TestStartsWithUpper` método inclui a letra maiúscula grega alfa (u + 0391) e a letra maiúscula cirílica em (u + 041C).</span><span class="sxs-lookup"><span data-stu-id="1bd9b-157">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="1bd9b-158">O teste de caracteres minúsculos no `TestDoesNotStartWithUpper` método inclui a letra grega pequena alfa (u + 03B1) e a letra cirílica minúscula Ghe (u + 0433).</span><span class="sxs-lookup"><span data-stu-id="1bd9b-158">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="1bd9b-159">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-159">Save your changes.</span></span>

1. <span data-ttu-id="1bd9b-160">Execute os testes:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-160">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="1bd9b-161">A saída do terminal mostra que todos os testes passaram.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-161">The terminal output shows that all tests passed.</span></span>

   ```output
   Starting test execution, please wait...
   A total of 1 test files matched the specified pattern.

   Passed!  - Failed:     0, Passed:     3, Skipped:     0, Total:     3, Duration: 3 ms - StringLibraryTest.dll (net5.0)
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="1bd9b-162">Lidar com falhas de teste</span><span class="sxs-lookup"><span data-stu-id="1bd9b-162">Handle test failures</span></span>

<span data-ttu-id="1bd9b-163">Se você estiver fazendo o TDD (desenvolvimento controlado por teste), você escreverá testes primeiro e eles falharão na primeira vez em que forem executados.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-163">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="1bd9b-164">Em seguida, você adiciona código ao aplicativo que torna o teste com sucesso.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-164">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="1bd9b-165">Para este tutorial, você criou o teste depois de gravar o código do aplicativo que ele valida, para que você não tenha visto o teste falhar.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-165">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="1bd9b-166">Para validar que um teste falha quando você espera que ele falhe, adicione um valor inválido para a entrada de teste.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-166">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="1bd9b-167">Modifique a matriz `words` no método `TestDoesNotStartWithUpper` para incluir a cadeia de caracteres “Error”.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-167">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="1bd9b-168">Execute os testes:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-168">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="1bd9b-169">A saída do terminal mostra que um teste falha e fornece uma mensagem de erro para o teste com falha: "Assert. IsFalse falhou.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-169">The terminal output shows that one test fails, and it provides an error message for the failed test: "Assert.IsFalse failed.</span></span> <span data-ttu-id="1bd9b-170">Esperado para 'Error': false, real: True".</span><span class="sxs-lookup"><span data-stu-id="1bd9b-170">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="1bd9b-171">Devido à falha, nenhuma cadeia de caracteres na matriz após o "erro" foi testada.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-171">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   ```output
   Starting test execution, please wait...
   A total of 1 test files matched the specified pattern.
     Failed TestDoesNotStartWithUpper [28 ms]
     Error Message:
      Assert.IsFalse failed. Expected for 'Error': false; Actual: True
     Stack Trace:
        at StringLibraryTest.UnitTest1.TestDoesNotStartWithUpper() in C:\ClassLibraryProjects\StringLibraryTest\UnitTest1.cs:line 33

   Failed!  - Failed:     1, Passed:     2, Skipped:     0, Total:     3, Duration: 31 ms - StringLibraryTest.dll (net5.0)
   ```

1. <span data-ttu-id="1bd9b-172">Remova a cadeia de caracteres "Error" que você adicionou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-172">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="1bd9b-173">Execute novamente o teste e os testes são aprovados.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-173">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="1bd9b-174">Testar a versão de lançamento da biblioteca</span><span class="sxs-lookup"><span data-stu-id="1bd9b-174">Test the Release version of the library</span></span>

<span data-ttu-id="1bd9b-175">Agora que todos os testes passaram durante a execução da compilação de depuração da biblioteca, execute o testa um tempo adicional em relação à compilação da versão da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-175">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="1bd9b-176">Vários fatores, incluindo as otimizações do compilador, podem produzir um comportamento diferente entre as compilações de Depuração e Lançamento.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-176">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="1bd9b-177">Execute os testes com a configuração de Build de versão:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-177">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="1bd9b-178">Os testes são aprovados.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-178">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="1bd9b-179">Depurar testes</span><span class="sxs-lookup"><span data-stu-id="1bd9b-179">Debug tests</span></span>

<span data-ttu-id="1bd9b-180">Se você estiver usando Visual Studio Code como o IDE, poderá usar o mesmo processo mostrado em [depurar um aplicativo de console .NET usando Visual Studio Code](debugging-with-visual-studio-code.md) para depurar o código usando o projeto de teste de unidade.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-180">If you're using Visual Studio Code as your IDE, you can use the same process shown in [Debug a .NET console application using Visual Studio Code](debugging-with-visual-studio-code.md) to debug code using your unit test project.</span></span> <span data-ttu-id="1bd9b-181">Em vez de iniciar o projeto de aplicativo de *demonstração* , abra *StringLibraryTest/UnitTest1. cs* e selecione **executar todos os testes** entre as linhas 7 e 8.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-181">Instead of starting the *ShowCase* app project, open *StringLibraryTest/UnitTest1.cs*, and select **Run All Tests** between lines 7 and 8.</span></span> <span data-ttu-id="1bd9b-182">Se você não conseguir encontrá-lo, pressione <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> para abrir a paleta de comandos e digite **recarregar janela**.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-182">If you're unable to find it, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> to open the command palette and enter **Reload Window**.</span></span>

<span data-ttu-id="1bd9b-183">Visual Studio Code inicia o projeto de teste com o depurador anexado.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-183">Visual Studio Code starts the test project with the debugger attached.</span></span> <span data-ttu-id="1bd9b-184">A execução será interrompida em qualquer ponto de interrupção que você adicionou ao projeto de teste ou ao código de biblioteca subjacente.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-184">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1bd9b-185">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1bd9b-185">Additional resources</span></span>

* [<span data-ttu-id="1bd9b-186">Teste de unidade no .NET</span><span class="sxs-lookup"><span data-stu-id="1bd9b-186">Unit testing in .NET</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="1bd9b-187">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="1bd9b-187">Next steps</span></span>

<span data-ttu-id="1bd9b-188">Neste tutorial, você testou uma unidade de biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-188">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="1bd9b-189">Você pode tornar a biblioteca disponível para outras pessoas publicando-a no [NuGet](https://nuget.org) como um pacote.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-189">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="1bd9b-190">Para saber como, siga um tutorial do NuGet:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-190">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1bd9b-191">Criar e publicar um pacote usando a CLI dotnet</span><span class="sxs-lookup"><span data-stu-id="1bd9b-191">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="1bd9b-192">Se você publicar uma biblioteca como um pacote NuGet, outras pessoas poderão instalá-la e usá-la.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-192">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="1bd9b-193">Para saber como, siga um tutorial do NuGet:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-193">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1bd9b-194">Instalar e usar um pacote usando a CLI do dotnet</span><span class="sxs-lookup"><span data-stu-id="1bd9b-194">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="1bd9b-195">Uma biblioteca não precisa ser distribuída como um pacote.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-195">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="1bd9b-196">Ele pode ser agrupado com um aplicativo de console que o utiliza.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-196">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="1bd9b-197">Para saber como publicar um aplicativo de console, consulte o tutorial anterior nesta série:</span><span class="sxs-lookup"><span data-stu-id="1bd9b-197">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1bd9b-198">Publicar um aplicativo de console .NET usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1bd9b-198">Publish a .NET console application using Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
