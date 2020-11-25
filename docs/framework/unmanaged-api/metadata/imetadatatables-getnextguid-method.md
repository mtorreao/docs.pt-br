---
title: Método IMetaDataTables::GetNextGuid
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
ms.openlocfilehash: 71dce539941f78feff3d5f89028d654cade25feb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727257"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="ba82b-102">Método IMetaDataTables::GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="ba82b-102">IMetaDataTables::GetNextGuid Method</span></span>

<span data-ttu-id="ba82b-103">Obtém o índice do próximo valor de GUID na coluna da tabela atual.</span><span class="sxs-lookup"><span data-stu-id="ba82b-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba82b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ba82b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba82b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ba82b-105">Parameters</span></span>  

 `ixGuid`  
 <span data-ttu-id="ba82b-106">no O valor de índice de uma coluna de tabela de GUID.</span><span class="sxs-lookup"><span data-stu-id="ba82b-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="ba82b-107">fora Um ponteiro para o índice do próximo valor de GUID.</span><span class="sxs-lookup"><span data-stu-id="ba82b-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba82b-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="ba82b-108">Remarks</span></span>  

  <span data-ttu-id="ba82b-109">Não recomendamos o uso desse método, pois ele não retorna resultados consistentes.</span><span class="sxs-lookup"><span data-stu-id="ba82b-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="ba82b-110">Para obter informações sobre a tabela de GUID, consulte a documentação de Common Language Infrastructure (CLI), especialmente "partição II: definição de metadados e semântica".</span><span class="sxs-lookup"><span data-stu-id="ba82b-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="ba82b-111">A documentação está disponível online; consulte [padrões ECMA C# e Common Language Infrastructure](../../../standard/components.md#applicable-standards) e o [padrão ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="ba82b-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba82b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba82b-112">Requirements</span></span>  

 <span data-ttu-id="ba82b-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba82b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba82b-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ba82b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba82b-115">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba82b-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba82b-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba82b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba82b-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="ba82b-117">See also</span></span>

- [<span data-ttu-id="ba82b-118">Interface IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="ba82b-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="ba82b-119">Interface IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="ba82b-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
