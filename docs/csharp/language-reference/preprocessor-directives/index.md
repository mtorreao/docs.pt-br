---
description: Diretivas de pré-processador do C#
title: Diretivas de pré-processador do C#
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 1269522b2687b76292f7b796a4ffc8095f23442e
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099055"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="4df10-103">Diretivas de pré-processador do C#</span><span class="sxs-lookup"><span data-stu-id="4df10-103">C# preprocessor directives</span></span>

<span data-ttu-id="4df10-104">Esta seção contém informações sobre as seguintes diretivas de pré-processador do C#:</span><span class="sxs-lookup"><span data-stu-id="4df10-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="4df10-105">#if</span><span class="sxs-lookup"><span data-stu-id="4df10-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="4df10-106">#else</span><span class="sxs-lookup"><span data-stu-id="4df10-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="4df10-107">#elif</span><span class="sxs-lookup"><span data-stu-id="4df10-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="4df10-108">#endif</span><span class="sxs-lookup"><span data-stu-id="4df10-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="4df10-109">#define</span><span class="sxs-lookup"><span data-stu-id="4df10-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="4df10-110">#undef</span><span class="sxs-lookup"><span data-stu-id="4df10-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="4df10-111">#warning</span><span class="sxs-lookup"><span data-stu-id="4df10-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="4df10-112">#error</span><span class="sxs-lookup"><span data-stu-id="4df10-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="4df10-113">#line</span><span class="sxs-lookup"><span data-stu-id="4df10-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="4df10-114">#nullable</span><span class="sxs-lookup"><span data-stu-id="4df10-114">#nullable</span></span>](./preprocessor-nullable.md)
- [<span data-ttu-id="4df10-115">#region</span><span class="sxs-lookup"><span data-stu-id="4df10-115">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="4df10-116">#endregion</span><span class="sxs-lookup"><span data-stu-id="4df10-116">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="4df10-117">#pragma</span><span class="sxs-lookup"><span data-stu-id="4df10-117">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="4df10-118">aviso de #pragma</span><span class="sxs-lookup"><span data-stu-id="4df10-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="4df10-119">soma de verificação de #pragma</span><span class="sxs-lookup"><span data-stu-id="4df10-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="4df10-120">Para obter mais informações e exemplos, consulte os tópicos individuais.</span><span class="sxs-lookup"><span data-stu-id="4df10-120">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="4df10-121">Embora o compilador não tenha um pré-processador separado, as diretivas descritas nesta seção são processadas como se houvesse um.</span><span class="sxs-lookup"><span data-stu-id="4df10-121">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="4df10-122">Eles são usados para ajudar a compilação condicional.</span><span class="sxs-lookup"><span data-stu-id="4df10-122">They are used to help in conditional compilation.</span></span> <span data-ttu-id="4df10-123">Ao contrário das diretivas de C e C++, não é possível usar essas diretivas para criar macros.</span><span class="sxs-lookup"><span data-stu-id="4df10-123">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="4df10-124">Uma diretiva de pré-processador deve ser a única instrução em uma linha.</span><span class="sxs-lookup"><span data-stu-id="4df10-124">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="4df10-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="4df10-125">See also</span></span>

- [<span data-ttu-id="4df10-126">Referência do C#</span><span class="sxs-lookup"><span data-stu-id="4df10-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4df10-127">Guia de programação C#</span><span class="sxs-lookup"><span data-stu-id="4df10-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
