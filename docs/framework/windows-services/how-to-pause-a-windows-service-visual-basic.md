---
title: 'Como: Pausar um Serviço Windows (Visual Basic)'
description: Leia como usar o componente ServiceController para pausar um serviço do Windows (como o serviço de administração do IIS) em um computador local com Visual Basic.
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
ms.openlocfilehash: a8c3074fdbf8d7b948b00def4e6a664310fc6ec2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270583"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="8dfc7-103">Como: Pausar um Serviço Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8dfc7-103">How to: Pause a Windows Service (Visual Basic)</span></span>

<span data-ttu-id="8dfc7-104">Este exemplo usa o componente <xref:System.ServiceProcess.ServiceController> para pausar o serviço de administração do IIS no computador local.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-104">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dfc7-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8dfc7-105">Example</span></span>  

 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="8dfc7-106">Este exemplo de código também está disponível como um snippet de código do IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-106">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="8dfc7-107">No selecionador de snippet de código, ele está localizado em **Sistema Operacional Windows &gt; Serviços Windows**.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-107">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="8dfc7-108">Para obter mais informações, consulte [Snippets de Código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="8dfc7-108">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8dfc7-109">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="8dfc7-109">Compiling the Code</span></span>  

 <span data-ttu-id="8dfc7-110">Este exemplo requer:</span><span class="sxs-lookup"><span data-stu-id="8dfc7-110">This example requires:</span></span>  
  
- <span data-ttu-id="8dfc7-111">Uma referência do projeto para System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-111">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="8dfc7-112">Acesso aos membros do namespace <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-112">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="8dfc7-113">Adicione uma instrução `Imports` se você não está qualificando totalmente os nomes de membros em seu código.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-113">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="8dfc7-114">Para obter mais informações, consulte [Instrução Imports (tipo e namespace .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="8dfc7-114">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8dfc7-115">Programação robusta</span><span class="sxs-lookup"><span data-stu-id="8dfc7-115">Robust Programming</span></span>  

 <span data-ttu-id="8dfc7-116">A propriedade <xref:System.ServiceProcess.ServiceController.MachineName%2A> da classe <xref:System.ServiceProcess.ServiceController> é o computador local por padrão.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-116">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="8dfc7-117">Para referenciar os Serviços Windows em outro computador, altere a propriedade <xref:System.ServiceProcess.ServiceController.MachineName%2A> para o nome desse computador.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-117">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="8dfc7-118">As seguintes condições podem causar uma exceção:</span><span class="sxs-lookup"><span data-stu-id="8dfc7-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="8dfc7-119">O serviço não pode ser colocado em pausa.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-119">The service cannot be paused.</span></span> <span data-ttu-id="8dfc7-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="8dfc7-120">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="8dfc7-121">Ocorreu um erro ao acessar uma API do sistema.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="8dfc7-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="8dfc7-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8dfc7-123">Segurança do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8dfc7-123">.NET Framework Security</span></span>  

 <span data-ttu-id="8dfc7-124">O controle de serviços no computador pode ser restringido usando o <xref:System.ServiceProcess.ServiceControllerPermissionAccess> para definir permissões no <xref:System.ServiceProcess.ServiceControllerPermission>.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="8dfc7-125">O acesso a informações de serviço pode ser restringido usando o <xref:System.Security.Permissions.PermissionState> para definir permissões em <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="8dfc7-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dfc7-126">Veja também</span><span class="sxs-lookup"><span data-stu-id="8dfc7-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [<span data-ttu-id="8dfc7-127">Como: Continuar um serviço Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8dfc7-127">How to: Continue a Windows Service (Visual Basic)</span></span>](how-to-continue-a-windows-service-visual-basic.md)
