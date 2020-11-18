---
title: Como lançar exceções explicitamente
description: Saiba como lançar uma exceção explicitamente no .NET usando a instrução C# throw ou a instrução Visual Basic throw.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
ms.openlocfilehash: 37ba5f952d621ff2e209a3bac375b62894c944a7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828043"
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="14d13-103">Como gerar exceções explicitamente</span><span class="sxs-lookup"><span data-stu-id="14d13-103">How to explicitly throw exceptions</span></span>

<span data-ttu-id="14d13-104">Você pode lançar uma exceção explicitamente usando o C# [`throw`](../../csharp/language-reference/keywords/throw.md) ou a [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) instrução Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="14d13-104">You can explicitly throw an exception using the C# [`throw`](../../csharp/language-reference/keywords/throw.md) or the Visual Basic [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) statement.</span></span> <span data-ttu-id="14d13-105">Você também pode lançar novamente uma exceção capturada usando a instrução `throw`.</span><span class="sxs-lookup"><span data-stu-id="14d13-105">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="14d13-106">É uma boa prática adicionar informações a uma exceção que é lançada novamente para fornecer mais informações durante a depuração.</span><span class="sxs-lookup"><span data-stu-id="14d13-106">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="14d13-107">O exemplo de código a seguir usa um bloco `try`/`catch` para capturar uma possível <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="14d13-107">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="14d13-108">Após o bloco `try`, há um bloco `catch` que captura a <xref:System.IO.FileNotFoundException> e grava uma mensagem no console se o arquivo de dados não é encontrado.</span><span class="sxs-lookup"><span data-stu-id="14d13-108">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="14d13-109">A próxima instrução é a instrução `throw`, que gera uma nova <xref:System.IO.FileNotFoundException> e adiciona informações de texto à exceção.</span><span class="sxs-lookup"><span data-stu-id="14d13-109">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="14d13-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="14d13-110">See also</span></span>

- [<span data-ttu-id="14d13-111">Exceções</span><span class="sxs-lookup"><span data-stu-id="14d13-111">Exceptions</span></span>](index.md)
