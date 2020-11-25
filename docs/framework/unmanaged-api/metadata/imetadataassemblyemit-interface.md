---
title: Interface IMetaDataAssemblyEmit
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
ms.openlocfilehash: 5d8bc54a94e1571ff8335c934407bbf235179ecc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728284"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="36873-102">Interface IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="36873-102">IMetaDataAssemblyEmit Interface</span></span>

<span data-ttu-id="36873-103">Fornece métodos que dão suporte ao modelo de autodescrição usado pelo Common Language Runtime para resolver e consumir recursos.</span><span class="sxs-lookup"><span data-stu-id="36873-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36873-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="36873-104">Methods</span></span>  
  
|<span data-ttu-id="36873-105">Método</span><span class="sxs-lookup"><span data-stu-id="36873-105">Method</span></span>|<span data-ttu-id="36873-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="36873-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36873-107">Método DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="36873-107">DefineAssembly Method</span></span>](imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="36873-108">Cria uma estrutura de dados de assembly contendo metadados para o assembly especificado e retorna o token de metadados associado.</span><span class="sxs-lookup"><span data-stu-id="36873-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="36873-109">Método DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="36873-109">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="36873-110">Cria uma `AssemblyRef` estrutura que contém metadados para o assembly ao qual este assembly faz referência e retorna o token de metadados associado.</span><span class="sxs-lookup"><span data-stu-id="36873-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="36873-111">Método DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="36873-111">DefineExportedType Method</span></span>](imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="36873-112">Cria uma `ExportedType` estrutura que contém metadados para o tipo exportado especificado e retorna o token de metadados associado.</span><span class="sxs-lookup"><span data-stu-id="36873-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="36873-113">Método DefineFile</span><span class="sxs-lookup"><span data-stu-id="36873-113">DefineFile Method</span></span>](imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="36873-114">Cria uma `File` estrutura de metadados que contém metadados para o assembly referenciado por esse assembly e retorna o token de metadados associado.</span><span class="sxs-lookup"><span data-stu-id="36873-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="36873-115">Método DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="36873-115">DefineManifestResource Method</span></span>](imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="36873-116">Cria uma `ManifestResource` estrutura que contém metadados para o recurso de manifesto especificado e retorna o token de metadados associado.</span><span class="sxs-lookup"><span data-stu-id="36873-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="36873-117">Método SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="36873-117">SetAssemblyProps Method</span></span>](imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="36873-118">Modifica a estrutura de `Assembly` metadados especificada.</span><span class="sxs-lookup"><span data-stu-id="36873-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="36873-119">Método SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="36873-119">SetAssemblyRefProps Method</span></span>](imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="36873-120">Modifica a estrutura de `AssemblyRef` metadados especificada.</span><span class="sxs-lookup"><span data-stu-id="36873-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="36873-121">Método SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="36873-121">SetExportedTypeProps Method</span></span>](imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="36873-122">Modifica a estrutura de `ExportedType` metadados especificada.</span><span class="sxs-lookup"><span data-stu-id="36873-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="36873-123">Método SetFileProps</span><span class="sxs-lookup"><span data-stu-id="36873-123">SetFileProps Method</span></span>](imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="36873-124">Modifica a estrutura de `File` metadados especificada.</span><span class="sxs-lookup"><span data-stu-id="36873-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="36873-125">Método SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="36873-125">SetManifestResourceProps Method</span></span>](imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="36873-126">Modifica a estrutura de `ManifestResource` metadados especificada.</span><span class="sxs-lookup"><span data-stu-id="36873-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36873-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="36873-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36873-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36873-128">Requirements</span></span>  

 <span data-ttu-id="36873-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36873-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36873-130">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="36873-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36873-131">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36873-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36873-132">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36873-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36873-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="36873-133">See also</span></span>

- [<span data-ttu-id="36873-134">Interfaces de metadados</span><span class="sxs-lookup"><span data-stu-id="36873-134">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="36873-135">Interface IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="36873-135">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
