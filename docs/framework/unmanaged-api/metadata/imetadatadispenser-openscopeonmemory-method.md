---
title: Método IMetaDataDispenser::OpenScopeOnMemory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 26293e38a275ca691c7d48dceb12c1e7dd316536
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713412"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="f72a2-102">Método IMetaDataDispenser::OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="f72a2-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>

<span data-ttu-id="f72a2-103">Abre uma área de memória que contém os metadados existentes.</span><span class="sxs-lookup"><span data-stu-id="f72a2-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="f72a2-104">Ou seja, esse método abre uma área especificada de memória na qual os dados existentes são tratados como metadados.</span><span class="sxs-lookup"><span data-stu-id="f72a2-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f72a2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f72a2-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f72a2-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f72a2-106">Parameters</span></span>  

 `pData`  
 <span data-ttu-id="f72a2-107">no Um ponteiro que especifica o endereço inicial da área de memória.</span><span class="sxs-lookup"><span data-stu-id="f72a2-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="f72a2-108">no O tamanho da área de memória, em bytes.</span><span class="sxs-lookup"><span data-stu-id="f72a2-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="f72a2-109">no Um valor da enumeração [CorOpenFlags](coropenflags-enumeration.md) para especificar o modo (leitura, gravação e assim por diante) para abertura.</span><span class="sxs-lookup"><span data-stu-id="f72a2-109">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="f72a2-110">no A IID da interface de metadados desejada a ser retornada; o chamador usará a interface para importar (ler) ou emitir (gravar) metadados.</span><span class="sxs-lookup"><span data-stu-id="f72a2-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="f72a2-111">O valor de `riid` deve especificar uma das interfaces "Import" ou "Emit".</span><span class="sxs-lookup"><span data-stu-id="f72a2-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="f72a2-112">Os valores válidos são IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 ou IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="f72a2-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="f72a2-113">fora O ponteiro para a interface retornada.</span><span class="sxs-lookup"><span data-stu-id="f72a2-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f72a2-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="f72a2-114">Remarks</span></span>  

 <span data-ttu-id="f72a2-115">A cópia na memória dos metadados pode ser consultada usando métodos de uma das interfaces "Import" ou adicionadas ao uso de métodos de uma das interfaces "Emit".</span><span class="sxs-lookup"><span data-stu-id="f72a2-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="f72a2-116">O `OpenScopeOnMemory` método é semelhante ao método [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) , exceto que os metadados de interesse já existem na memória, em vez de em um arquivo no disco.</span><span class="sxs-lookup"><span data-stu-id="f72a2-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="f72a2-117">Se a área de destino da memória não contiver metadados de Common Language Runtime (CLR), o `OpenScopeOnMemory` método falhará.</span><span class="sxs-lookup"><span data-stu-id="f72a2-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f72a2-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f72a2-118">Requirements</span></span>  

 <span data-ttu-id="f72a2-119">**Plataforma:** Consulte [requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f72a2-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f72a2-120">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f72a2-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f72a2-121">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f72a2-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f72a2-122">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f72a2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72a2-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="f72a2-123">See also</span></span>

- [<span data-ttu-id="f72a2-124">Interface IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="f72a2-124">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="f72a2-125">Interface IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="f72a2-125">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="f72a2-126">Interface IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="f72a2-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="f72a2-127">Interface IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="f72a2-127">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="f72a2-128">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f72a2-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f72a2-129">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f72a2-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="f72a2-130">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f72a2-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f72a2-131">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f72a2-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
