---
title: Estrutura BucketParameters
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
ms.openlocfilehash: 8b54cb30ec96ad0fb7851af6f2d465fe771886ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677842"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="205fb-102">Estrutura BucketParameters</span><span class="sxs-lookup"><span data-stu-id="205fb-102">BucketParameters Structure</span></span>

<span data-ttu-id="205fb-103">Armazena o nome de tipo de um evento e os parâmetros para a exceção atual associada ao evento.</span><span class="sxs-lookup"><span data-stu-id="205fb-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="205fb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="205fb-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="205fb-105">Membros</span><span class="sxs-lookup"><span data-stu-id="205fb-105">Members</span></span>  
  
|<span data-ttu-id="205fb-106">Membro</span><span class="sxs-lookup"><span data-stu-id="205fb-106">Member</span></span>|<span data-ttu-id="205fb-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="205fb-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="205fb-108">`true`, se o restante desta estrutura for válido; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="205fb-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="205fb-109">Nome do tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="205fb-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="205fb-110">Uma matriz de cadeias de caracteres, cada uma delas especifica um parâmetro para a exceção atual associada ao evento.</span><span class="sxs-lookup"><span data-stu-id="205fb-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="205fb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="205fb-111">Requirements</span></span>  

 <span data-ttu-id="205fb-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="205fb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="205fb-113">**Cabeçalho:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="205fb-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="205fb-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="205fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="205fb-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="205fb-115">See also</span></span>

- [<span data-ttu-id="205fb-116">Estruturas de hospedagem</span><span class="sxs-lookup"><span data-stu-id="205fb-116">Hosting Structures</span></span>](hosting-structures.md)
