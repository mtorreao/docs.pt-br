---
title: Interface IMetaDataDispenserEx
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: 60d321c1a87a5da433437c9d4587fa9f8947acf4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713373"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="667d4-102">Interface IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="667d4-102">IMetaDataDispenserEx Interface</span></span>

<span data-ttu-id="667d4-103">Estende a interface de [interface IMetaDataDispenser](imetadatadispenser-interface.md) para fornecer a capacidade de controlar como as APIs de metadados operam no escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="667d4-103">Extends the [IMetaDataDispenser Interface](imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="667d4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="667d4-104">Methods</span></span>  
  
|<span data-ttu-id="667d4-105">Método</span><span class="sxs-lookup"><span data-stu-id="667d4-105">Method</span></span>|<span data-ttu-id="667d4-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="667d4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="667d4-107">Método FindAssembly</span><span class="sxs-lookup"><span data-stu-id="667d4-107">FindAssembly Method</span></span>](imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="667d4-108">Este método não está implementado.</span><span class="sxs-lookup"><span data-stu-id="667d4-108">This method is not implemented.</span></span> <span data-ttu-id="667d4-109">Se chamado, ele retornará E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="667d4-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="667d4-110">Método FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="667d4-110">FindAssemblyModule Method</span></span>](imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="667d4-111">Este método não está implementado.</span><span class="sxs-lookup"><span data-stu-id="667d4-111">This method is not implemented.</span></span> <span data-ttu-id="667d4-112">Se chamado, ele retornará E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="667d4-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="667d4-113">Método GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="667d4-113">GetCORSystemDirectory Method</span></span>](imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="667d4-114">Obtém o diretório que contém o Common Language Runtime atual (CLR).</span><span class="sxs-lookup"><span data-stu-id="667d4-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="667d4-115">Esse método só tem suporte para uso por depuradores fora do processo.</span><span class="sxs-lookup"><span data-stu-id="667d4-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="667d4-116">Se for chamado de outro componente, ele retornará E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="667d4-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="667d4-117">Método GetOption</span><span class="sxs-lookup"><span data-stu-id="667d4-117">GetOption Method</span></span>](imetadatadispenserex-getoption-method.md)|<span data-ttu-id="667d4-118">Obtém o valor da opção especificada para o escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="667d4-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="667d4-119">A opção controla como as chamadas para o escopo de metadados atual são tratadas.</span><span class="sxs-lookup"><span data-stu-id="667d4-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="667d4-120">Método OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="667d4-120">OpenScopeOnITypeInfo Method</span></span>](imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="667d4-121">Este método não está implementado.</span><span class="sxs-lookup"><span data-stu-id="667d4-121">This method is not implemented.</span></span> <span data-ttu-id="667d4-122">Se chamado, ele retornará E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="667d4-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="667d4-123">Método SetOption</span><span class="sxs-lookup"><span data-stu-id="667d4-123">SetOption Method</span></span>](imetadatadispenserex-setoption-method.md)|<span data-ttu-id="667d4-124">Define a opção especificada para um determinado valor para o escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="667d4-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="667d4-125">A opção controla como as chamadas para o escopo de metadados atual são tratadas.</span><span class="sxs-lookup"><span data-stu-id="667d4-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="667d4-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="667d4-126">Requirements</span></span>  

 <span data-ttu-id="667d4-127">**Plataforma:** Consulte [requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="667d4-127">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="667d4-128">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="667d4-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="667d4-129">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="667d4-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="667d4-130">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="667d4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="667d4-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="667d4-131">See also</span></span>

- [<span data-ttu-id="667d4-132">Interfaces de metadados</span><span class="sxs-lookup"><span data-stu-id="667d4-132">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="667d4-133">Interface IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="667d4-133">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="667d4-134">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="667d4-134">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="667d4-135">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="667d4-135">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
