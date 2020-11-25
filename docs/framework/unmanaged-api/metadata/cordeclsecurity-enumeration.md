---
title: Enumeração CorDeclSecurity
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
ms.openlocfilehash: dd599ce8c63fa94e1a18b4e2d18fa334238728bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718872"
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="115e5-102">Enumeração CorDeclSecurity</span><span class="sxs-lookup"><span data-stu-id="115e5-102">CorDeclSecurity Enumeration</span></span>

<span data-ttu-id="115e5-103">Especifica as ações de segurança que podem ser executadas usando a segurança declarativa.</span><span class="sxs-lookup"><span data-stu-id="115e5-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="115e5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="115e5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="115e5-105">Membros</span><span class="sxs-lookup"><span data-stu-id="115e5-105">Members</span></span>  
  
|<span data-ttu-id="115e5-106">Membro</span><span class="sxs-lookup"><span data-stu-id="115e5-106">Member</span></span>|<span data-ttu-id="115e5-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="115e5-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="115e5-108">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="115e5-109">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="115e5-110">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="115e5-111">Todos os chamadores na pilha de chamadas deverão ter a permissão especificada pelo objeto de permissão atual.</span><span class="sxs-lookup"><span data-stu-id="115e5-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="115e5-112">O código de chamada pode acessar o recurso identificado pelo objeto de permissão atual, mesmo que os chamadores mais altos na pilha não tenham recebido permissão para acessar o recurso</span><span class="sxs-lookup"><span data-stu-id="115e5-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="115e5-113">A capacidade de acessar o recurso especificado pelo objeto de permissão atual é negada aos chamadores, mesmo que eles tenham recebido permissão para acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="115e5-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="115e5-114">Somente os recursos especificados por esse objeto de permissão poderão ser acessados, mesmo que o código tenha recebido permissão para acessar outros recursos.</span><span class="sxs-lookup"><span data-stu-id="115e5-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="115e5-115">É necessário que o chamador imediato tenha recebido a permissão especificada para um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="115e5-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="115e5-116">A classe derivada que herda outra classe ou a substituição de um método é necessária para ter recebido a permissão especificada.</span><span class="sxs-lookup"><span data-stu-id="115e5-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="115e5-117">O chamador pode solicitar as permissões mínimas necessárias para que o código seja executado.</span><span class="sxs-lookup"><span data-stu-id="115e5-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="115e5-118">Esta ação só pode ser usada no escopo do assembly.</span><span class="sxs-lookup"><span data-stu-id="115e5-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="115e5-119">O chamador pode solicitar permissões adicionais que são opcionais (não é necessário executar).</span><span class="sxs-lookup"><span data-stu-id="115e5-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="115e5-120">Essa solicitação recusa implicitamente todas as outras permissões não solicitadas especificamente.</span><span class="sxs-lookup"><span data-stu-id="115e5-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="115e5-121">Esta ação só pode ser usada no escopo do assembly.</span><span class="sxs-lookup"><span data-stu-id="115e5-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="115e5-122">A solicitação do chamador para permissões que podem ser usadas não será concedida.</span><span class="sxs-lookup"><span data-stu-id="115e5-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="115e5-123">Esta ação só pode ser usada no escopo do assembly.</span><span class="sxs-lookup"><span data-stu-id="115e5-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="115e5-124">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="115e5-125">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="115e5-126">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="115e5-127">O chamador imediato deverá ter recebido a permissão especificada.</span><span class="sxs-lookup"><span data-stu-id="115e5-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="115e5-128">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="115e5-129">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="115e5-130">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="115e5-131">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="115e5-132">Reservado.</span><span class="sxs-lookup"><span data-stu-id="115e5-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="115e5-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="115e5-133">Requirements</span></span>  

 <span data-ttu-id="115e5-134">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="115e5-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="115e5-135">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="115e5-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="115e5-136">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="115e5-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="115e5-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="115e5-137">See also</span></span>

- [<span data-ttu-id="115e5-138">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="115e5-138">Metadata Enumerations</span></span>](metadata-enumerations.md)
