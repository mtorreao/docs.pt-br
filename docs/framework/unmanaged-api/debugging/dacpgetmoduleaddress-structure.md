---
title: Estrutura DacpGetModuleAddress
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a65fa9974165fa36e59a7fb83dca6dd902f7d8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724387"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="0ca47-102">Estrutura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="0ca47-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="0ca47-103">Define o contêiner para uma solicitação de endereço de módulo.</span><span class="sxs-lookup"><span data-stu-id="0ca47-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0ca47-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0ca47-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="0ca47-105">Membros</span><span class="sxs-lookup"><span data-stu-id="0ca47-105">Members</span></span>

| <span data-ttu-id="0ca47-106">Membro</span><span class="sxs-lookup"><span data-stu-id="0ca47-106">Member</span></span>      | <span data-ttu-id="0ca47-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0ca47-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="0ca47-108">O ponteiro para o módulo.</span><span class="sxs-lookup"><span data-stu-id="0ca47-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="0ca47-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="0ca47-109">Methods</span></span>

| <span data-ttu-id="0ca47-110">Método</span><span class="sxs-lookup"><span data-stu-id="0ca47-110">Method</span></span>                                                                                               | <span data-ttu-id="0ca47-111">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0ca47-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="0ca47-112">Solicitação</span><span class="sxs-lookup"><span data-stu-id="0ca47-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="0ca47-113">Executa uma solicitação para popular a estrutura da estrutura de tempo de execução fornecida.</span><span class="sxs-lookup"><span data-stu-id="0ca47-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0ca47-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="0ca47-114">Remarks</span></span>

<span data-ttu-id="0ca47-115">Essa estrutura reside dentro do tempo de execução e não é exposta por nenhum cabeçalho ou arquivo de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="0ca47-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0ca47-116">Para usá-lo, defina a estrutura conforme especificado acima, em que `CLRDATA_ADDRESS` é um inteiro sem sinal de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="0ca47-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="0ca47-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ca47-117">Requirements</span></span>

<span data-ttu-id="0ca47-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ca47-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0ca47-119">**Cabeçalho:** None</span><span class="sxs-lookup"><span data-stu-id="0ca47-119">**Header:** None</span></span>  
<span data-ttu-id="0ca47-120">**Biblioteca:** None</span><span class="sxs-lookup"><span data-stu-id="0ca47-120">**Library:** None</span></span>  
<span data-ttu-id="0ca47-121">**.NET Framework versões:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0ca47-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0ca47-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="0ca47-122">See also</span></span>

- [<span data-ttu-id="0ca47-123">Depuração</span><span class="sxs-lookup"><span data-stu-id="0ca47-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="0ca47-124">Estruturas de depuração</span><span class="sxs-lookup"><span data-stu-id="0ca47-124">Debugging Structures</span></span>](debugging-structures.md)
