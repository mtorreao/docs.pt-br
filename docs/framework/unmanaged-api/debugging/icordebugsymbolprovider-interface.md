---
title: Interface ICorDebugSymbolProvider
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: ff1f39be3d3db43f70cfa4a0711a3f42c180bc1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672078"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="78d5a-102">Interface ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="78d5a-102">ICorDebugSymbolProvider Interface</span></span>

<span data-ttu-id="78d5a-103">Fornece métodos que podem ser usados para recuperar informações de símbolo de depuração.</span><span class="sxs-lookup"><span data-stu-id="78d5a-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="78d5a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="78d5a-104">Methods</span></span>  
  
|<span data-ttu-id="78d5a-105">Método</span><span class="sxs-lookup"><span data-stu-id="78d5a-105">Method</span></span>|<span data-ttu-id="78d5a-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="78d5a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="78d5a-107">Método GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="78d5a-107">GetAssemblyImageBytes Method</span></span>](icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="78d5a-108">Lê dados de um assembly mesclado, dado um endereço virtual relativo (RVA) no assembly mesclado.</span><span class="sxs-lookup"><span data-stu-id="78d5a-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="78d5a-109">Método GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="78d5a-109">GetAssemblyImageMetadata Method</span></span>](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="78d5a-110">Retorna os metadados de um assembly mesclado.</span><span class="sxs-lookup"><span data-stu-id="78d5a-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="78d5a-111">Método GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="78d5a-111">GetCodeRange Method</span></span>](icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="78d5a-112">Obtém o endereço inicial e o tamanho do método de acordo com um endereço virtual relativo (RVA) em um método.</span><span class="sxs-lookup"><span data-stu-id="78d5a-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="78d5a-113">Método GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="78d5a-113">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="78d5a-114">Obtém os símbolos de campo de instância que correspondem a uma assinatura de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="78d5a-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="78d5a-115">Método GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="78d5a-115">GetMergedAssemblyRecords Method</span></span>](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="78d5a-116">Obtém os registros de símbolo de todos os assemblies mesclados.</span><span class="sxs-lookup"><span data-stu-id="78d5a-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="78d5a-117">Método GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="78d5a-117">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="78d5a-118">Obtém os símbolos locais de um método de acordo com o endereço virtual relativo (RVA) desse método.</span><span class="sxs-lookup"><span data-stu-id="78d5a-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="78d5a-119">Método GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="78d5a-119">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="78d5a-120">Obtém os símbolos de parâmetro de um método de acordo com o endereço virtual relativo (RVA) desse método.</span><span class="sxs-lookup"><span data-stu-id="78d5a-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="78d5a-121">Método GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="78d5a-121">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="78d5a-122">Retorna informações sobre as propriedades do método, como o token de metadados do método e informações sobre seus parâmetros genéricos, considerando um endereço virtual relativo (RVA) nesse método.</span><span class="sxs-lookup"><span data-stu-id="78d5a-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="78d5a-123">Método GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="78d5a-123">GetObjectSize Method</span></span>](icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="78d5a-124">Retorna o tamanho do objeto de um objeto com base em sua assinatura de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="78d5a-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="78d5a-125">Método GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="78d5a-125">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="78d5a-126">Obtém os símbolos de campo estático que correspondem a uma assinatura de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="78d5a-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="78d5a-127">Método GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="78d5a-127">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="78d5a-128">Retorna informações sobre as propriedades de um tipo, como o número de assinatura de seus parâmetros genéricos, considerando um endereço virtual relativo (RVA) em uma vtable.</span><span class="sxs-lookup"><span data-stu-id="78d5a-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78d5a-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="78d5a-129">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78d5a-130">Essa interface está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="78d5a-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="78d5a-131">Se você implementar essa interface para cenários ICorDebug fora do .NET Native, o Common Language Runtime ignorará essa interface.</span><span class="sxs-lookup"><span data-stu-id="78d5a-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78d5a-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78d5a-132">Requirements</span></span>  

 <span data-ttu-id="78d5a-133">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78d5a-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78d5a-134">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78d5a-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78d5a-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78d5a-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78d5a-136">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78d5a-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d5a-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="78d5a-137">See also</span></span>

- [<span data-ttu-id="78d5a-138">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="78d5a-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="78d5a-139">Depuração</span><span class="sxs-lookup"><span data-stu-id="78d5a-139">Debugging</span></span>](index.md)
