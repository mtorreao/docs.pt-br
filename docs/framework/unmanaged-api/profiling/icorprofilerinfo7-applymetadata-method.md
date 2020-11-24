---
title: 'Método ICorProfilerInfo7:: ApplyMetaData'
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
ms.openlocfilehash: 2c71db25422740880d8b29576eff247d5eba5f1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686105"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="f5ba8-102">Método ICorProfilerInfo7:: ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="f5ba8-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>

<span data-ttu-id="f5ba8-103">[Com suporte no .NET Framework 4.6.1 e versões posteriores]</span><span class="sxs-lookup"><span data-stu-id="f5ba8-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="f5ba8-104">Aplica os metadados recentemente definidos pelos `IMetadataEmit::Define*` métodos a um módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ba8-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f5ba8-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5ba8-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f5ba8-106">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="f5ba8-107">no O identificador do módulo cujos metadados foram alterados.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5ba8-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="f5ba8-108">Remarks</span></span>  

 <span data-ttu-id="f5ba8-109">Se forem feitas alterações de metadados após o retorno de chamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , você deverá chamar esse método antes de usar os novos metadados.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-109">If metadata changes are made after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="f5ba8-110">`ApplyMetaData` o só dá suporte à adição dos seguintes tipos de metadados:</span><span class="sxs-lookup"><span data-stu-id="f5ba8-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="f5ba8-111">`AssemblyRef` registros, que você cria chamando o [IMetaDataAssemblyEmit::D efineassemblyref](../metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="f5ba8-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="f5ba8-112">método.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-112">method.</span></span>  
  
- <span data-ttu-id="f5ba8-113">`TypeRef` registros, que você cria chamando o método [IMetaDataEmit::D efinetyperefbyname](../metadata/imetadataemit-definetyperefbyname-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f5ba8-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="f5ba8-114">`TypeSpec` registros, que você cria chamando o método [IMetaDataEmit:: GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f5ba8-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="f5ba8-115">`MemberRef` registros, que você cria chamando o método [IMetaDataEmit::D efinememberref](../metadata/imetadataemit-definememberref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f5ba8-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="f5ba8-116">`MemberSpec` registros, que você cria chamando o método [IMetaDataEmit2::D efinemethodspec](../metadata/imetadataemit2-definemethodspec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f5ba8-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="f5ba8-117">`UserString` registros, que você cria chamando o método [IMetaDataEmit::D efineuserstring](../metadata/imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f5ba8-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="f5ba8-118">A partir do .NET Core 3,0, `ApplyMetaData` o também oferece suporte aos seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="f5ba8-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="f5ba8-119">`TypeDef` registros, que você cria chamando o método [IMetaDataEmit::D efinetypedef](../metadata/imetadataemit-definetypedef-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f5ba8-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="f5ba8-120">`MethodDef` registros, que você cria chamando o método [IMetaDataEmit::D efinemethod](../metadata/imetadataemit-definemethod-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f5ba8-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="f5ba8-121">No entanto, não há suporte para a adição de métodos virtuais a um tipo existente.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="f5ba8-122">Métodos virtuais devem ser adicionados antes do retorno de chamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f5ba8-122">Virtual methods must be added before the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="f5ba8-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5ba8-123">Requirements</span></span>  

 <span data-ttu-id="f5ba8-124">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5ba8-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5ba8-125">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="f5ba8-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f5ba8-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5ba8-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5ba8-127">**.NET Framework versões:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5ba8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ba8-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="f5ba8-128">See also</span></span>

- [<span data-ttu-id="f5ba8-129">Interface ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="f5ba8-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
