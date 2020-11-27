---
title: 'Como: Criar um domínio do aplicativo'
description: Examine como criar um domínio de aplicativo no .NET. Você pode criar um domínio de aplicativo para carregar assemblies para gerenciar pessoalmente ou criar um para executar código.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
ms.openlocfilehash: fb022511ee395a9312e4dbaf7c0beee03c9b4569
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264082"
---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="1bc3d-104">Como: Criar um domínio do aplicativo</span><span class="sxs-lookup"><span data-stu-id="1bc3d-104">How to: Create an Application Domain</span></span>

<span data-ttu-id="1bc3d-105">Um host Common Language Runtime cria domínios de aplicativos automaticamente quando eles são necessários.</span><span class="sxs-lookup"><span data-stu-id="1bc3d-105">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="1bc3d-106">No entanto, você pode criar seus próprios domínios dos aplicativos e carregá-los nos assemblies que você deseja gerenciar pessoalmente.</span><span class="sxs-lookup"><span data-stu-id="1bc3d-106">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="1bc3d-107">Você também pode criar domínios do aplicativo do qual o código é executado.</span><span class="sxs-lookup"><span data-stu-id="1bc3d-107">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="1bc3d-108">Crie um novo domínio do aplicativo usando um dos métodos **CreateDomain** sobrecarregados na classe <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1bc3d-108">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="1bc3d-109">Você pode dar ao domínio do aplicativo um nome e referenciá-lo por esse nome.</span><span class="sxs-lookup"><span data-stu-id="1bc3d-109">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="1bc3d-110">O exemplo a seguir cria um novo domínio do aplicativo, atribui a ele o nome `MyDomain` e, em seguida, imprime o nome do domínio do host e o domínio do aplicativo filho recém-criado no console.</span><span class="sxs-lookup"><span data-stu-id="1bc3d-110">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bc3d-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1bc3d-111">Example</span></span>  

 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1bc3d-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1bc3d-112">See also</span></span>

- [<span data-ttu-id="1bc3d-113">Programação com domínios do aplicativo</span><span class="sxs-lookup"><span data-stu-id="1bc3d-113">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="1bc3d-114">Usando domínios do aplicativo</span><span class="sxs-lookup"><span data-stu-id="1bc3d-114">Using Application Domains</span></span>](use.md)
