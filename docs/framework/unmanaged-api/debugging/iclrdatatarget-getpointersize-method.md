---
title: Método ICLRDataTarget::GetPointerSize
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
ms.openlocfilehash: 077aa50465d99c9098f26e67b3852feb0d399142
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703506"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="558eb-102">Método ICLRDataTarget::GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="558eb-102">ICLRDataTarget::GetPointerSize Method</span></span>

<span data-ttu-id="558eb-103">Obtém o tamanho, em bytes, do tipo de ponteiro usado pelo processo de destino.</span><span class="sxs-lookup"><span data-stu-id="558eb-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="558eb-104">Esse método é chamado pelo Common Language Runtime Data Access Services.</span><span class="sxs-lookup"><span data-stu-id="558eb-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="558eb-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="558eb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="558eb-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="558eb-106">Parameters</span></span>  

 `pointerSize`  
 <span data-ttu-id="558eb-107">fora Um ponteiro para um valor inteiro que especifica o tamanho, em bytes, de um ponteiro no processo de destino.</span><span class="sxs-lookup"><span data-stu-id="558eb-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="558eb-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="558eb-108">Remarks</span></span>  

 <span data-ttu-id="558eb-109">Este método é implementado pelo autor do aplicativo de depuração.</span><span class="sxs-lookup"><span data-stu-id="558eb-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="558eb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="558eb-110">Requirements</span></span>  

 <span data-ttu-id="558eb-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="558eb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="558eb-112">**Cabeçalho:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="558eb-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="558eb-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="558eb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="558eb-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="558eb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="558eb-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="558eb-115">See also</span></span>

- [<span data-ttu-id="558eb-116">Interface ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="558eb-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
