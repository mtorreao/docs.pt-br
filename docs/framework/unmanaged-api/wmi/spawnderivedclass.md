---
title: Função SpawnDerivedClass (referência de API não gerenciada)
description: A função SpawnDerivedClass cria um novo objeto que deriva de um objeto.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 8020dd851b6773e6c76c53892c4b2bc21e4261bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716506"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="6452b-103">Função SpawnDerivedClass</span><span class="sxs-lookup"><span data-stu-id="6452b-103">SpawnDerivedClass function</span></span>

<span data-ttu-id="6452b-104">Cria um objeto de classe derivada recentemente por meio de um objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="6452b-104">Creates a newly derived class object from a specified object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6452b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6452b-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a><span data-ttu-id="6452b-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6452b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6452b-107">no Este parâmetro não é usado.</span><span class="sxs-lookup"><span data-stu-id="6452b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="6452b-108">no Um ponteiro para uma instância de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="6452b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="6452b-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="6452b-109">[in] Reserved.</span></span> <span data-ttu-id="6452b-110">Esse parâmetro deve ser 0.</span><span class="sxs-lookup"><span data-stu-id="6452b-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="6452b-111">fora Recebe o ponteiro para o novo objeto de definição de classe.</span><span class="sxs-lookup"><span data-stu-id="6452b-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="6452b-112">Se ocorrer um erro, um novo objeto não será retornado e `ppNewClass` permanecerá não modificado.</span><span class="sxs-lookup"><span data-stu-id="6452b-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="6452b-113">Seu valor não pode ser `null` .</span><span class="sxs-lookup"><span data-stu-id="6452b-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="6452b-114">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="6452b-114">Return value</span></span>

<span data-ttu-id="6452b-115">Os valores a seguir retornados por essa função são definidos no arquivo de cabeçalho *WbemCli. h* ou você pode defini-los como constantes em seu código:</span><span class="sxs-lookup"><span data-stu-id="6452b-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6452b-116">Constante</span><span class="sxs-lookup"><span data-stu-id="6452b-116">Constant</span></span>  |<span data-ttu-id="6452b-117">Valor</span><span class="sxs-lookup"><span data-stu-id="6452b-117">Value</span></span>  |<span data-ttu-id="6452b-118">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="6452b-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="6452b-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6452b-119">0x80041001</span></span> | <span data-ttu-id="6452b-120">Houve uma falha geral.</span><span class="sxs-lookup"><span data-stu-id="6452b-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="6452b-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="6452b-121">0x80041016</span></span> | <span data-ttu-id="6452b-122">Uma operação inválida, como a geração de uma classe de uma instância, foi solicitada.</span><span class="sxs-lookup"><span data-stu-id="6452b-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="6452b-123">A classe de origem não foi totalmente definida ou registrada com o gerenciamento do Windows, portanto, não é permitida uma nova classe derivada.</span><span class="sxs-lookup"><span data-stu-id="6452b-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6452b-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6452b-124">0x80041006</span></span> | <span data-ttu-id="6452b-125">Não há memória disponível suficiente para concluir a operação.</span><span class="sxs-lookup"><span data-stu-id="6452b-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6452b-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6452b-126">0x80041008</span></span> | <span data-ttu-id="6452b-127">`ppNewClass` é `null`.</span><span class="sxs-lookup"><span data-stu-id="6452b-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6452b-128">0</span><span class="sxs-lookup"><span data-stu-id="6452b-128">0</span></span> | <span data-ttu-id="6452b-129">A chamada de função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="6452b-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6452b-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="6452b-130">Remarks</span></span>

<span data-ttu-id="6452b-131">Essa função encapsula uma chamada para o método [IWbemClassObject:: SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="6452b-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="6452b-132">`ptr` deve ser uma definição de classe que se torna a classe pai do objeto gerado.</span><span class="sxs-lookup"><span data-stu-id="6452b-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="6452b-133">O objeto retornado se torna uma subclasse do objeto atual.</span><span class="sxs-lookup"><span data-stu-id="6452b-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="6452b-134">O novo objeto retornado em `ppNewClass` torna-se automaticamente uma subclasse do objeto atual.</span><span class="sxs-lookup"><span data-stu-id="6452b-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="6452b-135">Esse comportamento não pode ser substituído.</span><span class="sxs-lookup"><span data-stu-id="6452b-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="6452b-136">Não há nenhum outro método pelo qual as subclasses (classes derivadas) podem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="6452b-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="6452b-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6452b-137">Requirements</span></span>  

 <span data-ttu-id="6452b-138">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6452b-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6452b-139">**Cabeçalho:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="6452b-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6452b-140">**.NET Framework versões:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6452b-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6452b-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="6452b-141">See also</span></span>

- [<span data-ttu-id="6452b-142">WMI e Contadores de Desempenho (Referência de API Não Gerenciada)</span><span class="sxs-lookup"><span data-stu-id="6452b-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
