---
title: Método ICorProfilerInfo::GetAppDomainInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAppDomainInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type:
- apiref
ms.openlocfilehash: 62055a98197f5f8bd4cfc02e99891b83ef6341e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680271"
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a><span data-ttu-id="7dee1-102">Método ICorProfilerInfo::GetAppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="7dee1-102">ICorProfilerInfo::GetAppDomainInfo Method</span></span>

<span data-ttu-id="7dee1-103">Aceita uma ID de domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7dee1-103">Accepts an application domain ID.</span></span> <span data-ttu-id="7dee1-104">Retorna um nome de domínio de aplicativo e a ID do processo que o contém.</span><span class="sxs-lookup"><span data-stu-id="7dee1-104">Returns an application domain name and the ID of the process that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dee1-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7dee1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dee1-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7dee1-106">Parameters</span></span>  

 `appDomainId`  
 <span data-ttu-id="7dee1-107">no A ID do domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7dee1-107">[in] The ID of the application domain.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7dee1-108">no O comprimento, em caracteres, do `szName` buffer de retorno.</span><span class="sxs-lookup"><span data-stu-id="7dee1-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7dee1-109">fora Um ponteiro para o tamanho total do caractere do nome de domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7dee1-109">[out] A pointer to the total character length of the application domain name.</span></span>  
  
 `szName`  
 <span data-ttu-id="7dee1-110">fora Um buffer de caracteres largo fornecido pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="7dee1-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="7dee1-111">Quando o método retornar, `szName` conterá o nome de domínio do aplicativo completo ou parcial.</span><span class="sxs-lookup"><span data-stu-id="7dee1-111">When the method returns, `szName` will contain the full or partial application domain name.</span></span>  
  
 `pProcessId`  
 <span data-ttu-id="7dee1-112">fora Um ponteiro para a ID do processo que contém o domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7dee1-112">[out] A pointer to the ID of the process that contains the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dee1-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="7dee1-113">Remarks</span></span>  

 <span data-ttu-id="7dee1-114">Depois que esse método retornar, você deverá verificar se o `szName` buffer era grande o suficiente para conter o nome completo do domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7dee1-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the application domain.</span></span> <span data-ttu-id="7dee1-115">Para fazer isso, compare o valor que `pcchName` aponta com o valor do `cchName` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7dee1-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="7dee1-116">Se `pcchName` apontar para um valor maior que `cchName` , aloque um `szName` buffer maior, atualize `cchName` com o tamanho novo, maior e chame `GetAppDomainInfo` novamente.</span><span class="sxs-lookup"><span data-stu-id="7dee1-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAppDomainInfo` again.</span></span>  
  
 <span data-ttu-id="7dee1-117">Como alternativa, você pode primeiro chamar `GetAppDomainInfo` com um buffer de comprimento zero `szName` para obter o tamanho de buffer correto.</span><span class="sxs-lookup"><span data-stu-id="7dee1-117">Alternatively, you can first call `GetAppDomainInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="7dee1-118">Em seguida, você pode definir o tamanho do buffer para o valor retornado em `pcchName` e chamar `GetAppDomainInfo` novamente.</span><span class="sxs-lookup"><span data-stu-id="7dee1-118">You can then set the buffer size to the value returned in `pcchName` and call `GetAppDomainInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dee1-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7dee1-119">Requirements</span></span>  

 <span data-ttu-id="7dee1-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dee1-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dee1-121">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="7dee1-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7dee1-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dee1-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dee1-123">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dee1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dee1-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="7dee1-124">See also</span></span>

- [<span data-ttu-id="7dee1-125">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="7dee1-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="7dee1-126">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="7dee1-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="7dee1-127">Criação de perfil</span><span class="sxs-lookup"><span data-stu-id="7dee1-127">Profiling</span></span>](index.md)
