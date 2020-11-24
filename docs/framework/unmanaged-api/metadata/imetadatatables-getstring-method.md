---
title: Método IMetaDataTables::GetString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
ms.openlocfilehash: 8ecaa003084064be1071a85aa726c38d773ec0b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672572"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="5cb4f-102">Método IMetaDataTables::GetString</span><span class="sxs-lookup"><span data-stu-id="5cb4f-102">IMetaDataTables::GetString Method</span></span>

<span data-ttu-id="5cb4f-103">Obtém a cadeia de caracteres no índice especificado da coluna de tabela no escopo de referência atual.</span><span class="sxs-lookup"><span data-stu-id="5cb4f-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cb4f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5cb4f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cb4f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5cb4f-105">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="5cb4f-106">no O índice no qual começar a procurar o próximo valor.</span><span class="sxs-lookup"><span data-stu-id="5cb4f-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="5cb4f-107">fora Um ponteiro para um ponteiro para o valor de cadeia de caracteres retornado.</span><span class="sxs-lookup"><span data-stu-id="5cb4f-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cb4f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5cb4f-108">Requirements</span></span>  

 <span data-ttu-id="5cb4f-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cb4f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cb4f-110">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5cb4f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5cb4f-111">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5cb4f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5cb4f-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cb4f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cb4f-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="5cb4f-113">See also</span></span>

- [<span data-ttu-id="5cb4f-114">Interface IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="5cb4f-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="5cb4f-115">Interface IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="5cb4f-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
