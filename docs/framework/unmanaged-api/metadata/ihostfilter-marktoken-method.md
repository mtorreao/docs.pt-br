---
title: Método IHostFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: b4db3b115517f0a146aeab469f091008d31efc86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718222"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="df00b-102">Método IHostFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="df00b-102">IHostFilter::MarkToken Method</span></span>

<span data-ttu-id="df00b-103">Indica que o token de metadados especificado será processado.</span><span class="sxs-lookup"><span data-stu-id="df00b-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df00b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df00b-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df00b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="df00b-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="df00b-106">no O token de metadados a ser processado.</span><span class="sxs-lookup"><span data-stu-id="df00b-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df00b-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="df00b-107">Remarks</span></span>  

 <span data-ttu-id="df00b-108">Normalmente, você deseja que um token seja processado se ele estiver no escopo de metadados.</span><span class="sxs-lookup"><span data-stu-id="df00b-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="df00b-109">O `MarkToken` método é passado para o mecanismo de metadados por meio do método [IMetaDataEmit:: sethandlers](imetadataemit-sethandler-method.md) .</span><span class="sxs-lookup"><span data-stu-id="df00b-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df00b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df00b-110">Requirements</span></span>  

 <span data-ttu-id="df00b-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df00b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df00b-112">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="df00b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df00b-113">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df00b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df00b-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df00b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df00b-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="df00b-115">See also</span></span>

- [<span data-ttu-id="df00b-116">Interfaces de metadados</span><span class="sxs-lookup"><span data-stu-id="df00b-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="df00b-117">Interface IHostFilter</span><span class="sxs-lookup"><span data-stu-id="df00b-117">IHostFilter Interface</span></span>](ihostfilter-interface.md)
