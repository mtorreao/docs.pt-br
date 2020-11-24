---
title: Enumeração ECustomDumpFlavor
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
ms.openlocfilehash: 1b8440ed6e878aac3dd08d9f8ed528c93739a724
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686313"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="401e9-102">Enumeração ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="401e9-102">ECustomDumpFlavor Enumeration</span></span>

<span data-ttu-id="401e9-103">Contém valores que indicam quais itens incluir em um subconjunto personalizado de um despejo de heap ao relatar erros.</span><span class="sxs-lookup"><span data-stu-id="401e9-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401e9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="401e9-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="401e9-105">Membros</span><span class="sxs-lookup"><span data-stu-id="401e9-105">Members</span></span>  
  
|<span data-ttu-id="401e9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="401e9-106">Member</span></span>|<span data-ttu-id="401e9-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="401e9-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="401e9-108">Especifica que o despejo de heap personalizado deve iniciar como um minidespejo e incluir dados adicionais especificados por quaisquer instâncias de [CustomDumpItem](customdumpitem-structure.md) passadas para o mesmo método.</span><span class="sxs-lookup"><span data-stu-id="401e9-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="401e9-109">Especifica que o despejo de heap personalizado deve coletar todos os dados de estado de tempo de execução que não foram alocados dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="401e9-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="401e9-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="401e9-110">Remarks</span></span>  

 <span data-ttu-id="401e9-111">Um parâmetro do tipo `ECustomDumpFlavor` é passado para o método [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="401e9-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="401e9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="401e9-112">Requirements</span></span>  

 <span data-ttu-id="401e9-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="401e9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="401e9-114">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="401e9-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="401e9-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="401e9-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="401e9-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="401e9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401e9-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="401e9-117">See also</span></span>

- [<span data-ttu-id="401e9-118">Enumeração ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="401e9-118">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="401e9-119">Interface ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="401e9-119">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="401e9-120">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="401e9-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
