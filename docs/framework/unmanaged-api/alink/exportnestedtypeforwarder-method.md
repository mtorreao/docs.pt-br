---
title: Método ExportNestedTypeForwarder
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: 45adda6551e1cec994f59acbb0e8d2b5c56c4df6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684805"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="7d002-102">Método ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="7d002-102">ExportNestedTypeForwarder Method</span></span>

<span data-ttu-id="7d002-103">Adiciona um encaminhador de tipo para um tipo aninhado à tabela de tipos do assembly especificado.</span><span class="sxs-lookup"><span data-stu-id="7d002-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d002-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7d002-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d002-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7d002-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="7d002-106">ID do assembly do qual exportar.</span><span class="sxs-lookup"><span data-stu-id="7d002-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7d002-107">Token do arquivo ou ID do assembly do arquivo que define o tipo.</span><span class="sxs-lookup"><span data-stu-id="7d002-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="7d002-108">Token para o tipo.</span><span class="sxs-lookup"><span data-stu-id="7d002-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="7d002-109">Token do tipo pai.</span><span class="sxs-lookup"><span data-stu-id="7d002-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="7d002-110">Nome de tipo totalmente qualificado para exportar.</span><span class="sxs-lookup"><span data-stu-id="7d002-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7d002-111">`ComType` sinalizadores como `tdPublic` ou `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="7d002-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="7d002-112">Recebe o token do tipo de exportação.</span><span class="sxs-lookup"><span data-stu-id="7d002-112">Receives token of export type.</span></span> <span data-ttu-id="7d002-113">Isso é necessário apenas para emitir tipos aninhados.</span><span class="sxs-lookup"><span data-stu-id="7d002-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d002-114">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="7d002-114">Return Value</span></span>  

 <span data-ttu-id="7d002-115">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="7d002-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d002-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d002-116">Requirements</span></span>  

 <span data-ttu-id="7d002-117">Requer ALink. h</span><span class="sxs-lookup"><span data-stu-id="7d002-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d002-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="7d002-118">See also</span></span>

- [<span data-ttu-id="7d002-119">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="7d002-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7d002-120">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="7d002-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7d002-121">API do ALink</span><span class="sxs-lookup"><span data-stu-id="7d002-121">ALink API</span></span>](index.md)
