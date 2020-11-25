---
title: Enumeração ValidatorFlags
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
ms.openlocfilehash: 92c430cdb8b46cf75dde9a8395ce713116dc05a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732847"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="9cb8e-102">Enumeração ValidatorFlags</span><span class="sxs-lookup"><span data-stu-id="9cb8e-102">ValidatorFlags Enumeration</span></span>

<span data-ttu-id="9cb8e-103">Contém valores que indicam o tipo de validação que deve ser executado em uma chamada para o método [ICLRValidator:: Validate](iclrvalidator-validate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9cb8e-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb8e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9cb8e-104">Syntax</span></span>  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="9cb8e-105">Membros</span><span class="sxs-lookup"><span data-stu-id="9cb8e-105">Members</span></span>  
  
|<span data-ttu-id="9cb8e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9cb8e-106">Member</span></span>|<span data-ttu-id="9cb8e-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9cb8e-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="9cb8e-108">Especifica que somente a MSIL (Microsoft Intermediate Language) no arquivo executável deve ser validada.</span><span class="sxs-lookup"><span data-stu-id="9cb8e-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="9cb8e-109">Especifica que somente o formato do arquivo executável deve ser validado.</span><span class="sxs-lookup"><span data-stu-id="9cb8e-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="9cb8e-110">Especifica que todos os tipos de validação devem ser executados e relatados em.</span><span class="sxs-lookup"><span data-stu-id="9cb8e-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="9cb8e-111">Especifica que o formato do arquivo executável não deve ser validado.</span><span class="sxs-lookup"><span data-stu-id="9cb8e-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="9cb8e-112">Especifica que as mensagens de erro de validação devem incluir as linhas do código-fonte que geram erros de validação.</span><span class="sxs-lookup"><span data-stu-id="9cb8e-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="9cb8e-113">Esse valor de campo não é válido na versão .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="9cb8e-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9cb8e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9cb8e-114">Requirements</span></span>  

 <span data-ttu-id="9cb8e-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cb8e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cb8e-116">**Cabeçalho:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="9cb8e-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="9cb8e-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9cb8e-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cb8e-118">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cb8e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb8e-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="9cb8e-119">See also</span></span>

- [<span data-ttu-id="9cb8e-120">Interface ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="9cb8e-120">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="9cb8e-121">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="9cb8e-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
