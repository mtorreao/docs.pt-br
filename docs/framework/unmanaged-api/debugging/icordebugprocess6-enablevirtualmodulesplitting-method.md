---
title: Método ICorDebugProcess6::EnableVirtualModuleSplitting
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
ms.openlocfilehash: 56795c6879d95253383c26c92e060f252a018914
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690194"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a><span data-ttu-id="c2dbf-102">Método ICorDebugProcess6::EnableVirtualModuleSplitting</span><span class="sxs-lookup"><span data-stu-id="c2dbf-102">ICorDebugProcess6::EnableVirtualModuleSplitting Method</span></span>

<span data-ttu-id="c2dbf-103">Habilita ou desabilita a divisão de módulo virtual.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-103">Enables or disables virtual module splitting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2dbf-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c2dbf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2dbf-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c2dbf-105">Parameters</span></span>  

 `enableSplitting`  
 <span data-ttu-id="c2dbf-106">`true` para habilitar a divisão de módulo virtual; `false` para desabilitá-la.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-106">`true` to enable virtual module splitting; `false` to disable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2dbf-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="c2dbf-107">Remarks</span></span>  

 <span data-ttu-id="c2dbf-108">A divisão do módulo virtual faz com que o [ICorDebug](icordebug-interface.md) reconheça módulos que foram mesclados em conjunto durante o processo de compilação e os apresenta como um grupo de módulos separados em vez de um único módulo grande.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-108">Virtual module splitting causes [ICorDebug](icordebug-interface.md) to recognize modules that were merged together during the build process and present them as a group of separate modules rather than a single large module.</span></span> <span data-ttu-id="c2dbf-109">Fazer isso altera o comportamento de vários métodos [ICorDebug](icordebug-interface.md) descritos abaixo.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-109">Doing this changes the behavior of various [ICorDebug](icordebug-interface.md) methods described below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2dbf-110">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-110">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="c2dbf-111">Esse método pode ser chamado e o valor de `enableSplitting` pode ser alterado a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-111">This method can be called and the value of `enableSplitting` can be changed at any time.</span></span> <span data-ttu-id="c2dbf-112">Ele não causa nenhuma alteração funcional com estado em um objeto [ICorDebug](icordebug-interface.md) , diferente de alterar o comportamento dos métodos listados na [divisão do módulo virtual e a seção APIs de depuração não gerenciada](#APIs) no momento em que eles são chamados.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-112">It does not cause any stateful functional changes in an [ICorDebug](icordebug-interface.md) object, other than altering the behavior of the methods listed in the [Virtual module splitting and the unmanaged debugging APIs](#APIs) section at the time they are called.</span></span> <span data-ttu-id="c2dbf-113">Usar módulos virtuais provoca uma perda de desempenho ao chamar esses métodos.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-113">Using virtual modules does incur a performance penalty when calling those methods.</span></span> <span data-ttu-id="c2dbf-114">Além disso, o cache na memória significativo dos metadados virtualizados pode ser necessário para implementar corretamente as APIs [IMetaDataImport](../metadata/imetadataimport-interface.md) , e esses caches podem ser retidos mesmo após a divisão do módulo virtual ser desativada.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-114">In addition, significant in-memory caching of the virtualized metadata may be required to correctly implement the [IMetaDataImport](../metadata/imetadataimport-interface.md) APIs, and these caches may be retained even after virtual module splitting has been turned off.</span></span>  
  
## <a name="terminology"></a><span data-ttu-id="c2dbf-115">Terminologia</span><span class="sxs-lookup"><span data-stu-id="c2dbf-115">Terminology</span></span>  

 <span data-ttu-id="c2dbf-116">Os seguintes termos são usados para descrever a divisão do módulo virtual:</span><span class="sxs-lookup"><span data-stu-id="c2dbf-116">The following terms are used when describing virtual module splitting:</span></span>  
  
 <span data-ttu-id="c2dbf-117">módulos de contêiner ou contêineres</span><span class="sxs-lookup"><span data-stu-id="c2dbf-117">container modules, or containers</span></span>  
 <span data-ttu-id="c2dbf-118">Os módulos agregados.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-118">The aggregate modules.</span></span>  
  
 <span data-ttu-id="c2dbf-119">submódulos ou módulos virtuais</span><span class="sxs-lookup"><span data-stu-id="c2dbf-119">sub-modules, or virtual modules</span></span>  
 <span data-ttu-id="c2dbf-120">Os módulos encontrados em um contêiner.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-120">The modules found in a container.</span></span>  
  
 <span data-ttu-id="c2dbf-121">módulos regulares</span><span class="sxs-lookup"><span data-stu-id="c2dbf-121">regular modules</span></span>  
 <span data-ttu-id="c2dbf-122">Módulos que não foram mesclados no tempo de compilação.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-122">Modules that were not merged at build time.</span></span> <span data-ttu-id="c2dbf-123">Eles não são módulos de contêiner nem submódulos.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-123">They are neither container modules nor sub-modules.</span></span>  
  
 <span data-ttu-id="c2dbf-124">Os módulos do contêiner e submódulos são representados por objetos de interface ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-124">Both container modules and sub-modules are represented by ICorDebugModule interface objects.</span></span> <span data-ttu-id="c2dbf-125">No entanto, o comportamento da interface é ligeiramente diferente em cada caso, como \<x-ref to section> descreve a seção.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-125">However, the behavior of the interface is slightly different in each case, as the \<x-ref to section> section describes.</span></span>  
  
## <a name="modules-and-assemblies"></a><span data-ttu-id="c2dbf-126">Módulos e assemblies</span><span class="sxs-lookup"><span data-stu-id="c2dbf-126">Modules and assemblies</span></span>  

 <span data-ttu-id="c2dbf-127">Vários assemblies de módulo não são suportados para cenários de mesclagem de assembly, portanto, há um relacionamento individual entre um módulo e um assembly.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-127">Multi-module assemblies are not supported for assembly merging scenarios, so there is a one-to-one relationship between a module and an assembly.</span></span> <span data-ttu-id="c2dbf-128">Cada objeto ICorDebugModule, independentemente se ele representa um módulo de contêiner ou um submódulo, possui um objeto ICorDebugAssembly correspondente.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-128">Each ICorDebugModule object, regardless of whether it represents a container module or a sub-module, has a corresponding ICorDebugAssembly object.</span></span> <span data-ttu-id="c2dbf-129">O método [ICorDebugModule:: GetAssembly](icordebugmodule-getassembly-method.md) converte do módulo para o assembly.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-129">The [ICorDebugModule::GetAssembly](icordebugmodule-getassembly-method.md) method converts from the module to the assembly.</span></span> <span data-ttu-id="c2dbf-130">Para mapear na outra direção, o método [ICorDebugAssembly:: EnumerateModules](icordebugassembly-enumeratemodules-method.md) enumera somente 1 módulo.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-130">To map in the other direction, the [ICorDebugAssembly::EnumerateModules](icordebugassembly-enumeratemodules-method.md) method enumerates only 1 module.</span></span> <span data-ttu-id="c2dbf-131">Como o assembly e o module formam um par de ligação estreita nesse caso, os termos assembly e módulo se tornar sinônimos.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-131">Because assembly and module form a tightly coupled pair in this case, the terms assembly and module become largely interchangeable.</span></span>  
  
## <a name="behavioral-differences"></a><span data-ttu-id="c2dbf-132">Diferenças de comportamento</span><span class="sxs-lookup"><span data-stu-id="c2dbf-132">Behavioral differences</span></span>  

 <span data-ttu-id="c2dbf-133">Módulos de contêiner têm as seguintes características e comportamentos:</span><span class="sxs-lookup"><span data-stu-id="c2dbf-133">Container modules have the following behaviors and characteristics:</span></span>  
  
- <span data-ttu-id="c2dbf-134">Seus metadados para todos os submódulos constituintes é mesclado.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-134">Their metadata for all of the constituent sub-modules is merged together.</span></span>  
  
- <span data-ttu-id="c2dbf-135">Seus nomes de tipos podem ser danificados.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-135">Their type names may be mangled.</span></span>  
  
- <span data-ttu-id="c2dbf-136">O método [ICorDebugModule:: GetName](icordebugmodule-getname-method.md) retorna o caminho para um módulo em disco.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-136">The [ICorDebugModule::GetName](icordebugmodule-getname-method.md) method returns the path to an on-disk module.</span></span>  
  
- <span data-ttu-id="c2dbf-137">O método [ICorDebugModule:: GetSize](icordebugmodule-getsize-method.md) retorna o tamanho dessa imagem.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-137">The [ICorDebugModule::GetSize](icordebugmodule-getsize-method.md) method returns the size of that image.</span></span>  
  
- <span data-ttu-id="c2dbf-138">O método ICorDebugAssembly3.EnumerateContainedAssemblies lista os submódulos.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-138">The ICorDebugAssembly3.EnumerateContainedAssemblies method lists the sub-modules.</span></span>  
  
- <span data-ttu-id="c2dbf-139">O método ICorDebugAssembly3.GetContainerAssembly retorna `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-139">The ICorDebugAssembly3.GetContainerAssembly method returns `S_FALSE`.</span></span>  
  
 <span data-ttu-id="c2dbf-140">Submódulos têm as seguintes características e comportamentos:</span><span class="sxs-lookup"><span data-stu-id="c2dbf-140">Sub-modules have the following behaviors and characteristics:</span></span>  
  
- <span data-ttu-id="c2dbf-141">Eles têm um conjunto reduzido de metadados que corresponde apenas ao assembly original que foi mesclado.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-141">They have a reduced set of metadata that corresponds only to the original assembly that was merged.</span></span>  
  
- <span data-ttu-id="c2dbf-142">Os nomes de metadados não são danificados.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-142">The metadata names are not mangled.</span></span>  
  
- <span data-ttu-id="c2dbf-143">Os tokens de metadados dificilmente correspondem aos tokens do assembly original antes de ser mesclado no processo de compilação.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-143">Metadata tokens are unlikely to match the tokens in the original assembly before it was merged in the build process.</span></span>  
  
- <span data-ttu-id="c2dbf-144">O método [ICorDebugModule:: GetName](icordebugmodule-getname-method.md) retorna o nome do assembly, não um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-144">The [ICorDebugModule::GetName](icordebugmodule-getname-method.md) method returns the assembly name, not a file path.</span></span>  
  
- <span data-ttu-id="c2dbf-145">O método [ICorDebugModule:: GetSize](icordebugmodule-getsize-method.md) retorna o tamanho original da imagem não mesclada.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-145">The [ICorDebugModule::GetSize](icordebugmodule-getsize-method.md) method returns the original unmerged image size.</span></span>  
  
- <span data-ttu-id="c2dbf-146">O método ICorDebugModule3.EnumerateContainedAssemblies retorna `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-146">The ICorDebugModule3.EnumerateContainedAssemblies method returns `S_FALSE`.</span></span>  
  
- <span data-ttu-id="c2dbf-147">O método ICorDebugAssembly3.GetContainerAssembly retorna o módulo recipiente.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-147">The ICorDebugAssembly3.GetContainerAssembly method returns the containing module.</span></span>  
  
## <a name="interfaces-retrieved-from-modules"></a><span data-ttu-id="c2dbf-148">Interfaces obtidas de módulos</span><span class="sxs-lookup"><span data-stu-id="c2dbf-148">Interfaces retrieved from modules</span></span>  

 <span data-ttu-id="c2dbf-149">Uma variedade de interfaces pode ser criada ou obtida de módulos.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-149">A variety of interfaces can be created or retrieved from modules.</span></span> <span data-ttu-id="c2dbf-150">Entre eles estão:</span><span class="sxs-lookup"><span data-stu-id="c2dbf-150">Some of these include:</span></span>  
  
- <span data-ttu-id="c2dbf-151">Um objeto ICorDebugClass, que é retornado pelo método [ICorDebugModule:: GetClassFromToken](icordebugmodule-getclassfromtoken-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c2dbf-151">An ICorDebugClass object, which is returned by the [ICorDebugModule::GetClassFromToken](icordebugmodule-getclassfromtoken-method.md) method.</span></span>  
  
- <span data-ttu-id="c2dbf-152">Um objeto ICorDebugAssembly, que é retornado pelo método [ICorDebugModule:: GetAssembly](icordebugmodule-getassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c2dbf-152">An ICorDebugAssembly object, which is returned by the [ICorDebugModule::GetAssembly](icordebugmodule-getassembly-method.md) method.</span></span>  
  
 <span data-ttu-id="c2dbf-153">Esses objetos são sempre armazenados em cache por [ICorDebug](icordebug-interface.md), e eles terão a mesma identidade de ponteiro, independentemente de terem sido criados ou consultados a partir do módulo de contêiner ou de um submódulo.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-153">These objects are always cached by [ICorDebug](icordebug-interface.md), and they will have the same pointer identity regardless of whether they were created or queried from the container module or a sub-module.</span></span> <span data-ttu-id="c2dbf-154">O submódulo fornece uma exibição filtrada desses objetos em cache, não um cache separado com suas própria cópias.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-154">The sub-module provides a filtered view of these cached objects, not a separate cache with its own copies.</span></span>  
  
<a name="APIs"></a>

## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a><span data-ttu-id="c2dbf-155">Divisão do módulo virtual e APIs de depuração não gerenciadas</span><span class="sxs-lookup"><span data-stu-id="c2dbf-155">Virtual module splitting and the unmanaged debugging APIs</span></span>  

 <span data-ttu-id="c2dbf-156">A tabela a seguir mostra como a divisão de módulo virtual afeta o comportamento de outros métodos na API de depuração não gerenciada.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-156">The following table shows how virtual module splitting affects the behavior of other methods in the unmanaged debugging API.</span></span>  
  
|<span data-ttu-id="c2dbf-157">Método</span><span class="sxs-lookup"><span data-stu-id="c2dbf-157">Method</span></span>|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[<span data-ttu-id="c2dbf-158">ICorDebugFunction::GetModule</span><span class="sxs-lookup"><span data-stu-id="c2dbf-158">ICorDebugFunction::GetModule</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="c2dbf-159">Retorna o submódulo no qual essa função foi originalmente definida.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-159">Returns the sub-module this function was originally defined in</span></span>|<span data-ttu-id="c2dbf-160">Retorna o módulo recipiente ao qual essa função foi mesclada.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-160">Returns the container module this function was merged into</span></span>|  
|[<span data-ttu-id="c2dbf-161">ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="c2dbf-161">ICorDebugClass::GetModule</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="c2dbf-162">Retorna o submódulo no qual essa classe foi originalmente definida.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-162">Returns the sub-module this class was originally defined in.</span></span>|<span data-ttu-id="c2dbf-163">Retorna o módulo recipiente ao qual essa classe foi mesclada.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-163">Returns the container module this class was merged into.</span></span>|  
|<span data-ttu-id="c2dbf-164">ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="c2dbf-164">ICorDebugModuleDebugEvent::GetModule</span></span>|<span data-ttu-id="c2dbf-165">Retorna o módulo recipiente que foi carregado.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-165">Returns the container module that was loaded.</span></span> <span data-ttu-id="c2dbf-166">Submódulos não recebem eventos de carga independente dessa configuração.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-166">Sub-modules are not given load events regardless of this setting.</span></span>|<span data-ttu-id="c2dbf-167">Retorna o módulo recipiente que foi carregado.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-167">Returns the container module that was loaded.</span></span>|  
|[<span data-ttu-id="c2dbf-168">ICorDebugAppDomain::EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="c2dbf-168">ICorDebugAppDomain::EnumerateAssemblies</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="c2dbf-169">Retorna uma lista de sub-assemblies e assemblies regulares; nenhum assembly contêiner está incluído.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-169">Returns a list of sub-assemblies and regular assemblies; no container assemblies are included.</span></span> <span data-ttu-id="c2dbf-170">**Observação:**  Se algum assembly de contêiner estiver com símbolos ausentes, nenhum de seus subassemblys será enumerado.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-170">**Note:**  If any container assembly is missing symbols, none of its sub-assemblies will be enumerated.</span></span> <span data-ttu-id="c2dbf-171">Se qualquer assembly regular estiver com símbolos ausentes, ele pode ou não ser enumerado.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-171">If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|<span data-ttu-id="c2dbf-172">Retorna uma lista de assemblies recipientes e assemblies regulares; nenhum assembly contêiner está incluído.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-172">Returns a list of container assemblies and regular assemblies; no sub-assemblies are included.</span></span> <span data-ttu-id="c2dbf-173">**Observação:**  Se algum assembly regular tiver símbolos ausentes, ele poderá ou não ser enumerado.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-173">**Note:**  If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|  
|<span data-ttu-id="c2dbf-174">[ICorDebugCode:: GetCode](icordebugcode-getcode-method.md) (ao fazer referência somente ao código Il)</span><span class="sxs-lookup"><span data-stu-id="c2dbf-174">[ICorDebugCode::GetCode](icordebugcode-getcode-method.md) (when referring to IL code only)</span></span>|<span data-ttu-id="c2dbf-175">Retorna IL que seria válido em uma imagem de assembly pré-mesclagem.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-175">Returns IL that would be valid in a pre-merge assembly image.</span></span> <span data-ttu-id="c2dbf-176">Especificamente, qualquer tokens de metadados embutido serão corretamente tokens TypeRef ou MemberRef quando os tipos sendo mencionados não são definidos no módulo virtual que contém o IL.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-176">Specifically, any inline metadata tokens will correctly be TypeRef or MemberRef tokens when the types being referred to are not defined in the virtual module containing the IL.</span></span> <span data-ttu-id="c2dbf-177">Esses tokens TypeRef ou MemberRef podem ser pesquisados no objeto [IMetaDataImport](../metadata/imetadataimport-interface.md) para o objeto ICorDebugModule virtual correspondente.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-177">These TypeRef or MemberRef tokens can be looked up in the [IMetaDataImport](../metadata/imetadataimport-interface.md) object for the corresponding virtual ICorDebugModule object.</span></span>|<span data-ttu-id="c2dbf-178">Retorna o IL na imagem de assembly pós-mesclagem.</span><span class="sxs-lookup"><span data-stu-id="c2dbf-178">Returns the IL in the post-merge assembly image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2dbf-179">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2dbf-179">Requirements</span></span>  

 <span data-ttu-id="c2dbf-180">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2dbf-180">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2dbf-181">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2dbf-181">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2dbf-182">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2dbf-182">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2dbf-183">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2dbf-183">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2dbf-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="c2dbf-184">See also</span></span>

- [<span data-ttu-id="c2dbf-185">Interface ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="c2dbf-185">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="c2dbf-186">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="c2dbf-186">Debugging Interfaces</span></span>](debugging-interfaces.md)
