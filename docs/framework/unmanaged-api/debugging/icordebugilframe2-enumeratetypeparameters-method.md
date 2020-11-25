---
title: Método ICorDebugILFrame2::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
ms.openlocfilehash: 73c17864047270302dbc115667eec4bf5ea1569d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725034"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="d0430-102">Método ICorDebugILFrame2::EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="d0430-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>

<span data-ttu-id="d0430-103">Obtém um objeto ICorDebugTypeEnum que contém os <xref:System.Type> parâmetros neste quadro.</span><span class="sxs-lookup"><span data-stu-id="d0430-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0430-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d0430-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0430-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d0430-105">Parameters</span></span>  

 `ppTyParEnum`  
 <span data-ttu-id="d0430-106">Um ponteiro para o endereço de um objeto de interface ICorDebugTypeEnum que permite a enumeração de parâmetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="d0430-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="d0430-107">A lista de parâmetros de tipo inclui os parâmetros de tipo de classe (se houver) seguidos pelos parâmetros de tipo de método (se houver).</span><span class="sxs-lookup"><span data-stu-id="d0430-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0430-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="d0430-108">Remarks</span></span>  

 <span data-ttu-id="d0430-109">Use o método [IMetaDataImport2:: EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) para determinar quantos parâmetros de tipo de classe e parâmetros de tipo de método essa lista contém.</span><span class="sxs-lookup"><span data-stu-id="d0430-109">Use the [IMetaDataImport2::EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="d0430-110">Os parâmetros de tipo nem sempre estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d0430-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0430-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0430-111">Requirements</span></span>  

 <span data-ttu-id="d0430-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0430-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0430-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0430-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0430-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0430-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0430-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0430-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
