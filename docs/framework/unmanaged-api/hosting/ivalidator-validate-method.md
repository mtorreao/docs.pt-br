---
title: Método IValidator::Validate
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
ms.openlocfilehash: 3c59114f78af1aa8705318af093e47d4f03a82ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699138"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="17614-102">Método IValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="17614-102">IValidator::Validate Method</span></span>

<span data-ttu-id="17614-103">Valida o executável portátil (PE) ou o arquivo. MSIL (Microsoft Intermediate Language) especificado.</span><span class="sxs-lookup"><span data-stu-id="17614-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17614-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="17614-104">Syntax</span></span>  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17614-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="17614-105">Parameters</span></span>  

 `veh`  
 <span data-ttu-id="17614-106">no Um ponteiro para uma `IVEHandler` instância que manipula erros de validação.</span><span class="sxs-lookup"><span data-stu-id="17614-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="17614-107">no Um ponteiro para o domínio do aplicativo no qual o arquivo é carregado.</span><span class="sxs-lookup"><span data-stu-id="17614-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="17614-108">no Uma combinação de bits de valor [ValidatorFlags](validatorflags-enumeration.md) , que indica as validações que devem ser executadas.</span><span class="sxs-lookup"><span data-stu-id="17614-108">[in] A bitwise combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="17614-109">no O número máximo de erros a serem permitidos antes de sair da validação.</span><span class="sxs-lookup"><span data-stu-id="17614-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="17614-110">no Não usado.</span><span class="sxs-lookup"><span data-stu-id="17614-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="17614-111">no Uma cadeia de caracteres que especifica o nome do arquivo a ser validado.</span><span class="sxs-lookup"><span data-stu-id="17614-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="17614-112">no Um ponteiro para o buffer de memória no qual o arquivo está armazenado.</span><span class="sxs-lookup"><span data-stu-id="17614-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="17614-113">no O tamanho, em bytes, do arquivo a ser validado.</span><span class="sxs-lookup"><span data-stu-id="17614-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17614-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17614-114">Requirements</span></span>  

 <span data-ttu-id="17614-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17614-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17614-116">**Cabeçalho:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="17614-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="17614-117">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17614-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17614-118">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17614-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
