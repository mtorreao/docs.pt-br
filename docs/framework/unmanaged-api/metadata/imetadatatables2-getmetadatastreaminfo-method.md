---
title: Método IMetaDataTables2::GetMetaDataStreamInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 21fc79f62dba4b16a7a067dff8fb9dcc795c9d35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708719"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="54e3a-102">Método IMetaDataTables2::GetMetaDataStreamInfo</span><span class="sxs-lookup"><span data-stu-id="54e3a-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>

<span data-ttu-id="54e3a-103">Obtém o nome, o tamanho e o conteúdo do fluxo de metadados no índice especificado.</span><span class="sxs-lookup"><span data-stu-id="54e3a-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e3a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="54e3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54e3a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="54e3a-105">Parameters</span></span>  

 `ix`  
 <span data-ttu-id="54e3a-106">no O índice do fluxo de metadados solicitado.</span><span class="sxs-lookup"><span data-stu-id="54e3a-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="54e3a-107">fora Um ponteiro para o nome do fluxo.</span><span class="sxs-lookup"><span data-stu-id="54e3a-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="54e3a-108">fora Um ponteiro para o fluxo de metadados.</span><span class="sxs-lookup"><span data-stu-id="54e3a-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="54e3a-109">fora O tamanho, em bytes, de `ppv` .</span><span class="sxs-lookup"><span data-stu-id="54e3a-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54e3a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54e3a-110">Requirements</span></span>  

 <span data-ttu-id="54e3a-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54e3a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54e3a-112">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="54e3a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="54e3a-113">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54e3a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="54e3a-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e3a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e3a-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="54e3a-115">See also</span></span>

- [<span data-ttu-id="54e3a-116">Interface IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="54e3a-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="54e3a-117">Interface IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="54e3a-117">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
