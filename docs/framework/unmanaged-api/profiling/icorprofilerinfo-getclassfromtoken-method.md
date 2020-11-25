---
title: Método ICorProfilerInfo::GetClassFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 7d9fe7d6d5c5af32be22ba19b52e7d40033a6eb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706743"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="6a5bd-102">Método ICorProfilerInfo::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="6a5bd-102">ICorProfilerInfo::GetClassFromToken Method</span></span>

<span data-ttu-id="6a5bd-103">Obtém a ID da classe, dado o token de metadados.</span><span class="sxs-lookup"><span data-stu-id="6a5bd-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="6a5bd-104">Esse método é obsoleto no .NET Framework versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="6a5bd-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="6a5bd-105">Use [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="6a5bd-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a5bd-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6a5bd-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a5bd-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6a5bd-107">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="6a5bd-108">no A ID do módulo que contém a classe.</span><span class="sxs-lookup"><span data-stu-id="6a5bd-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="6a5bd-109">no Um `mdTypeDef` token de metadados que faz referência à classe.</span><span class="sxs-lookup"><span data-stu-id="6a5bd-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="6a5bd-110">fora Um ponteiro para a ID de classe.</span><span class="sxs-lookup"><span data-stu-id="6a5bd-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a5bd-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="6a5bd-111">Remarks</span></span>  

 <span data-ttu-id="6a5bd-112">Este método é obsoleto; em vez disso, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` para todos os tipos.</span><span class="sxs-lookup"><span data-stu-id="6a5bd-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a5bd-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a5bd-113">Requirements</span></span>  

 <span data-ttu-id="6a5bd-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a5bd-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a5bd-115">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="6a5bd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a5bd-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a5bd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a5bd-117">**Versões do .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="6a5bd-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a5bd-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="6a5bd-118">See also</span></span>

- [<span data-ttu-id="6a5bd-119">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="6a5bd-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
