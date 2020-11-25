---
title: Método IMetaDataImport::GetScopeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: 5a89d1406daa9a2416a708b63d88fd9005234015
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729194"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="f5db1-102">Método IMetaDataImport::GetScopeProps</span><span class="sxs-lookup"><span data-stu-id="f5db1-102">IMetaDataImport::GetScopeProps Method</span></span>

<span data-ttu-id="f5db1-103">Obtém o nome e, opcionalmente, o identificador de versão do assembly ou módulo no escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="f5db1-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5db1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f5db1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5db1-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f5db1-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="f5db1-106">fora Um buffer para o assembly ou o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="f5db1-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f5db1-107">no O tamanho em caracteres largos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="f5db1-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="f5db1-108">fora O número de caracteres largos retornados em `szName` .</span><span class="sxs-lookup"><span data-stu-id="f5db1-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="f5db1-109">[saída, opcional] Um ponteiro para um GUID que identifica exclusivamente a versão do assembly ou módulo.</span><span class="sxs-lookup"><span data-stu-id="f5db1-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5db1-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="f5db1-110">Remarks</span></span>  

 <span data-ttu-id="f5db1-111">O método [IMetaDataEmit:: SetModuleProps](imetadataemit-setmoduleprops-method.md) é usado para definir essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="f5db1-111">The [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5db1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5db1-112">Requirements</span></span>  

 <span data-ttu-id="f5db1-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5db1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5db1-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f5db1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5db1-115">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5db1-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5db1-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5db1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5db1-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="f5db1-117">See also</span></span>

- [<span data-ttu-id="f5db1-118">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f5db1-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f5db1-119">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f5db1-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
