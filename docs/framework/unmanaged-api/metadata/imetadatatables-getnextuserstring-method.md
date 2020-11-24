---
title: Método IMetaDataTables::GetNextUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
ms.openlocfilehash: bb53d980a7b2121854748d5117bc539fed125163
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680359"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="d63b6-102">Método IMetaDataTables::GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="d63b6-102">IMetaDataTables::GetNextUserString Method</span></span>

<span data-ttu-id="d63b6-103">Obtém o índice da linha que contém a próxima cadeia de caracteres embutida em código na coluna da tabela atual.</span><span class="sxs-lookup"><span data-stu-id="d63b6-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d63b6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d63b6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d63b6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d63b6-105">Parameters</span></span>  

 `ixUserString`  
 <span data-ttu-id="d63b6-106">no Um valor de índice da coluna de cadeia de caracteres atual.</span><span class="sxs-lookup"><span data-stu-id="d63b6-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="d63b6-107">fora Um ponteiro para o índice de linha da próxima cadeia de caracteres na coluna.</span><span class="sxs-lookup"><span data-stu-id="d63b6-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d63b6-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="d63b6-108">Remarks</span></span>  

 <span data-ttu-id="d63b6-109">Não recomendamos o uso desse método, pois ele não retorna resultados consistentes.</span><span class="sxs-lookup"><span data-stu-id="d63b6-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="d63b6-110">Para obter informações sobre a tabela de GUID, consulte a documentação de Common Language Infrastructure (CLI), especialmente "partição II: definição de metadados e semântica".</span><span class="sxs-lookup"><span data-stu-id="d63b6-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="d63b6-111">A documentação está disponível online; consulte [padrões ECMA C# e Common Language Infrastructure](../../../standard/components.md#applicable-standards) e o [padrão ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="d63b6-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d63b6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d63b6-112">Requirements</span></span>  

 <span data-ttu-id="d63b6-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d63b6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d63b6-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d63b6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d63b6-115">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d63b6-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d63b6-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d63b6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d63b6-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="d63b6-117">See also</span></span>

- [<span data-ttu-id="d63b6-118">Interface IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="d63b6-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="d63b6-119">Interface IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="d63b6-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
