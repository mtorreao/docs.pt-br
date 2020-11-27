---
title: Criar um Provedor de Automação de Interface de Usuário do Lado do Cliente
description: Veja um exemplo de como criar um provedor de automação de interface do usuário do lado do cliente. O exemplo implementa um provedor do lado do cliente simples para uma janela de console.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: 17a6deca2efc67d1409e89f7accf7a3b89a27807
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276536"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="e4822-104">Criar um Provedor de Automação de Interface de Usuário do Lado do Cliente</span><span class="sxs-lookup"><span data-stu-id="e4822-104">Create a Client-Side UI Automation Provider</span></span>

> [!NOTE]
> <span data-ttu-id="e4822-105">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="e4822-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e4822-106">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="e4822-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="e4822-107">Este tópico contém um código de exemplo que mostra como implementar um provedor de automação de interface do usuário do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="e4822-107">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4822-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e4822-108">Example</span></span>  

 <span data-ttu-id="e4822-109">O código de exemplo a seguir pode ser incorporado em uma DLL (biblioteca de vínculo dinâmico) que implementa um provedor do lado do cliente muito simples para uma janela de console.</span><span class="sxs-lookup"><span data-stu-id="e4822-109">The following example code can be built into a dynamic-link library (DLL) that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="e4822-110">O código não tem nenhuma funcionalidade útil, mas destina-se a demonstrar as etapas básicas na configuração de um assembly de provedor que pode ser registrado por um aplicativo cliente de automação de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="e4822-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="e4822-111">Veja também</span><span class="sxs-lookup"><span data-stu-id="e4822-111">See also</span></span>

- [<span data-ttu-id="e4822-112">Visão Geral dos Provedores de Automação de Interface do Usuário</span><span class="sxs-lookup"><span data-stu-id="e4822-112">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="e4822-113">Registrar um Módulo Provedor do Lado do Cliente</span><span class="sxs-lookup"><span data-stu-id="e4822-113">Register a Client-Side Provider Assembly</span></span>](register-a-client-side-provider-assembly.md)
