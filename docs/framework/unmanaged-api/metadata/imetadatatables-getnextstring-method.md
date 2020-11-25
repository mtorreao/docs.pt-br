---
title: Método IMetaDataTables::GetNextString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
ms.openlocfilehash: b79dbdd64ac171d1bc4cd30b96ee76b4a853afb6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727244"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="488e1-102">Método IMetaDataTables::GetNextString</span><span class="sxs-lookup"><span data-stu-id="488e1-102">IMetaDataTables::GetNextString Method</span></span>

<span data-ttu-id="488e1-103">Obtém o índice da próxima cadeia de caracteres na coluna da tabela atual.</span><span class="sxs-lookup"><span data-stu-id="488e1-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="488e1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="488e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="488e1-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="488e1-105">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="488e1-106">no O valor de índice de uma coluna de tabela de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="488e1-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="488e1-107">fora Um ponteiro para o índice da próxima cadeia de caracteres na coluna.</span><span class="sxs-lookup"><span data-stu-id="488e1-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="488e1-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="488e1-108">Requirements</span></span>  

 <span data-ttu-id="488e1-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="488e1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="488e1-110">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="488e1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="488e1-111">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="488e1-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="488e1-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="488e1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="488e1-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="488e1-113">See also</span></span>

- [<span data-ttu-id="488e1-114">Interface IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="488e1-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="488e1-115">Interface IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="488e1-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
