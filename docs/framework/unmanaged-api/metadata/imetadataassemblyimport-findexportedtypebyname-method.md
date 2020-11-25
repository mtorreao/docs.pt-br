---
title: Método IMetaDataAssemblyImport::FindExportedTypeByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: b1672d98d76241e5af4b6b60a38785f1278e15a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731586"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="fd1ab-102">Método IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="fd1ab-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>

<span data-ttu-id="fd1ab-103">Obtém um ponteiro para um tipo exportado, dado seu nome e tipo de delimitador.</span><span class="sxs-lookup"><span data-stu-id="fd1ab-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd1ab-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fd1ab-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd1ab-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fd1ab-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="fd1ab-106">no O nome do tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="fd1ab-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="fd1ab-107">no O token de metadados para a classe de circunscrição do tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="fd1ab-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="fd1ab-108">Esse valor é `mdExportedTypeNil` se o tipo exportado solicitado não for um tipo aninhado.</span><span class="sxs-lookup"><span data-stu-id="fd1ab-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="fd1ab-109">fora Um ponteiro para o `mdExportedType` token que representa o tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="fd1ab-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd1ab-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="fd1ab-110">Remarks</span></span>  

 <span data-ttu-id="fd1ab-111">O `FindExportedTypeByName` método usa as regras padrão empregadas pelo Common Language Runtime para resolver referências.</span><span class="sxs-lookup"><span data-stu-id="fd1ab-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd1ab-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd1ab-112">Requirements</span></span>  

 <span data-ttu-id="fd1ab-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd1ab-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd1ab-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fd1ab-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd1ab-115">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd1ab-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd1ab-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd1ab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd1ab-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="fd1ab-117">See also</span></span>

- [<span data-ttu-id="fd1ab-118">Interface IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="fd1ab-118">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="fd1ab-119">Como o runtime localiza assemblies</span><span class="sxs-lookup"><span data-stu-id="fd1ab-119">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
