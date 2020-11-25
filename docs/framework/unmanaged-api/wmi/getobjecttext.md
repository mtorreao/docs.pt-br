---
title: Função GetObjectText (referência de API não gerenciada)
description: A função GetObjectText retorna uma renderização textual de um objeto na sintaxe do MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6ad2b29202222d594cc7976a13929002164314a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718365"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="5c95c-103">Função GetObjectText</span><span class="sxs-lookup"><span data-stu-id="5c95c-103">GetObjectText function</span></span>

<span data-ttu-id="5c95c-104">Retorna uma renderização textual do objeto na sintaxe Managed Object Format (MOF).</span><span class="sxs-lookup"><span data-stu-id="5c95c-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="5c95c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5c95c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a><span data-ttu-id="5c95c-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5c95c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5c95c-107">no Este parâmetro não é usado.</span><span class="sxs-lookup"><span data-stu-id="5c95c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5c95c-108">no Um ponteiro para uma instância de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="5c95c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="5c95c-109">no Normalmente 0.</span><span class="sxs-lookup"><span data-stu-id="5c95c-109">[in] Normally 0.</span></span> <span data-ttu-id="5c95c-110">Se `WBEM_FLAG_NO_FLAVORS` (ou 0x1) for especificado, os qualificadores serão incluídos sem informações de propagação ou de tipo.</span><span class="sxs-lookup"><span data-stu-id="5c95c-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

<span data-ttu-id="5c95c-111">`pstrObjectText` fora Um ponteiro para uma `null` entrada on.</span><span class="sxs-lookup"><span data-stu-id="5c95c-111">`pstrObjectText` [out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="5c95c-112">No retorno, um alocado recentemente `BSTR` que contém uma renderização de sintaxe do MOF do objeto.</span><span class="sxs-lookup"><span data-stu-id="5c95c-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="5c95c-113">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="5c95c-113">Return value</span></span>

<span data-ttu-id="5c95c-114">Os valores a seguir retornados por essa função são definidos no arquivo de cabeçalho *WbemCli. h* ou você pode defini-los como constantes em seu código:</span><span class="sxs-lookup"><span data-stu-id="5c95c-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5c95c-115">Constante</span><span class="sxs-lookup"><span data-stu-id="5c95c-115">Constant</span></span>  |<span data-ttu-id="5c95c-116">Valor</span><span class="sxs-lookup"><span data-stu-id="5c95c-116">Value</span></span>  |<span data-ttu-id="5c95c-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c95c-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="5c95c-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="5c95c-118">0x80041001</span></span> | <span data-ttu-id="5c95c-119">Houve uma falha geral.</span><span class="sxs-lookup"><span data-stu-id="5c95c-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5c95c-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5c95c-120">0x80041008</span></span> | <span data-ttu-id="5c95c-121">Um parâmetro não é válido.</span><span class="sxs-lookup"><span data-stu-id="5c95c-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5c95c-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5c95c-122">0x80041006</span></span> | <span data-ttu-id="5c95c-123">Não há memória disponível suficiente para concluir a operação.</span><span class="sxs-lookup"><span data-stu-id="5c95c-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5c95c-124">0</span><span class="sxs-lookup"><span data-stu-id="5c95c-124">0</span></span> | <span data-ttu-id="5c95c-125">A chamada de função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="5c95c-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5c95c-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="5c95c-126">Remarks</span></span>

<span data-ttu-id="5c95c-127">Essa função encapsula uma chamada para o método [IWbemClassObject:: GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) .</span><span class="sxs-lookup"><span data-stu-id="5c95c-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="5c95c-128">O texto MOF retornado não contém todas as informações sobre o objeto, mas apenas informações suficientes para o compilador MOF serem capazes de recriar o objeto original.</span><span class="sxs-lookup"><span data-stu-id="5c95c-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="5c95c-129">Por exemplo, nenhum qualificador propagado ou propriedades de classe pai são incluídos.</span><span class="sxs-lookup"><span data-stu-id="5c95c-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="5c95c-130">O algoritmo a seguir é usado para reconstruir o texto dos parâmetros de um método:</span><span class="sxs-lookup"><span data-stu-id="5c95c-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="5c95c-131">Os parâmetros são resequenciados na ordem de seus valores de identificador.</span><span class="sxs-lookup"><span data-stu-id="5c95c-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="5c95c-132">Parâmetros que são especificados como `[in]` e `[out]` são combinados em um único parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5c95c-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>

<span data-ttu-id="5c95c-133">`pstrObjectText` deve ser um ponteiro para um `null` quando a função é chamada; ele não deve apontar para uma cadeia de caracteres que seja válida antes da chamada de método, pois o ponteiro não será desalocado.</span><span class="sxs-lookup"><span data-stu-id="5c95c-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="5c95c-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c95c-134">Requirements</span></span>  

<span data-ttu-id="5c95c-135">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c95c-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c95c-136">**Cabeçalho:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="5c95c-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5c95c-137">**.NET Framework versões:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5c95c-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c95c-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="5c95c-138">See also</span></span>

- [<span data-ttu-id="5c95c-139">WMI e Contadores de Desempenho (Referência de API Não Gerenciada)</span><span class="sxs-lookup"><span data-stu-id="5c95c-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
