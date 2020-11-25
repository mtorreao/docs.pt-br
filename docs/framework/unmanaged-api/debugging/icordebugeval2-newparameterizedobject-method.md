---
title: Método ICorDebugEval2::NewParameterizedObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
ms.openlocfilehash: 8c91296bd4185fd98962d49f611a3cdcb5f0ad28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729649"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="a8a21-102">Método ICorDebugEval2::NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="a8a21-102">ICorDebugEval2::NewParameterizedObject Method</span></span>

<span data-ttu-id="a8a21-103">Cria uma instância de um novo objeto de tipo com parâmetros e chama o método de construtor do objeto.</span><span class="sxs-lookup"><span data-stu-id="a8a21-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8a21-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a8a21-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8a21-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a8a21-105">Parameters</span></span>  

 `pConstructor`  
 <span data-ttu-id="a8a21-106">no Um ponteiro para um objeto ICorDebugFunction que representa o construtor do objeto a ser instanciado.</span><span class="sxs-lookup"><span data-stu-id="a8a21-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="a8a21-107">no O número de argumentos de tipo passado.</span><span class="sxs-lookup"><span data-stu-id="a8a21-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="a8a21-108">no Uma matriz de ponteiros, cada um dos quais aponta para um objeto ICorDebugType que representa um argumento de tipo para o objeto que está sendo instanciado.</span><span class="sxs-lookup"><span data-stu-id="a8a21-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="a8a21-109">no O número de argumentos passados para o construtor.</span><span class="sxs-lookup"><span data-stu-id="a8a21-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="a8a21-110">no Uma matriz de ponteiros, cada um dos quais aponta para um objeto ICorDebugValue que representa um valor de argumento que é passado para o construtor.</span><span class="sxs-lookup"><span data-stu-id="a8a21-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8a21-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="a8a21-111">Remarks</span></span>  

 <span data-ttu-id="a8a21-112">O construtor do objeto pode ter <xref:System.Type> parâmetros.</span><span class="sxs-lookup"><span data-stu-id="a8a21-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8a21-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8a21-113">Requirements</span></span>  

 <span data-ttu-id="a8a21-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8a21-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8a21-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8a21-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8a21-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8a21-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8a21-117">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8a21-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
