---
title: Método IMetaDataTables::GetNextBlob
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
ms.openlocfilehash: ba694f485d5a51870a1283b6ccbcb7b042a14501
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685624"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="a6740-102">Método IMetaDataTables::GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="a6740-102">IMetaDataTables::GetNextBlob Method</span></span>

<span data-ttu-id="a6740-103">Obtém o índice do próximo objeto binário grande (BLOB) na tabela.</span><span class="sxs-lookup"><span data-stu-id="a6740-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6740-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a6740-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6740-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a6740-105">Parameters</span></span>  

 `ixBlob`  
 <span data-ttu-id="a6740-106">no O índice, como retornado de uma coluna de BLOBs.</span><span class="sxs-lookup"><span data-stu-id="a6740-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="a6740-107">fora Um ponteiro para o índice do próximo BLOB.</span><span class="sxs-lookup"><span data-stu-id="a6740-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6740-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6740-108">Requirements</span></span>  

 <span data-ttu-id="a6740-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6740-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6740-110">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a6740-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6740-111">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6740-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6740-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6740-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6740-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="a6740-113">See also</span></span>

- [<span data-ttu-id="a6740-114">Interface IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a6740-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="a6740-115">Interface IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a6740-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
