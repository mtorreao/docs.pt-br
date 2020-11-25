---
title: Método IManagedObject::GetSerializedBuffer
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
ms.openlocfilehash: 159ece09ae0b6a67780639da8aae8c0e4b412bb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730681"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="9f9b2-102">Método IManagedObject::GetSerializedBuffer</span><span class="sxs-lookup"><span data-stu-id="9f9b2-102">IManagedObject::GetSerializedBuffer Method</span></span>

<span data-ttu-id="9f9b2-103">Obtém a representação da cadeia de caracteres deste objeto gerenciado.</span><span class="sxs-lookup"><span data-stu-id="9f9b2-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f9b2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9f9b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f9b2-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9f9b2-105">Parameters</span></span>  

 `pBSTR`  
 <span data-ttu-id="9f9b2-106">fora Um ponteiro para uma cadeia de caracteres que é o objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="9f9b2-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f9b2-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="9f9b2-107">Remarks</span></span>  

 <span data-ttu-id="9f9b2-108">O `GetSerializedBuffer` método serializa o objeto para que ele possa ser empacotado para o cliente.</span><span class="sxs-lookup"><span data-stu-id="9f9b2-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f9b2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f9b2-109">Requirements</span></span>  

 <span data-ttu-id="9f9b2-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f9b2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f9b2-111">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9f9b2-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f9b2-112">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f9b2-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f9b2-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f9b2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f9b2-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="9f9b2-114">See also</span></span>

- [<span data-ttu-id="9f9b2-115">Interface IManagedObject</span><span class="sxs-lookup"><span data-stu-id="9f9b2-115">IManagedObject Interface</span></span>](imanagedobject-interface.md)
