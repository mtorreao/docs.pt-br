---
title: CorFlags.exe (Ferramenta de Conversão de CorFlags)
description: Entenda CorFlags.exe, a ferramenta de conversão CorFlags. Essa ferramenta permite que você configure a seção CorFlags do cabeçalho de uma imagem executável portátil.
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: 3f9f2a71a7a33de13264ce60fa7ff6ea5832aace
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247181"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="f7238-104">CorFlags.exe (Ferramenta de Conversão de CorFlags)</span><span class="sxs-lookup"><span data-stu-id="f7238-104">CorFlags.exe (CorFlags Conversion Tool)</span></span>

<span data-ttu-id="f7238-105">A ferramenta Conversão CorFlags permite configurar a seção CorFlags do cabeçalho de uma imagem PE (Portable Executable).</span><span class="sxs-lookup"><span data-stu-id="f7238-105">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="f7238-106">Essa ferramenta é instalada automaticamente com o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f7238-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="f7238-107">Para executar a ferramenta, use o Prompt de Comando do Desenvolvedor para Visual Studio (ou o Prompt de Comando do Visual Studio no Windows 7).</span><span class="sxs-lookup"><span data-stu-id="f7238-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="f7238-108">Para obter mais informações, consulte [Prompts de Comando](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f7238-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="f7238-109">No prompt de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f7238-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7238-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f7238-110">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7238-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f7238-111">Parameters</span></span>  
  
|<span data-ttu-id="f7238-112">Parâmetro obrigatório</span><span class="sxs-lookup"><span data-stu-id="f7238-112">Required parameter</span></span>|<span data-ttu-id="f7238-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7238-113">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="f7238-114">O nome do assembly para o qual configurar o CorFlags.</span><span class="sxs-lookup"><span data-stu-id="f7238-114">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="f7238-115">Opção</span><span class="sxs-lookup"><span data-stu-id="f7238-115">Option</span></span>|<span data-ttu-id="f7238-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7238-116">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="f7238-117">Define o sinalizador 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="f7238-117">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="f7238-118">Limpa o sinalizador 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="f7238-118">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="f7238-119">Define o sinalizador 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="f7238-119">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="f7238-120">O aplicativo é executado como um processo 32 bits, mesmo em plataformas 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f7238-120">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="f7238-121">Defina esse sinalizador apenas em arquivos EXE.</span><span class="sxs-lookup"><span data-stu-id="f7238-121">Set this flag only on EXE files.</span></span> <span data-ttu-id="f7238-122">Se o sinalizador for definido em uma DLL, a DLL não será carregada em processos 64 bits, e uma exceção <xref:System.BadImageFormatException> será acionada.</span><span class="sxs-lookup"><span data-stu-id="f7238-122">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="f7238-123">Um arquivo EXE com esse sinalizador pode ser carregado em um processo 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f7238-123">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="f7238-124">Novidades no .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="f7238-124">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="f7238-125">Limpa o sinalizador 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="f7238-125">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="f7238-126">Novidades no .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="f7238-126">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="f7238-127">Exibe sintaxe de comando e opções para a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="f7238-127">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="f7238-128">Força uma atualização, mesmo que o assembly tenha nome forte.</span><span class="sxs-lookup"><span data-stu-id="f7238-128">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="f7238-129">**Importante:** se atualizar um assembly de nome forte, você deverá assiná-lo novamente antes de executar o código.</span><span class="sxs-lookup"><span data-stu-id="f7238-129">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="f7238-130">Exibe sintaxe de comando e opções para a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="f7238-130">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="f7238-131">Define o sinalizador ILONLY.</span><span class="sxs-lookup"><span data-stu-id="f7238-131">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="f7238-132">Limpa o sinalizador ILONLY.</span><span class="sxs-lookup"><span data-stu-id="f7238-132">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="f7238-133">Suprime a exibição do banner de inicialização da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7238-133">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="f7238-134">Reverte a versão do cabeçalho do CLR para 2.0.</span><span class="sxs-lookup"><span data-stu-id="f7238-134">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="f7238-135">Atualiza a versão do cabeçalho do CLR para 2.5.</span><span class="sxs-lookup"><span data-stu-id="f7238-135">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="f7238-136">**Observação:** os assemblies devem ter uma versão do cabeçalho do CLR 2.5 ou posterior para serem executados nativamente.</span><span class="sxs-lookup"><span data-stu-id="f7238-136">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7238-137">Comentários</span><span class="sxs-lookup"><span data-stu-id="f7238-137">Remarks</span></span>  

 <span data-ttu-id="f7238-138">Se nenhuma opção estiver especificada, a ferramenta Conversão CorFlags exibirá os sinalizadores para o assembly especificado.</span><span class="sxs-lookup"><span data-stu-id="f7238-138">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7238-139">Veja também</span><span class="sxs-lookup"><span data-stu-id="f7238-139">See also</span></span>

- [<span data-ttu-id="f7238-140">Ferramentas</span><span class="sxs-lookup"><span data-stu-id="f7238-140">Tools</span></span>](index.md)
- [<span data-ttu-id="f7238-141">Aplicativos de 64 bits</span><span class="sxs-lookup"><span data-stu-id="f7238-141">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="f7238-142">Prompts de comando</span><span class="sxs-lookup"><span data-stu-id="f7238-142">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
