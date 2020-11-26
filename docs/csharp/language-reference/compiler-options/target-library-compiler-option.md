---
description: -target:library (opções do compilador C#)
title: -target:library (opções do compilador C#)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 0f5b1e1bec8fd601bf111e1c2c64adf22d0a064e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193719"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="db76e-103">-target:library (opções do compilador C#)</span><span class="sxs-lookup"><span data-stu-id="db76e-103">-target:library (C# Compiler Options)</span></span>

<span data-ttu-id="db76e-104">A opção **-target:library** faz com que o compilador crie uma DLL (biblioteca de vínculo dinâmico) em vez de um EXE (arquivo executável).</span><span class="sxs-lookup"><span data-stu-id="db76e-104">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db76e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="db76e-105">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="db76e-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="db76e-106">Remarks</span></span>  

 <span data-ttu-id="db76e-107">A DLL será criada com a extensão .dll.</span><span class="sxs-lookup"><span data-stu-id="db76e-107">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="db76e-108">A menos que seja especificado de outra forma com a opção [-out](./out-compiler-option.md), o nome do arquivo de saída usa o nome do primeiro arquivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="db76e-108">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="db76e-109">Quando especificado na linha de comando, todos os arquivos até a próxima opção **-out** ou **-target:module** são usados para criar o arquivo .dll.</span><span class="sxs-lookup"><span data-stu-id="db76e-109">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="db76e-110">Ao criar um arquivo .dll, um método [Main](../../programming-guide/main-and-command-args/index.md) não é necessário.</span><span class="sxs-lookup"><span data-stu-id="db76e-110">When building a .dll file, a [Main](../../programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="db76e-111">Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="db76e-111">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="db76e-112">Abra a página **Propriedades** do projeto.</span><span class="sxs-lookup"><span data-stu-id="db76e-112">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="db76e-113">Clique na página de propriedades do **Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="db76e-113">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="db76e-114">Modifique a propriedade **Tipo de saída**.</span><span class="sxs-lookup"><span data-stu-id="db76e-114">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="db76e-115">Para obter informações sobre como definir essa opção do compilador programaticamente, consulte <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="db76e-115">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db76e-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="db76e-116">Example</span></span>  

 <span data-ttu-id="db76e-117">Compile `in.cs`, criando `in.dll`:</span><span class="sxs-lookup"><span data-stu-id="db76e-117">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="db76e-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="db76e-118">See also</span></span>

- [<span data-ttu-id="db76e-119">-Target (opções do compilador C#)</span><span class="sxs-lookup"><span data-stu-id="db76e-119">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="db76e-120">Opções do compilador de C#</span><span class="sxs-lookup"><span data-stu-id="db76e-120">C# Compiler Options</span></span>](./index.md)
