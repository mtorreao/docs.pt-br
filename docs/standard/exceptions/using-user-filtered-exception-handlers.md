---
title: Usar manipuladores de exceção filtrados pelo usuário
description: Saiba como usar manipuladores de exceção filtrados pelo usuário em C# e Visual Basic.
ms.date: 12/14/2020
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
dev_langs:
- csharp
- vb
ms.openlocfilehash: 2dba43ad2fc685a6555ab43fc973814fd7f359a3
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512665"
---
# <a name="use-user-filtered-exception-handlers"></a><span data-ttu-id="f1708-103">Usar manipuladores de exceção filtrados pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f1708-103">Use user-filtered exception handlers</span></span>

<span data-ttu-id="f1708-104">Os manipuladores de exceção filtrados por usuário capturam e tratam exceções com base nos requisitos que você define para a exceção.</span><span class="sxs-lookup"><span data-stu-id="f1708-104">User-filtered exception handlers catch and handle exceptions based on requirements you define for the exception.</span></span> <span data-ttu-id="f1708-105">Esses manipuladores usam a `catch` instrução com a `when` palavra-chave ( `Catch` e `When` em Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="f1708-105">These handlers use the `catch` statement with the `when` keyword (`Catch` and `When` in Visual Basic).</span></span>  
  
 <span data-ttu-id="f1708-106">Essa técnica é útil quando um objeto de exceção em particular corresponde a vários erros.</span><span class="sxs-lookup"><span data-stu-id="f1708-106">This technique is useful when a particular exception object corresponds to multiple errors.</span></span> <span data-ttu-id="f1708-107">Nesse caso, o objeto normalmente tem uma propriedade que contém o código de erro específico associado ao erro.</span><span class="sxs-lookup"><span data-stu-id="f1708-107">In this case, the object typically has a property that contains the specific error code associated with the error.</span></span> <span data-ttu-id="f1708-108">Você pode usar a propriedade código de erro na expressão para selecionar apenas o erro específico que você deseja tratar nessa `catch` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f1708-108">You can use the error code property in the expression to select only the particular error you want to handle in that `catch` clause.</span></span>  
  
 <span data-ttu-id="f1708-109">O exemplo a seguir ilustra a `catch` / `when` instrução.</span><span class="sxs-lookup"><span data-stu-id="f1708-109">The following example illustrates the `catch`/`when` statement.</span></span>

```csharp
try
{
    //Try statements.  
}
catch (Exception ex) when (ex.Message.Contains("404"))
{
    //Catch statements.
}
```  
  
```vb
Try  
    'Try statements.  
    Catch When Err = VBErr_ClassLoadException
    'Catch statements.
End Try  
```  
  
 <span data-ttu-id="f1708-110">A expressão da cláusula filtrada pelo usuário não é restrita de nenhuma forma.</span><span class="sxs-lookup"><span data-stu-id="f1708-110">The expression of the user-filtered clause is not restricted in any way.</span></span> <span data-ttu-id="f1708-111">Se ocorrer uma exceção durante a execução da expressão filtrada pelo usuário, essa exceção será descartada e será considerado que a expressão do filtro foi avaliada como falsa.</span><span class="sxs-lookup"><span data-stu-id="f1708-111">If an exception occurs during execution of the user-filtered expression, that exception is discarded and the filter expression is considered to have evaluated to false.</span></span> <span data-ttu-id="f1708-112">Nesse caso, o Common Language Runtime continua a pesquisar um manipulador para a exceção atual.</span><span class="sxs-lookup"><span data-stu-id="f1708-112">In this case, the common language runtime continues the search for a handler for the current exception.</span></span>  
  
## <a name="combine-the-specific-exception-and-the-user-filtered-clauses"></a><span data-ttu-id="f1708-113">Combinar a exceção específica e as cláusulas filtradas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f1708-113">Combine the specific exception and the user-filtered clauses</span></span>  

 <span data-ttu-id="f1708-114">Uma `catch` instrução pode conter a exceção específica e as cláusulas filtradas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f1708-114">A `catch` statement can contain both the specific exception and the user-filtered clauses.</span></span> <span data-ttu-id="f1708-115">O runtime testa primeiro a exceção específica.</span><span class="sxs-lookup"><span data-stu-id="f1708-115">The runtime tests the specific exception first.</span></span> <span data-ttu-id="f1708-116">Se a exceção específica for bem-sucedida, o runtime executará o filtro do usuário.</span><span class="sxs-lookup"><span data-stu-id="f1708-116">If the specific exception succeeds, the runtime executes the user filter.</span></span> <span data-ttu-id="f1708-117">O filtro genérico pode conter uma referência à variável declarada no filtro da classe.</span><span class="sxs-lookup"><span data-stu-id="f1708-117">The generic filter can contain a reference to the variable declared in the class filter.</span></span> <span data-ttu-id="f1708-118">Observe que a ordem das duas cláusulas do filtro não pode ser invertida.</span><span class="sxs-lookup"><span data-stu-id="f1708-118">Note that the order of the two filter clauses cannot be reversed.</span></span>  
  
 <span data-ttu-id="f1708-119">O exemplo a seguir mostra uma exceção específica na instrução **Catch** , bem como a cláusula filtrada pelo usuário usando a palavra-chave **When** .</span><span class="sxs-lookup"><span data-stu-id="f1708-119">The following example shows a specific exception in the **catch** statement as well as the user-filtered clause using the **when** keyword.</span></span>  
  
```csharp
try
{
    //Try statements.  
}
catch (System.Net.Http.HttpRequestException ex) when (ex.Message.Contains("404"))
{
    //Catch statements.
}
```  
  
```vb
Try  
    'Try statements.
    Catch cle As ClassLoadException When cle.IsRecoverable()  
    'Catch statements.
End Try  
```  

## <a name="see-also"></a><span data-ttu-id="f1708-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f1708-120">See also</span></span>

- [<span data-ttu-id="f1708-121">Exceções</span><span class="sxs-lookup"><span data-stu-id="f1708-121">Exceptions</span></span>](index.md)
