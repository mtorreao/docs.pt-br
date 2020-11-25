---
title: Método ICeeGen::EmitString
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
ms.openlocfilehash: b9c907868df31da8d995c6a6b86db258d395335d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715440"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="649fe-102">Método ICeeGen::EmitString</span><span class="sxs-lookup"><span data-stu-id="649fe-102">ICeeGen::EmitString Method</span></span>

<span data-ttu-id="649fe-103">Emite a cadeia de caracteres especificada na base de código.</span><span class="sxs-lookup"><span data-stu-id="649fe-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="649fe-104">Este método é obsoleto e não deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="649fe-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="649fe-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="649fe-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="649fe-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="649fe-106">Parameters</span></span>  

 `lpString`  
 <span data-ttu-id="649fe-107">no A cadeia de caracteres a ser emitida.</span><span class="sxs-lookup"><span data-stu-id="649fe-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="649fe-108">fora O endereço virtual relativo da cadeia de caracteres emitida.</span><span class="sxs-lookup"><span data-stu-id="649fe-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="649fe-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="649fe-109">Requirements</span></span>  

 <span data-ttu-id="649fe-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="649fe-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="649fe-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="649fe-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="649fe-112">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="649fe-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="649fe-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="649fe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="649fe-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="649fe-114">See also</span></span>

- [<span data-ttu-id="649fe-115">Interface ICeeGen</span><span class="sxs-lookup"><span data-stu-id="649fe-115">ICeeGen Interface</span></span>](iceegen-interface.md)
