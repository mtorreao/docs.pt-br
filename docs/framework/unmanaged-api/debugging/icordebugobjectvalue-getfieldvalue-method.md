---
title: Método ICorDebugObjectValue::GetFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 745be25183f6b94e7a807c4230961d72e2836fe5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695329"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="6d405-102">Método ICorDebugObjectValue::GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="6d405-102">ICorDebugObjectValue::GetFieldValue Method</span></span>

<span data-ttu-id="6d405-103">Obtém o valor do campo especificado da classe especificada para esse valor de objeto.</span><span class="sxs-lookup"><span data-stu-id="6d405-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d405-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6d405-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d405-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6d405-105">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="6d405-106">no Um ponteiro para um objeto "ICorDebugClass" que representa a classe para a qual obter o valor do campo.</span><span class="sxs-lookup"><span data-stu-id="6d405-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="6d405-107">no Um `mdFieldDef` token que faz referência aos metadados que descrevem o campo.</span><span class="sxs-lookup"><span data-stu-id="6d405-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="6d405-108">fora Um ponteiro para um objeto "ICorDebugValue" que representa o valor do campo especificado.</span><span class="sxs-lookup"><span data-stu-id="6d405-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d405-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="6d405-109">Remarks</span></span>  

 <span data-ttu-id="6d405-110">A classe, especificada no `pClass` parâmetro, deve estar na hierarquia da classe do valor do objeto e o campo deve ser um campo dessa classe.</span><span class="sxs-lookup"><span data-stu-id="6d405-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="6d405-111">O `GetFieldValue` método ainda terá sucesso para objetos genéricos e classes genéricas.</span><span class="sxs-lookup"><span data-stu-id="6d405-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="6d405-112">Por exemplo, se MyDictionary \<V> herda de Dictionary \<string,V> e o valor Object for do tipo MyDictionary \<int32> , passar o `ICorDebugClass` objeto para Dictionary \<K,V> obterá com êxito um campo de Dictionary \<string,int32> .</span><span class="sxs-lookup"><span data-stu-id="6d405-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d405-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d405-113">Requirements</span></span>  

 <span data-ttu-id="6d405-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d405-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d405-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d405-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d405-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d405-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d405-117">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d405-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d405-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="6d405-118">See also</span></span>
