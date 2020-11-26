---
description: -target:module (opções do compilador C#)
title: -target:module (opções do compilador C#)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: d8691e5e4477dbbe989344469b44382d5e0e7c8b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193602"
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="e9d4a-103">-target:module (opções do compilador C#)</span><span class="sxs-lookup"><span data-stu-id="e9d4a-103">-target:module (C# Compiler Options)</span></span>

<span data-ttu-id="e9d4a-104">Essa opção faz com que o compilador não gere um manifesto do assembly.</span><span class="sxs-lookup"><span data-stu-id="e9d4a-104">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d4a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e9d4a-105">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="e9d4a-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="e9d4a-106">Remarks</span></span>  

 <span data-ttu-id="e9d4a-107">Por padrão, o arquivo de saída criado por meio da compilação com essa opção terá uma extensão .netmodule.</span><span class="sxs-lookup"><span data-stu-id="e9d4a-107">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="e9d4a-108">Um arquivo que não tem um manifesto do assembly não pode ser carregado pelo tempo de execução do .NET.</span><span class="sxs-lookup"><span data-stu-id="e9d4a-108">A file that does not have an assembly manifest cannot be loaded by the .NET runtime.</span></span> <span data-ttu-id="e9d4a-109">No entanto, esse arquivo pode ser incorporado no manifesto do assembly de um assembly por meio de [-addmodule](./addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e9d4a-109">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="e9d4a-110">Se mais de um módulo for criado em uma única compilação, tipos [internos](../keywords/internal.md) em um módulo estarão disponíveis para outros módulos na compilação.</span><span class="sxs-lookup"><span data-stu-id="e9d4a-110">If more than one module is created in a single compilation, [internal](../keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="e9d4a-111">Quando o código em um módulo referenciar tipos `internal` em outro módulo, os dois módulos deverão ser incorporados em um manifesto do assembly, por meio de **-addmodule**.</span><span class="sxs-lookup"><span data-stu-id="e9d4a-111">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="e9d4a-112">Não há suporte para a criação de um módulo no ambiente de desenvolvimento do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e9d4a-112">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="e9d4a-113">Para obter informações sobre como definir essa opção do compilador programaticamente, consulte <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9d4a-113">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9d4a-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e9d4a-114">Example</span></span>  

 <span data-ttu-id="e9d4a-115">Compile `in.cs`, criando `in.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="e9d4a-115">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9d4a-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="e9d4a-116">See also</span></span>

- [<span data-ttu-id="e9d4a-117">-Target (opções do compilador C#)</span><span class="sxs-lookup"><span data-stu-id="e9d4a-117">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="e9d4a-118">Opções do compilador de C#</span><span class="sxs-lookup"><span data-stu-id="e9d4a-118">C# Compiler Options</span></span>](./index.md)
