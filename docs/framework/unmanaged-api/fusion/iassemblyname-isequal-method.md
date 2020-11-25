---
title: Método IAssemblyName::IsEqual
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
ms.openlocfilehash: 0fabf8159c2626d4e1716e3be60baaf1ec834032
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712970"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="71f99-102">Método IAssemblyName::IsEqual</span><span class="sxs-lookup"><span data-stu-id="71f99-102">IAssemblyName::IsEqual Method</span></span>

<span data-ttu-id="71f99-103">Determina se um objeto [IAssemblyName](iassemblyname-interface.md) especificado é igual a este `IAssemblyName` , com base nos sinalizadores de comparação especificados.</span><span class="sxs-lookup"><span data-stu-id="71f99-103">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f99-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="71f99-104">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71f99-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="71f99-105">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="71f99-106">no O `IAssemblyName` objeto para o qual comparar `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="71f99-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="71f99-107">no Uma combinação de bits de [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) de valores que influencia a comparação.</span><span class="sxs-lookup"><span data-stu-id="71f99-107">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71f99-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71f99-108">Requirements</span></span>  

 <span data-ttu-id="71f99-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71f99-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71f99-110">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="71f99-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="71f99-111">**Versões do .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71f99-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f99-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="71f99-112">See also</span></span>

- [<span data-ttu-id="71f99-113">Interface IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="71f99-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="71f99-114">Enumerações Fusion</span><span class="sxs-lookup"><span data-stu-id="71f99-114">Fusion Enumerations</span></span>](fusion-enumerations.md)
