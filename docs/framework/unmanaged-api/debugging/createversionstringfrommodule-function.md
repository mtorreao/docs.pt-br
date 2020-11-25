---
title: Função CreateVersionStringFromModule
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
ms.openlocfilehash: 1b944034251b34350057866b2a52e63e934d72d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733341"
---
# <a name="createversionstringfrommodule-function"></a><span data-ttu-id="884b6-102">Função CreateVersionStringFromModule</span><span class="sxs-lookup"><span data-stu-id="884b6-102">CreateVersionStringFromModule Function</span></span>

<span data-ttu-id="884b6-103">Cria uma cadeia de caracteres de versão de um caminho Common Language Runtime (CLR) em um processo de destino.</span><span class="sxs-lookup"><span data-stu-id="884b6-103">Creates a version string from a common language runtime (CLR) path in a target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="884b6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="884b6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="884b6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="884b6-105">Parameters</span></span>  

 `pidDebuggee`  
 <span data-ttu-id="884b6-106">no Identificador do processo no qual o CLR de destino é carregado.</span><span class="sxs-lookup"><span data-stu-id="884b6-106">[in] Identifier of the process in which the target CLR is loaded.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="884b6-107">no Caminho completo ou relativo para o CLR de destino que é carregado no processo.</span><span class="sxs-lookup"><span data-stu-id="884b6-107">[in] Full or relative path to the target CLR that is loaded in the process.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="884b6-108">fora Buffer de retorno para armazenar a cadeia de caracteres de versão para o CLR de destino.</span><span class="sxs-lookup"><span data-stu-id="884b6-108">[out] Return buffer for storing the version string for the target CLR.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="884b6-109">no Tamanho de `pBuffer` .</span><span class="sxs-lookup"><span data-stu-id="884b6-109">[in] Size of `pBuffer`.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="884b6-110">fora Comprimento da cadeia de caracteres de versão retornada por `pBuffer` .</span><span class="sxs-lookup"><span data-stu-id="884b6-110">[out] Length of the version string returned by `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="884b6-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="884b6-111">Return Value</span></span>  

 <span data-ttu-id="884b6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="884b6-112">S_OK</span></span>  
 <span data-ttu-id="884b6-113">A cadeia de caracteres de versão para o CLR de destino foi retornada com êxito em `pBuffer` .</span><span class="sxs-lookup"><span data-stu-id="884b6-113">The version string for the target CLR was successfully returned in `pBuffer`.</span></span>  
  
 <span data-ttu-id="884b6-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="884b6-114">E_INVALIDARG</span></span>  
 <span data-ttu-id="884b6-115">`szModuleName` é NULL ou `pBuffer` or `cchBuffer` é nulo.</span><span class="sxs-lookup"><span data-stu-id="884b6-115">`szModuleName` is null, or either `pBuffer` or `cchBuffer` is null.</span></span> <span data-ttu-id="884b6-116">`pBuffer` e `cchBuffer` devem ser nulos ou não nulos.</span><span class="sxs-lookup"><span data-stu-id="884b6-116">`pBuffer` and `cchBuffer` must both be null or non-null.</span></span>  
  
 <span data-ttu-id="884b6-117">HRESULT_FROM_WIN32 (ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="884b6-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>  
 <span data-ttu-id="884b6-118">`pdwLength` é maior que `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="884b6-118">`pdwLength` is greater than `cchBuffer`.</span></span> <span data-ttu-id="884b6-119">Esse pode ser um resultado esperado se você tiver passado nulo para `pBuffer` and e `cchBuffer` , e tiver consultado o tamanho de buffer necessário usando `pdwLength` .</span><span class="sxs-lookup"><span data-stu-id="884b6-119">This may be an expected result if you have passed null for both `pBuffer` and `cchBuffer`, and queried the necessary buffer size by using `pdwLength`.</span></span>  
  
 <span data-ttu-id="884b6-120">HRESULT_FROM_WIN32 (ERROR_MOD_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="884b6-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span></span>  
 <span data-ttu-id="884b6-121">`szModuleName` Não contém um caminho para um CLR válido no processo de destino.</span><span class="sxs-lookup"><span data-stu-id="884b6-121">`szModuleName` does not contain a path to a valid CLR in the target process.</span></span>  
  
 <span data-ttu-id="884b6-122">E_FAIL (ou outros códigos de retorno de E_)</span><span class="sxs-lookup"><span data-stu-id="884b6-122">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="884b6-123">`pidDebuggee` Não se refere a um processo válido ou a outra falha.</span><span class="sxs-lookup"><span data-stu-id="884b6-123">`pidDebuggee` does not refer to a valid process, or other failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="884b6-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="884b6-124">Remarks</span></span>  

 <span data-ttu-id="884b6-125">Essa função aceita um processo CLR identificado pelo `pidDebuggee` e um caminho de cadeia de caracteres especificado por `szModuleName` .</span><span class="sxs-lookup"><span data-stu-id="884b6-125">This function accepts a CLR process that is identified by `pidDebuggee` and a string path that is specified by `szModuleName`.</span></span> <span data-ttu-id="884b6-126">A cadeia de caracteres de versão é retornada no buffer que `pBuffer` aponta para.</span><span class="sxs-lookup"><span data-stu-id="884b6-126">The version string is returned in the buffer that `pBuffer` points to.</span></span> <span data-ttu-id="884b6-127">Essa cadeia de caracteres é opaca para o usuário da função; ou seja, não há nenhum significado intrínseco na própria cadeia de caracteres de versão.</span><span class="sxs-lookup"><span data-stu-id="884b6-127">This string is opaque to the function user; that is, there is no intrinsic meaning in the version string itself.</span></span> <span data-ttu-id="884b6-128">Ele é usado unicamente no contexto dessa função e da [função CreateDebuggingInterfaceFromVersion](createdebugginginterfacefromversion-function-for-silverlight.md).</span><span class="sxs-lookup"><span data-stu-id="884b6-128">It is used solely in the context of this function and the [CreateDebuggingInterfaceFromVersion function](createdebugginginterfacefromversion-function-for-silverlight.md).</span></span>  
  
 <span data-ttu-id="884b6-129">Essa função deve ser chamada duas vezes.</span><span class="sxs-lookup"><span data-stu-id="884b6-129">This function should be called twice.</span></span> <span data-ttu-id="884b6-130">Quando você o chama pela primeira vez, passe NULL para `pBuffer` e `cchBuffer` .</span><span class="sxs-lookup"><span data-stu-id="884b6-130">When you call it the first time, pass null for both `pBuffer` and `cchBuffer`.</span></span> <span data-ttu-id="884b6-131">Quando você fizer isso, o tamanho do buffer necessário para `pBuffer` será retornado em `pdwLength` .</span><span class="sxs-lookup"><span data-stu-id="884b6-131">When you do this, the size of the buffer necessary for `pBuffer` will be returned in `pdwLength`.</span></span> <span data-ttu-id="884b6-132">Em seguida, você pode chamar a função uma segunda vez e passar o buffer para dentro `pBuffer` e seu tamanho em `cchBuffer` .</span><span class="sxs-lookup"><span data-stu-id="884b6-132">You can then call the function a second time, and pass the buffer in `pBuffer` and its size in `cchBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="884b6-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="884b6-133">Requirements</span></span>  

 <span data-ttu-id="884b6-134">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="884b6-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="884b6-135">**Cabeçalho:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="884b6-135">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="884b6-136">**Biblioteca:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="884b6-136">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="884b6-137">**Versões do .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="884b6-137">**.NET Framework Versions:** 3.5 SP1</span></span>
