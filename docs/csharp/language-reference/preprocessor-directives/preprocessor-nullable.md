---
description: '#Nullable-referência C#'
title: '#Nullable-referência C#'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099456"
---
# <a name="nullable-c-reference"></a><span data-ttu-id="3342f-103">#nullable (referência C#)</span><span class="sxs-lookup"><span data-stu-id="3342f-103">#nullable (C# Reference)</span></span>

<span data-ttu-id="3342f-104">A `#nullable` diretiva de pré-processador define o *contexto de anotação anulável* e o *contexto de aviso anulável*.</span><span class="sxs-lookup"><span data-stu-id="3342f-104">The `#nullable` preprocessor directive sets the *nullable annotation context* and *nullable warning context*.</span></span> <span data-ttu-id="3342f-105">Essa diretiva controla se as anotações anuláveis têm efeito e se são fornecidos avisos de nulidade.</span><span class="sxs-lookup"><span data-stu-id="3342f-105">This directive controls whether nullable annotations have effect, and whether nullability warnings are given.</span></span> <span data-ttu-id="3342f-106">Cada contexto é *desabilitado* ou *habilitado*.</span><span class="sxs-lookup"><span data-stu-id="3342f-106">Each context is either *disabled* or *enabled*.</span></span>

<span data-ttu-id="3342f-107">Ambos os contextos podem ser especificados no nível do projeto (fora do código-fonte do C#).</span><span class="sxs-lookup"><span data-stu-id="3342f-107">Both contexts can be specified at the project level (outside of C# source code).</span></span> <span data-ttu-id="3342f-108">A `#nullable` diretiva controla os contextos de anotação e de aviso e tem precedência sobre as configurações de nível de projeto.</span><span class="sxs-lookup"><span data-stu-id="3342f-108">The `#nullable` directive controls the annotation and warning contexts and takes precedence over the project-level settings.</span></span> <span data-ttu-id="3342f-109">Uma diretiva define os contextos que ele controla até que outra diretiva o substitua, ou até o final do arquivo de origem.</span><span class="sxs-lookup"><span data-stu-id="3342f-109">A directive sets the context(s) it controls until another directive overrides it, or until the end of the source file.</span></span>

<span data-ttu-id="3342f-110">O efeito das diretivas é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3342f-110">The effect of the directives is as follows:</span></span>

- <span data-ttu-id="3342f-111">`#nullable disable`: Define a anotação anulável e contextos de aviso como *desabilitado*.</span><span class="sxs-lookup"><span data-stu-id="3342f-111">`#nullable disable`: Sets the nullable annotation and warning contexts to *disabled*.</span></span>
- <span data-ttu-id="3342f-112">`#nullable enable`: Define a anotação anulável e contextos de aviso como *habilitado*.</span><span class="sxs-lookup"><span data-stu-id="3342f-112">`#nullable enable`: Sets the nullable annotation and warning contexts to *enabled*.</span></span>
- <span data-ttu-id="3342f-113">`#nullable restore`: Restaura os contextos de anotação e de aviso anuláveis para as configurações do projeto.</span><span class="sxs-lookup"><span data-stu-id="3342f-113">`#nullable restore`: Restores the nullable annotation and warning contexts to project settings.</span></span>
- <span data-ttu-id="3342f-114">`#nullable disable annotations`: Define o contexto de anotação anulável como *desabilitado*.</span><span class="sxs-lookup"><span data-stu-id="3342f-114">`#nullable disable annotations`: Sets the nullable annotation context to *disabled*.</span></span>
- <span data-ttu-id="3342f-115">`#nullable enable annotations`: Define o contexto de anotação anulável como *habilitado*.</span><span class="sxs-lookup"><span data-stu-id="3342f-115">`#nullable enable annotations`: Sets the nullable annotation context to *enabled*.</span></span>
- <span data-ttu-id="3342f-116">`#nullable restore annotations`: Restaura o contexto de anotação anulável para as configurações do projeto.</span><span class="sxs-lookup"><span data-stu-id="3342f-116">`#nullable restore annotations`: Restores the nullable annotation context to project settings.</span></span>
- <span data-ttu-id="3342f-117">`#nullable disable warnings`: Define o contexto de aviso anulável como *desabilitado*.</span><span class="sxs-lookup"><span data-stu-id="3342f-117">`#nullable disable warnings`: Sets the nullable warning context to *disabled*.</span></span>
- <span data-ttu-id="3342f-118">`#nullable enable warnings`: Define o contexto de aviso anulável como *habilitado*.</span><span class="sxs-lookup"><span data-stu-id="3342f-118">`#nullable enable warnings`: Sets the nullable warning context to *enabled*.</span></span>
- <span data-ttu-id="3342f-119">`#nullable restore warnings`: Restaura o contexto de aviso anulável para as configurações do projeto.</span><span class="sxs-lookup"><span data-stu-id="3342f-119">`#nullable restore warnings`: Restores the nullable warning context to project settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="3342f-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="3342f-120">See also</span></span>

- [<span data-ttu-id="3342f-121">Referência do C#</span><span class="sxs-lookup"><span data-stu-id="3342f-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3342f-122">Guia de programação C#</span><span class="sxs-lookup"><span data-stu-id="3342f-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3342f-123">Diretivas de pré-processador do C#</span><span class="sxs-lookup"><span data-stu-id="3342f-123">C# Preprocessor Directives</span></span>](./index.md)
