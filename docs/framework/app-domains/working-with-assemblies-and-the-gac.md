---
title: Trabalhando com assemblies e o cache de assemblies global
description: Trabalhe com assemblies e o GAC (cache de assembly global) no .NET. Examine os motivos pelos quais você pode querer instalar um assembly no GAC.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
ms.openlocfilehash: e27fdd7def2d234e1e8eb7557e869bf478d68210
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279305"
---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a><span data-ttu-id="fca60-104">Trabalhando com assemblies e o cache de assemblies global</span><span class="sxs-lookup"><span data-stu-id="fca60-104">Working with Assemblies and the Global Assembly Cache</span></span>

<span data-ttu-id="fca60-105">Se você pretender compartilhar um assembly com vários aplicativos, será necessário instalá-lo no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-105">If you intend to share an assembly among several applications, you can install it into the global assembly cache.</span></span> <span data-ttu-id="fca60-106">Cada computador em que o Common Language Runtime está instalado tem um cache de código em todo o computador.</span><span class="sxs-lookup"><span data-stu-id="fca60-106">Each computer where the common language runtime is installed has this machine-wide code cache.</span></span> <span data-ttu-id="fca60-107">O cache de assembly global armazena assemblies projetados especificamente para serem compartilhados por vários aplicativos no computador.</span><span class="sxs-lookup"><span data-stu-id="fca60-107">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span> <span data-ttu-id="fca60-108">Um assembly deve ter um nome forte para ser instalado no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-108">An assembly must have a strong name to be installed in the global assembly cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fca60-109">Assemblies colocados no cache de assembly global devem ter o mesmo nome de assembly e de arquivo (não incluindo a extensão de nome de arquivo).</span><span class="sxs-lookup"><span data-stu-id="fca60-109">Assemblies placed in the global assembly cache must have the same assembly name and file name (not including the file name extension).</span></span> <span data-ttu-id="fca60-110">Por exemplo, um assembly com o nome de myAssembly deve ter um nome de arquivo de myAssembly.exe ou myAssembly.dll.</span><span class="sxs-lookup"><span data-stu-id="fca60-110">For example, an assembly with the assembly name of myAssembly must have a file name of either myAssembly.exe or myAssembly.dll.</span></span>  
  
<span data-ttu-id="fca60-111">Você deve compartilhar assemblies instalando-os no cache de assembly global somente quando necessário.</span><span class="sxs-lookup"><span data-stu-id="fca60-111">You should share assemblies by installing them into the global assembly cache only when necessary.</span></span> <span data-ttu-id="fca60-112">Como diretriz geral, mantenha as dependências de um assembly particulares e localize os assemblies no diretório de aplicativo, a menos que o compartilhamento de um assembly seja explicitamente obrigatório.</span><span class="sxs-lookup"><span data-stu-id="fca60-112">As a general guideline, keep assembly dependencies private and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="fca60-113">Além disso, você não precisa instalar assemblies no cache de assembly global a fim de torná-los acessíveis para interoperabilidade COM ou código não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="fca60-113">In addition, you do not have to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
<span data-ttu-id="fca60-114">Há diversas razões para instalar um assembly no cache de assembly global:</span><span class="sxs-lookup"><span data-stu-id="fca60-114">There are several reasons why you might want to install an assembly into the global assembly cache:</span></span>  
  
- <span data-ttu-id="fca60-115">Local compartilhado.</span><span class="sxs-lookup"><span data-stu-id="fca60-115">Shared location.</span></span>  
  
     <span data-ttu-id="fca60-116">Assemblies que devem ser usados por aplicativos podem ser colocados no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-116">Assemblies that should be used by applications can be put in the global assembly cache.</span></span> <span data-ttu-id="fca60-117">Por exemplo, se todos os aplicativos devem usar um assembly localizado no cache de assembly global, uma declaração de política de versão pode adicionada ao arquivo Machine.config que redireciona referências para o assembly.</span><span class="sxs-lookup"><span data-stu-id="fca60-117">For example, if all applications should use an assembly located in the global assembly cache, a version policy statement can be added to the Machine.config file that redirects references to the assembly.</span></span>  
  
- <span data-ttu-id="fca60-118">Segurança do arquivo.</span><span class="sxs-lookup"><span data-stu-id="fca60-118">File security.</span></span>  
  
     <span data-ttu-id="fca60-119">Os administradores geralmente protegem o diretório systemroot usando uma ACL (Lista de Controle de Acesso) para controlar os acesso de gravação e de execução.</span><span class="sxs-lookup"><span data-stu-id="fca60-119">Administrators often protect the systemroot directory using an Access Control List (ACL) to control write and execute access.</span></span> <span data-ttu-id="fca60-120">Como o cache de assembly global é instalado em um diretório do systemroot, ele herda a ACL desse diretório.</span><span class="sxs-lookup"><span data-stu-id="fca60-120">Because the global assembly cache is installed in the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="fca60-121">É recomendável que apenas usuários com privilégios Administrador tenham permissão para excluir arquivos do cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-121">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
- <span data-ttu-id="fca60-122">Controle de versão lado a lado.</span><span class="sxs-lookup"><span data-stu-id="fca60-122">Side-by-side versioning.</span></span>  
  
     <span data-ttu-id="fca60-123">Várias cópias de assemblies com o mesmo nome, mas com informações diferentes de versão, podem ser mantidas no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-123">Multiple copies of assemblies with the same name but different version information can be maintained in the global assembly cache.</span></span>  
  
- <span data-ttu-id="fca60-124">Local adicional de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fca60-124">Additional search location.</span></span>  
  
     <span data-ttu-id="fca60-125">O Common Language Runtime verifica o cache de assembly global para um assembly que corresponde à solicitação de assembly antes de investigar ou usar as informações da base de código em um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="fca60-125">The common language runtime checks the global assembly cache for an assembly that matches the assembly request before probing or using the codebase information in a configuration file.</span></span>  
  
 <span data-ttu-id="fca60-126">Observe que há situações em que explicitamente não é recomendado instalar um assembly no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-126">Note that there are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="fca60-127">Se colocar um dos assemblies que compõem um aplicativo no cache de assembly global, você não poderá mais replicar nem instalar o aplicativo usando XCOPY para copiar o diretório do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fca60-127">If you place one of the assemblies that make up an application into the global assembly cache, you can no longer replicate or install the application by using XCOPY to copy the application directory.</span></span> <span data-ttu-id="fca60-128">Nesse caso, você também deve mover o assembly para o cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-128">In this case, you must also move the assembly into the global assembly cache.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fca60-129">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="fca60-129">In This Section</span></span>  

[<span data-ttu-id="fca60-130">Como instalar um assembly no cache de assembly global</span><span class="sxs-lookup"><span data-stu-id="fca60-130">How to: Install an Assembly into the Global Assembly Cache</span></span>](install-assembly-into-gac.md)  
<span data-ttu-id="fca60-131">Descreve as maneiras de instalar um assembly no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-131">Describes the ways to install an assembly into the global assembly cache.</span></span>  
  
[<span data-ttu-id="fca60-132">Como: Exibir o conteúdo do cache de assembly global</span><span class="sxs-lookup"><span data-stu-id="fca60-132">How to: View the Contents of the Global Assembly Cache</span></span>](how-to-view-the-contents-of-the-gac.md)  
<span data-ttu-id="fca60-133">Explica como usar a [Gacutil.exe (Ferramenta de Cache de Assembly Global)](../tools/gacutil-exe-gac-tool.md) para exibir o conteúdo do cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-133">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
[<span data-ttu-id="fca60-134">Como: Remover um assembly do cache de assembly global</span><span class="sxs-lookup"><span data-stu-id="fca60-134">How to: Remove an Assembly from the Global Assembly Cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)  
<span data-ttu-id="fca60-135">Explica como usar a [Gacutil.exe (Ferramenta de Cache de Assembly Global)](../tools/gacutil-exe-gac-tool.md) para remover um assembly do cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-135">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to remove an assembly from the global assembly cache.</span></span>  
  
[<span data-ttu-id="fca60-136">Usando componentes atendidos com o cache de assemblies global</span><span class="sxs-lookup"><span data-stu-id="fca60-136">Using Serviced Components with the Global Assembly Cache</span></span>](use-serviced-components-with-the-gac.md)  
<span data-ttu-id="fca60-137">Explica por que componentes de atendidos (componentes COM+ gerenciados) devem ser colocados no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-137">Explains why serviced components (managed COM+ components) should be placed in the global assembly cache.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fca60-138">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="fca60-138">Related Sections</span></span>  

[<span data-ttu-id="fca60-139">Criando assemblies</span><span class="sxs-lookup"><span data-stu-id="fca60-139">Creating Assemblies</span></span>](../../standard/assembly/create.md)  
<span data-ttu-id="fca60-140">Apresenta uma visão geral da criação de assemblies.</span><span class="sxs-lookup"><span data-stu-id="fca60-140">Provides an overview of creating assemblies.</span></span>  
  
[<span data-ttu-id="fca60-141">Cache de assemblies global</span><span class="sxs-lookup"><span data-stu-id="fca60-141">Global Assembly Cache</span></span>](gac.md)  
<span data-ttu-id="fca60-142">Descreve o cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fca60-142">Describes the global assembly cache.</span></span>  
  
[<span data-ttu-id="fca60-143">Como exibir o conteúdo de um assembly</span><span class="sxs-lookup"><span data-stu-id="fca60-143">How to: View Assembly Contents</span></span>](../../standard/assembly/view-contents.md)  
<span data-ttu-id="fca60-144">Explica como usar o [Ildasm.exe (IL Disassembler)](../tools/ildasm-exe-il-disassembler.md) para exibir informações MSIL (Microsoft Intermediate Language) em um assembly.</span><span class="sxs-lookup"><span data-stu-id="fca60-144">Explains how to use the [Ildasm.exe (IL Disassembler)](../tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in an assembly.</span></span>  
  
[<span data-ttu-id="fca60-145">Como o runtime localiza assemblies</span><span class="sxs-lookup"><span data-stu-id="fca60-145">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)  
<span data-ttu-id="fca60-146">Descreve como o Common Language Runtime localiza e carrega os assemblies que compõem seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fca60-146">Describes how the common language runtime locates and loads the assemblies that make up your application.</span></span>  
  
[<span data-ttu-id="fca60-147">Programação com assemblies</span><span class="sxs-lookup"><span data-stu-id="fca60-147">Programming with Assemblies</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="fca60-148">Descreve assemblies, os blocos de construção de aplicativos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="fca60-148">Describes assemblies, the building blocks of managed applications.</span></span>
