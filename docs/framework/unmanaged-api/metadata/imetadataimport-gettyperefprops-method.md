---
title: Método IMetaDataImport::GetTypeRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
ms.openlocfilehash: 5d98481d7934b4c96178aaa32fb0f9378eb359fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729157"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="e2ee1-102">Método IMetaDataImport::GetTypeRefProps</span><span class="sxs-lookup"><span data-stu-id="e2ee1-102">IMetaDataImport::GetTypeRefProps Method</span></span>

<span data-ttu-id="e2ee1-103">Obtém os metadados associados com o <xref:System.Type> referido pelo token TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="e2ee1-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ee1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e2ee1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2ee1-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e2ee1-105">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="e2ee1-106">no O token TypeRef que representa o tipo para o qual retornar metadados.</span><span class="sxs-lookup"><span data-stu-id="e2ee1-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="e2ee1-107">fora Um ponteiro para o escopo no qual a referência é feita.</span><span class="sxs-lookup"><span data-stu-id="e2ee1-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="e2ee1-108">Esse valor é um token AssemblyRef ou ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="e2ee1-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="e2ee1-109">fora Um buffer que contém o nome do tipo.</span><span class="sxs-lookup"><span data-stu-id="e2ee1-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e2ee1-110">no O tamanho solicitado em caracteres largos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="e2ee1-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="e2ee1-111">fora O tamanho retornado em caracteres largos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="e2ee1-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ee1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2ee1-112">Requirements</span></span>  

 <span data-ttu-id="e2ee1-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2ee1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2ee1-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e2ee1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2ee1-115">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2ee1-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e2ee1-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ee1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ee1-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="e2ee1-117">See also</span></span>

- [<span data-ttu-id="e2ee1-118">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e2ee1-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e2ee1-119">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e2ee1-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
