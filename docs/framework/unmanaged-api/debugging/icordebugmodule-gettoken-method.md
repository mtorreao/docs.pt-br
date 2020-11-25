---
title: Método ICorDebugModule::GetToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
ms.openlocfilehash: 6ffc74247a4ecafcc3744923c0def99220b5ca6f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709876"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="997cb-102">Método ICorDebugModule::GetToken</span><span class="sxs-lookup"><span data-stu-id="997cb-102">ICorDebugModule::GetToken Method</span></span>

<span data-ttu-id="997cb-103">Obtém o token para a entrada de tabela deste módulo.</span><span class="sxs-lookup"><span data-stu-id="997cb-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="997cb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="997cb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="997cb-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="997cb-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="997cb-106">fora Um ponteiro para o `mdModule` token que faz referência aos metadados do módulo.</span><span class="sxs-lookup"><span data-stu-id="997cb-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="997cb-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="997cb-107">Remarks</span></span>  

 <span data-ttu-id="997cb-108">O token pode ser passado para as interfaces de importação de metadados [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md)e [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="997cb-108">The token can be passed to the [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="997cb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="997cb-109">Requirements</span></span>  

 <span data-ttu-id="997cb-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="997cb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="997cb-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="997cb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="997cb-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="997cb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="997cb-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="997cb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="997cb-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="997cb-114">See also</span></span>

- [<span data-ttu-id="997cb-115">Metadados</span><span class="sxs-lookup"><span data-stu-id="997cb-115">Metadata</span></span>](../metadata/index.md)
