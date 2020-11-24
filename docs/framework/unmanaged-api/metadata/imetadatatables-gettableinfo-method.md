---
title: Método IMetaDataTables::GetTableInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
ms.openlocfilehash: 65943ac169106a95feaff7d44017444e65764b60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672520"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="f8b1f-102">Método IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="f8b1f-102">IMetaDataTables::GetTableInfo Method</span></span>

<span data-ttu-id="f8b1f-103">Obtém o nome, o tamanho da linha, o número de linhas, o número de colunas e o índice da coluna de chave da tabela especificada.</span><span class="sxs-lookup"><span data-stu-id="f8b1f-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8b1f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f8b1f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8b1f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f8b1f-105">Parameters</span></span>  

 `ixTbl`  
 <span data-ttu-id="f8b1f-106">no O identificador da tabela cujas propriedades retornar.</span><span class="sxs-lookup"><span data-stu-id="f8b1f-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="f8b1f-107">fora Um ponteiro para o tamanho, em bytes, de uma linha de tabela.</span><span class="sxs-lookup"><span data-stu-id="f8b1f-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="f8b1f-108">fora Um ponteiro para o número de linhas na tabela.</span><span class="sxs-lookup"><span data-stu-id="f8b1f-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="f8b1f-109">fora Um ponteiro para o número de colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="f8b1f-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="f8b1f-110">fora Um ponteiro para o índice da coluna de chave ou-1 se a tabela não tiver nenhuma coluna de chave.</span><span class="sxs-lookup"><span data-stu-id="f8b1f-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="f8b1f-111">fora Um ponteiro para um ponteiro para o nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="f8b1f-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8b1f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8b1f-112">Requirements</span></span>  

 <span data-ttu-id="f8b1f-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8b1f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8b1f-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f8b1f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8b1f-115">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f8b1f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8b1f-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8b1f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8b1f-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="f8b1f-117">See also</span></span>

- [<span data-ttu-id="f8b1f-118">Interface IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="f8b1f-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="f8b1f-119">Interface IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="f8b1f-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
