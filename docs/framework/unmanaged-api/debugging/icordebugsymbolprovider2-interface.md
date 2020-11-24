---
title: Interface ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: 3bef03e9e85224058bc17e1f0ce8746e98aa30f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688335"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="0c266-102">Interface ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="0c266-102">ICorDebugSymbolProvider2 Interface</span></span>

<span data-ttu-id="0c266-103">Estende logicamente a interface [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) para recuperar informações adicionais de símbolo de depuração.</span><span class="sxs-lookup"><span data-stu-id="0c266-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c266-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0c266-104">Methods</span></span>  
  
|<span data-ttu-id="0c266-105">Método</span><span class="sxs-lookup"><span data-stu-id="0c266-105">Method</span></span>|<span data-ttu-id="0c266-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0c266-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c266-107">Método GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="0c266-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="0c266-108">Retorna o método iniciando o endereço virtual relativo de um método e o quadro pai, dado um endereço virtual relativo de código.</span><span class="sxs-lookup"><span data-stu-id="0c266-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="0c266-109">Método GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="0c266-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="0c266-110">Recupera um mapa de dicionário genérico.</span><span class="sxs-lookup"><span data-stu-id="0c266-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c266-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="0c266-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c266-112">Essa interface está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0c266-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0c266-113">Se você implementar essa interface para cenários ICorDebug fora do .NET Native, o Common Language Runtime ignorará essa interface.</span><span class="sxs-lookup"><span data-stu-id="0c266-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c266-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c266-114">Requirements</span></span>  

 <span data-ttu-id="0c266-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c266-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c266-116">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c266-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c266-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c266-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c266-118">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c266-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c266-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="0c266-119">See also</span></span>

- [<span data-ttu-id="0c266-120">Interface ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="0c266-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="0c266-121">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="0c266-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0c266-122">Depuração</span><span class="sxs-lookup"><span data-stu-id="0c266-122">Debugging</span></span>](index.md)
