---
title: Método ICorProfilerInfo2::GetStringLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
ms.openlocfilehash: d141a78a953d4e0ab922535ad2363c79f2e18ecd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727036"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="a0215-102">Método ICorProfilerInfo2::GetStringLayout</span><span class="sxs-lookup"><span data-stu-id="a0215-102">ICorProfilerInfo2::GetStringLayout Method</span></span>

<span data-ttu-id="a0215-103">Obtém informações sobre o layout de um objeto de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a0215-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="a0215-104">Esse método é preterido no .NET Framework 4 e é substituído pelo método [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a0215-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0215-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a0215-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0215-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a0215-106">Parameters</span></span>  

 `pBufferLengthOffset`  
 <span data-ttu-id="a0215-107">fora Um ponteiro para o deslocamento do local, relativo ao `ObjectID` ponteiro, que armazena o comprimento da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a0215-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="a0215-108">O comprimento é armazenado como um `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="a0215-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0215-109">Esse parâmetro retorna o comprimento da cadeia de caracteres em si, não o comprimento do buffer.</span><span class="sxs-lookup"><span data-stu-id="a0215-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="a0215-110">O comprimento do buffer não está mais disponível.</span><span class="sxs-lookup"><span data-stu-id="a0215-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="a0215-111">fora Um ponteiro para o deslocamento do local, relativo ao `ObjectID` ponteiro, que armazena o comprimento da própria cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a0215-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="a0215-112">O comprimento é armazenado como um `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="a0215-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="a0215-113">fora Um ponteiro para o deslocamento do buffer, relativo ao `ObjectID` ponteiro, que armazena a cadeia de caracteres largos.</span><span class="sxs-lookup"><span data-stu-id="a0215-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0215-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="a0215-114">Remarks</span></span>  

 <span data-ttu-id="a0215-115">O `GetStringLayout` método obtém os deslocamentos, em relação ao `ObjectID` ponteiro, dos locais nos quais os seguintes itens são armazenados:</span><span class="sxs-lookup"><span data-stu-id="a0215-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="a0215-116">O comprimento do buffer da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a0215-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="a0215-117">O comprimento da própria cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a0215-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="a0215-118">O buffer que contém a cadeia real de caracteres largos.</span><span class="sxs-lookup"><span data-stu-id="a0215-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="a0215-119">Cadeias de caracteres podem ser terminadas em nulo.</span><span class="sxs-lookup"><span data-stu-id="a0215-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0215-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0215-120">Requirements</span></span>  

 <span data-ttu-id="a0215-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0215-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0215-122">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="a0215-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a0215-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0215-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0215-124">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0215-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0215-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="a0215-125">See also</span></span>

- [<span data-ttu-id="a0215-126">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="a0215-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="a0215-127">Interface ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="a0215-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
