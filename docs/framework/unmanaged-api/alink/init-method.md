---
title: Método Init
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 25a1c29ab94a785304b83d5b1bcb2d7176742a68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726012"
---
# <a name="init-method"></a><span data-ttu-id="74eaf-102">Método Init</span><span class="sxs-lookup"><span data-stu-id="74eaf-102">Init Method</span></span>

<span data-ttu-id="74eaf-103">Prepara objetos que implementam a [interface IALink](ialink-interface.md) para uso.</span><span class="sxs-lookup"><span data-stu-id="74eaf-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74eaf-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="74eaf-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="74eaf-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="74eaf-105">Parameters</span></span>  

 `pDispenser`  
 <span data-ttu-id="74eaf-106">Ponteiro de [interface IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) para o dispensador de metadados.</span><span class="sxs-lookup"><span data-stu-id="74eaf-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="74eaf-107">Ponteiro de [interface IMetaDataError](../metadata/imetadataerror-interface.md) para uma interface de tratamento de erro opcional.</span><span class="sxs-lookup"><span data-stu-id="74eaf-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74eaf-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="74eaf-108">Return Value</span></span>  

 <span data-ttu-id="74eaf-109">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="74eaf-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74eaf-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74eaf-110">Requirements</span></span>  

 <span data-ttu-id="74eaf-111">Requer ALink. h</span><span class="sxs-lookup"><span data-stu-id="74eaf-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74eaf-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="74eaf-112">See also</span></span>

- [<span data-ttu-id="74eaf-113">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="74eaf-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="74eaf-114">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="74eaf-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="74eaf-115">API do ALink</span><span class="sxs-lookup"><span data-stu-id="74eaf-115">ALink API</span></span>](index.md)
