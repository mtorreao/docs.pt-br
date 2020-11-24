---
title: Interface IDefinitionAppId
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
ms.openlocfilehash: 1e6c42d8e74d2d3e7925c657c67832f662416e64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673859"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="28a19-102">Interface IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="28a19-102">IDefinitionAppId Interface</span></span>

<span data-ttu-id="28a19-103">Representa um identificador exclusivo para o código que define o aplicativo no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="28a19-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28a19-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="28a19-104">Methods</span></span>  
  
|<span data-ttu-id="28a19-105">Método</span><span class="sxs-lookup"><span data-stu-id="28a19-105">Method</span></span>|<span data-ttu-id="28a19-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="28a19-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="28a19-107">Obtém uma cadeia de caracteres formatada que representa o código neste `IDefinitionAppId` objeto.</span><span class="sxs-lookup"><span data-stu-id="28a19-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="28a19-108">Define o código desse `IDefinitionAppId` objeto como o valor de cadeia de caracteres formatado especificado.</span><span class="sxs-lookup"><span data-stu-id="28a19-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="28a19-109">Obtém um ponteiro de interface para um objeto [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) que contém os assemblies no caminho do aplicativo atual.</span><span class="sxs-lookup"><span data-stu-id="28a19-109">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="28a19-110">Define o caminho do aplicativo para o assembly no escopo atual como o valor referenciado pelo objeto [IDefinitionIdentity](idefinitionidentity-interface.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="28a19-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="28a19-111">Obtém um ponteiro para uma representação de cadeia de caracteres do identificador de token para uma assinatura para este `IDefinitionAppId` objeto.</span><span class="sxs-lookup"><span data-stu-id="28a19-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="28a19-112">Define o identificador de token de uma assinatura para esse `IDefinitionAppId` objeto para o valor de cadeia de caracteres especificado.</span><span class="sxs-lookup"><span data-stu-id="28a19-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28a19-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28a19-113">Requirements</span></span>  

 <span data-ttu-id="28a19-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28a19-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28a19-115">**Cabeçalho:** Isolamento. h</span><span class="sxs-lookup"><span data-stu-id="28a19-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="28a19-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28a19-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a19-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="28a19-117">See also</span></span>

- [<span data-ttu-id="28a19-118">Interfaces de fusão</span><span class="sxs-lookup"><span data-stu-id="28a19-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
