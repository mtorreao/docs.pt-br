---
title: Enumeração EContextType
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
ms.openlocfilehash: c6d1ace12bd07fa1f14c8570eca1f950a5c22be9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686326"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="30681-102">Enumeração EContextType</span><span class="sxs-lookup"><span data-stu-id="30681-102">EContextType Enumeration</span></span>

<span data-ttu-id="30681-103">Descreve o contexto de segurança do thread em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="30681-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30681-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="30681-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="30681-105">Membros</span><span class="sxs-lookup"><span data-stu-id="30681-105">Members</span></span>  
  
|<span data-ttu-id="30681-106">Membro</span><span class="sxs-lookup"><span data-stu-id="30681-106">Member</span></span>|<span data-ttu-id="30681-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="30681-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="30681-108">Indica o contexto no thread atual no momento em que o Common Language Runtime (CLR) chama o método [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) ou o contexto solicitado pelo CLR em uma chamada para o método [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="30681-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="30681-109">Indica um contexto sobre o qual o host tem privilégios mais baixos, como o coletor de lixo ou construtores de classe ou módulo.</span><span class="sxs-lookup"><span data-stu-id="30681-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30681-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="30681-110">Remarks</span></span>  

 <span data-ttu-id="30681-111">O CLR fornece um dos `EContextType` valores como um valor de parâmetro em chamadas para os `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` métodos e.</span><span class="sxs-lookup"><span data-stu-id="30681-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30681-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30681-112">Requirements</span></span>  

 <span data-ttu-id="30681-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30681-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30681-114">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="30681-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30681-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30681-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30681-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30681-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30681-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="30681-117">See also</span></span>

- [<span data-ttu-id="30681-118">Interface IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="30681-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="30681-119">Interface IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="30681-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="30681-120">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="30681-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
