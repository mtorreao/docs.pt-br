---
title: Enumeração CorRefToDefCheck
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
ms.openlocfilehash: e7ce604acddb88d5a15844cbce2622b21e364cc1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706106"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="2c525-102">Enumeração CorRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="2c525-102">CorRefToDefCheck Enumeration</span></span>

<span data-ttu-id="2c525-103">Especifica sinalizadores para controlar quais itens referenciados são convertidos em suas definições a fim de otimizar o código.</span><span class="sxs-lookup"><span data-stu-id="2c525-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c525-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2c525-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="2c525-105">Membros</span><span class="sxs-lookup"><span data-stu-id="2c525-105">Members</span></span>  
  
|<span data-ttu-id="2c525-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2c525-106">Member</span></span>|<span data-ttu-id="2c525-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2c525-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="2c525-108">Especifica que referências de tipo e referências de membro devem ser convertidas em definições.</span><span class="sxs-lookup"><span data-stu-id="2c525-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="2c525-109">Esse é o valor padrão ( `MDTypeRefToDef` &#124; `MDMemberRefToDef` ).</span><span class="sxs-lookup"><span data-stu-id="2c525-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="2c525-110">Especifica que todos os itens referenciados devem ser convertidos em definições.</span><span class="sxs-lookup"><span data-stu-id="2c525-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="2c525-111">Especifica que nenhum item referenciado deve ser convertido em definições.</span><span class="sxs-lookup"><span data-stu-id="2c525-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="2c525-112">Especifica que apenas referências de tipo devem ser convertidas em definições de tipo.</span><span class="sxs-lookup"><span data-stu-id="2c525-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="2c525-113">Especifica que somente referências de membro devem ser convertidas em definições.</span><span class="sxs-lookup"><span data-stu-id="2c525-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="2c525-114">Ou seja, as referências de membro devem ser convertidas em definições de método ou definições de campo.</span><span class="sxs-lookup"><span data-stu-id="2c525-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c525-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c525-115">Requirements</span></span>  

 <span data-ttu-id="2c525-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c525-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c525-117">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="2c525-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2c525-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c525-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c525-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c525-119">See also</span></span>

- [<span data-ttu-id="2c525-120">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="2c525-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
