---
title: Estrutura COR_IL_MAP
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
ms.openlocfilehash: fb6b5d43e60b52c867535c42d59a098ef3c959bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726376"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="dbc2e-102">Estrutura COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="dbc2e-102">COR_IL_MAP Structure</span></span>

<span data-ttu-id="dbc2e-103">Especifica mudanças no deslocamento relativo de uma função.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbc2e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dbc2e-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="dbc2e-105">Membros</span><span class="sxs-lookup"><span data-stu-id="dbc2e-105">Members</span></span>  
  
|<span data-ttu-id="dbc2e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="dbc2e-106">Member</span></span>|<span data-ttu-id="dbc2e-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="dbc2e-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="dbc2e-108">O antigo deslocamento da MSIL (Microsoft Intermediate Language) relativo ao início da função.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="dbc2e-109">O novo deslocamento MSIL relativo ao início da função.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="dbc2e-110">`true` Se o mapeamento é conhecido como preciso; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="dbc2e-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbc2e-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="dbc2e-111">Remarks</span></span>  

 <span data-ttu-id="dbc2e-112">O formato do mapa é o seguinte: o depurador irá pressupor que `oldOffset` se refere a um deslocamento MSIL dentro do código MSIL original e não modificado.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="dbc2e-113">O `newOffset` parâmetro refere-se ao deslocamento MSIL correspondente dentro do novo código instrumentado.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="dbc2e-114">Para que a depuração funcione corretamente, os requisitos a seguir devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="dbc2e-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="dbc2e-115">O mapa deve ser classificado em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="dbc2e-116">O código MSIL instrumentado não deve ser reordenado.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="dbc2e-117">O código MSIL original não deve ser removido.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="dbc2e-118">O mapa deve incluir entradas para mapear todos os pontos de sequência do arquivo de banco de dados do programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="dbc2e-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="dbc2e-119">O mapa não interpola as entradas ausentes.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="dbc2e-120">O exemplo a seguir mostra um mapa e seus resultados.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="dbc2e-121">Mapeada</span><span class="sxs-lookup"><span data-stu-id="dbc2e-121">Map:</span></span>  
  
- <span data-ttu-id="dbc2e-122">0 deslocamento antigo, 0 deslocamento novo</span><span class="sxs-lookup"><span data-stu-id="dbc2e-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="dbc2e-123">5 deslocamento antigo, 10 novos deslocamentos</span><span class="sxs-lookup"><span data-stu-id="dbc2e-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="dbc2e-124">9 deslocamento antigo, 20 deslocamento novo</span><span class="sxs-lookup"><span data-stu-id="dbc2e-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="dbc2e-125">Resultados:</span><span class="sxs-lookup"><span data-stu-id="dbc2e-125">Results:</span></span>  
  
- <span data-ttu-id="dbc2e-126">Um deslocamento antigo de 0, 1, 2, 3 ou 4 será mapeado para um novo deslocamento de 0.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="dbc2e-127">Um deslocamento antigo de 5, 6, 7 ou 8 será mapeado para o novo deslocamento 10.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="dbc2e-128">Um deslocamento antigo de 9 ou superior será mapeado para o novo deslocamento 20.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="dbc2e-129">Um novo deslocamento de 0, 1, 2, 3, 4, 5, 6, 7, 8 ou 9 será mapeado para o deslocamento antigo 0.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="dbc2e-130">Um novo deslocamento de 10, 11, 12, 13, 14, 15, 16, 17, 18 ou 19 será mapeado para o deslocamento antigo 5.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="dbc2e-131">Um novo deslocamento de 20 ou mais será mapeado para o deslocamento antigo 9.</span><span class="sxs-lookup"><span data-stu-id="dbc2e-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbc2e-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbc2e-132">Requirements</span></span>  

 <span data-ttu-id="dbc2e-133">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbc2e-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbc2e-134">**Cabeçalho:** CorDebug. idl, CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="dbc2e-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="dbc2e-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbc2e-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbc2e-136">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbc2e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc2e-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="dbc2e-137">See also</span></span>

- [<span data-ttu-id="dbc2e-138">Estruturas de depuração</span><span class="sxs-lookup"><span data-stu-id="dbc2e-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="dbc2e-139">Depuração</span><span class="sxs-lookup"><span data-stu-id="dbc2e-139">Debugging</span></span>](index.md)
