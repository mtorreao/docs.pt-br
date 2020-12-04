---
title: Monitorar eventos de tempo de execução de contenção de bloqueio
description: Consulte eventos de ETW que coletam informações específicas para as contenções de bloqueio do monitor.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- monitor lock contention events (CoreCLR)
- ETW, EventPipe, LTTng contention events (CoreCLR)
ms.openlocfilehash: 38e5f493d4b223b4839dbd6f814cf656722189b2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96585614"
---
# <a name="net-runtime-contention-events"></a><span data-ttu-id="0808e-103">Eventos de contenção do tempo de execução do .NET</span><span class="sxs-lookup"><span data-stu-id="0808e-103">.NET runtime contention events</span></span>

<span data-ttu-id="0808e-104">Esses eventos de tempo de execução capturam informações sobre contenções de bloqueio de monitor, como with `Monitor.Enter` ou a palavra-chave C# lock.</span><span class="sxs-lookup"><span data-stu-id="0808e-104">These runtime events capture information about monitor lock contentions such as with `Monitor.Enter` or the C# lock keyword.</span></span> <span data-ttu-id="0808e-105">Para obter mais informações sobre como usar esses eventos para fins de diagnóstico, consulte [log e rastreamento de aplicativos .net](../../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="0808e-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="contentionstart_v1-event"></a><span data-ttu-id="0808e-106">ContentionStart_V1 evento</span><span class="sxs-lookup"><span data-stu-id="0808e-106">ContentionStart_V1 event</span></span>

<span data-ttu-id="0808e-107">Esse evento é emitido no início de uma contenção de bloqueio de monitor.</span><span class="sxs-lookup"><span data-stu-id="0808e-107">This event is emitted at the start of a monitor lock contention.</span></span>

|<span data-ttu-id="0808e-108">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="0808e-108">Keyword for raising the event</span></span>|<span data-ttu-id="0808e-109">Level</span><span class="sxs-lookup"><span data-stu-id="0808e-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="0808e-110">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="0808e-110">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="0808e-111">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="0808e-111">Informational (4)</span></span>|

 <span data-ttu-id="0808e-112">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="0808e-112">The following table shows event information.</span></span>

|<span data-ttu-id="0808e-113">Evento</span><span class="sxs-lookup"><span data-stu-id="0808e-113">Event</span></span>|<span data-ttu-id="0808e-114">ID do evento</span><span class="sxs-lookup"><span data-stu-id="0808e-114">Event ID</span></span>|<span data-ttu-id="0808e-115">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="0808e-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="0808e-116">81</span><span class="sxs-lookup"><span data-stu-id="0808e-116">81</span></span>|<span data-ttu-id="0808e-117">Uma contenção de bloqueio de monitor é iniciada.</span><span class="sxs-lookup"><span data-stu-id="0808e-117">A monitor lock contention starts.</span></span>|

|<span data-ttu-id="0808e-118">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="0808e-118">Field name</span></span>|<span data-ttu-id="0808e-119">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0808e-119">Data type</span></span>|<span data-ttu-id="0808e-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="0808e-120">Description</span></span>|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|<span data-ttu-id="0808e-121">`0` para gerenciado; `1` para nativo.</span><span class="sxs-lookup"><span data-stu-id="0808e-121">`0` for managed; `1` for native.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="0808e-122">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="0808e-122">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="contentionstop_v1-event"></a><span data-ttu-id="0808e-123">ContentionStop_V1 evento</span><span class="sxs-lookup"><span data-stu-id="0808e-123">ContentionStop_V1 event</span></span>

<span data-ttu-id="0808e-124">Esse evento é emitido no final de uma contenção de bloqueio de monitor.</span><span class="sxs-lookup"><span data-stu-id="0808e-124">This event is emitted at the end of a monitor lock contention.</span></span>

|<span data-ttu-id="0808e-125">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="0808e-125">Keyword for raising the event</span></span>|<span data-ttu-id="0808e-126">Level</span><span class="sxs-lookup"><span data-stu-id="0808e-126">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="0808e-127">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="0808e-127">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="0808e-128">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="0808e-128">Informational (4)</span></span>|

 <span data-ttu-id="0808e-129">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="0808e-129">The following table shows event information.</span></span>

|<span data-ttu-id="0808e-130">Evento</span><span class="sxs-lookup"><span data-stu-id="0808e-130">Event</span></span>|<span data-ttu-id="0808e-131">ID do evento</span><span class="sxs-lookup"><span data-stu-id="0808e-131">Event ID</span></span>|<span data-ttu-id="0808e-132">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="0808e-132">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStop_V1`|<span data-ttu-id="0808e-133">91</span><span class="sxs-lookup"><span data-stu-id="0808e-133">91</span></span>|<span data-ttu-id="0808e-134">Uma contenção de bloqueio de monitor termina.</span><span class="sxs-lookup"><span data-stu-id="0808e-134">A monitor lock contention ends.</span></span>|

|<span data-ttu-id="0808e-135">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="0808e-135">Field name</span></span>|<span data-ttu-id="0808e-136">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0808e-136">Data type</span></span>|<span data-ttu-id="0808e-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="0808e-137">Description</span></span>|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|<span data-ttu-id="0808e-138">`0` para gerenciado; `1` para nativo.</span><span class="sxs-lookup"><span data-stu-id="0808e-138">`0` for managed; `1` for native.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="0808e-139">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="0808e-139">Unique ID for the instance of CoreCLR.</span></span>|
|`DurationNs`|`win:Double`|<span data-ttu-id="0808e-140">Duração da contenção em nanossegundos.</span><span class="sxs-lookup"><span data-stu-id="0808e-140">Duration of the contention in nanoseconds.</span></span>|
