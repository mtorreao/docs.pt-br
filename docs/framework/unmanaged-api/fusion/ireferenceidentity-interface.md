---
title: Interface IReferenceIdentity
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
ms.openlocfilehash: 867c09caa3bd3aed50de21c2ef91a02782830be2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704546"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="59c96-102">Interface IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="59c96-102">IReferenceIdentity Interface</span></span>

<span data-ttu-id="59c96-103">Representa uma referência à assinatura exclusiva de um objeto de código.</span><span class="sxs-lookup"><span data-stu-id="59c96-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="59c96-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="59c96-104">Methods</span></span>  
  
|<span data-ttu-id="59c96-105">Método</span><span class="sxs-lookup"><span data-stu-id="59c96-105">Method</span></span>|<span data-ttu-id="59c96-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="59c96-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="59c96-107">Obtém um ponteiro de interface para uma nova `IReferenceIdentity` instância que é idêntica a isso `IReferenceIdentity` , exceto para as alterações de atributo especificadas.</span><span class="sxs-lookup"><span data-stu-id="59c96-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="59c96-108">Obtém um ponteiro de interface para uma `IEnumIDENTITY_ATTRIBUTE` instância que contém os atributos associados a isso `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="59c96-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="59c96-109">Obtém o valor do atributo no namespace especificado, com o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="59c96-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="59c96-110">Define o atributo que tem o namespace especificado e o nome especificado para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="59c96-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59c96-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59c96-111">Requirements</span></span>  

 <span data-ttu-id="59c96-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59c96-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59c96-113">**Cabeçalho:** Isolamento. h</span><span class="sxs-lookup"><span data-stu-id="59c96-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="59c96-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59c96-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59c96-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="59c96-115">See also</span></span>

- [<span data-ttu-id="59c96-116">Interfaces de fusão</span><span class="sxs-lookup"><span data-stu-id="59c96-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="59c96-117">Interface IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="59c96-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
