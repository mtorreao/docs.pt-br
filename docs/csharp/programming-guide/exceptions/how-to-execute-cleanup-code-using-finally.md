---
title: Como executar o código de limpeza usando o guia de programação finally-C#
description: Saiba como executar o código de limpeza usando uma instrução ' Finally '. As instruções finally garantem que qualquer limpeza necessária de objetos ocorra imediatamente.
ms.date: 12/09/2020
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: e9b5d3086488d3f7e3c0709317d6fafd15c439e8
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110176"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="3b1af-104">Como executar o código de limpeza usando finally (guia de programação C#)</span><span class="sxs-lookup"><span data-stu-id="3b1af-104">How to execute cleanup code using finally (C# Programming Guide)</span></span>

<span data-ttu-id="3b1af-105">O propósito de uma instrução `finally` é garantir que a limpeza necessária de objetos, normalmente objetos que estão mantendo recursos externos, ocorra imediatamente, mesmo que uma exceção seja lançada.</span><span class="sxs-lookup"><span data-stu-id="3b1af-105">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="3b1af-106">Um exemplo dessa limpeza é chamar <xref:System.IO.Stream.Close%2A> em um <xref:System.IO.FileStream> imediatamente após o uso, em vez de esperar que o objeto passe pela coleta de lixo feita pelo Common Language Runtime, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3b1af-106">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>

:::code language="csharp" source="snippets/exceptions/Program.cs" ID="NoCleanup":::

## <a name="example"></a><span data-ttu-id="3b1af-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3b1af-107">Example</span></span>

<span data-ttu-id="3b1af-108">Para transformar o código anterior em uma instrução `try-catch-finally`, o código de limpeza é separado do código funcional, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="3b1af-108">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>

:::code language="csharp" source="snippets/exceptions/Program.cs" ID="WithCleanup":::

<span data-ttu-id="3b1af-109">Como uma exceção pode ocorrer a qualquer momento dentro do `try` bloco antes da `OpenWrite()` chamada, ou a `OpenWrite()` chamada em si falhar, não temos certeza de que o arquivo está aberto quando tentamos fechá-lo.</span><span class="sxs-lookup"><span data-stu-id="3b1af-109">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we aren't guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="3b1af-110">O `finally` bloco adiciona uma verificação para certificar-se de que o <xref:System.IO.FileStream> objeto não é `null` antes de chamar o <xref:System.IO.Stream.Close%2A> método.</span><span class="sxs-lookup"><span data-stu-id="3b1af-110">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object isn't `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="3b1af-111">Sem a `null` verificação, o `finally` bloco poderia lançar seu próprio <xref:System.NullReferenceException> , mas gerar exceções em `finally` blocos deve ser evitado se for possível.</span><span class="sxs-lookup"><span data-stu-id="3b1af-111">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it's possible.</span></span>

<span data-ttu-id="3b1af-112">Uma conexão de banco de dados é outra boa candidata a ser fechada em um bloco `finally`.</span><span class="sxs-lookup"><span data-stu-id="3b1af-112">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="3b1af-113">Como o número de conexões permitidas para um servidor de banco de dados é, às vezes, limitado, você deve fechar conexões de banco de dados assim que possível.</span><span class="sxs-lookup"><span data-stu-id="3b1af-113">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="3b1af-114">Se uma exceção for lançada antes que você possa fechar a conexão, o uso do `finally` bloco será melhor do que aguardar a coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="3b1af-114">If an exception is thrown before you can close your connection, using the `finally` block is better than waiting for garbage collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b1af-115">Veja também</span><span class="sxs-lookup"><span data-stu-id="3b1af-115">See also</span></span>

- [<span data-ttu-id="3b1af-116">Instrução using</span><span class="sxs-lookup"><span data-stu-id="3b1af-116">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
- [<span data-ttu-id="3b1af-117">try-catch</span><span class="sxs-lookup"><span data-stu-id="3b1af-117">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="3b1af-118">try-finally</span><span class="sxs-lookup"><span data-stu-id="3b1af-118">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="3b1af-119">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="3b1af-119">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
