---
title: Função GetDemultiplexedStub (referência de API não gerenciada)
description: A função GetDemultiplexedStub cria um coletor de encaminhador de objetos para ajudar um cliente a receber chamadas assíncronas do gerenciamento do Windows.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f8f9b56268168bb16c476a9366facd17e8ac44e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730624"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="896b6-103">Função GetDemultiplexedStub</span><span class="sxs-lookup"><span data-stu-id="896b6-103">GetDemultiplexedStub function</span></span>

<span data-ttu-id="896b6-104">Cria um coletor do encaminhador de objeto para ajudar um cliente a receber chamadas assíncronas do Gerenciamento do Windows.</span><span class="sxs-lookup"><span data-stu-id="896b6-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="896b6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="896b6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a><span data-ttu-id="896b6-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="896b6-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="896b6-107">no Um ponteiro para a implementação em processo do cliente do [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="896b6-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="896b6-108">no Um sinalizador que indica se o evento é local ( `true` ); caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="896b6-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="896b6-109">fora Um coletor de encaminhador de objetos para auxiliar um cliente no recebimento de chamadas assíncronas do gerenciamento do Windows.</span><span class="sxs-lookup"><span data-stu-id="896b6-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="896b6-110">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="896b6-110">Return value</span></span>

<span data-ttu-id="896b6-111">Se a função for realizada com sucesso, o valor de retorno será `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="896b6-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="896b6-112">Se a função falhar, o valor de retorno será um código de erro diferente de zero.</span><span class="sxs-lookup"><span data-stu-id="896b6-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="896b6-113">Para obter informações de erro estendidas, chame a função [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="896b6-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="896b6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="896b6-114">Requirements</span></span>  

 <span data-ttu-id="896b6-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="896b6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="896b6-116">**Cabeçalho:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="896b6-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="896b6-117">**.NET Framework versões:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="896b6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="896b6-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="896b6-118">See also</span></span>

- [<span data-ttu-id="896b6-119">WMI e Contadores de Desempenho (Referência de API Não Gerenciada)</span><span class="sxs-lookup"><span data-stu-id="896b6-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
