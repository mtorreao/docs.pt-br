---
title: Interface ICLRValidator
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: d9ccd5c6c91b1ab2166ff40a0fb2048e15927d3a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723942"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="aa1ae-102">Interface ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="aa1ae-102">ICLRValidator Interface</span></span>

<span data-ttu-id="aa1ae-103">Fornece métodos para validar imagens executáveis portáteis (PE) e relatar erros de validação.</span><span class="sxs-lookup"><span data-stu-id="aa1ae-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa1ae-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="aa1ae-104">Methods</span></span>  
  
|<span data-ttu-id="aa1ae-105">Método</span><span class="sxs-lookup"><span data-stu-id="aa1ae-105">Method</span></span>|<span data-ttu-id="aa1ae-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="aa1ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa1ae-107">Método FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="aa1ae-107">FormatEventInfo Method</span></span>](iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="aa1ae-108">Obtém uma mensagem detalhada sobre o erro de validação especificado.</span><span class="sxs-lookup"><span data-stu-id="aa1ae-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="aa1ae-109">Método Validate</span><span class="sxs-lookup"><span data-stu-id="aa1ae-109">Validate Method</span></span>](iclrvalidator-validate-method.md)|<span data-ttu-id="aa1ae-110">Valida o executável portátil ou o MSIL (Microsoft Intermediate Language) no arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="aa1ae-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa1ae-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa1ae-111">Requirements</span></span>  

 <span data-ttu-id="aa1ae-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa1ae-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa1ae-113">**Cabeçalho:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="aa1ae-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="aa1ae-114">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa1ae-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa1ae-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa1ae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa1ae-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="aa1ae-116">See also</span></span>

- [<span data-ttu-id="aa1ae-117">Interface ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="aa1ae-117">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="aa1ae-118">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="aa1ae-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="aa1ae-119">Coclass CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="aa1ae-119">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
