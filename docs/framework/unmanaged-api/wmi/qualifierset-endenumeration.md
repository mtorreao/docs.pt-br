---
title: Função QualifierSet_EndEnumeration (referência de API não gerenciada)
description: A função QualifierSet_EndEnumeration encerra uma enumeração.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2739003fc9c1f93d379e4a59338cbef7a1a0f135
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726737"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="b2222-103">Função QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="b2222-103">QualifierSet_EndEnumeration function</span></span>

<span data-ttu-id="b2222-104">Encerra a enumeração iniciada com uma chamada para a função [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b2222-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b2222-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b2222-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="b2222-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b2222-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b2222-107">no Este parâmetro não é usado.</span><span class="sxs-lookup"><span data-stu-id="b2222-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="b2222-108">`ptr` no Um ponteiro para uma instância de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="b2222-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="b2222-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="b2222-109">Return value</span></span>

<span data-ttu-id="b2222-110">O valor a seguir retornado por essa função é definido no arquivo de cabeçalho *WbemCli. h* ou você pode defini-lo como uma constante no seu código:</span><span class="sxs-lookup"><span data-stu-id="b2222-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="b2222-111">Constante</span><span class="sxs-lookup"><span data-stu-id="b2222-111">Constant</span></span>  |<span data-ttu-id="b2222-112">Valor</span><span class="sxs-lookup"><span data-stu-id="b2222-112">Value</span></span>  |<span data-ttu-id="b2222-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="b2222-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b2222-114">0</span><span class="sxs-lookup"><span data-stu-id="b2222-114">0</span></span> | <span data-ttu-id="b2222-115">A chamada de função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="b2222-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b2222-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="b2222-116">Remarks</span></span>

<span data-ttu-id="b2222-117">Essa função encapsula uma chamada para o método [IWbemQualifierSet:: endenumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .</span><span class="sxs-lookup"><span data-stu-id="b2222-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="b2222-118">Essa chamada é recomendada, mas não obrigatória.</span><span class="sxs-lookup"><span data-stu-id="b2222-118">This call is recommended, but not required.</span></span> <span data-ttu-id="b2222-119">Ele libera imediatamente os recursos associados à enumeração.</span><span class="sxs-lookup"><span data-stu-id="b2222-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="b2222-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2222-120">Requirements</span></span>  

<span data-ttu-id="b2222-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2222-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="b2222-122">**Cabeçalho:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="b2222-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="b2222-123">**.NET Framework versões:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b2222-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2222-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="b2222-124">See also</span></span>

- [<span data-ttu-id="b2222-125">WMI e Contadores de Desempenho (Referência de API Não Gerenciada)</span><span class="sxs-lookup"><span data-stu-id="b2222-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
