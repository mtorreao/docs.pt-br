---
title: Próxima função (referência de API não gerenciada)
description: A função Next recupera a próxima Propriedade em uma enumeração.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c2a7fae32e82caae40a95bfdad10fa78082988ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726776"
---
# <a name="next-function"></a><span data-ttu-id="6a98e-103">Função Next</span><span class="sxs-lookup"><span data-stu-id="6a98e-103">Next function</span></span>

<span data-ttu-id="6a98e-104">Recupera a próxima Propriedade em uma enumeração que começa com uma chamada para [BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="6a98e-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="6a98e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6a98e-105">Syntax</span></span>

```cpp
HRESULT Next (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="6a98e-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6a98e-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="6a98e-107">no Este parâmetro não é usado.</span><span class="sxs-lookup"><span data-stu-id="6a98e-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="6a98e-108">no Um ponteiro para uma instância de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="6a98e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`\
<span data-ttu-id="6a98e-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="6a98e-109">[in] Reserved.</span></span> <span data-ttu-id="6a98e-110">Esse parâmetro deve ser 0.</span><span class="sxs-lookup"><span data-stu-id="6a98e-110">This parameter must be 0.</span></span>

`pstrName`\
<span data-ttu-id="6a98e-111">fora Um novo `BSTR` que contém o nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="6a98e-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="6a98e-112">Você pode definir esse parâmetro como `null` se o nome não for necessário.</span><span class="sxs-lookup"><span data-stu-id="6a98e-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`\
<span data-ttu-id="6a98e-113">fora Um `VARIANT` preenchido com o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="6a98e-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="6a98e-114">Você pode definir esse parâmetro como `null` se o valor não for necessário.</span><span class="sxs-lookup"><span data-stu-id="6a98e-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="6a98e-115">Se a função retornar um código de erro, o `VARIANT` passado para `pVal` será deixado sem modificações.</span><span class="sxs-lookup"><span data-stu-id="6a98e-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span>

`pvtType`\
<span data-ttu-id="6a98e-116">fora Um ponteiro para uma `CIMTYPE` variável (um `LONG` no qual o tipo da propriedade é colocado).</span><span class="sxs-lookup"><span data-stu-id="6a98e-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="6a98e-117">O valor dessa propriedade pode ser a `VT_NULL_VARIANT` ; nesse caso, é necessário determinar o tipo real da propriedade.</span><span class="sxs-lookup"><span data-stu-id="6a98e-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="6a98e-118">Esse parâmetro também pode ser `null` .</span><span class="sxs-lookup"><span data-stu-id="6a98e-118">This parameter can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="6a98e-119">[out] `null` ou um valor que recebe informações sobre a origem da propriedade.</span><span class="sxs-lookup"><span data-stu-id="6a98e-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="6a98e-120">Consulte a seção [Comentários] para obter os valores possíveis.</span><span class="sxs-lookup"><span data-stu-id="6a98e-120">See the [Remarks] section for possible values.</span></span>

## <a name="return-value"></a><span data-ttu-id="6a98e-121">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="6a98e-121">Return value</span></span>

<span data-ttu-id="6a98e-122">Os valores a seguir retornados por essa função são definidos no arquivo de cabeçalho *WbemCli. h* ou você pode defini-los como constantes em seu código:</span><span class="sxs-lookup"><span data-stu-id="6a98e-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6a98e-123">Constante</span><span class="sxs-lookup"><span data-stu-id="6a98e-123">Constant</span></span>  |<span data-ttu-id="6a98e-124">Valor</span><span class="sxs-lookup"><span data-stu-id="6a98e-124">Value</span></span>  |<span data-ttu-id="6a98e-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="6a98e-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="6a98e-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6a98e-126">0x80041001</span></span> | <span data-ttu-id="6a98e-127">Houve uma falha geral.</span><span class="sxs-lookup"><span data-stu-id="6a98e-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6a98e-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6a98e-128">0x80041008</span></span> | <span data-ttu-id="6a98e-129">Um parâmetro é inválido.</span><span class="sxs-lookup"><span data-stu-id="6a98e-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="6a98e-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="6a98e-130">0x8004101d</span></span> | <span data-ttu-id="6a98e-131">Não havia nenhuma chamada para a [`BeginEnumeration`](beginenumeration.md) função.</span><span class="sxs-lookup"><span data-stu-id="6a98e-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6a98e-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6a98e-132">0x80041006</span></span> | <span data-ttu-id="6a98e-133">Não há memória suficiente disponível para iniciar uma nova enumeração.</span><span class="sxs-lookup"><span data-stu-id="6a98e-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="6a98e-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="6a98e-134">0x80041015</span></span> | <span data-ttu-id="6a98e-135">A chamada de procedimento remoto entre o processo atual e o gerenciamento do Windows falhou.</span><span class="sxs-lookup"><span data-stu-id="6a98e-135">The remote procedure call between the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6a98e-136">0</span><span class="sxs-lookup"><span data-stu-id="6a98e-136">0</span></span> | <span data-ttu-id="6a98e-137">A chamada de função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="6a98e-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="6a98e-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="6a98e-138">0x40005</span></span> | <span data-ttu-id="6a98e-139">Não há mais propriedades na enumeração.</span><span class="sxs-lookup"><span data-stu-id="6a98e-139">There are no more properties in the enumeration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="6a98e-140">Comentários</span><span class="sxs-lookup"><span data-stu-id="6a98e-140">Remarks</span></span>

<span data-ttu-id="6a98e-141">Essa função encapsula uma chamada para o método [IWbemClassObject:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) .</span><span class="sxs-lookup"><span data-stu-id="6a98e-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="6a98e-142">Esse método também retorna propriedades do sistema.</span><span class="sxs-lookup"><span data-stu-id="6a98e-142">This method also returns system properties.</span></span>

<span data-ttu-id="6a98e-143">Se o tipo subjacente da propriedade for um caminho de objeto, uma data ou hora ou outro tipo especial, o tipo retornado não conterá informações suficientes.</span><span class="sxs-lookup"><span data-stu-id="6a98e-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="6a98e-144">O chamador deve examinar a `CIMTYPE` propriedade especificada para determinar se a propriedade é uma referência de objeto, uma data ou hora ou outro tipo especial.</span><span class="sxs-lookup"><span data-stu-id="6a98e-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="6a98e-145">Se `plFlavor` não for `null` , o `LONG` valor receberá informações sobre a origem da propriedade, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6a98e-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="6a98e-146">Constante</span><span class="sxs-lookup"><span data-stu-id="6a98e-146">Constant</span></span>  |<span data-ttu-id="6a98e-147">Valor</span><span class="sxs-lookup"><span data-stu-id="6a98e-147">Value</span></span>  |<span data-ttu-id="6a98e-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="6a98e-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="6a98e-149">0x40</span><span class="sxs-lookup"><span data-stu-id="6a98e-149">0x40</span></span> | <span data-ttu-id="6a98e-150">A propriedade é uma propriedade padrão do sistema.</span><span class="sxs-lookup"><span data-stu-id="6a98e-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="6a98e-151">0x20</span><span class="sxs-lookup"><span data-stu-id="6a98e-151">0x20</span></span> | <span data-ttu-id="6a98e-152">Para uma classe: a propriedade é herdada da classe pai.</span><span class="sxs-lookup"><span data-stu-id="6a98e-152">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="6a98e-153">Para uma instância: a propriedade, embora herdada da classe pai, não foi modificada pela instância.</span><span class="sxs-lookup"><span data-stu-id="6a98e-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="6a98e-154">0</span><span class="sxs-lookup"><span data-stu-id="6a98e-154">0</span></span> | <span data-ttu-id="6a98e-155">Para uma classe: a propriedade pertence à classe derivada.</span><span class="sxs-lookup"><span data-stu-id="6a98e-155">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="6a98e-156">Para uma instância: a propriedade é modificada pela instância; ou seja, um valor foi fornecido ou um qualificador foi adicionado ou modificado.</span><span class="sxs-lookup"><span data-stu-id="6a98e-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="6a98e-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a98e-157">Requirements</span></span>

<span data-ttu-id="6a98e-158">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a98e-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="6a98e-159">**Cabeçalho:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="6a98e-159">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="6a98e-160">**.NET Framework versões:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6a98e-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6a98e-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="6a98e-161">See also</span></span>

- [<span data-ttu-id="6a98e-162">WMI e Contadores de Desempenho (Referência de API Não Gerenciada)</span><span class="sxs-lookup"><span data-stu-id="6a98e-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
