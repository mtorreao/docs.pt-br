---
title: Enumeração EClrUnhandledException
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: bccd44e1bead4feadf67929dc104557715904577
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686430"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="d1adb-102">Enumeração EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="d1adb-102">EClrUnhandledException Enumeration</span></span>

<span data-ttu-id="d1adb-103">Descreve as opções disponíveis para gerenciar exceções que não são manipuladas no código do usuário.</span><span class="sxs-lookup"><span data-stu-id="d1adb-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1adb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d1adb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="d1adb-105">Membros</span><span class="sxs-lookup"><span data-stu-id="d1adb-105">Members</span></span>  
  
|<span data-ttu-id="d1adb-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d1adb-106">Member</span></span>|<span data-ttu-id="d1adb-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="d1adb-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="d1adb-108">Especifica que o comportamento padrão ocorre.</span><span class="sxs-lookup"><span data-stu-id="d1adb-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="d1adb-109">O processo é interrompido.</span><span class="sxs-lookup"><span data-stu-id="d1adb-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="d1adb-110">Especifica que o Common Language Runtime (CLR) ignora exceções sem tratamento e permite que o host determine qualquer ação adicional.</span><span class="sxs-lookup"><span data-stu-id="d1adb-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1adb-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="d1adb-111">Remarks</span></span>  

 <span data-ttu-id="d1adb-112">Para especificar que o CLR se comporte como versões anteriores, use o `eHostDeterminedPolicy` membro.</span><span class="sxs-lookup"><span data-stu-id="d1adb-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1adb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1adb-113">Requirements</span></span>  

 <span data-ttu-id="d1adb-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1adb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1adb-115">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d1adb-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1adb-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d1adb-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1adb-117">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1adb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1adb-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="d1adb-118">See also</span></span>

- [<span data-ttu-id="d1adb-119">Enumeração EClrFailure</span><span class="sxs-lookup"><span data-stu-id="d1adb-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="d1adb-120">Enumeração EClrOperation</span><span class="sxs-lookup"><span data-stu-id="d1adb-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="d1adb-121">Interface ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="d1adb-121">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="d1adb-122">Método SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="d1adb-122">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="d1adb-123">Interface IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="d1adb-123">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="d1adb-124">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="d1adb-124">Hosting Enumerations</span></span>](hosting-enumerations.md)
