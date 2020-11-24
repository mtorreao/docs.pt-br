---
title: Método EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
ms.openlocfilehash: 445c833d10631341ef7ad579eaff8ddd96be3428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684844"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="685a0-102">Método EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="685a0-102">EnumCustomAttributes Method</span></span>

<span data-ttu-id="685a0-103">Recupera atributos personalizados no nível do assembly.</span><span class="sxs-lookup"><span data-stu-id="685a0-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685a0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="685a0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="685a0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="685a0-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="685a0-106">Identificador do enumerador.</span><span class="sxs-lookup"><span data-stu-id="685a0-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="685a0-107">Tipo de atributos a serem enumerados.</span><span class="sxs-lookup"><span data-stu-id="685a0-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="685a0-108">Use `mdTokenNill` para todos os atributos.</span><span class="sxs-lookup"><span data-stu-id="685a0-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="685a0-109">Recebe tokens de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="685a0-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="685a0-110">Especifica o tamanho da `rCustomValues` matriz.</span><span class="sxs-lookup"><span data-stu-id="685a0-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="685a0-111">Opcionalmente, recebe a contagem de valores de token.</span><span class="sxs-lookup"><span data-stu-id="685a0-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="685a0-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="685a0-112">Return Value</span></span>  

 <span data-ttu-id="685a0-113">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="685a0-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="685a0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="685a0-114">Requirements</span></span>  

 <span data-ttu-id="685a0-115">Requer ALink. h</span><span class="sxs-lookup"><span data-stu-id="685a0-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685a0-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="685a0-116">See also</span></span>

- [<span data-ttu-id="685a0-117">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="685a0-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="685a0-118">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="685a0-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="685a0-119">API do ALink</span><span class="sxs-lookup"><span data-stu-id="685a0-119">ALink API</span></span>](index.md)
