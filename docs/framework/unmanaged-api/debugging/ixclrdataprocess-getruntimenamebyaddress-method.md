---
title: 'Método IXCLRDataProcess:: GetRuntimeNameByAddress'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 6648bdafe6e5cdd402bcfa02a148c57f0f1e209e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270478"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a><span data-ttu-id="289c9-102">Método IXCLRDataProcess:: GetRuntimeNameByAddress</span><span class="sxs-lookup"><span data-stu-id="289c9-102">IXCLRDataProcess::GetRuntimeNameByAddress Method</span></span>

<span data-ttu-id="289c9-103">Obtém um nome para o endereço fornecido.</span><span class="sxs-lookup"><span data-stu-id="289c9-103">Gets a name for the given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="289c9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="289c9-104">Syntax</span></span>

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a><span data-ttu-id="289c9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="289c9-105">Parameters</span></span>

`address`\
<span data-ttu-id="289c9-106">no Um `CLRDATA_ADDRESS` valor que representa um endereço de código.</span><span class="sxs-lookup"><span data-stu-id="289c9-106">[in] A `CLRDATA_ADDRESS` value that represents a code address.</span></span>

`flags`\
<span data-ttu-id="289c9-107">no Definido como ' 0 '.</span><span class="sxs-lookup"><span data-stu-id="289c9-107">[in] Set to '0'.</span></span>

`bufLen`\
<span data-ttu-id="289c9-108">no O comprimento do buffer.</span><span class="sxs-lookup"><span data-stu-id="289c9-108">[in] The length of the buffer.</span></span>

`namLen`\
<span data-ttu-id="289c9-109">fora Um ponteiro para o número de caracteres retornados.</span><span class="sxs-lookup"><span data-stu-id="289c9-109">[out] A pointer to the number of characters returned.</span></span>

`namBuf`\
<span data-ttu-id="289c9-110">[out, size_is ( `bufLen` )] o buffer de entrada de comprimento `bufLen` que armazena o nome do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="289c9-110">[out, size_is(`bufLen`)] The input buffer of length `bufLen` that stores the runtime name.</span></span>

`displacement`\
<span data-ttu-id="289c9-111">fora Um `CLRDATA_ADDRESS` ponteiro para o deslocamento de código do símbolo retornado.</span><span class="sxs-lookup"><span data-stu-id="289c9-111">[out] A `CLRDATA_ADDRESS` pointer to the code offset of the returned symbol.</span></span>

## <a name="remarks"></a><span data-ttu-id="289c9-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="289c9-112">Remarks</span></span>

<span data-ttu-id="289c9-113">O método fornecido faz parte da `IXCLRDataProcess` interface e corresponde ao 16º slot da tabela de métodos virtuais.</span><span class="sxs-lookup"><span data-stu-id="289c9-113">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 16th slot of the virtual-method table.</span></span>

> [!NOTE]
> <span data-ttu-id="289c9-114">Se o buffer não for grande o suficiente para o nome, esse método retornará `S_FALSE` e definirá `nameLen` como o tamanho de buffer necessário.</span><span class="sxs-lookup"><span data-stu-id="289c9-114">If the buffer is not large enough for the name, this method returns `S_FALSE` and sets `nameLen` to the required buffer length.</span></span>

## <a name="requirements"></a><span data-ttu-id="289c9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="289c9-115">Requirements</span></span>

<span data-ttu-id="289c9-116">**Plataformas:** Consulte [os requisitos do sistema](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="289c9-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="289c9-117">**Cabeçalho:** None</span><span class="sxs-lookup"><span data-stu-id="289c9-117">**Header:** None\</span></span>
<span data-ttu-id="289c9-118">**Biblioteca:** None</span><span class="sxs-lookup"><span data-stu-id="289c9-118">**Library:** None\</span></span>
<span data-ttu-id="289c9-119">**.NET Framework versões:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="289c9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="289c9-120">Veja também</span><span class="sxs-lookup"><span data-stu-id="289c9-120">See also</span></span>

- [<span data-ttu-id="289c9-121">Depuração</span><span class="sxs-lookup"><span data-stu-id="289c9-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="289c9-122">Interface IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="289c9-122">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
