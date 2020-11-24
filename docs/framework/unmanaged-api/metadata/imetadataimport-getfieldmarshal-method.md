---
title: Método IMetaDataImport::GetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
ms.openlocfilehash: 35f73135dbeea1c79d15e0a9e9367c5d533487ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676849"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="8b955-102">Método IMetaDataImport::GetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="8b955-102">IMetaDataImport::GetFieldMarshal Method</span></span>

<span data-ttu-id="8b955-103">Obtém um ponteiro para o tipo nativo não gerenciado do campo representado pelo token de metadados do campo especificado.</span><span class="sxs-lookup"><span data-stu-id="8b955-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b955-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8b955-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b955-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8b955-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="8b955-106">no O token de metadados que representa o campo para obter informações de marshaling de interoperabilidade para.</span><span class="sxs-lookup"><span data-stu-id="8b955-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="8b955-107">fora Um ponteiro para a assinatura de metadados do tipo nativo do campo.</span><span class="sxs-lookup"><span data-stu-id="8b955-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="8b955-108">fora O tamanho em bytes de `ppvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="8b955-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b955-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b955-109">Requirements</span></span>  

 <span data-ttu-id="8b955-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b955-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b955-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8b955-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b955-112">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b955-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b955-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b955-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b955-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="8b955-114">See also</span></span>

- [<span data-ttu-id="8b955-115">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8b955-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8b955-116">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8b955-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
