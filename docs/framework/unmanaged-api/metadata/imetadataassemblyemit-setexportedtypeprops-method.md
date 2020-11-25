---
title: Método IMetaDataAssemblyEmit::SetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
ms.openlocfilehash: 076d027945dc27942e4b0989e14e86d829f76679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713477"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="0b24c-102">Método IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="0b24c-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>

<span data-ttu-id="0b24c-103">Modifica a estrutura de `ExportedType` metadados especificada.</span><span class="sxs-lookup"><span data-stu-id="0b24c-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b24c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0b24c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b24c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0b24c-105">Parameters</span></span>  

 `ct`  
 <span data-ttu-id="0b24c-106">no O token de metadados que especifica a `ExportedType` estrutura de metadados a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="0b24c-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="0b24c-107">no O token, do tipo `File` , `AssemblyRef` ou `ExportedType` , que especifica como esse tipo é implementado.</span><span class="sxs-lookup"><span data-stu-id="0b24c-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="0b24c-108">no O `TypeDef` token referenciado no arquivo de código.</span><span class="sxs-lookup"><span data-stu-id="0b24c-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="0b24c-109">no Uma combinação de bits de valores que especifica atributos do tipo.</span><span class="sxs-lookup"><span data-stu-id="0b24c-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b24c-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="0b24c-110">Remarks</span></span>  

 <span data-ttu-id="0b24c-111">Para criar uma `ExportedType` estrutura de metadados, use o método [IMetaDataAssemblyEmit::D efineexportedtype](imetadataassemblyemit-defineexportedtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0b24c-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b24c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b24c-112">Requirements</span></span>  

 <span data-ttu-id="0b24c-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b24c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b24c-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0b24c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b24c-115">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b24c-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0b24c-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b24c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b24c-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="0b24c-117">See also</span></span>

- [<span data-ttu-id="0b24c-118">Interface IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="0b24c-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
