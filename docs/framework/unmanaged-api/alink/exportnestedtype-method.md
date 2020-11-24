---
title: Método ExportNestedType
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
ms.openlocfilehash: 69c99e2facfcb9077c3fc4131186ba3882c7cef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684831"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="44b61-102">Método ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="44b61-102">ExportNestedType Method</span></span>

<span data-ttu-id="44b61-103">Especifica os tipos aninhados como exportáveis.</span><span class="sxs-lookup"><span data-stu-id="44b61-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="44b61-104">O [método ExportType](exporttype-method.md) também pode exportar tipos aninhados, mas esse método é mais rápido.</span><span class="sxs-lookup"><span data-stu-id="44b61-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44b61-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="44b61-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="44b61-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="44b61-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="44b61-107">ID do assembly do qual exportar.</span><span class="sxs-lookup"><span data-stu-id="44b61-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="44b61-108">Token de arquivo ou assembly de arquivo que define o tipo a ser tornado exportável.</span><span class="sxs-lookup"><span data-stu-id="44b61-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="44b61-109">Tipo de token do tipo a ser tornado exportável.</span><span class="sxs-lookup"><span data-stu-id="44b61-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="44b61-110">Token do tipo pai.</span><span class="sxs-lookup"><span data-stu-id="44b61-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="44b61-111">Nome de tipo totalmente qualificado para exportar.</span><span class="sxs-lookup"><span data-stu-id="44b61-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="44b61-112">`ComType` sinalizadores como `tdPublic` ou `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="44b61-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="44b61-113">Esse valor pode ser passado para o [método DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="44b61-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="44b61-114">Recebe o token para o tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="44b61-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44b61-115">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="44b61-115">Return Value</span></span>  

 <span data-ttu-id="44b61-116">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="44b61-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44b61-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44b61-117">Requirements</span></span>  

 <span data-ttu-id="44b61-118">Requer ALink. h</span><span class="sxs-lookup"><span data-stu-id="44b61-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44b61-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="44b61-119">See also</span></span>

- [<span data-ttu-id="44b61-120">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="44b61-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="44b61-121">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="44b61-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="44b61-122">API do ALink</span><span class="sxs-lookup"><span data-stu-id="44b61-122">ALink API</span></span>](index.md)
