---
title: Método IMetaDataTables::GetColumnInfo
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: 227d9ab67ab3091508232be3018ca520a6b5dcc6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711046"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="7bc05-102">Método IMetaDataTables::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="7bc05-102">IMetaDataTables::GetColumnInfo Method</span></span>

<span data-ttu-id="7bc05-103">Obtém dados sobre a coluna especificada na tabela especificada.</span><span class="sxs-lookup"><span data-stu-id="7bc05-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bc05-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7bc05-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bc05-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7bc05-105">Parameters</span></span>

=======

 `ixTbl`  
 <span data-ttu-id="7bc05-106">no O índice da tabela desejada.</span><span class="sxs-lookup"><span data-stu-id="7bc05-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="7bc05-107">no O índice da coluna desejada.</span><span class="sxs-lookup"><span data-stu-id="7bc05-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="7bc05-108">fora Um ponteiro para o deslocamento da coluna na linha.</span><span class="sxs-lookup"><span data-stu-id="7bc05-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="7bc05-109">fora Um ponteiro para o tamanho, em bytes, da coluna.</span><span class="sxs-lookup"><span data-stu-id="7bc05-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="7bc05-110">fora Um ponteiro para o tipo dos valores na coluna.</span><span class="sxs-lookup"><span data-stu-id="7bc05-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="7bc05-111">fora Um ponteiro para um ponteiro para o nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="7bc05-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="7bc05-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="7bc05-112">Remarks</span></span>

<span data-ttu-id="7bc05-113">O tipo de coluna retornado cai dentro de um intervalo de valores:</span><span class="sxs-lookup"><span data-stu-id="7bc05-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="7bc05-114">pType</span><span class="sxs-lookup"><span data-stu-id="7bc05-114">pType</span></span>                    | <span data-ttu-id="7bc05-115">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="7bc05-115">Description</span></span>   | <span data-ttu-id="7bc05-116">Função auxiliar</span><span class="sxs-lookup"><span data-stu-id="7bc05-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="7bc05-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="7bc05-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="7bc05-118">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="7bc05-118">(0..63)</span></span>   | <span data-ttu-id="7bc05-119">Eliminá</span><span class="sxs-lookup"><span data-stu-id="7bc05-119">Rid</span></span>           | <span data-ttu-id="7bc05-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="7bc05-120">**IsRidType**</span></span><br><span data-ttu-id="7bc05-121">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="7bc05-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="7bc05-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="7bc05-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="7bc05-123">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="7bc05-123">(64..95)</span></span> | <span data-ttu-id="7bc05-124">Token codificado</span><span class="sxs-lookup"><span data-stu-id="7bc05-124">Coded token</span></span> | <span data-ttu-id="7bc05-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="7bc05-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="7bc05-126">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="7bc05-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="7bc05-127">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="7bc05-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="7bc05-128">Int16</span><span class="sxs-lookup"><span data-stu-id="7bc05-128">Int16</span></span>         | <span data-ttu-id="7bc05-129">**Isfixatype**</span><span class="sxs-lookup"><span data-stu-id="7bc05-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="7bc05-130">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="7bc05-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="7bc05-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="7bc05-131">UInt16</span></span>        | <span data-ttu-id="7bc05-132">**Isfixatype**</span><span class="sxs-lookup"><span data-stu-id="7bc05-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="7bc05-133">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="7bc05-133">`iLONG` (98)</span></span>             | <span data-ttu-id="7bc05-134">Int32</span><span class="sxs-lookup"><span data-stu-id="7bc05-134">Int32</span></span>         | <span data-ttu-id="7bc05-135">**Isfixatype**</span><span class="sxs-lookup"><span data-stu-id="7bc05-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="7bc05-136">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="7bc05-136">`iULONG` (99)</span></span>            | <span data-ttu-id="7bc05-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="7bc05-137">UInt32</span></span>        | <span data-ttu-id="7bc05-138">**Isfixatype**</span><span class="sxs-lookup"><span data-stu-id="7bc05-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="7bc05-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="7bc05-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="7bc05-140">Byte</span><span class="sxs-lookup"><span data-stu-id="7bc05-140">Byte</span></span>          | <span data-ttu-id="7bc05-141">**Isfixatype**</span><span class="sxs-lookup"><span data-stu-id="7bc05-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="7bc05-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="7bc05-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="7bc05-143">String</span><span class="sxs-lookup"><span data-stu-id="7bc05-143">String</span></span>        | <span data-ttu-id="7bc05-144">**Isheaptype**</span><span class="sxs-lookup"><span data-stu-id="7bc05-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="7bc05-145">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="7bc05-145">`iGUID` (102)</span></span>            | <span data-ttu-id="7bc05-146">Guid</span><span class="sxs-lookup"><span data-stu-id="7bc05-146">Guid</span></span>          | <span data-ttu-id="7bc05-147">**Isheaptype**</span><span class="sxs-lookup"><span data-stu-id="7bc05-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="7bc05-148">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="7bc05-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="7bc05-149">Blob</span><span class="sxs-lookup"><span data-stu-id="7bc05-149">Blob</span></span>          | <span data-ttu-id="7bc05-150">**Isheaptype**</span><span class="sxs-lookup"><span data-stu-id="7bc05-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="7bc05-151">Os valores que são armazenados no *heap* (ou seja, `IsHeapType == true` ) podem ser lidos usando:</span><span class="sxs-lookup"><span data-stu-id="7bc05-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="7bc05-152">`iSTRING`: **IMetadataTables. GetString**</span><span class="sxs-lookup"><span data-stu-id="7bc05-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="7bc05-153">`iGUID`: **IMetadataTables. GETguid**</span><span class="sxs-lookup"><span data-stu-id="7bc05-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="7bc05-154">`iBLOB`: **IMetadataTables. getBlob**</span><span class="sxs-lookup"><span data-stu-id="7bc05-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7bc05-155">Para usar as constantes definidas na tabela acima, inclua a diretiva `#define _DEFINE_META_DATA_META_CONSTANTS` fornecida pelo arquivo de cabeçalho *cor. h* .</span><span class="sxs-lookup"><span data-stu-id="7bc05-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="7bc05-156">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bc05-156">Requirements</span></span>  

 <span data-ttu-id="7bc05-157">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bc05-157">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bc05-158">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7bc05-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7bc05-159">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7bc05-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7bc05-160">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bc05-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc05-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="7bc05-161">See also</span></span>

- [<span data-ttu-id="7bc05-162">Interface IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="7bc05-162">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="7bc05-163">Interface IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="7bc05-163">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
