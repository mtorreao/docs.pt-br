---
title: Eventos de tempo de execução de coleta de lixo
description: Consulte eventos de tempo de execução do .NET que coletam informações de diagnóstico específicas para o coletor de lixo do .NET.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- GC events
- garbage collection events (CoreCLR)
- ETW, EventPipe, LTTng garbage collection events (CoreCLR)
ms.openlocfilehash: 2799a93f351baf23ec7a359b0b4b2be5c216dc4d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96585615"
---
# <a name="net-runtime-garbage-collection-events"></a><span data-ttu-id="3c988-103">Eventos de coleta de lixo do .NET Runtime</span><span class="sxs-lookup"><span data-stu-id="3c988-103">.NET runtime garbage collection events</span></span>

<span data-ttu-id="3c988-104"> Esses eventos coletam informações referentes à coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="3c988-104">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="3c988-105">Eles ajudam no diagnóstico e na depuração, incluindo a determinação de quantas vezes a coleta de lixo foi executada, a quantidade de memória liberada durante a coleta de lixo etc. Para obter mais informações sobre como usar esses eventos para fins de diagnóstico, consulte [log e rastreamento de aplicativos .net](../../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="3c988-105">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, etc. For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="gcstart_v2-event"></a><span data-ttu-id="3c988-106">GCStart_V2 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-106">GCStart_V2 Event</span></span>

<span data-ttu-id="3c988-107">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-107">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-108">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-108">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-109">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-110">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-110">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-111">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-111">Informational (4)</span></span>|

<span data-ttu-id="3c988-112">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-112">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-113">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-113">Event</span></span>|<span data-ttu-id="3c988-114">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-114">Event ID</span></span>|<span data-ttu-id="3c988-115">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="3c988-116">1</span><span class="sxs-lookup"><span data-stu-id="3c988-116">1</span></span>|<span data-ttu-id="3c988-117">Uma coleta de lixo foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="3c988-117">A garbage collection has started.</span></span>|

<span data-ttu-id="3c988-118">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-118">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-119">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-119">Field name</span></span>|<span data-ttu-id="3c988-120">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-120">Data type</span></span>|<span data-ttu-id="3c988-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-121">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="3c988-122">A *n*° de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="3c988-122">The *n* th garbage collection.</span></span>|
|`Depth`|`win:UInt32`|<span data-ttu-id="3c988-123">A geração que está sendo coletada.</span><span class="sxs-lookup"><span data-stu-id="3c988-123">The generation that is being collected.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="3c988-124">Motivo do gatilho da coleta de lixo:</span><span class="sxs-lookup"><span data-stu-id="3c988-124">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="3c988-125">`0x0` -Alocação de heap de objeto pequeno.</span><span class="sxs-lookup"><span data-stu-id="3c988-125">`0x0` - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="3c988-126">`0x1` Induzida.</span><span class="sxs-lookup"><span data-stu-id="3c988-126">`0x1` - Induced.</span></span><br /><br /> <span data-ttu-id="3c988-127">`0x2` -Memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="3c988-127">`0x2` - Low memory.</span></span><br /><br /> <span data-ttu-id="3c988-128">`0x3` Esvaziá.</span><span class="sxs-lookup"><span data-stu-id="3c988-128">`0x3` - Empty.</span></span><br /><br /> <span data-ttu-id="3c988-129">`0x4` -Alocação de heap de objeto grande.</span><span class="sxs-lookup"><span data-stu-id="3c988-129">`0x4` - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="3c988-130">`0x5` -Sem espaço (para heap de objeto pequeno).</span><span class="sxs-lookup"><span data-stu-id="3c988-130">`0x5` - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="3c988-131">`0x6` -Sem espaço (para heap de objeto grande).</span><span class="sxs-lookup"><span data-stu-id="3c988-131">`0x6` - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="3c988-132">`0x7` -Induzido, mas não forçado como bloqueio.</span><span class="sxs-lookup"><span data-stu-id="3c988-132">`0x7` - Induced but not forced as blocking.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="3c988-133">`0x0` -A coleta de lixo de bloqueio ocorreu fora da coleta de lixo em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3c988-133">`0x0` - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="3c988-134">`0x1` -Coleta de lixo em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3c988-134">`0x1` - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="3c988-135">`0x2` -A coleta de lixo de bloqueio ocorreu durante a coleta de lixo em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3c988-135">`0x2` - Blocking garbage collection occurred during background garbage collection.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="3c988-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="3c988-136">win:UInt16</span></span>|<span data-ttu-id="3c988-137">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-137">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="3c988-138">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="3c988-138">GCEnd_V1 Event</span></span>

<span data-ttu-id="3c988-139">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-139">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-140">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-140">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-141">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-141">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-142">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-142">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-143">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-143">Informational (4)</span></span>|

<span data-ttu-id="3c988-144">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-144">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-145">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-145">Event</span></span>|<span data-ttu-id="3c988-146">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-146">Event ID</span></span>|<span data-ttu-id="3c988-147">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-147">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="3c988-148">2</span><span class="sxs-lookup"><span data-stu-id="3c988-148">2</span></span>|<span data-ttu-id="3c988-149">A coleta de lixo foi encerrada.</span><span class="sxs-lookup"><span data-stu-id="3c988-149">The garbage collection has ended.</span></span>|

<span data-ttu-id="3c988-150">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-150">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-151">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-151">Field name</span></span>|<span data-ttu-id="3c988-152">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-152">Data type</span></span>|<span data-ttu-id="3c988-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-153">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="3c988-154">A *n*° de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="3c988-154">The *n* th garbage collection.</span></span>|
|`Depth`|`win:UInt32`|<span data-ttu-id="3c988-155">A geração que foi coletada.</span><span class="sxs-lookup"><span data-stu-id="3c988-155">The generation that was collected.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="3c988-156">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="3c988-156">win:UInt16</span></span>|<span data-ttu-id="3c988-157">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-157">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcheapstats_v2-event"></a><span data-ttu-id="3c988-158">GCHeapStats_V2 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-158">GCHeapStats_V2 Event</span></span>

<span data-ttu-id="3c988-159">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-159">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-160">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-160">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-161">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-161">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-162">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-162">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-163">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-163">Informational (4)</span></span>|

<span data-ttu-id="3c988-164">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-164">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-165">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-165">Event</span></span>|<span data-ttu-id="3c988-166">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-166">Event ID</span></span>|<span data-ttu-id="3c988-167">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-167">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V2`|<span data-ttu-id="3c988-168">4</span><span class="sxs-lookup"><span data-stu-id="3c988-168">4</span></span>|<span data-ttu-id="3c988-169">Mostra as estatísticas de heap no final de cada coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="3c988-169">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="3c988-170">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-170">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-171">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-171">Field name</span></span>|<span data-ttu-id="3c988-172">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-172">Data type</span></span>|<span data-ttu-id="3c988-173">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-173">Description</span></span>|
|----------------|---------------|-----------------|
|`GenerationSize0`|`win:UInt64`|<span data-ttu-id="3c988-174">O tamanho, em bytes, da memória de geração 0.</span><span class="sxs-lookup"><span data-stu-id="3c988-174">The size, in bytes, of generation 0 memory.</span></span>|
|`TotalPromotedSize0`|`win:UInt64`|<span data-ttu-id="3c988-175">O número de bytes que são promovidos da geração 0 para a geração 1.</span><span class="sxs-lookup"><span data-stu-id="3c988-175">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|`GenerationSize1`|`win:UInt64`|<span data-ttu-id="3c988-176">O tamanho, em bytes, da memória de geração 1.</span><span class="sxs-lookup"><span data-stu-id="3c988-176">The size, in bytes, of generation 1 memory.</span></span>|
|`TotalPromotedSize1`|`win:UInt64`|<span data-ttu-id="3c988-177">O número de bytes que são promovidos da geração 1 para a geração 2.</span><span class="sxs-lookup"><span data-stu-id="3c988-177">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|`GenerationSize2`|`win:UInt64`|<span data-ttu-id="3c988-178">O tamanho, em bytes, da memória de geração 2.</span><span class="sxs-lookup"><span data-stu-id="3c988-178">The size, in bytes, of generation 2 memory.</span></span>|
|`TotalPromotedSize2`|`win:UInt64`|<span data-ttu-id="3c988-179">O número de bytes que sobreviveram na geração 2 após a última coleta.</span><span class="sxs-lookup"><span data-stu-id="3c988-179">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|`GenerationSize3`|`win:UInt64`|<span data-ttu-id="3c988-180">O tamanho, em bytes, do heap de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="3c988-180">The size, in bytes, of the large object heap.</span></span>|
|`TotalPromotedSize3`|`win:UInt64`|<span data-ttu-id="3c988-181">O número de bytes que sobreviveram no heap de objetos grandes após a última coleta.</span><span class="sxs-lookup"><span data-stu-id="3c988-181">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|`FinalizationPromotedSize`|`win:UInt64`|<span data-ttu-id="3c988-182">O tamanho total, em bytes, dos objetos que estão prontos para finalização.</span><span class="sxs-lookup"><span data-stu-id="3c988-182">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|`FinalizationPromotedCount`|`win:UInt64`|<span data-ttu-id="3c988-183">O número de objetos que estão prontos para finalização.</span><span class="sxs-lookup"><span data-stu-id="3c988-183">The number of objects that are ready for finalization.</span></span>|
|`PinnedObjectCount`|`win:UInt32`|<span data-ttu-id="3c988-184">O número de objetos (imóveis) fixados.</span><span class="sxs-lookup"><span data-stu-id="3c988-184">The number of pinned (unmovable) objects.</span></span>|
|`SinkBlockCount`|`win:UInt32`|<span data-ttu-id="3c988-185">O número de blocos de sincronização em uso.</span><span class="sxs-lookup"><span data-stu-id="3c988-185">The number of synchronization blocks in use.</span></span>|
|`GCHandleCount`|`win:UInt32`|<span data-ttu-id="3c988-186">O número de manipuladores de coleta de lixo em uso.</span><span class="sxs-lookup"><span data-stu-id="3c988-186">The number of garbage collection handles in use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="3c988-187">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-187">Unique ID for the instance of CoreCLR.</span></span>|
|`GenerationSize4`|`win:UInt64`|<span data-ttu-id="3c988-188">O tamanho, em bytes, do heap de objeto fixado.</span><span class="sxs-lookup"><span data-stu-id="3c988-188">The size, in bytes, of the pinned object heap.</span></span>|
|`TotalPromotedSize4`|`win:UInt64`|<span data-ttu-id="3c988-189">O número de bytes que sobreviveram no heap de objeto fixado após a última coleta.</span><span class="sxs-lookup"><span data-stu-id="3c988-189">The number of bytes that survived in the pinned object heap after the last collection.</span></span>|

## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="3c988-190">GCCreateSegment_V1 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-190">GCCreateSegment_V1 event</span></span>

<span data-ttu-id="3c988-191">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-191">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-192">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-192">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-193">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-193">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-194">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-194">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-195">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-195">Informational (4)</span></span>|

<span data-ttu-id="3c988-196">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-196">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-197">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-197">Event</span></span>|<span data-ttu-id="3c988-198">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-198">Event ID</span></span>|<span data-ttu-id="3c988-199">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-199">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="3c988-200">5</span><span class="sxs-lookup"><span data-stu-id="3c988-200">5</span></span>|<span data-ttu-id="3c988-201">Um novo segmento de coleta de lixo foi criado.</span><span class="sxs-lookup"><span data-stu-id="3c988-201">A new garbage collection segment has been created.</span></span> <span data-ttu-id="3c988-202">Além disso, quando o rastreamento é habilitado em um processo que já está em execução, esse evento é acionado para cada segmento existente.</span><span class="sxs-lookup"><span data-stu-id="3c988-202">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="3c988-203">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-203">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-204">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-204">Field name</span></span>|<span data-ttu-id="3c988-205">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-205">Data type</span></span>|<span data-ttu-id="3c988-206">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-206">Description</span></span>|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|<span data-ttu-id="3c988-207">O endereço do segmento.</span><span class="sxs-lookup"><span data-stu-id="3c988-207">The address of the segment.</span></span>|
|`Size`|`win:UInt64`|<span data-ttu-id="3c988-208">O tamanho do segmento.</span><span class="sxs-lookup"><span data-stu-id="3c988-208">The size of the segment.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="3c988-209">0x0 – Heap de objetos pequenos.</span><span class="sxs-lookup"><span data-stu-id="3c988-209">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="3c988-210">0x1 – Heap de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="3c988-210">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="3c988-211">0x2 – Heap somente leitura.</span><span class="sxs-lookup"><span data-stu-id="3c988-211">0x2 - Read-only heap.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="3c988-212">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-212">Unique ID for the instance of CoreCLR.</span></span>|

<span data-ttu-id="3c988-213">Observe que o tamanho de segmentos alocados pelo coletor de lixo é específico à implementação e está sujeito a alterações a qualquer momento, incluindo em atualizações periódicas.</span><span class="sxs-lookup"><span data-stu-id="3c988-213">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="3c988-214">Seu aplicativo nunca deve fazer suposições sobre o tamanho de um segmento em particular nem depender dele, tampouco deve tentar configurar a quantidade de memória disponível para alocações de segmento.</span><span class="sxs-lookup"><span data-stu-id="3c988-214">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="3c988-215">GCFreeSegment_V1 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-215">GCFreeSegment_V1 event</span></span>

<span data-ttu-id="3c988-216">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-216">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-217">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-217">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-218">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-218">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-219">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-219">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-220">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-220">Informational (4)</span></span>|

<span data-ttu-id="3c988-221">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-221">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-222">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-222">Event</span></span>|<span data-ttu-id="3c988-223">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-223">Event ID</span></span>|<span data-ttu-id="3c988-224">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-224">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="3c988-225">6</span><span class="sxs-lookup"><span data-stu-id="3c988-225">6</span></span>|<span data-ttu-id="3c988-226">Um segmento de coleta de lixo foi liberado.</span><span class="sxs-lookup"><span data-stu-id="3c988-226">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="3c988-227">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-227">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-228">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-228">Field name</span></span>|<span data-ttu-id="3c988-229">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-229">Data type</span></span>|<span data-ttu-id="3c988-230">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-230">Description</span></span>|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|<span data-ttu-id="3c988-231">O endereço do segmento.</span><span class="sxs-lookup"><span data-stu-id="3c988-231">The address of the segment.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="3c988-232">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-232">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="3c988-233">GCRestartEEBegin_V1 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-233">GCRestartEEBegin_V1 event</span></span>

<span data-ttu-id="3c988-234">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-234">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-235">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-235">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-236">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-236">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-237">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-237">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-238">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-238">Informational (4)</span></span>|

<span data-ttu-id="3c988-239">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-239">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-240">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-240">Event</span></span>|<span data-ttu-id="3c988-241">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-241">Event ID</span></span>|<span data-ttu-id="3c988-242">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-242">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="3c988-243">7</span><span class="sxs-lookup"><span data-stu-id="3c988-243">7</span></span>|<span data-ttu-id="3c988-244">A continuidade da suspensão do Common Language Runtime foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="3c988-244">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="3c988-245">Esse evento não tem nenhum dado de evento.</span><span class="sxs-lookup"><span data-stu-id="3c988-245">This event does not have any event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="3c988-246">GCRestartEEEnd_V1 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-246">GCRestartEEEnd_V1 event</span></span>

<span data-ttu-id="3c988-247">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-247">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-248">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-248">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-249">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-249">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-250">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-250">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-251">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-251">Informational (4)</span></span>|

<span data-ttu-id="3c988-252">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-252">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-253">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-253">Event</span></span>|<span data-ttu-id="3c988-254">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-254">Event Id</span></span>|<span data-ttu-id="3c988-255">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-255">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="3c988-256">3</span><span class="sxs-lookup"><span data-stu-id="3c988-256">3</span></span>|<span data-ttu-id="3c988-257">A continuidade da suspensão do Common Language Runtime foi encerrada.</span><span class="sxs-lookup"><span data-stu-id="3c988-257">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="3c988-258">Esse evento não tem nenhum dado de evento.</span><span class="sxs-lookup"><span data-stu-id="3c988-258">This event does not have any event data.</span></span>

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="3c988-259">GCSuspendEEEnd_V1 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-259">GCSuspendEEEnd_V1 event</span></span>

<span data-ttu-id="3c988-260">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-260">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-261">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-261">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-262">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-262">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-263">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-263">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-264">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-264">Informational (4)</span></span>|

<span data-ttu-id="3c988-265">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-265">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-266">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-266">Event</span></span>|<span data-ttu-id="3c988-267">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-267">Event ID</span></span>|<span data-ttu-id="3c988-268">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-268">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="3c988-269">8</span><span class="sxs-lookup"><span data-stu-id="3c988-269">8</span></span>|<span data-ttu-id="3c988-270">Fim da suspensão do mecanismo de execução da coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="3c988-270">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="3c988-271">Esse evento não tem nenhum dado de evento.</span><span class="sxs-lookup"><span data-stu-id="3c988-271">This event does not have any event data.</span></span>

## <a name="gcsuspendeebegin_v1-event"></a><span data-ttu-id="3c988-272">GCSuspendEEBegin_V1 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-272">GCSuspendEEBegin_V1 event</span></span>

<span data-ttu-id="3c988-273">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-273">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-274">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-274">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-275">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-275">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-276">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-276">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-277">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-277">Informational (4)</span></span>|

<span data-ttu-id="3c988-278">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-278">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-279">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-279">Event</span></span>|<span data-ttu-id="3c988-280">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-280">Event ID</span></span>|<span data-ttu-id="3c988-281">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-281">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEBegin_V1`|<span data-ttu-id="3c988-282">8</span><span class="sxs-lookup"><span data-stu-id="3c988-282">8</span></span>|<span data-ttu-id="3c988-283">Início da suspensão do mecanismo de execução da coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="3c988-283">Start of suspension of the execution engine for garbage collection.</span></span>|

|<span data-ttu-id="3c988-284">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-284">Field name</span></span>|<span data-ttu-id="3c988-285">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-285">Data type</span></span>|<span data-ttu-id="3c988-286">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-286">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="3c988-287">A *n*° de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="3c988-287">The *n* th garbage collection.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="3c988-288">Motivo da suspensão de EE.</span><span class="sxs-lookup"><span data-stu-id="3c988-288">Reason for EE suspension.</span></span><br/><br/><span data-ttu-id="3c988-289">`0x0`: Suspender para outros</span><span class="sxs-lookup"><span data-stu-id="3c988-289">`0x0`: Suspend for Other</span></span><br/><br/><span data-ttu-id="3c988-290">`0x1`: Suspender para GC.</span><span class="sxs-lookup"><span data-stu-id="3c988-290">`0x1`: Suspend for GC.</span></span><br/><br/><span data-ttu-id="3c988-291">`0x2`: Suspender para desligamento de AppDomain.</span><span class="sxs-lookup"><span data-stu-id="3c988-291">`0x2`: Suspend for AppDomain shutdown.</span></span><br/><br/><span data-ttu-id="3c988-292">`0x3`: Suspender para a densidade de código.</span><span class="sxs-lookup"><span data-stu-id="3c988-292">`0x3`: Suspend for code pitching.</span></span><br/><br/><span data-ttu-id="3c988-293">`0x4`: Suspender para desligamento.</span><span class="sxs-lookup"><span data-stu-id="3c988-293">`0x4`: Suspend for shutdown.</span></span><br/><br/><span data-ttu-id="3c988-294">`0x5`: Suspender para o depurador.</span><span class="sxs-lookup"><span data-stu-id="3c988-294">`0x5`: Suspend for debugger.</span></span><br/><br/><span data-ttu-id="3c988-295">`0x6`: Suspender para o CG Prep.</span><span class="sxs-lookup"><span data-stu-id="3c988-295">`0x6`: Suspend for GC Prep.</span></span><br/><br/><span data-ttu-id="3c988-296">`0x7`: Suspender para varredura do depurador</span><span class="sxs-lookup"><span data-stu-id="3c988-296">`0x7`: Suspend for debugger sweep</span></span>|

## <a name="gcallocationtick_v3-event"></a><span data-ttu-id="3c988-297">GCAllocationTick_V3 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-297">GCAllocationTick_V3 event</span></span>

<span data-ttu-id="3c988-298">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-298">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-299">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-299">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-300">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-300">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-301">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-301">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-302">Detalhado (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-302">Verbose (4)</span></span>|

<span data-ttu-id="3c988-303">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-303">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-304">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-304">Event</span></span>|<span data-ttu-id="3c988-305">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-305">Event ID</span></span>|<span data-ttu-id="3c988-306">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-306">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V3`|<span data-ttu-id="3c988-307">10</span><span class="sxs-lookup"><span data-stu-id="3c988-307">10</span></span>|<span data-ttu-id="3c988-308">A cada vez, aproximadamente 100 KB são alocados.</span><span class="sxs-lookup"><span data-stu-id="3c988-308">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="3c988-309">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-309">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-310">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-310">Field name</span></span>|<span data-ttu-id="3c988-311">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-311">Data type</span></span>|<span data-ttu-id="3c988-312">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-312">Description</span></span>|
|----------------|---------------|-----------------|
|`AllocationAmount`|`win:UInt32`|<span data-ttu-id="3c988-313">O tamanho de alocação, em bytes.</span><span class="sxs-lookup"><span data-stu-id="3c988-313">The allocation size, in bytes.</span></span> <span data-ttu-id="3c988-314">Esse valor é preciso para alocações menores do que o tamanho de um ULONG (4.294.967.295 bytes).</span><span class="sxs-lookup"><span data-stu-id="3c988-314">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="3c988-315">Se a alocação for maior, esse campo conterá um valor truncado.</span><span class="sxs-lookup"><span data-stu-id="3c988-315">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="3c988-316">Use `AllocationAmount64` para alocações muito grandes.</span><span class="sxs-lookup"><span data-stu-id="3c988-316">Use `AllocationAmount64` for very large allocations.</span></span>|
|`AllocationKind`|`win:UInt32`|<span data-ttu-id="3c988-317">`0x0` -Alocação de objeto pequeno (a alocação está em heap de objeto pequeno).</span><span class="sxs-lookup"><span data-stu-id="3c988-317">`0x0` - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="3c988-318">`0x1` -Alocação de objeto grande (a alocação está em heap de objeto grande).</span><span class="sxs-lookup"><span data-stu-id="3c988-318">`0x1` - Large object allocation (allocation is in large object heap).</span></span>|
|`AllocationAmount64`|`win:UInt64`|<span data-ttu-id="3c988-319">O tamanho de alocação, em bytes.</span><span class="sxs-lookup"><span data-stu-id="3c988-319">The allocation size, in bytes.</span></span> <span data-ttu-id="3c988-320">Esse valor é preciso para alocações muito grandes.</span><span class="sxs-lookup"><span data-stu-id="3c988-320">This value is accurate for very large allocations.</span></span>|
|`TypeId`|`win:Pointer`|<span data-ttu-id="3c988-321">O endereço da MethodTable.</span><span class="sxs-lookup"><span data-stu-id="3c988-321">The address of the MethodTable.</span></span> <span data-ttu-id="3c988-322">Quando há vários tipos de objetos que foram alocados durante esse evento, esse é o endereço da MethodTable que corresponde ao último objeto alocado (o objeto que fez com que o limite de 100 KB fosse excedido).</span><span class="sxs-lookup"><span data-stu-id="3c988-322">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="3c988-323">O nome do tipo que foi alocado.</span><span class="sxs-lookup"><span data-stu-id="3c988-323">The name of the type that was allocated.</span></span> <span data-ttu-id="3c988-324">Quando há vários tipos de objetos que foram alocados durante esse evento, esse é o tipo do último objeto alocado (o objeto que fez com que o limite de 100 KB fosse excedido).</span><span class="sxs-lookup"><span data-stu-id="3c988-324">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|`HeapIndex`|`win:UInt32`|<span data-ttu-id="3c988-325">O heap em que o objeto foi alocado.</span><span class="sxs-lookup"><span data-stu-id="3c988-325">The heap where the object was allocated.</span></span> <span data-ttu-id="3c988-326">Esse valor é 0 (zero) durante a execução da coleta de lixo da estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3c988-326">This value is 0 (zero) when running with workstation garbage collection.</span></span>|
|`Address`|`win:Pointer`|<span data-ttu-id="3c988-327">O endereço do último objeto alocado.</span><span class="sxs-lookup"><span data-stu-id="3c988-327">The address of the last allocated object.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="3c988-328">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-328">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="3c988-329">GCCreateConcurrentThread_V1 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-329">GCCreateConcurrentThread_V1 event</span></span>

<span data-ttu-id="3c988-330">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-330">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-331">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-331">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-332">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-332">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-333">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-333">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-334">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-334">Informational (4)</span></span>|
|<span data-ttu-id="3c988-335">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="3c988-335">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="3c988-336">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-336">Informational (4)</span></span>|

<span data-ttu-id="3c988-337">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-337">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-338">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-338">Event</span></span>|<span data-ttu-id="3c988-339">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-339">Event ID</span></span>|<span data-ttu-id="3c988-340">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-340">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="3c988-341">11</span><span class="sxs-lookup"><span data-stu-id="3c988-341">11</span></span>|<span data-ttu-id="3c988-342">O thread da coleta de lixo simultânea foi criado.</span><span class="sxs-lookup"><span data-stu-id="3c988-342">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="3c988-343">Esse evento não tem nenhum dado de evento.</span><span class="sxs-lookup"><span data-stu-id="3c988-343">This event does not have any event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="3c988-344">GCTerminateConcurrentThread_V1 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-344">GCTerminateConcurrentThread_V1 event</span></span>

<span data-ttu-id="3c988-345">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-345">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-346">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-346">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-347">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-347">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-348">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-348">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-349">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-349">Informational (4)</span></span>|
|<span data-ttu-id="3c988-350">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="3c988-350">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="3c988-351">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-351">Informational (4)</span></span>|

<span data-ttu-id="3c988-352">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-352">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-353">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-353">Event</span></span>|<span data-ttu-id="3c988-354">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-354">Event ID</span></span>|<span data-ttu-id="3c988-355">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-355">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="3c988-356">12</span><span class="sxs-lookup"><span data-stu-id="3c988-356">12</span></span>|<span data-ttu-id="3c988-357">O thread da coleta de lixo simultânea foi terminado.</span><span class="sxs-lookup"><span data-stu-id="3c988-357">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="3c988-358">Esse evento não tem nenhum dado de evento.</span><span class="sxs-lookup"><span data-stu-id="3c988-358">This event does not have any event data.</span></span>

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="3c988-359">GCFinalizersBegin_V1 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-359">GCFinalizersBegin_V1 event</span></span>

<span data-ttu-id="3c988-360">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-360">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-361">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-361">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-362">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-362">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-363">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-363">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-364">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-364">Informational (4)</span></span>|

<span data-ttu-id="3c988-365">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-365">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-366">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-366">Event</span></span>|<span data-ttu-id="3c988-367">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-367">Event ID</span></span>|<span data-ttu-id="3c988-368">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-368">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="3c988-369">14</span><span class="sxs-lookup"><span data-stu-id="3c988-369">14</span></span>|<span data-ttu-id="3c988-370">O início da execução dos finalizadores.</span><span class="sxs-lookup"><span data-stu-id="3c988-370">The start of running finalizers.</span></span>|

<span data-ttu-id="3c988-371">Esse evento não tem nenhum dado de evento.</span><span class="sxs-lookup"><span data-stu-id="3c988-371">This event does not have any event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="3c988-372">GCFinalizersEnd_V1 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-372">GCFinalizersEnd_V1 event</span></span>

<span data-ttu-id="3c988-373">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-373">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-374">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-374">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-375">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-375">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-376">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-376">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-377">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-377">Informational (4)</span></span>|

<span data-ttu-id="3c988-378">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-378">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-379">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-379">Event</span></span>|<span data-ttu-id="3c988-380">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-380">Event ID</span></span>|<span data-ttu-id="3c988-381">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-381">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="3c988-382">13</span><span class="sxs-lookup"><span data-stu-id="3c988-382">13</span></span>|<span data-ttu-id="3c988-383">O fim da execução dos finalizadores.</span><span class="sxs-lookup"><span data-stu-id="3c988-383">The end of running finalizers.</span></span>|

<span data-ttu-id="3c988-384">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-384">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-385">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-385">Field name</span></span>|<span data-ttu-id="3c988-386">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-386">Data type</span></span>|<span data-ttu-id="3c988-387">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-387">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="3c988-388">O número de finalizadores que foram executados.</span><span class="sxs-lookup"><span data-stu-id="3c988-388">The number of finalizers that were run.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="3c988-389">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="3c988-389">win:UInt16</span></span>|<span data-ttu-id="3c988-390">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-390">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="setgchandle-event"></a><span data-ttu-id="3c988-391">Evento setgchandle</span><span class="sxs-lookup"><span data-stu-id="3c988-391">SetGCHandle event</span></span>

<span data-ttu-id="3c988-392">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-392">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-393">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-393">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-394">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-394">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-395">`GCHandleKeyword` 0x2</span><span class="sxs-lookup"><span data-stu-id="3c988-395">`GCHandleKeyword` (0x2)</span></span>|<span data-ttu-id="3c988-396">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-396">Informational (4)</span></span>|

<span data-ttu-id="3c988-397">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-397">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-398">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-398">Event</span></span>|<span data-ttu-id="3c988-399">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-399">Event ID</span></span>|<span data-ttu-id="3c988-400">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-400">Raised when</span></span>|
|-----------|--------------|-----------------|
|`SetGCHandle`|<span data-ttu-id="3c988-401">30</span><span class="sxs-lookup"><span data-stu-id="3c988-401">30</span></span>|<span data-ttu-id="3c988-402">Um identificador de GC foi definido.</span><span class="sxs-lookup"><span data-stu-id="3c988-402">A GC Handle has been set.</span></span>|

<span data-ttu-id="3c988-403">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-403">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-404">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-404">Field name</span></span>|<span data-ttu-id="3c988-405">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-405">Data type</span></span>|<span data-ttu-id="3c988-406">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-406">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="3c988-407">O endereço do identificador alocado.</span><span class="sxs-lookup"><span data-stu-id="3c988-407">The address of the allocated handle.</span></span>|
|`ObjectID`|`win:Pointer`|<span data-ttu-id="3c988-408">O endereço do objeto cujo identificador foi criado.</span><span class="sxs-lookup"><span data-stu-id="3c988-408">The address of the object whose handle was created.</span></span>|
|`Kind`|`win:UInt32`|<span data-ttu-id="3c988-409">O tipo de identificador de GC que foi definido.</span><span class="sxs-lookup"><span data-stu-id="3c988-409">The type of GC handle that was set.</span></span> <br /><br /><span data-ttu-id="3c988-410">`0x0`: WeakShort</span><span class="sxs-lookup"><span data-stu-id="3c988-410">`0x0`: WeakShort</span></span> <br/><br/><span data-ttu-id="3c988-411">`0x1`: WeakLong</span><span class="sxs-lookup"><span data-stu-id="3c988-411">`0x1`: WeakLong</span></span> <br /><br /><span data-ttu-id="3c988-412">`0x2`: Forte</span><span class="sxs-lookup"><span data-stu-id="3c988-412">`0x2`: Strong</span></span> <br /><br /><span data-ttu-id="3c988-413">`0x3`: Fixado</span><span class="sxs-lookup"><span data-stu-id="3c988-413">`0x3`: Pinned</span></span> <br /><br /><span data-ttu-id="3c988-414">`0x4`: Variável</span><span class="sxs-lookup"><span data-stu-id="3c988-414">`0x4`: Variable</span></span><br /><br /><span data-ttu-id="3c988-415">`0x5`: RefCounted</span><span class="sxs-lookup"><span data-stu-id="3c988-415">`0x5`: RefCounted</span></span> <br /><br /><span data-ttu-id="3c988-416">`0x6`: Dependente</span><span class="sxs-lookup"><span data-stu-id="3c988-416">`0x6`: Dependent</span></span><br /><br /><span data-ttu-id="3c988-417">`0x7`: AsyncPinned</span><span class="sxs-lookup"><span data-stu-id="3c988-417">`0x7`: AsyncPinned</span></span><br /><br /><span data-ttu-id="3c988-418">`0x8`: Identificador sizedref</span><span class="sxs-lookup"><span data-stu-id="3c988-418">`0x8`: SizedRef</span></span>|
|`Generation`|`win:UInt32`|<span data-ttu-id="3c988-419">A geração do objeto cujo identificador foi criado.</span><span class="sxs-lookup"><span data-stu-id="3c988-419">The generation of the object whose handle was created.</span></span>|
|`AppDomainID`|`win:UInt64`|<span data-ttu-id="3c988-420">A ID do AppDomain.</span><span class="sxs-lookup"><span data-stu-id="3c988-420">The AppDomain ID.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="3c988-421">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-421">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="destroygchandle-event"></a><span data-ttu-id="3c988-422">Evento DestroyGCHandle</span><span class="sxs-lookup"><span data-stu-id="3c988-422">DestroyGCHandle event</span></span>

<span data-ttu-id="3c988-423">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-423">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-424">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-424">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-425">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-425">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-426">`GCHandleKeyword` 0x2</span><span class="sxs-lookup"><span data-stu-id="3c988-426">`GCHandleKeyword` (0x2)</span></span>|<span data-ttu-id="3c988-427">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-427">Informational (4)</span></span>|

<span data-ttu-id="3c988-428">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-428">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-429">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-429">Event</span></span>|<span data-ttu-id="3c988-430">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-430">Event ID</span></span>|<span data-ttu-id="3c988-431">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-431">Raised when</span></span>|
|-----------|--------------|-----------------|
|`DestroyGCHandle`|<span data-ttu-id="3c988-432">31</span><span class="sxs-lookup"><span data-stu-id="3c988-432">31</span></span>|<span data-ttu-id="3c988-433">Um identificador de GC é destruído.</span><span class="sxs-lookup"><span data-stu-id="3c988-433">A GC Handle is destroyed.</span></span>|

<span data-ttu-id="3c988-434">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-434">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-435">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-435">Field name</span></span>|<span data-ttu-id="3c988-436">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-436">Data type</span></span>|<span data-ttu-id="3c988-437">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-437">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="3c988-438">O endereço do identificador destruído.</span><span class="sxs-lookup"><span data-stu-id="3c988-438">The address of the destroyed handle.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="3c988-439">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="3c988-439">win:UInt16</span></span>|<span data-ttu-id="3c988-440">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-440">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="pinobjectatgctime-event"></a><span data-ttu-id="3c988-441">Evento PinObjectAtGCTime</span><span class="sxs-lookup"><span data-stu-id="3c988-441">PinObjectAtGCTime event</span></span>

<span data-ttu-id="3c988-442">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-442">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-443">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-443">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-444">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-444">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-445">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-445">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-446">Detalhado (5)</span><span class="sxs-lookup"><span data-stu-id="3c988-446">Verbose (5)</span></span>|

<span data-ttu-id="3c988-447">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-447">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-448">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-448">Event</span></span>|<span data-ttu-id="3c988-449">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-449">Event ID</span></span>|<span data-ttu-id="3c988-450">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-450">Raised when</span></span>|
|-----------|--------------|-----------------|
|`PinObjectAtGCTime`|<span data-ttu-id="3c988-451">33</span><span class="sxs-lookup"><span data-stu-id="3c988-451">33</span></span>|<span data-ttu-id="3c988-452">Um objeto foi fixado durante um GC.</span><span class="sxs-lookup"><span data-stu-id="3c988-452">An object was pinned during a GC.</span></span>|

<span data-ttu-id="3c988-453">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-453">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-454">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-454">Field name</span></span>|<span data-ttu-id="3c988-455">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-455">Data type</span></span>|<span data-ttu-id="3c988-456">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-456">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="3c988-457">O endereço do identificador.</span><span class="sxs-lookup"><span data-stu-id="3c988-457">The address of the handle.</span></span>|
|`ObjectID`|`win:Pointer`|<span data-ttu-id="3c988-458">O endereço do objeto fixado.</span><span class="sxs-lookup"><span data-stu-id="3c988-458">The address of the pinned object.</span></span>|
|`ObjectSize`|`win:UInt64`|<span data-ttu-id="3c988-459">O tamanho do objeto fixado.</span><span class="sxs-lookup"><span data-stu-id="3c988-459">The size of the pinned object.</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="3c988-460">O nome do tipo do objeto fixado.</span><span class="sxs-lookup"><span data-stu-id="3c988-460">The name of the type of the pinned object.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="3c988-461">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-461">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gctriggered-event"></a><span data-ttu-id="3c988-462">Evento GCTriggered</span><span class="sxs-lookup"><span data-stu-id="3c988-462">GCTriggered event</span></span>

<span data-ttu-id="3c988-463">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-463">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-464">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-464">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-465">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-465">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-466">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-466">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-467">Detalhado (5)</span><span class="sxs-lookup"><span data-stu-id="3c988-467">Verbose (5)</span></span>|

<span data-ttu-id="3c988-468">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-468">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-469">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-469">Event</span></span>|<span data-ttu-id="3c988-470">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-470">Event ID</span></span>|<span data-ttu-id="3c988-471">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-471">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTriggered`|<span data-ttu-id="3c988-472">33</span><span class="sxs-lookup"><span data-stu-id="3c988-472">33</span></span>|<span data-ttu-id="3c988-473">Um GC foi disparado.</span><span class="sxs-lookup"><span data-stu-id="3c988-473">A GC has been triggered.</span></span>|

<span data-ttu-id="3c988-474">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-474">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-475">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-475">Field name</span></span>|<span data-ttu-id="3c988-476">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-476">Data type</span></span>|<span data-ttu-id="3c988-477">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-477">Description</span></span>|
|----------------|---------------|-----------------|
|`Reason`|`win:UInt32`|<span data-ttu-id="3c988-478">O motivo pelo qual um GC foi disparado.</span><span class="sxs-lookup"><span data-stu-id="3c988-478">The reason a GC was triggered.</span></span><br/><br/><span data-ttu-id="3c988-479">`0x0`: AllocSmall</span><span class="sxs-lookup"><span data-stu-id="3c988-479">`0x0`: AllocSmall</span></span><br/><br/><span data-ttu-id="3c988-480">`0x1`: Induzido</span><span class="sxs-lookup"><span data-stu-id="3c988-480">`0x1`: Induced</span></span> <br/><br/><span data-ttu-id="3c988-481">`0x2`: LowMemory</span><span class="sxs-lookup"><span data-stu-id="3c988-481">`0x2`: LowMemory</span></span> <br/><br/><span data-ttu-id="3c988-482">`0x3`: Vazio</span><span class="sxs-lookup"><span data-stu-id="3c988-482">`0x3`: Empty</span></span> <br/><br/><span data-ttu-id="3c988-483">`0x4`: AllocLarge</span><span class="sxs-lookup"><span data-stu-id="3c988-483">`0x4`: AllocLarge</span></span> <br/><br/><span data-ttu-id="3c988-484">`0x5`: OutOfSpaceSmallObjectHeap</span><span class="sxs-lookup"><span data-stu-id="3c988-484">`0x5`: OutOfSpaceSmallObjectHeap</span></span> <br/><br/><span data-ttu-id="3c988-485">`0x6`: OutOfSpaceLargeObjectHeap</span><span class="sxs-lookup"><span data-stu-id="3c988-485">`0x6`: OutOfSpaceLargeObjectHeap</span></span> <br/><br/><span data-ttu-id="3c988-486">`0x7`:InducedNoForce</span><span class="sxs-lookup"><span data-stu-id="3c988-486">`0x7`:InducedNoForce</span></span> <br/><br/><span data-ttu-id="3c988-487">`0x8`: Estresse</span><span class="sxs-lookup"><span data-stu-id="3c988-487">`0x8`: Stress</span></span> <br/><br/><span data-ttu-id="3c988-488">`0x9`: InducedLowMemory</span><span class="sxs-lookup"><span data-stu-id="3c988-488">`0x9`: InducedLowMemory</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="3c988-489">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-489">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="increasememorypressure-event"></a><span data-ttu-id="3c988-490">Evento IncreaseMemoryPressure</span><span class="sxs-lookup"><span data-stu-id="3c988-490">IncreaseMemoryPressure event</span></span>

<span data-ttu-id="3c988-491">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-491">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-492">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-492">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-493">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-493">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-494">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-494">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-495">Informações (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-495">Information (4)</span></span>|

<span data-ttu-id="3c988-496">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-496">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-497">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-497">Event</span></span>|<span data-ttu-id="3c988-498">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-498">Event ID</span></span>|<span data-ttu-id="3c988-499">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-499">Raised when</span></span>|
|----------------|---------------|-----------------|
|`IncreaseMemoryPressure`|<span data-ttu-id="3c988-500">200</span><span class="sxs-lookup"><span data-stu-id="3c988-500">200</span></span>|<span data-ttu-id="3c988-501">A pressão de memória foi aumentada.</span><span class="sxs-lookup"><span data-stu-id="3c988-501">Memory pressure was increased.</span></span>|

<span data-ttu-id="3c988-502">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-502">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-503">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-503">Field Name</span></span>|<span data-ttu-id="3c988-504">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-504">Data type</span></span>|<span data-ttu-id="3c988-505">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-505">Description</span></span>|
|----------------|---------------|-----------------|
|`ClrInstanceID`|<span data-ttu-id="3c988-506">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="3c988-506">win:UInt16</span></span>|<span data-ttu-id="3c988-507">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-507">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="decreasememorypressure-event"></a><span data-ttu-id="3c988-508">Evento DecreaseMemoryPressure</span><span class="sxs-lookup"><span data-stu-id="3c988-508">DecreaseMemoryPressure event</span></span>

<span data-ttu-id="3c988-509">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-509">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-510">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-510">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-511">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-511">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-512">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-512">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-513">Informações (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-513">Information (4)</span></span>|

<span data-ttu-id="3c988-514">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-514">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-515">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-515">Event</span></span>|<span data-ttu-id="3c988-516">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-516">Event ID</span></span>|<span data-ttu-id="3c988-517">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-517">Raised when</span></span>|
|----------------|---------------|-----------------|
|`DecreaseMemoryPressure`|<span data-ttu-id="3c988-518">201</span><span class="sxs-lookup"><span data-stu-id="3c988-518">201</span></span>|<span data-ttu-id="3c988-519">A pressão de memória foi reduzida.</span><span class="sxs-lookup"><span data-stu-id="3c988-519">Memory pressure was decreased.</span></span>|

<span data-ttu-id="3c988-520">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-520">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-521">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-521">Field Name</span></span>|<span data-ttu-id="3c988-522">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-522">Data type</span></span>|<span data-ttu-id="3c988-523">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-523">Description</span></span>|
|----------------|---------------|-----------------|
|`BytesFreed`|`win:UInt32`|<span data-ttu-id="3c988-524">Bytes liberados.</span><span class="sxs-lookup"><span data-stu-id="3c988-524">Bytes freed.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="3c988-525">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-525">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcmarkwithtype-event"></a><span data-ttu-id="3c988-526">Evento GCMarkWithType</span><span class="sxs-lookup"><span data-stu-id="3c988-526">GCMarkWithType event</span></span>

<span data-ttu-id="3c988-527">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-527">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-528">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-528">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-529">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-529">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-530">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-530">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-531">Informações (4)</span><span class="sxs-lookup"><span data-stu-id="3c988-531">Information (4)</span></span>|

<span data-ttu-id="3c988-532">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-532">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-533">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-533">Event</span></span>|<span data-ttu-id="3c988-534">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-534">Event ID</span></span>|<span data-ttu-id="3c988-535">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-535">Raised when</span></span>|
|----------------|---------------|-----------------|
|`GCMarkWithType`|<span data-ttu-id="3c988-536">202</span><span class="sxs-lookup"><span data-stu-id="3c988-536">202</span></span>|<span data-ttu-id="3c988-537">Uma raiz GC foi marcada durante A fase de marca do GC.</span><span class="sxs-lookup"><span data-stu-id="3c988-537">A GC root has been marked during GC mark phase.</span></span>|

<span data-ttu-id="3c988-538">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-538">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-539">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-539">Field Name</span></span>|<span data-ttu-id="3c988-540">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-540">Data type</span></span>|<span data-ttu-id="3c988-541">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-541">Description</span></span>|
|----------------|---------------|-----------------|
|`HeapNum`|`win:UInt32`|<span data-ttu-id="3c988-542">O número do heap.</span><span class="sxs-lookup"><span data-stu-id="3c988-542">The heap number.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="3c988-543">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="3c988-543">win:UInt16</span></span>|<span data-ttu-id="3c988-544">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-544">Unique ID for the instance of CoreCLR.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="3c988-545">O tipo de raiz do GC.</span><span class="sxs-lookup"><span data-stu-id="3c988-545">The GC root type.</span></span><br/><br/><span data-ttu-id="3c988-546">`0x0`: Pilha</span><span class="sxs-lookup"><span data-stu-id="3c988-546">`0x0`: Stack</span></span><br/><br/><span data-ttu-id="3c988-547">`0x1`: Finalizador</span><span class="sxs-lookup"><span data-stu-id="3c988-547">`0x1`: Finalizer</span></span><br/><br/><span data-ttu-id="3c988-548">`0x2`: Identificador</span><span class="sxs-lookup"><span data-stu-id="3c988-548">`0x2`: Handle</span></span><br/><br/><span data-ttu-id="3c988-549">`0x3`: Mais antigo</span><span class="sxs-lookup"><span data-stu-id="3c988-549">`0x3`: Older</span></span><br/><br/><span data-ttu-id="3c988-550">`0x4`: Identificador sizedref</span><span class="sxs-lookup"><span data-stu-id="3c988-550">`0x4`: SizedRef</span></span><br/><br/><span data-ttu-id="3c988-551">`0x5`: Estouro</span><span class="sxs-lookup"><span data-stu-id="3c988-551">`0x5`: Overflow</span></span><br/><br/>|
|`Bytes`|`win:UInt64`|<span data-ttu-id="3c988-552">O número de bytes marcados.</span><span class="sxs-lookup"><span data-stu-id="3c988-552">The number of bytes marked.</span></span>|

## <a name="gcjoin_v2-event"></a><span data-ttu-id="3c988-553">GCJoin_V2 evento</span><span class="sxs-lookup"><span data-stu-id="3c988-553">GCJoin_V2 event</span></span>

<span data-ttu-id="3c988-554">A seguinte tabela mostra a palavra-chave e o nível:</span><span class="sxs-lookup"><span data-stu-id="3c988-554">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="3c988-555">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3c988-555">Keyword for raising the event</span></span>|<span data-ttu-id="3c988-556">Level</span><span class="sxs-lookup"><span data-stu-id="3c988-556">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="3c988-557">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="3c988-557">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="3c988-558">Detalhado (5)</span><span class="sxs-lookup"><span data-stu-id="3c988-558">Verbose (5)</span></span>|

<span data-ttu-id="3c988-559">A seguinte tabela mostra as informações do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-559">The following table shows the event information:</span></span>

|<span data-ttu-id="3c988-560">Evento</span><span class="sxs-lookup"><span data-stu-id="3c988-560">Event</span></span>|<span data-ttu-id="3c988-561">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c988-561">Event ID</span></span>|<span data-ttu-id="3c988-562">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3c988-562">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCJoin_V2`|<span data-ttu-id="3c988-563">203</span><span class="sxs-lookup"><span data-stu-id="3c988-563">203</span></span>|<span data-ttu-id="3c988-564">Um thread GC ingressado.</span><span class="sxs-lookup"><span data-stu-id="3c988-564">A GC thread joined.</span></span>|

<span data-ttu-id="3c988-565">A seguinte tabela mostra os dados do evento:</span><span class="sxs-lookup"><span data-stu-id="3c988-565">The following table shows the event data:</span></span>

|<span data-ttu-id="3c988-566">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3c988-566">Field name</span></span>|<span data-ttu-id="3c988-567">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3c988-567">Data type</span></span>|<span data-ttu-id="3c988-568">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c988-568">Description</span></span>|
|----------------|---------------|-----------------|
|`Heap`|`win:UInt32`|<span data-ttu-id="3c988-569">O número do heap</span><span class="sxs-lookup"><span data-stu-id="3c988-569">The heap number</span></span>|
|`JoinTime`|`win:UInt32`|<span data-ttu-id="3c988-570">Indica se este evento é acionado no início de uma junção ou término de uma junção ( `0x0` para o início da junção, `0x1` para término da junção)</span><span class="sxs-lookup"><span data-stu-id="3c988-570">Indicates whether this event is fired at the start of a join or end of a join (`0x0` for join start, `0x1` for join end)</span></span>|
|`JoinType`|`win:UInt32`|<span data-ttu-id="3c988-571">O tipo de junção.</span><span class="sxs-lookup"><span data-stu-id="3c988-571">The join type.</span></span> <br/><br/><span data-ttu-id="3c988-572">`0x0`: Última junção</span><span class="sxs-lookup"><span data-stu-id="3c988-572">`0x0`: Last Join</span></span><br/><br/><span data-ttu-id="3c988-573">`0x1`: Junção</span><span class="sxs-lookup"><span data-stu-id="3c988-573">`0x1`: Join</span></span> <br/><br/><span data-ttu-id="3c988-574">`0x2`: Reiniciar</span><span class="sxs-lookup"><span data-stu-id="3c988-574">`0x2`: Restart</span></span> <br/><br/><span data-ttu-id="3c988-575">`0x3`: Primeira junção inversa</span><span class="sxs-lookup"><span data-stu-id="3c988-575">`0x3`: First Reverse Join</span></span><br/><br/><span data-ttu-id="3c988-576">`0x4`: Junção inversa</span><span class="sxs-lookup"><span data-stu-id="3c988-576">`0x4`: Reverse Join</span></span><br/><br/>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="3c988-577">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3c988-577">Unique ID for the instance of CoreCLR.</span></span>|
