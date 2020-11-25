---
title: 'Método ICorDebugSymbolProvider:: GetStaticFieldSymbols'
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
ms.openlocfilehash: 09e68c751da6500c5580f4945e8dd1c486a09217
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698657"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="a872c-102">Método ICorDebugSymbolProvider:: GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="a872c-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>

<span data-ttu-id="a872c-103">Obtém os símbolos de campo estático que correspondem a uma assinatura de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="a872c-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a872c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a872c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a872c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a872c-105">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="a872c-106">no O número de bytes na `typeSig` matriz.</span><span class="sxs-lookup"><span data-stu-id="a872c-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="a872c-107">no Uma matriz de bytes que contém a `typespec` assinatura.</span><span class="sxs-lookup"><span data-stu-id="a872c-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="a872c-108">no O número de símbolos solicitados.</span><span class="sxs-lookup"><span data-stu-id="a872c-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="a872c-109">fora Um ponteiro para o número de símbolos recuperados pelo método.</span><span class="sxs-lookup"><span data-stu-id="a872c-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="a872c-110">fora Um ponteiro para uma matriz [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) que contém os símbolos de campo estáticos solicitados.</span><span class="sxs-lookup"><span data-stu-id="a872c-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a872c-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="a872c-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a872c-112">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a872c-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a872c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a872c-113">Requirements</span></span>  

 <span data-ttu-id="a872c-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a872c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a872c-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a872c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a872c-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a872c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a872c-117">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a872c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a872c-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="a872c-118">See also</span></span>

- [<span data-ttu-id="a872c-119">Método GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="a872c-119">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="a872c-120">Interface ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="a872c-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a872c-121">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="a872c-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
