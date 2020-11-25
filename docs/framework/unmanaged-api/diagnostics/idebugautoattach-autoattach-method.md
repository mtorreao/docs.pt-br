---
title: Método IDebugAutoAttach::AutoAttach
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
ms.openlocfilehash: 64dd653bb0d4e383075a999e0803e4acfd0fae3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720094"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="70df6-102">Método IDebugAutoAttach::AutoAttach</span><span class="sxs-lookup"><span data-stu-id="70df6-102">IDebugAutoAttach::AutoAttach Method</span></span>

<span data-ttu-id="70df6-103">Executa a anexação automática do depurador invocado pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="70df6-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70df6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="70df6-104">Syntax</span></span>  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70df6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="70df6-105">Parameters</span></span>  

 `guidPort`  
 <span data-ttu-id="70df6-106">no Sempre definido como `GUID_NULL` .</span><span class="sxs-lookup"><span data-stu-id="70df6-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="70df6-107">no ID do processo, normalmente recuperada com a `GetCurrentProcessId` função.</span><span class="sxs-lookup"><span data-stu-id="70df6-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="70df6-108">no Tipo de programa: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` ou `AUTOATTACH_PROGRAM_UNKNOWN` .</span><span class="sxs-lookup"><span data-stu-id="70df6-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="70df6-109">no ID do programa.</span><span class="sxs-lookup"><span data-stu-id="70df6-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="70df6-110">no Cadeia de caracteres passada pelo verbo Debug.</span><span class="sxs-lookup"><span data-stu-id="70df6-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70df6-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="70df6-111">Return Value</span></span>  

 <span data-ttu-id="70df6-112">S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="70df6-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70df6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70df6-113">Requirements</span></span>  

 <span data-ttu-id="70df6-114">**Cabeçalho:** DbgAutoAttach. h</span><span class="sxs-lookup"><span data-stu-id="70df6-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70df6-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="70df6-115">See also</span></span>

- [<span data-ttu-id="70df6-116">Interface IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="70df6-116">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)
