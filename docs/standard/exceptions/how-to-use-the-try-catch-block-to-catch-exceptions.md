---
title: Como usar o bloco try-catch para capturar exceções
description: Use o bloco try para conter instruções que podem gerar ou gerar uma exceção. Coloque instruções para manipular exceções em um ou mais blocos catch.
ms.date: 02/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: cfe5b2b304cdb9efe7f0d91059fe1c279b4fa2dd
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828004"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="1838e-104">Como usar o bloco try/catch para capturar exceções</span><span class="sxs-lookup"><span data-stu-id="1838e-104">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="1838e-105">Colocar todas as instruções de código que podem elevar ou gerar uma exceção em um bloco `try` e posicionar instruções usadas para tratar a exceção ou exceções em um ou mais blocos `catch` abaixo do bloco `try`.</span><span class="sxs-lookup"><span data-stu-id="1838e-105">Place any code statements that might raise or throw an exception in a `try` block, and place statements used to handle the exception or exceptions in one or more `catch` blocks below the `try` block.</span></span> <span data-ttu-id="1838e-106">Cada bloco `catch` inclui o tipo de exceção e pode conter instruções adicionais necessárias para lidar com esse tipo de exceção.</span><span class="sxs-lookup"><span data-stu-id="1838e-106">Each `catch` block includes the exception type and can contain additional statements needed to handle that exception type.</span></span>

<span data-ttu-id="1838e-107">No exemplo a seguir, um <xref:System.IO.StreamReader> abre um arquivo chamado *data.txt* e recupera uma linha desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="1838e-107">In the following example, a <xref:System.IO.StreamReader> opens a file called *data.txt* and retrieves a line from the file.</span></span> <span data-ttu-id="1838e-108">Uma vez que o código pode gerar qualquer uma de três exceções, ele é colocado em um bloco `try`.</span><span class="sxs-lookup"><span data-stu-id="1838e-108">Since the code might throw any of three exceptions, it's placed in a `try` block.</span></span> <span data-ttu-id="1838e-109">Três blocos `catch` capturam as exceções e lidam com elas, exibindo os resultados no console.</span><span class="sxs-lookup"><span data-stu-id="1838e-109">Three `catch` blocks catch the exceptions and handle them by displaying the results to the console.</span></span>

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

<span data-ttu-id="1838e-110">O CLR (Common Language Runtime) captura exceções não manipuladas pelos blocos `catch`.</span><span class="sxs-lookup"><span data-stu-id="1838e-110">The Common Language Runtime (CLR) catches exceptions not handled by `catch` blocks.</span></span> <span data-ttu-id="1838e-111">Se uma exceção é capturada pelo CLR, um dos seguintes resultados pode ocorrer dependendo da configuração do CLR:</span><span class="sxs-lookup"><span data-stu-id="1838e-111">If an exception is caught by the CLR, one of the following results may occur depending on your CLR configuration:</span></span>

- <span data-ttu-id="1838e-112">Uma caixa de diálogo **Depurar** é exibida.</span><span class="sxs-lookup"><span data-stu-id="1838e-112">A **Debug** dialog box appears.</span></span>
- <span data-ttu-id="1838e-113">O programa interromperá a execução e uma caixa de diálogo será exibida com informações de exceção.</span><span class="sxs-lookup"><span data-stu-id="1838e-113">The program stops execution and a dialog box with exception information appears.</span></span>
- <span data-ttu-id="1838e-114">Um erro é impresso no [fluxo de saída de erro padrão](xref:System.Console.Error).</span><span class="sxs-lookup"><span data-stu-id="1838e-114">An error prints out to the [standard error output stream](xref:System.Console.Error).</span></span>

> [!NOTE]
> <span data-ttu-id="1838e-115">A maioria dos códigos pode lançar uma exceção, sendo que algumas exceções, tais como <xref:System.OutOfMemoryException>, podem ser geradas pelo próprio CLR, a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="1838e-115">Most code can throw an exception, and some exceptions, like <xref:System.OutOfMemoryException>, can be thrown by the CLR itself at any time.</span></span> <span data-ttu-id="1838e-116">Embora os aplicativos não precisem lidar com essas exceções, esteja ciente dessa possibilidade ao gravar bibliotecas para serem usadas por outros.</span><span class="sxs-lookup"><span data-stu-id="1838e-116">While applications aren't required to deal with these exceptions, be aware of the possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="1838e-117">Para obter sugestões sobre quando definir código em um bloco `try`, confira [Práticas recomendadas para exceções](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="1838e-117">For suggestions on when to set code in a `try` block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1838e-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="1838e-118">See also</span></span>

- [<span data-ttu-id="1838e-119">Exceções</span><span class="sxs-lookup"><span data-stu-id="1838e-119">Exceptions</span></span>](index.md)
- [<span data-ttu-id="1838e-120">Tratamento de erros de E/S no .NET</span><span class="sxs-lookup"><span data-stu-id="1838e-120">Handling I/O errors in .NET</span></span>](../io/handling-io-errors.md)
