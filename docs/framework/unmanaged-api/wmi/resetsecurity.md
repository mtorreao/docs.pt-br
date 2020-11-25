---
title: Função ResetSecurity (referência de API não gerenciada)
description: A função ResetSecurity atribui um token de representação ao thread atual.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 259bef74356f16221f1453dd4086e2fbb26faa83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721108"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="001fc-103">Função ResetSecurity</span><span class="sxs-lookup"><span data-stu-id="001fc-103">ResetSecurity function</span></span>

<span data-ttu-id="001fc-104">Atribui o token de representação fornecido para o thread atual.</span><span class="sxs-lookup"><span data-stu-id="001fc-104">Assigns the supplied impersonation token to the current thread.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="001fc-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="001fc-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
);
```  

## <a name="parameters"></a><span data-ttu-id="001fc-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="001fc-106">Parameters</span></span>

`token`  
<span data-ttu-id="001fc-107">no O token de representação a ser associado ao thread atual.</span><span class="sxs-lookup"><span data-stu-id="001fc-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="001fc-108">Seu valor pode ser `null`.</span><span class="sxs-lookup"><span data-stu-id="001fc-108">Its value can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="001fc-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="001fc-109">Return value</span></span>

<span data-ttu-id="001fc-110">Se a função for realizada com sucesso, o valor de retorno será `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="001fc-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="001fc-111">Se a função falhar, o valor de retorno será um código de erro diferente de zero.</span><span class="sxs-lookup"><span data-stu-id="001fc-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="001fc-112">Para obter informações de erro estendidas, chame a função [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="001fc-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="001fc-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="001fc-113">Requirements</span></span>  

 <span data-ttu-id="001fc-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="001fc-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="001fc-115">**Cabeçalho:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="001fc-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="001fc-116">**.NET Framework versões:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="001fc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="001fc-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="001fc-117">See also</span></span>

- [<span data-ttu-id="001fc-118">WMI e Contadores de Desempenho (Referência de API Não Gerenciada)</span><span class="sxs-lookup"><span data-stu-id="001fc-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
