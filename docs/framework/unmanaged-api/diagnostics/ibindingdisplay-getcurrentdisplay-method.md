---
title: Método IBindingDisplay::GetCurrentDisplay
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: d52f089923d16f93345444c07ff8e0619644f2eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725142"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="fed32-102">Método IBindingDisplay::GetCurrentDisplay</span><span class="sxs-lookup"><span data-stu-id="fed32-102">IBindingDisplay::GetCurrentDisplay Method</span></span>

<span data-ttu-id="fed32-103">Retorna as informações de exibição da Associação atual.</span><span class="sxs-lookup"><span data-stu-id="fed32-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed32-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fed32-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fed32-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fed32-105">Parameters</span></span>  

 `display`  
 <span data-ttu-id="fed32-106">[out, retval] Um ponteiro para um SafeArray que contém as informações de exibição de associação.</span><span class="sxs-lookup"><span data-stu-id="fed32-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fed32-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="fed32-107">Remarks</span></span>  

 <span data-ttu-id="fed32-108">O método [IBindingDisplay:: InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) deve ter êxito anteriormente e o programa deve ser interrompido por um depurador.</span><span class="sxs-lookup"><span data-stu-id="fed32-108">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="fed32-109">O chamador deve desalocar a `SAFEARRAY` memória retornada usando [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="fed32-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed32-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fed32-110">Requirements</span></span>  

 <span data-ttu-id="fed32-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fed32-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed32-112">**Cabeçalho:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="fed32-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="fed32-113">**Biblioteca:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="fed32-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="fed32-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fed32-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed32-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="fed32-115">See also</span></span>

- [<span data-ttu-id="fed32-116">Interface IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="fed32-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="fed32-117">Método InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="fed32-117">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
