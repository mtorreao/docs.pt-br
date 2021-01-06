---
description: Tipos de referência – Referência em C#
title: Tipos de referência – Referência em C#
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 075ec5ecd8f71f5cb85bab0e2baff56409709191
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899607"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="78b34-103">Tipos de referência (Referência em C#)</span><span class="sxs-lookup"><span data-stu-id="78b34-103">Reference types (C# Reference)</span></span>

<span data-ttu-id="78b34-104">Há dois tipos em C#: tipos de referência e valor.</span><span class="sxs-lookup"><span data-stu-id="78b34-104">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="78b34-105">Variáveis de tipos de referência armazenam referências em seus dados (objetos) enquanto que variáveis de tipos de valor contém diretamente seus dados.</span><span class="sxs-lookup"><span data-stu-id="78b34-105">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="78b34-106">Com tipos de referência, duas variáveis podem fazer referência ao mesmo objeto; portanto, operações em uma variável podem afetar o objeto referenciado pela outra variável.</span><span class="sxs-lookup"><span data-stu-id="78b34-106">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="78b34-107">Com tipos de valor, cada variável tem sua própria cópia dos dados e as operações em uma variável não podem afetar a outra (exceto no caso das variáveis de parâmetros in, ref e out. Confira o modificador de parâmetro [in](in-parameter-modifier.md), [ref](ref.md) e [out](out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="78b34-107">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="78b34-108">As seguintes palavras-chaves são usadas para declarar tipos de referência:</span><span class="sxs-lookup"><span data-stu-id="78b34-108">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="78b34-109">class</span><span class="sxs-lookup"><span data-stu-id="78b34-109">class</span></span>](class.md)

- [<span data-ttu-id="78b34-110">interface</span><span class="sxs-lookup"><span data-stu-id="78b34-110">interface</span></span>](interface.md)

- [<span data-ttu-id="78b34-111">delegate</span><span class="sxs-lookup"><span data-stu-id="78b34-111">delegate</span></span>](../builtin-types/reference-types.md)
- [<span data-ttu-id="78b34-112">gravável</span><span class="sxs-lookup"><span data-stu-id="78b34-112">record</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="78b34-113">O C# também oferece os seguintes tipos de referência internos:</span><span class="sxs-lookup"><span data-stu-id="78b34-113">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="78b34-114">dinâmico</span><span class="sxs-lookup"><span data-stu-id="78b34-114">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="78b34-115">object</span><span class="sxs-lookup"><span data-stu-id="78b34-115">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="78b34-116">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="78b34-116">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="78b34-117">Veja também</span><span class="sxs-lookup"><span data-stu-id="78b34-117">See also</span></span>

- [<span data-ttu-id="78b34-118">Referência do C#</span><span class="sxs-lookup"><span data-stu-id="78b34-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="78b34-119">Palavras-chave do C#</span><span class="sxs-lookup"><span data-stu-id="78b34-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="78b34-120">Tipos de ponteiro</span><span class="sxs-lookup"><span data-stu-id="78b34-120">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="78b34-121">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="78b34-121">Value types</span></span>](../builtin-types/value-types.md)
