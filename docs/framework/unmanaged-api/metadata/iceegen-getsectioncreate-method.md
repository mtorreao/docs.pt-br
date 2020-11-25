---
title: Método ICeeGen::GetSectionCreate
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
ms.openlocfilehash: 4ef3992d840f539ca07c411c2d740fa32b14edbc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722941"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="d74e2-102">Método ICeeGen::GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="d74e2-102">ICeeGen::GetSectionCreate Method</span></span>

<span data-ttu-id="d74e2-103">Gera e obtém uma seção de código usando os valores de nome e sinalizador especificados.</span><span class="sxs-lookup"><span data-stu-id="d74e2-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="d74e2-104">Este método é obsoleto e não deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="d74e2-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d74e2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d74e2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d74e2-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d74e2-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="d74e2-107">no Um ponteiro para uma cadeia de caracteres que especifica o nome da seção a ser criada.</span><span class="sxs-lookup"><span data-stu-id="d74e2-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="d74e2-108">no Sinalizadores que especificam opções.</span><span class="sxs-lookup"><span data-stu-id="d74e2-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="d74e2-109">fora Um ponteiro para a seção de código recém-criada.</span><span class="sxs-lookup"><span data-stu-id="d74e2-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d74e2-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="d74e2-110">Remarks</span></span>  

 <span data-ttu-id="d74e2-111">Chame `GetSectionCreate` somente se você tiver requisitos de seção especiais que não são tratados por outros métodos.</span><span class="sxs-lookup"><span data-stu-id="d74e2-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d74e2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d74e2-112">Requirements</span></span>  

 <span data-ttu-id="d74e2-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d74e2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d74e2-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d74e2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d74e2-115">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d74e2-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d74e2-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d74e2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74e2-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="d74e2-117">See also</span></span>

- [<span data-ttu-id="d74e2-118">Interface ICeeGen</span><span class="sxs-lookup"><span data-stu-id="d74e2-118">ICeeGen Interface</span></span>](iceegen-interface.md)
