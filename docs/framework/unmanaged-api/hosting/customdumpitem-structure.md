---
title: Estrutura CustomDumpItem
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
ms.openlocfilehash: c77e93686c7d121e9fe2a92f03970404ab823dc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673235"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="748de-102">Estrutura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="748de-102">CustomDumpItem Structure</span></span>

<span data-ttu-id="748de-103">Descreve um item a ser adicionado a um despejo personalizado no relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="748de-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="748de-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="748de-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="748de-105">Membros</span><span class="sxs-lookup"><span data-stu-id="748de-105">Members</span></span>  
  
|<span data-ttu-id="748de-106">Membro</span><span class="sxs-lookup"><span data-stu-id="748de-106">Member</span></span>|<span data-ttu-id="748de-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="748de-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="748de-108">Um valor [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) que indica o tipo de item a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="748de-108">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="748de-109">Não usado no momento.</span><span class="sxs-lookup"><span data-stu-id="748de-109">Not currently used.</span></span> <span data-ttu-id="748de-110">Os itens adicionados à União não devem ser maiores do que o tamanho do ponteiro.</span><span class="sxs-lookup"><span data-stu-id="748de-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="748de-111">Se `struct` for necessário, você deverá alocá-lo separadamente e apontar para ele.</span><span class="sxs-lookup"><span data-stu-id="748de-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="748de-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="748de-112">Remarks</span></span>  

 <span data-ttu-id="748de-113">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) usa um parâmetro do tipo `CustomDumpItem` .</span><span class="sxs-lookup"><span data-stu-id="748de-113">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="748de-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="748de-114">Requirements</span></span>  

 <span data-ttu-id="748de-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="748de-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="748de-116">**Cabeçalho:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="748de-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="748de-117">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="748de-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="748de-118">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="748de-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="748de-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="748de-119">See also</span></span>

- [<span data-ttu-id="748de-120">Estruturas de hospedagem</span><span class="sxs-lookup"><span data-stu-id="748de-120">Hosting Structures</span></span>](hosting-structures.md)
