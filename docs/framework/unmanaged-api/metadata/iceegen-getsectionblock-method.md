---
title: Método ICeeGen::GetSectionBlock
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: 9ce3afded5f914ecf970d8db738becc7f5cfff84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723136"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="0c065-102">Método ICeeGen::GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="0c065-102">ICeeGen::GetSectionBlock Method</span></span>

<span data-ttu-id="0c065-103">Obtém um bloco de seção da base de código.</span><span class="sxs-lookup"><span data-stu-id="0c065-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="0c065-104">Este método é obsoleto e não deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="0c065-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c065-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0c065-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="0c065-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0c065-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="0c065-107">no A seção da qual recuperar um bloco da base de código.</span><span class="sxs-lookup"><span data-stu-id="0c065-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="0c065-108">no O comprimento do bloco a ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="0c065-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="0c065-109">no O byte, em relação ao início da seção, com o qual alinhar o primeiro byte do bloco.</span><span class="sxs-lookup"><span data-stu-id="0c065-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="0c065-110">Essa é a posição do bloco dentro da seção.</span><span class="sxs-lookup"><span data-stu-id="0c065-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="0c065-111">fora Um ponteiro para um local que recebe o endereço do bloco recuperado.</span><span class="sxs-lookup"><span data-stu-id="0c065-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c065-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="0c065-112">Remarks</span></span>  

 <span data-ttu-id="0c065-113">Chame `GetSectionBlock` somente se você tiver requisitos de seção especiais que não são tratados por outros métodos.</span><span class="sxs-lookup"><span data-stu-id="0c065-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c065-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c065-114">Requirements</span></span>  

 <span data-ttu-id="0c065-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c065-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c065-116">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0c065-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c065-117">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c065-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c065-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c065-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c065-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="0c065-119">See also</span></span>

- [<span data-ttu-id="0c065-120">Interface ICeeGen</span><span class="sxs-lookup"><span data-stu-id="0c065-120">ICeeGen Interface</span></span>](iceegen-interface.md)
