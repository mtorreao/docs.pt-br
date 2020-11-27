---
title: 'Como: Configurar um domínio do aplicativo'
description: Configure um domínio de aplicativo no .NET. Você pode fornecer ao CLR informações de configuração para um novo domínio de aplicativo usando a classe AppDomainSetup.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
ms.openlocfilehash: bbda1f75da6b994c54cd71c56f16615a3758859b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271506"
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="b2af1-104">Como: Configurar um domínio do aplicativo</span><span class="sxs-lookup"><span data-stu-id="b2af1-104">How to: Configure an Application Domain</span></span>

<span data-ttu-id="b2af1-105">Você pode fornecer o Common Language Runtime com informações de configuração para um novo domínio de aplicativo usando a classe <xref:System.AppDomainSetup>.</span><span class="sxs-lookup"><span data-stu-id="b2af1-105">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="b2af1-106">Ao criar seus próprios domínios de aplicativo, a propriedade mais importante é <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2af1-106">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="b2af1-107">As outras propriedades **AppDomainSetup** são usadas principalmente por hosts de runtime para configurar um domínio de aplicativo específico.</span><span class="sxs-lookup"><span data-stu-id="b2af1-107">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="b2af1-108">A propriedade **ApplicationBase** define o diretório raiz do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b2af1-108">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="b2af1-109">Quando o runtime precisar atender a uma solicitação de tipo, ele investigará em busca do assembly que contém o tipo no diretório especificado pela propriedade **ApplicationBase**.</span><span class="sxs-lookup"><span data-stu-id="b2af1-109">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2af1-110">Um novo domínio de aplicativo herdará apenas a propriedade **ApplicationBase** do criador.</span><span class="sxs-lookup"><span data-stu-id="b2af1-110">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="b2af1-111">O exemplo a seguir cria uma instância da classe **AppDomainSetup**, usa essa classe para criar um novo domínio de aplicativo, escreve as informações no console e então descarrega o domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b2af1-111">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2af1-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b2af1-112">Example</span></span>  

 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b2af1-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b2af1-113">See also</span></span>

- [<span data-ttu-id="b2af1-114">Programação com domínios do aplicativo</span><span class="sxs-lookup"><span data-stu-id="b2af1-114">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="b2af1-115">Usando domínios do aplicativo</span><span class="sxs-lookup"><span data-stu-id="b2af1-115">Using Application Domains</span></span>](use.md)
