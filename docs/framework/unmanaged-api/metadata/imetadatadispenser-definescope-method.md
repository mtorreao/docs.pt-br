---
title: Método IMetaDataDispenser::DefineScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 87a39350986cb7bb62f76b0d9a6a9aae8f82e2f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726087"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="5e0a5-102">Método IMetaDataDispenser::DefineScope</span><span class="sxs-lookup"><span data-stu-id="5e0a5-102">IMetaDataDispenser::DefineScope Method</span></span>

<span data-ttu-id="5e0a5-103">Cria uma nova área na memória na qual você pode criar novos metadados.</span><span class="sxs-lookup"><span data-stu-id="5e0a5-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e0a5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5e0a5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e0a5-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5e0a5-105">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="5e0a5-106">no O CLSID da versão de estruturas de metadados a ser criada.</span><span class="sxs-lookup"><span data-stu-id="5e0a5-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="5e0a5-107">Esse valor deve ser CLSID_CorMetaDataRuntime para a versão de .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="5e0a5-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="5e0a5-108">no Sinalizadores que especificam opções.</span><span class="sxs-lookup"><span data-stu-id="5e0a5-108">[in] Flags that specify options.</span></span> <span data-ttu-id="5e0a5-109">Esse valor deve ser zero para o .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="5e0a5-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="5e0a5-110">no A IID da interface de metadados desejada a ser retornada; o chamador usará a interface para criar os novos metadados.</span><span class="sxs-lookup"><span data-stu-id="5e0a5-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="5e0a5-111">O valor de `riid` deve especificar uma das interfaces "Emit".</span><span class="sxs-lookup"><span data-stu-id="5e0a5-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="5e0a5-112">Os valores válidos são IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit ou IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="5e0a5-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="5e0a5-113">fora O ponteiro para a interface retornada.</span><span class="sxs-lookup"><span data-stu-id="5e0a5-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e0a5-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="5e0a5-114">Remarks</span></span>  

 <span data-ttu-id="5e0a5-115">`DefineScope` Cria um conjunto de tabelas de metadados na memória, gera um GUID exclusivo (identificador de versão de módulo ou MVID) para os metadados e cria uma entrada na tabela de módulo para a unidade de compilação que está sendo emitida.</span><span class="sxs-lookup"><span data-stu-id="5e0a5-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="5e0a5-116">Você pode anexar atributos ao escopo de metadados como um todo usando o método [IMetaDataEmit:: SetModuleProps](imetadataemit-setmoduleprops-method.md) ou [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md) , conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="5e0a5-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e0a5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e0a5-117">Requirements</span></span>  

 <span data-ttu-id="5e0a5-118">**Plataforma:** Consulte [requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e0a5-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e0a5-119">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5e0a5-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5e0a5-120">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5e0a5-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5e0a5-121">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e0a5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0a5-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="5e0a5-122">See also</span></span>

- [<span data-ttu-id="5e0a5-123">Interface IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="5e0a5-123">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="5e0a5-124">Interface IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="5e0a5-124">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="5e0a5-125">Interface IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5e0a5-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="5e0a5-126">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5e0a5-126">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5e0a5-127">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5e0a5-127">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
