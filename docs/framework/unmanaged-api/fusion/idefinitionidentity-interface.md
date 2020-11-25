---
title: Interface IDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 4f08fbbf9c8be16dff092327713e731c5aa14661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732856"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="f31c5-102">Interface IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="f31c5-102">IDefinitionIdentity Interface</span></span>

<span data-ttu-id="f31c5-103">Representa a assinatura exclusiva do código que define o aplicativo no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="f31c5-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f31c5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f31c5-104">Methods</span></span>  
  
|<span data-ttu-id="f31c5-105">Método</span><span class="sxs-lookup"><span data-stu-id="f31c5-105">Method</span></span>|<span data-ttu-id="f31c5-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="f31c5-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="f31c5-107">Obtém um ponteiro de interface para um novo `IDefinitionIdentity` objeto que é idêntico a este `IDefinitionIdentity` , exceto para as alterações de atributo especificadas.</span><span class="sxs-lookup"><span data-stu-id="f31c5-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="f31c5-108">Obtém um ponteiro de interface para um objeto [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) que contém os atributos associados a ele `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="f31c5-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="f31c5-109">Obtém o valor do atributo com o nome especificado no namespace especificado.</span><span class="sxs-lookup"><span data-stu-id="f31c5-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="f31c5-110">Define o atributo que tem o nome especificado no namespace especificado para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="f31c5-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f31c5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f31c5-111">Requirements</span></span>  

 <span data-ttu-id="f31c5-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f31c5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f31c5-113">**Cabeçalho:** Isolamento. h</span><span class="sxs-lookup"><span data-stu-id="f31c5-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f31c5-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f31c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f31c5-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="f31c5-115">See also</span></span>

- [<span data-ttu-id="f31c5-116">Interfaces de fusão</span><span class="sxs-lookup"><span data-stu-id="f31c5-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
