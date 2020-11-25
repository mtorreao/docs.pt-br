---
title: 'Método ICorDebugSymbolProvider:: GetMergedAssemblyRecords'
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: 10bbcf2e6a536eeb4ab8141c10c177a53faa1c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730871"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="a6a4e-102">Método ICorDebugSymbolProvider:: GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="a6a4e-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>

<span data-ttu-id="a6a4e-103">Obtém os registros de símbolo de todos os assemblies mesclados.</span><span class="sxs-lookup"><span data-stu-id="a6a4e-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6a4e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a6a4e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6a4e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a6a4e-105">Parameters</span></span>  

 `cRequestedRecords`  
 <span data-ttu-id="a6a4e-106">no O número de registros de símbolo solicitado.</span><span class="sxs-lookup"><span data-stu-id="a6a4e-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="a6a4e-107">fora Um ponteiro para o número de registros de símbolo recuperados pelo método.</span><span class="sxs-lookup"><span data-stu-id="a6a4e-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="a6a4e-108">Um ponteiro para uma matriz de objetos [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a6a4e-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6a4e-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="a6a4e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6a4e-110">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a6a4e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6a4e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6a4e-111">Requirements</span></span>  

 <span data-ttu-id="a6a4e-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6a4e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6a4e-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6a4e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6a4e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6a4e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6a4e-115">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6a4e-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a4e-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="a6a4e-116">See also</span></span>

- [<span data-ttu-id="a6a4e-117">Interface ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="a6a4e-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a6a4e-118">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="a6a4e-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
