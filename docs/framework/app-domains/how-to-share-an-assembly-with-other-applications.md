---
title: 'Como: compartilhar um assembly com outros aplicativos'
description: Consulte Como compartilhar um assembly com outros aplicativos no .NET. Os assemblies podem ser privados (o padrão) ou compartilhado. Para compartilhar um assembly, coloque-o no GAC.
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 1056f8b555713d5d67488537e6c06cc457c4d312
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242533"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a><span data-ttu-id="40443-105">Como: compartilhar um assembly com outros aplicativos</span><span class="sxs-lookup"><span data-stu-id="40443-105">How to: Share an assembly with other applications</span></span>

<span data-ttu-id="40443-106">Os assemblies podem ser particulares ou compartilhados: por padrão, a maioria dos programas simples consistem em um assembly particular porque eles não se destinam a serem usados por outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="40443-106">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  

<span data-ttu-id="40443-107">Para compartilhar um assembly com outros aplicativos, ele deve ser colocado no [GAC (cache de assembly global)](gac.md).</span><span class="sxs-lookup"><span data-stu-id="40443-107">In order to share an assembly with other applications, it must be placed in the [global assembly cache (GAC)](gac.md).</span></span>  
  
<span data-ttu-id="40443-108">Para compartilhar um assembly:</span><span class="sxs-lookup"><span data-stu-id="40443-108">To share an assembly:</span></span>
  
1. <span data-ttu-id="40443-109">Crie o assembly.</span><span class="sxs-lookup"><span data-stu-id="40443-109">Create your assembly.</span></span> <span data-ttu-id="40443-110">Para obter mais informações, consulte [criar assemblies](../../standard/assembly/create.md).</span><span class="sxs-lookup"><span data-stu-id="40443-110">For more information, see [Create assemblies](../../standard/assembly/create.md).</span></span>  
  
2. <span data-ttu-id="40443-111">Atribua um nome forte ao assembly.</span><span class="sxs-lookup"><span data-stu-id="40443-111">Assign a strong name to your assembly.</span></span> <span data-ttu-id="40443-112">Para obter mais informações, consulte [como assinar um assembly com um nome forte](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="40443-112">For more information, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>  
  
3. <span data-ttu-id="40443-113">Atribua informações de versão ao assembly.</span><span class="sxs-lookup"><span data-stu-id="40443-113">Assign version information to your assembly.</span></span> <span data-ttu-id="40443-114">Para obter mais informações, consulte [controle de versão do assembly](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="40443-114">For more information, see [Assembly versioning](../../standard/assembly/versioning.md).</span></span>  
  
4. <span data-ttu-id="40443-115">Adicione seu assembly ao cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="40443-115">Add your assembly to the global assembly cache.</span></span> <span data-ttu-id="40443-116">Para obter mais informações, consulte [como: instalar um assembly no cache de assembly global](install-assembly-into-gac.md).</span><span class="sxs-lookup"><span data-stu-id="40443-116">For more information, see [How to: Install an assembly into the global assembly cache](install-assembly-into-gac.md).</span></span>  
  
5. <span data-ttu-id="40443-117">Acesse os tipos contidos no assembly de outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="40443-117">Access the types contained in the assembly from other applications.</span></span> <span data-ttu-id="40443-118">Para obter mais informações, consulte [como referenciar um assembly de nome forte](../../standard/assembly/reference-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="40443-118">For more information, see [How to: Reference a strong-named assembly](../../standard/assembly/reference-strong-named.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40443-119">Veja também</span><span class="sxs-lookup"><span data-stu-id="40443-119">See also</span></span>

- [<span data-ttu-id="40443-120">Guia de programação em C#</span><span class="sxs-lookup"><span data-stu-id="40443-120">C# programming guide</span></span>](../../../api/index.md)
- [<span data-ttu-id="40443-121">Conceitos de programação (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40443-121">Programming concepts (Visual Basic)</span></span>](../../../api/index.md)
- [<span data-ttu-id="40443-122">Programar com assemblies</span><span class="sxs-lookup"><span data-stu-id="40443-122">Program with assemblies</span></span>](../../standard/assembly/index.md)
