---
title: Método ICorProfilerInfo::GetObjectSize
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
ms.openlocfilehash: 4abcf9f4575b32dd125fd8a00783043900993c3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724098"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="2f0b7-102">Método ICorProfilerInfo::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="2f0b7-102">ICorProfilerInfo::GetObjectSize Method</span></span>

<span data-ttu-id="2f0b7-103">Obtém o tamanho de um objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f0b7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2f0b7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f0b7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2f0b7-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="2f0b7-106">no A ID do objeto.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="2f0b7-107">fora Um ponteiro para o tamanho do objeto, em bytes.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f0b7-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="2f0b7-108">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2f0b7-109">Esse método é obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-109">This method is obsolete.</span></span> <span data-ttu-id="2f0b7-110">Ele retorna COR_E_OVERFLOW para objetos com mais de 4 GB em plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="2f0b7-111">Em vez disso, use o método  [ICorProfilerInfo4:: GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2f0b7-111">Use the  [ICorProfilerInfo4::GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="2f0b7-112">Objetos diferentes dos mesmos tipos geralmente têm o mesmo tamanho.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="2f0b7-113">No entanto, alguns tipos, como matrizes ou cadeias de caracteres, podem ter um tamanho diferente para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="2f0b7-114">O tamanho retornado pelo `GetObjectSize` método não inclui nenhum preenchimento de alinhamento que possa aparecer depois que o objeto estiver no heap de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="2f0b7-115">Se você usar o `GetObjectSize` método para avançar de objeto para objeto no heap de coleta de lixo, adicione o preenchimento de alinhamento manualmente, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="2f0b7-116">No Windows de 32 bits, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 e COR_PRF_GC_GEN_2 usam o alinhamento de 4 bytes e COR_PRF_GC_LARGE_OBJECT_HEAP usa o alinhamento de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="2f0b7-117">No Windows de 64 bits, o alinhamento é sempre de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="2f0b7-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f0b7-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f0b7-118">Requirements</span></span>  

 <span data-ttu-id="2f0b7-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f0b7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f0b7-120">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="2f0b7-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f0b7-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f0b7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f0b7-122">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f0b7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f0b7-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="2f0b7-123">See also</span></span>

- [<span data-ttu-id="2f0b7-124">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="2f0b7-124">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
