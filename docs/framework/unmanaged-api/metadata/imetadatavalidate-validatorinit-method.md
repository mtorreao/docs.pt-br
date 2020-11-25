---
title: Método IMetaDataValidate::ValidatorInit
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
ms.openlocfilehash: e2f54e11906cd4ba1440e220530f2ca5b9de769f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708550"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="998a0-102">Método IMetaDataValidate::ValidatorInit</span><span class="sxs-lookup"><span data-stu-id="998a0-102">IMetaDataValidate::ValidatorInit Method</span></span>

<span data-ttu-id="998a0-103">Define um sinalizador que especifica o tipo do módulo no escopo de metadados atual e registra o método de retorno de chamada especificado para erros de validação.</span><span class="sxs-lookup"><span data-stu-id="998a0-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="998a0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="998a0-104">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="998a0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="998a0-105">Parameters</span></span>  

 `dwModule`  
 <span data-ttu-id="998a0-106">no Um valor da enumeração [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) que especifica o tipo do módulo no escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="998a0-106">[in] A value of the [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="998a0-107">no Um ponteiro para uma instância [IUnknown](/cpp/atl/iunknown) que serve como um retorno de chamada de função para erros de validação.</span><span class="sxs-lookup"><span data-stu-id="998a0-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="998a0-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="998a0-108">Requirements</span></span>  

 <span data-ttu-id="998a0-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="998a0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="998a0-110">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="998a0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="998a0-111">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="998a0-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="998a0-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="998a0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="998a0-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="998a0-113">See also</span></span>

- [<span data-ttu-id="998a0-114">Interface IMetaDataValidate</span><span class="sxs-lookup"><span data-stu-id="998a0-114">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)
