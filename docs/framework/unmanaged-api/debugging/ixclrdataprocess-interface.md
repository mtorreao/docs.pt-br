---
title: Interface IXCLRDataProcess
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 376ec2b840bc17c79ed1f27c17a8ddd22c37a0f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245335"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="cd6aa-102">Interface IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="cd6aa-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="cd6aa-103">Fornece métodos para consultar informações sobre um processo.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="cd6aa-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cd6aa-104">Methods</span></span>

| <span data-ttu-id="cd6aa-105">Método</span><span class="sxs-lookup"><span data-stu-id="cd6aa-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="cd6aa-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="cd6aa-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="cd6aa-107">GetRuntimeNameByAddress</span><span class="sxs-lookup"><span data-stu-id="cd6aa-107">GetRuntimeNameByAddress</span></span>](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | <span data-ttu-id="cd6aa-108">Obtém um nome para o endereço fornecido.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-108">Gets a name for the given address.</span></span>                                                               |
| [<span data-ttu-id="cd6aa-109">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="cd6aa-109">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="cd6aa-110">Obtém um `AppDomain` em um processo por sua ID exclusiva.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-110">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="cd6aa-111">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="cd6aa-111">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="cd6aa-112">Fornece um identificador para enumerar os módulos de um processo.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-112">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="cd6aa-113">EnumModule</span><span class="sxs-lookup"><span data-stu-id="cd6aa-113">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="cd6aa-114">Enumera os módulos desse processo.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-114">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="cd6aa-115">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="cd6aa-115">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="cd6aa-116">Libera os recursos usados por iteradores internos usados durante a enumeração do módulo.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-116">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="cd6aa-117">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="cd6aa-117">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="cd6aa-118">Fornece um identificador para enumerar as instâncias de método de `AppDomain` Iniciar em um determinado endereço.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-118">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="cd6aa-119">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="cd6aa-119">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="cd6aa-120">Enumera as instâncias de método deste processo Iniciando em um deslocamento de endereço.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-120">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="cd6aa-121">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="cd6aa-121">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="cd6aa-122">Libera os recursos usados por iteradores internos usados durante a enumeração da instância.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-122">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="cd6aa-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="cd6aa-123">Remarks</span></span>

<span data-ttu-id="cd6aa-124">Essa interface reside dentro do tempo de execução e não é exposta por nenhum cabeçalho ou arquivo de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-124">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="cd6aa-125">No entanto, é uma interface COM que deriva de `IUnknown` com GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` que pode ser obtido por meio dos mecanismos com usuais.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-125">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="cd6aa-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd6aa-126">Requirements</span></span>

<span data-ttu-id="cd6aa-127">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd6aa-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="cd6aa-128">**Cabeçalho:** None</span><span class="sxs-lookup"><span data-stu-id="cd6aa-128">**Header:** None</span></span>  
<span data-ttu-id="cd6aa-129">**Biblioteca:** None</span><span class="sxs-lookup"><span data-stu-id="cd6aa-129">**Library:** None</span></span>  
<span data-ttu-id="cd6aa-130">**.NET Framework versões:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cd6aa-130">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="cd6aa-131">Veja também</span><span class="sxs-lookup"><span data-stu-id="cd6aa-131">See also</span></span>

- [<span data-ttu-id="cd6aa-132">Depuração</span><span class="sxs-lookup"><span data-stu-id="cd6aa-132">Debugging</span></span>](index.md)
- [<span data-ttu-id="cd6aa-133">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="cd6aa-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
