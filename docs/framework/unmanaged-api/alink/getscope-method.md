---
title: Método GetScope
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
ms.openlocfilehash: fd5ae6ef40cb171c33132df0f640acbef96d69b5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684662"
---
# <a name="getscope-method"></a><span data-ttu-id="8bd93-102">Método GetScope</span><span class="sxs-lookup"><span data-stu-id="8bd93-102">GetScope Method</span></span>

<span data-ttu-id="8bd93-103">Obtém um escopo de importação.</span><span class="sxs-lookup"><span data-stu-id="8bd93-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd93-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8bd93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bd93-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8bd93-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="8bd93-106">ID exclusiva do assembly para o qual importar.</span><span class="sxs-lookup"><span data-stu-id="8bd93-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="8bd93-107">ID exclusiva do arquivo do qual importar.</span><span class="sxs-lookup"><span data-stu-id="8bd93-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="8bd93-108">Escopo de base zero para importar.</span><span class="sxs-lookup"><span data-stu-id="8bd93-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="8bd93-109">Recebe a interface da [interface IMetaDataImport](../metadata/imetadataimport-interface.md) para o escopo.</span><span class="sxs-lookup"><span data-stu-id="8bd93-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bd93-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="8bd93-110">Return Value</span></span>  

 <span data-ttu-id="8bd93-111">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="8bd93-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bd93-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8bd93-112">Requirements</span></span>  

 <span data-ttu-id="8bd93-113">Requer ALink. h</span><span class="sxs-lookup"><span data-stu-id="8bd93-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd93-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="8bd93-114">See also</span></span>

- [<span data-ttu-id="8bd93-115">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="8bd93-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8bd93-116">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="8bd93-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8bd93-117">API do ALink</span><span class="sxs-lookup"><span data-stu-id="8bd93-117">ALink API</span></span>](index.md)
