---
title: Eventos de tempo de execução do ThreadPool
description: Consulte eventos de pool de threads de tempo de execução do .NET que coletam informações de diagnóstico sobre pool de threads no .NET Core Eventos de pool de threads são eventos de pool de threads de trabalho ou eventos de pool de threads de e/s
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- ThreadPool events (CoreCLR)
- ETW, thread pool events (CoreCLR)
ms.openlocfilehash: cdd6041c5842d4922c60e33daf6db366f7d35327
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96585637"
---
# <a name="net-runtime-thread-pool-events"></a><span data-ttu-id="4044e-104">Eventos do pool de threads de tempo de execução .NET</span><span class="sxs-lookup"><span data-stu-id="4044e-104">.NET runtime thread pool events</span></span>

<span data-ttu-id="4044e-105">Esses eventos coletam informações sobre threads de e/s de trabalho no ThreadPool.</span><span class="sxs-lookup"><span data-stu-id="4044e-105">These events collect information about worker and I/O threads in the threadpool.</span></span> <span data-ttu-id="4044e-106">Para obter mais informações sobre como usar esses eventos para fins de diagnóstico, consulte [log e rastreamento de aplicativos .net](../../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="4044e-106">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="iothreadcreate_v1-event"></a><span data-ttu-id="4044e-107">IOThreadCreate_V1 evento</span><span class="sxs-lookup"><span data-stu-id="4044e-107">IOThreadCreate_V1 event</span></span>

 <span data-ttu-id="4044e-108">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-108">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-109">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-109">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-110">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-110">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-111">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-111">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-112">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-112">Informational (4)</span></span>|

 <span data-ttu-id="4044e-113">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-113">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-114">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-114">Event</span></span>|<span data-ttu-id="4044e-115">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-115">Event ID</span></span>|<span data-ttu-id="4044e-116">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="4044e-116">Raised when</span></span>|
|-----------------------------------|-----------|
|`IOThreadCreate_V1`|<span data-ttu-id="4044e-117">44</span><span class="sxs-lookup"><span data-stu-id="4044e-117">44</span></span>|<span data-ttu-id="4044e-118">Um thread de E/S é criado no pool de threads.</span><span class="sxs-lookup"><span data-stu-id="4044e-118">An I/O thread is created in the thread pool.</span></span>|

 <span data-ttu-id="4044e-119">A tabela a seguir mostra os dados do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-119">The following table shows the event data.</span></span>

|<span data-ttu-id="4044e-120">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-120">Field name</span></span>|<span data-ttu-id="4044e-121">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-121">Data type</span></span>|<span data-ttu-id="4044e-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-122">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="4044e-123">Número de threads de E/S, incluindo o thread recém-criado.</span><span class="sxs-lookup"><span data-stu-id="4044e-123">Number of I/O threads, including the newly created thread.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="4044e-124">Número de threads de trabalho desativados.</span><span class="sxs-lookup"><span data-stu-id="4044e-124">Number of retired worker threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-125">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-125">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadterminate_v1-event"></a><span data-ttu-id="4044e-126">IOThreadTerminate_V1 evento</span><span class="sxs-lookup"><span data-stu-id="4044e-126">IOThreadTerminate_V1 event</span></span>

 <span data-ttu-id="4044e-127">A tabela a seguir mostra a palavra-chave e o nível</span><span class="sxs-lookup"><span data-stu-id="4044e-127">The following table shows the keyword and level</span></span>

|<span data-ttu-id="4044e-128">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-128">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-129">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-129">Level</span></span>
|-----------------------------------|-----------
|<span data-ttu-id="4044e-130">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-130">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-131">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-131">Informational (4)</span></span>

 <span data-ttu-id="4044e-132">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-132">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-133">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-133">Event</span></span>|<span data-ttu-id="4044e-134">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-134">Event ID</span></span>|<span data-ttu-id="4044e-135">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="4044e-135">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadTerminate`|<span data-ttu-id="4044e-136">45</span><span class="sxs-lookup"><span data-stu-id="4044e-136">45</span></span>|<span data-ttu-id="4044e-137">Um thread de e/s é encerrado no pool de threads.</span><span class="sxs-lookup"><span data-stu-id="4044e-137">An I/O thread is terminated in the thread pool.</span></span>|

 <span data-ttu-id="4044e-138">A tabela a seguir mostra os dados do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-138">The following table shows the event data.</span></span>

|<span data-ttu-id="4044e-139">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-139">Field name</span></span>|<span data-ttu-id="4044e-140">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-140">Data type</span></span>|<span data-ttu-id="4044e-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-141">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="4044e-142">Número de threads de E/S restantes no pool de threads.</span><span class="sxs-lookup"><span data-stu-id="4044e-142">Number of I/O threads remaining in the thread pool.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="4044e-143">Número de threads de E/S desativados.</span><span class="sxs-lookup"><span data-stu-id="4044e-143">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-144">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadretire_v1-event"></a><span data-ttu-id="4044e-145">IOThreadRetire_V1 evento</span><span class="sxs-lookup"><span data-stu-id="4044e-145">IOThreadRetire_V1 event</span></span>

 <span data-ttu-id="4044e-146">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-146">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-147">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-147">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-148">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-148">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-149">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-149">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-150">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-150">Informational (4)</span></span>|

 <span data-ttu-id="4044e-151">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-151">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-152">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-152">Event</span></span>|<span data-ttu-id="4044e-153">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-153">Event ID</span></span>|<span data-ttu-id="4044e-154">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="4044e-154">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadRetire_V1`|<span data-ttu-id="4044e-155">46</span><span class="sxs-lookup"><span data-stu-id="4044e-155">46</span></span>|<span data-ttu-id="4044e-156">Um thread de E/S se torna um candidato para desativação.</span><span class="sxs-lookup"><span data-stu-id="4044e-156">An I/O thread becomes a retirement candidate.</span></span>|

 <span data-ttu-id="4044e-157">A tabela a seguir mostra os dados do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-157">The following table shows the event data.</span></span>

|<span data-ttu-id="4044e-158">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-158">Field name</span></span>|<span data-ttu-id="4044e-159">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-159">Data type</span></span>|<span data-ttu-id="4044e-160">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-160">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="4044e-161">Número de threads de E/S restantes no pool de threads.</span><span class="sxs-lookup"><span data-stu-id="4044e-161">Number of I/O threads remaining in the thread pool.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="4044e-162">Número de threads de E/S desativados.</span><span class="sxs-lookup"><span data-stu-id="4044e-162">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-163">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-163">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadunretire_v1-event"></a><span data-ttu-id="4044e-164">IOThreadUnretire_V1 evento</span><span class="sxs-lookup"><span data-stu-id="4044e-164">IOThreadUnretire_V1 event</span></span>

 <span data-ttu-id="4044e-165">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-165">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-166">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-166">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-167">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-167">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-168">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-168">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-169">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-169">Informational (4)</span></span>|

 <span data-ttu-id="4044e-170">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-170">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-171">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-171">Event</span></span>|<span data-ttu-id="4044e-172">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-172">Event ID</span></span>|<span data-ttu-id="4044e-173">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="4044e-173">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadUnretire_V1`|<span data-ttu-id="4044e-174">47</span><span class="sxs-lookup"><span data-stu-id="4044e-174">47</span></span>|<span data-ttu-id="4044e-175">Um thread de E/S é ativado novamente devido à E/S que chega em um período de espera depois que o thread se torna um candidato para desativação.</span><span class="sxs-lookup"><span data-stu-id="4044e-175">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|

 <span data-ttu-id="4044e-176">A tabela a seguir mostra os dados do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-176">The following table shows the event data.</span></span>

|<span data-ttu-id="4044e-177">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-177">Field name</span></span>|<span data-ttu-id="4044e-178">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-178">Data type</span></span>|<span data-ttu-id="4044e-179">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-179">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="4044e-180">Número de threads de E/S no pool de threads, incluindo esse.</span><span class="sxs-lookup"><span data-stu-id="4044e-180">Number of I/O threads in the thread pool, including this one.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="4044e-181">Número de threads de E/S desativados.</span><span class="sxs-lookup"><span data-stu-id="4044e-181">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`Win:UInt16`|<span data-ttu-id="4044e-182">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-182">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadstart-event"></a><span data-ttu-id="4044e-183">Evento ThreadPoolWorkerThreadStart</span><span class="sxs-lookup"><span data-stu-id="4044e-183">ThreadPoolWorkerThreadStart event</span></span>

|<span data-ttu-id="4044e-184">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-184">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-185">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-185">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="4044e-186">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-186">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-187">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-187">Informational (4)</span></span>|

|<span data-ttu-id="4044e-188">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-188">Event</span></span>|<span data-ttu-id="4044e-189">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-189">Event ID</span></span>|<span data-ttu-id="4044e-190">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-190">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="4044e-191">50</span><span class="sxs-lookup"><span data-stu-id="4044e-191">50</span></span>|<span data-ttu-id="4044e-192">Um thread de trabalho é criado.</span><span class="sxs-lookup"><span data-stu-id="4044e-192">A worker thread is created.</span></span>|

|<span data-ttu-id="4044e-193">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-193">Field name</span></span>|<span data-ttu-id="4044e-194">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-194">Data type</span></span>|<span data-ttu-id="4044e-195">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-195">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-196">Número de threads de trabalho disponíveis para processar o trabalho, incluindo aqueles que já estão processando o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4044e-196">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-197">Número de threads de trabalho que não estão disponíveis para processar o trabalho, mas que estão sendo mantidos em reserva, caso mais threads sejam necessários posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4044e-197">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-198">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-198">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadstop-event"></a><span data-ttu-id="4044e-199">Evento ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="4044e-199">ThreadPoolWorkerThreadStop event</span></span>

|<span data-ttu-id="4044e-200">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-200">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-201">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-201">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="4044e-202">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-202">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-203">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-203">Informational (4)</span></span>|

|<span data-ttu-id="4044e-204">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-204">Event</span></span>|<span data-ttu-id="4044e-205">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-205">Event ID</span></span>|<span data-ttu-id="4044e-206">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-206">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="4044e-207">51</span><span class="sxs-lookup"><span data-stu-id="4044e-207">51</span></span>|<span data-ttu-id="4044e-208">Um thread de trabalho é interrompido.</span><span class="sxs-lookup"><span data-stu-id="4044e-208">A worker thread is stopped.</span></span>|

|<span data-ttu-id="4044e-209">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-209">Field name</span></span>|<span data-ttu-id="4044e-210">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-210">Data type</span></span>|<span data-ttu-id="4044e-211">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-211">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-212">Número de threads de trabalho disponíveis para processar o trabalho, incluindo aqueles que já estão processando o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4044e-212">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-213">Número de threads de trabalho que não estão disponíveis para processar o trabalho, mas que estão sendo mantidos em reserva, caso mais threads sejam necessários posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4044e-213">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-214">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-214">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadwait-event"></a><span data-ttu-id="4044e-215">Evento ThreadPoolWorkerThreadWait</span><span class="sxs-lookup"><span data-stu-id="4044e-215">ThreadPoolWorkerThreadWait event</span></span>

|<span data-ttu-id="4044e-216">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-216">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-217">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-217">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="4044e-218">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-218">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-219">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-219">Informational (4)</span></span>|

|<span data-ttu-id="4044e-220">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-220">Event</span></span>|<span data-ttu-id="4044e-221">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-221">Event ID</span></span>|<span data-ttu-id="4044e-222">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-222">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadWait`|<span data-ttu-id="4044e-223">57</span><span class="sxs-lookup"><span data-stu-id="4044e-223">57</span></span>|<span data-ttu-id="4044e-224">Um thread de trabalho começa a aguardar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4044e-224">A worker thread starts waiting for work.</span></span>|

|<span data-ttu-id="4044e-225">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-225">Field name</span></span>|<span data-ttu-id="4044e-226">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-226">Data type</span></span>|<span data-ttu-id="4044e-227">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-227">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-228">Número de threads de trabalho disponíveis para processar o trabalho, incluindo aqueles que já estão processando o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4044e-228">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-229">Número de threads de trabalho que não estão disponíveis para processar o trabalho, mas que estão sendo mantidos em reserva, caso mais threads sejam necessários posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4044e-229">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-230">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-230">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadretirementstart-event"></a><span data-ttu-id="4044e-231">Evento ThreadPoolWorkerThreadRetirementStart</span><span class="sxs-lookup"><span data-stu-id="4044e-231">ThreadPoolWorkerThreadRetirementStart event</span></span>

|<span data-ttu-id="4044e-232">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-232">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-233">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-233">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="4044e-234">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-234">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-235">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-235">Informational (4)</span></span>|

|<span data-ttu-id="4044e-236">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-236">Event</span></span>|<span data-ttu-id="4044e-237">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-237">Event ID</span></span>|<span data-ttu-id="4044e-238">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-238">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="4044e-239">52</span><span class="sxs-lookup"><span data-stu-id="4044e-239">52</span></span>|<span data-ttu-id="4044e-240">Um thread de trabalho é desativado.</span><span class="sxs-lookup"><span data-stu-id="4044e-240">A worker thread retires.</span></span>|

|<span data-ttu-id="4044e-241">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-241">Field name</span></span>|<span data-ttu-id="4044e-242">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-242">Data type</span></span>|<span data-ttu-id="4044e-243">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-243">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-244">Número de threads de trabalho disponíveis para processar o trabalho, incluindo aqueles que já estão processando o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4044e-244">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-245">Número de threads de trabalho que não estão disponíveis para processar o trabalho, mas que estão sendo mantidos em reserva, caso mais threads sejam necessários posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4044e-245">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-246">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadretirementstop-event"></a><span data-ttu-id="4044e-247">Evento ThreadPoolWorkerThreadRetirementStop</span><span class="sxs-lookup"><span data-stu-id="4044e-247">ThreadPoolWorkerThreadRetirementStop event</span></span>

|<span data-ttu-id="4044e-248">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-248">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-249">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-249">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="4044e-250">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-250">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-251">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-251">Informational (4)</span></span>|

|<span data-ttu-id="4044e-252">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-252">Event</span></span>|<span data-ttu-id="4044e-253">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-253">Event ID</span></span>|<span data-ttu-id="4044e-254">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-254">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="4044e-255">53</span><span class="sxs-lookup"><span data-stu-id="4044e-255">53</span></span>|<span data-ttu-id="4044e-256">Um thread de trabalho desativado fica ativo novamente.</span><span class="sxs-lookup"><span data-stu-id="4044e-256">A retired worker thread becomes active again.</span></span>|

|<span data-ttu-id="4044e-257">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-257">Field name</span></span>|<span data-ttu-id="4044e-258">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-258">Data type</span></span>|<span data-ttu-id="4044e-259">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-259">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-260">Número de threads de trabalho disponíveis para processar o trabalho, incluindo aqueles que já estão processando o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4044e-260">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-261">Número de threads de trabalho que não estão disponíveis para processar o trabalho, mas que estão sendo mantidos em reserva, caso mais threads sejam necessários posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4044e-261">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-262">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-262">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentsample-event"></a><span data-ttu-id="4044e-263">Evento ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="4044e-263">ThreadPoolWorkerThreadAdjustmentSample event</span></span>

 <span data-ttu-id="4044e-264">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-264">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-265">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-265">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-266">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-266">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-267">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-267">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-268">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-268">Informational (4)</span></span>|

 <span data-ttu-id="4044e-269">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-269">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-270">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-270">Event</span></span>|<span data-ttu-id="4044e-271">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-271">Event ID</span></span>|<span data-ttu-id="4044e-272">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-272">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="4044e-273">54</span><span class="sxs-lookup"><span data-stu-id="4044e-273">54</span></span>|<span data-ttu-id="4044e-274">Refere-se à coleta de informações para uma amostra; ou seja, uma medida da taxa de transferência com determinado nível de simultaneidade, em um instante.</span><span class="sxs-lookup"><span data-stu-id="4044e-274">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|

 <span data-ttu-id="4044e-275">A tabela a seguir mostra os dados do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-275">The following table shows the event data.</span></span>

|<span data-ttu-id="4044e-276">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-276">Field name</span></span>|<span data-ttu-id="4044e-277">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-277">Data type</span></span>|<span data-ttu-id="4044e-278">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-278">Description</span></span>|
|----------------|---------------|-----------------|
|`Throughput`|`win:Double`|<span data-ttu-id="4044e-279">Número de conclusões por unidade de tempo.</span><span class="sxs-lookup"><span data-stu-id="4044e-279">Number of completions per unit of time.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-280">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-280">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentadjustment-event"></a><span data-ttu-id="4044e-281">Evento ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="4044e-281">ThreadPoolWorkerThreadAdjustmentAdjustment event</span></span>

 <span data-ttu-id="4044e-282">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-282">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-283">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-283">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-284">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-284">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-285">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-285">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-286">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-286">Informational (4)</span></span>|

 <span data-ttu-id="4044e-287">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-287">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-288">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-288">Event</span></span>|<span data-ttu-id="4044e-289">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-289">Event ID</span></span>|<span data-ttu-id="4044e-290">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-290">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="4044e-291">55</span><span class="sxs-lookup"><span data-stu-id="4044e-291">55</span></span>|<span data-ttu-id="4044e-292">Registra uma alteração no controle, quando o algoritmo de injeção de threads (escalada) determina se uma alteração no nível de simultaneidade está em vigor.</span><span class="sxs-lookup"><span data-stu-id="4044e-292">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|

 <span data-ttu-id="4044e-293">A tabela a seguir mostra os dados do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-293">The following table shows the event data.</span></span>

|<span data-ttu-id="4044e-294">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-294">Field name</span></span>|<span data-ttu-id="4044e-295">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-295">Data type</span></span>|<span data-ttu-id="4044e-296">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-296">Description</span></span>|
|----------------|---------------|-----------------|
|`AverageThroughput`|`win:Double`|<span data-ttu-id="4044e-297">Taxa de transferência média de uma amostra de medidas.</span><span class="sxs-lookup"><span data-stu-id="4044e-297">Average throughput of a sample of measurements.</span></span>|
|`NewWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="4044e-298">Novo número de threads de trabalho ativos.</span><span class="sxs-lookup"><span data-stu-id="4044e-298">New number of active worker threads.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="4044e-299">Motivo do ajuste.</span><span class="sxs-lookup"><span data-stu-id="4044e-299">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="4044e-300">`0x0` Aquecimento.</span><span class="sxs-lookup"><span data-stu-id="4044e-300">`0x0` - Warmup.</span></span><br /><br /> <span data-ttu-id="4044e-301">`0x1` Inicializando.</span><span class="sxs-lookup"><span data-stu-id="4044e-301">`0x1` - Initializing.</span></span><br /><br /> <span data-ttu-id="4044e-302">`0x2` -Movimentação aleatória.</span><span class="sxs-lookup"><span data-stu-id="4044e-302">`0x2` - Random move.</span></span><br /><br /> <span data-ttu-id="4044e-303">`0x3` -Movimentação de escalada.</span><span class="sxs-lookup"><span data-stu-id="4044e-303">`0x3` - Climbing move.</span></span><br /><br /> <span data-ttu-id="4044e-304">`0x4` -Ponto de alteração.</span><span class="sxs-lookup"><span data-stu-id="4044e-304">`0x4` - Change point.</span></span><br /><br /> <span data-ttu-id="4044e-305">`0x5` Estabiliza.</span><span class="sxs-lookup"><span data-stu-id="4044e-305">`0x5` - Stabilizing.</span></span><br /><br /> <span data-ttu-id="4044e-306">`0x6` Priva.</span><span class="sxs-lookup"><span data-stu-id="4044e-306">`0x6` - Starvation.</span></span><br /><br /> <span data-ttu-id="4044e-307">`0x7` -O thread atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="4044e-307">`0x7` - Thread timed out.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-308">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-308">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentstats-event"></a><span data-ttu-id="4044e-309">Evento ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="4044e-309">ThreadPoolWorkerThreadAdjustmentStats event</span></span>

 <span data-ttu-id="4044e-310">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-310">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-311">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-311">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-312">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-312">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-313">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-313">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-314">Detalhado (5)</span><span class="sxs-lookup"><span data-stu-id="4044e-314">Verbose (5)</span></span>

 <span data-ttu-id="4044e-315">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-315">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-316">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-316">Event</span></span>|<span data-ttu-id="4044e-317">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-317">Event ID</span></span>|<span data-ttu-id="4044e-318">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-318">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="4044e-319">56</span><span class="sxs-lookup"><span data-stu-id="4044e-319">56</span></span>|<span data-ttu-id="4044e-320">Coleta de dados no pool de threads.</span><span class="sxs-lookup"><span data-stu-id="4044e-320">Gathers data on the thread pool.</span></span>|

 <span data-ttu-id="4044e-321">A tabela a seguir mostra os dados de evento</span><span class="sxs-lookup"><span data-stu-id="4044e-321">The following table shows the event data</span></span>

|<span data-ttu-id="4044e-322">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-322">Field name</span></span>|<span data-ttu-id="4044e-323">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-323">Data type</span></span>|<span data-ttu-id="4044e-324">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-324">Description</span></span>|
|----------------|---------------|-----------------|
|`Duration`|`win:Double`|<span data-ttu-id="4044e-325">Tempo, em segundos, durante o qual essas estatísticas foram coletadas.</span><span class="sxs-lookup"><span data-stu-id="4044e-325">Amount of time, in seconds, during which these statistics were collected.</span></span>|
|`Throughput`|`win:Double`|<span data-ttu-id="4044e-326">Número médio de conclusões por segundo durante esse intervalo.</span><span class="sxs-lookup"><span data-stu-id="4044e-326">Average number of completions per second during this interval.</span></span>|
|`ThreadWave`|`win:Double`|<span data-ttu-id="4044e-327">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-327">Reserved for internal use.</span></span>|
|`ThroughputWave`|`win:Double`|<span data-ttu-id="4044e-328">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-328">Reserved for internal use.</span></span>|
|`ThroughputErrorEstimate`|`win:Double`|<span data-ttu-id="4044e-329">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-329">Reserved for internal use.</span></span>|
|`AverageThroughputErrorEstimate`|`win:Double`|<span data-ttu-id="4044e-330">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-330">Reserved for internal use.</span></span>|
|`ThroughputRatio`|`win:Double`|<span data-ttu-id="4044e-331">A melhoria relativa na taxa de transferência causada por variações na contagem de threads de trabalho ativos durante esse intervalo.</span><span class="sxs-lookup"><span data-stu-id="4044e-331">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|
|`Confidence`|`win:Double`|<span data-ttu-id="4044e-332">Uma medida da validade do campo ThroughputRatio.</span><span class="sxs-lookup"><span data-stu-id="4044e-332">A measure of the validity of the ThroughputRatio field.</span></span>|
|`NewcontrolSetting`|`win:Double`|<span data-ttu-id="4044e-333">O número de threads de trabalho ativos que servirão como a linha de base para variações futuras na contagem de threads ativos.</span><span class="sxs-lookup"><span data-stu-id="4044e-333">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|
|`NewThreadWaveMagnitude`|`win:UInt16`|<span data-ttu-id="4044e-334">A magnitude das variações futuras na contagem de threads ativos.</span><span class="sxs-lookup"><span data-stu-id="4044e-334">The magnitude of future variations in active thread count.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-335">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-335">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolenqueue-event"></a><span data-ttu-id="4044e-336">Evento ThreadPoolEnqueue</span><span class="sxs-lookup"><span data-stu-id="4044e-336">ThreadPoolEnqueue event</span></span>

 <span data-ttu-id="4044e-337">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-337">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-338">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-338">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-339">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-339">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-340">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-340">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-341">Detalhado (5)</span><span class="sxs-lookup"><span data-stu-id="4044e-341">Verbose (5)</span></span>

 <span data-ttu-id="4044e-342">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-342">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-343">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-343">Event</span></span>|<span data-ttu-id="4044e-344">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-344">Event ID</span></span>|<span data-ttu-id="4044e-345">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-345">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolEnqueue`|<span data-ttu-id="4044e-346">61</span><span class="sxs-lookup"><span data-stu-id="4044e-346">61</span></span>|<span data-ttu-id="4044e-347">Um item de trabalho foi enfileirado na fila do pool de threads.</span><span class="sxs-lookup"><span data-stu-id="4044e-347">A work item was enqueued in the thread pool queue.</span></span>|

 <span data-ttu-id="4044e-348">A tabela a seguir mostra os dados de evento</span><span class="sxs-lookup"><span data-stu-id="4044e-348">The following table shows the event data</span></span>

|<span data-ttu-id="4044e-349">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-349">Field name</span></span>|<span data-ttu-id="4044e-350">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-350">Data type</span></span>|<span data-ttu-id="4044e-351">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-351">Description</span></span>|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|<span data-ttu-id="4044e-352">Ponteiro para a solicitação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4044e-352">Pointer to the work request.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-353">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-353">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooldequeue-event"></a><span data-ttu-id="4044e-354">Evento ThreadPoolDequeue</span><span class="sxs-lookup"><span data-stu-id="4044e-354">ThreadPoolDequeue event</span></span>

 <span data-ttu-id="4044e-355">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-355">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-356">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-356">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-357">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-357">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-358">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-358">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-359">Detalhado (5)</span><span class="sxs-lookup"><span data-stu-id="4044e-359">Verbose (5)</span></span>

 <span data-ttu-id="4044e-360">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-360">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-361">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-361">Event</span></span>|<span data-ttu-id="4044e-362">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-362">Event ID</span></span>|<span data-ttu-id="4044e-363">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-363">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolDequeue`|<span data-ttu-id="4044e-364">62</span><span class="sxs-lookup"><span data-stu-id="4044e-364">62</span></span>|<span data-ttu-id="4044e-365">Um item de trabalho foi removido da fila da fila do pool de threads.</span><span class="sxs-lookup"><span data-stu-id="4044e-365">A work item was dequeued from the thread pool queue.</span></span>|

 <span data-ttu-id="4044e-366">A tabela a seguir mostra os dados de evento</span><span class="sxs-lookup"><span data-stu-id="4044e-366">The following table shows the event data</span></span>

|<span data-ttu-id="4044e-367">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-367">Field name</span></span>|<span data-ttu-id="4044e-368">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-368">Data type</span></span>|<span data-ttu-id="4044e-369">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-369">Description</span></span>|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|<span data-ttu-id="4044e-370">Ponteiro para a solicitação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4044e-370">Pointer to the work request.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-371">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-371">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpoolioenqueue-event"></a><span data-ttu-id="4044e-372">Evento ThreadPoolIOEnqueue</span><span class="sxs-lookup"><span data-stu-id="4044e-372">ThreadPoolIOEnqueue event</span></span>

 <span data-ttu-id="4044e-373">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-373">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-374">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-374">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-375">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-375">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-376">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-376">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-377">Detalhado (5)</span><span class="sxs-lookup"><span data-stu-id="4044e-377">Verbose (5)</span></span>

 <span data-ttu-id="4044e-378">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-378">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-379">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-379">Event</span></span>|<span data-ttu-id="4044e-380">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-380">Event ID</span></span>|<span data-ttu-id="4044e-381">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-381">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIOEnqueue`|<span data-ttu-id="4044e-382">63</span><span class="sxs-lookup"><span data-stu-id="4044e-382">63</span></span>|<span data-ttu-id="4044e-383">Um thread enfileira uma notificação de conclusão de e/s depois que ocorre uma conclusão de e/s assíncrona.</span><span class="sxs-lookup"><span data-stu-id="4044e-383">A thread enqueues an IO completion notification after an async IO completion occurs.</span></span>|

 <span data-ttu-id="4044e-384">A tabela a seguir mostra os dados de evento</span><span class="sxs-lookup"><span data-stu-id="4044e-384">The following table shows the event data</span></span>

|<span data-ttu-id="4044e-385">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-385">Field name</span></span>|<span data-ttu-id="4044e-386">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-386">Data type</span></span>|<span data-ttu-id="4044e-387">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-387">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="4044e-388">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-388">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="4044e-389">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-389">Reserved for internal use.</span></span>|
|`MultiDequeues`|`win:Boolean`|<span data-ttu-id="4044e-390">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-390">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-391">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-391">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooliodequeue-event"></a><span data-ttu-id="4044e-392">Evento ThreadPoolIODequeue</span><span class="sxs-lookup"><span data-stu-id="4044e-392">ThreadPoolIODequeue event</span></span>

 <span data-ttu-id="4044e-393">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-393">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-394">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-394">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-395">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-395">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-396">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-396">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-397">Detalhado (5)</span><span class="sxs-lookup"><span data-stu-id="4044e-397">Verbose (5)</span></span>

 <span data-ttu-id="4044e-398">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-398">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-399">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-399">Event</span></span>|<span data-ttu-id="4044e-400">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-400">Event ID</span></span>|<span data-ttu-id="4044e-401">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-401">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIODequeue`|<span data-ttu-id="4044e-402">64</span><span class="sxs-lookup"><span data-stu-id="4044e-402">64</span></span>|<span data-ttu-id="4044e-403">Um thread desenfileira a notificação de conclusão de e/s.</span><span class="sxs-lookup"><span data-stu-id="4044e-403">A thread dequeues the IO completion notification.</span></span>|

 <span data-ttu-id="4044e-404">A tabela a seguir mostra os dados de evento</span><span class="sxs-lookup"><span data-stu-id="4044e-404">The following table shows the event data</span></span>

|<span data-ttu-id="4044e-405">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-405">Field name</span></span>|<span data-ttu-id="4044e-406">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-406">Data type</span></span>|<span data-ttu-id="4044e-407">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-407">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="4044e-408">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-408">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="4044e-409">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-409">Reserved for internal use.</span></span>|
|`MultiDequeues`|`win:Boolean`|<span data-ttu-id="4044e-410">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-410">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-411">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-411">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooliopack-event"></a><span data-ttu-id="4044e-412">Evento ThreadPoolIOPack</span><span class="sxs-lookup"><span data-stu-id="4044e-412">ThreadPoolIOPack event</span></span>

 <span data-ttu-id="4044e-413">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-413">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="4044e-414">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-414">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-415">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-415">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-416">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-416">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-417">Detalhado (5)</span><span class="sxs-lookup"><span data-stu-id="4044e-417">Verbose (5)</span></span>|

 <span data-ttu-id="4044e-418">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-418">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-419">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-419">Event</span></span>|<span data-ttu-id="4044e-420">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-420">Event ID</span></span>|<span data-ttu-id="4044e-421">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-421">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIOPack`|<span data-ttu-id="4044e-422">65</span><span class="sxs-lookup"><span data-stu-id="4044e-422">65</span></span>|<span data-ttu-id="4044e-423">O pacote de e/s sobreposto a ThreadPool é chamado.</span><span class="sxs-lookup"><span data-stu-id="4044e-423">ThreadPool overlapped IO pack is called.</span></span>|

 <span data-ttu-id="4044e-424">A tabela a seguir mostra os dados de evento</span><span class="sxs-lookup"><span data-stu-id="4044e-424">The following table shows the event data</span></span>

|<span data-ttu-id="4044e-425">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-425">Field name</span></span>|<span data-ttu-id="4044e-426">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-426">Data type</span></span>|<span data-ttu-id="4044e-427">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-427">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="4044e-428">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-428">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="4044e-429">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4044e-429">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-430">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-430">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadcreating-event"></a><span data-ttu-id="4044e-431">Evento ThreadCreating</span><span class="sxs-lookup"><span data-stu-id="4044e-431">ThreadCreating event</span></span>

 <span data-ttu-id="4044e-432">A tabela a seguir mostra as palavras-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-432">The following table shows the keywords and level.</span></span>

|<span data-ttu-id="4044e-433">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-433">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-434">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-434">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-435">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-435">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-436">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-436">Informational (4)</span></span>|

 <span data-ttu-id="4044e-437">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-437">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-438">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-438">Event</span></span>|<span data-ttu-id="4044e-439">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-439">Event ID</span></span>|<span data-ttu-id="4044e-440">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-440">Description</span></span>|
|----------------|---------------|-----------------|
|`ThreadCreating`|<span data-ttu-id="4044e-441">70</span><span class="sxs-lookup"><span data-stu-id="4044e-441">70</span></span>|<span data-ttu-id="4044e-442">O thread foi criado.</span><span class="sxs-lookup"><span data-stu-id="4044e-442">Thread has been created.</span></span>|

 <span data-ttu-id="4044e-443">A tabela a seguir mostra os dados do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-443">The following table shows the event data.</span></span>

|<span data-ttu-id="4044e-444">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-444">Field name</span></span>|<span data-ttu-id="4044e-445">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-445">Data type</span></span>|<span data-ttu-id="4044e-446">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-446">Description</span></span>|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|<span data-ttu-id="4044e-447">ID do thread</span><span class="sxs-lookup"><span data-stu-id="4044e-447">Thread ID</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-448">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-448">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadrunning-event"></a><span data-ttu-id="4044e-449">Evento ThreadRunning</span><span class="sxs-lookup"><span data-stu-id="4044e-449">ThreadRunning event</span></span>

 <span data-ttu-id="4044e-450">A tabela a seguir mostra as palavras-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="4044e-450">The following table shows the keywords and level.</span></span>

|<span data-ttu-id="4044e-451">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="4044e-451">Keyword for raising the event</span></span>|<span data-ttu-id="4044e-452">Level</span><span class="sxs-lookup"><span data-stu-id="4044e-452">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4044e-453">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4044e-453">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4044e-454">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4044e-454">Informational (4)</span></span>|

 <span data-ttu-id="4044e-455">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-455">The following table shows the event information.</span></span>

|<span data-ttu-id="4044e-456">Evento</span><span class="sxs-lookup"><span data-stu-id="4044e-456">Event</span></span>|<span data-ttu-id="4044e-457">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4044e-457">Event ID</span></span>|<span data-ttu-id="4044e-458">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-458">Description</span></span>|
|----------------|---------------|-----------------|
|`ThreadRunning`|<span data-ttu-id="4044e-459">71</span><span class="sxs-lookup"><span data-stu-id="4044e-459">71</span></span>|<span data-ttu-id="4044e-460">O thread começou a ser executado.</span><span class="sxs-lookup"><span data-stu-id="4044e-460">Thread has started running.</span></span>|

 <span data-ttu-id="4044e-461">A tabela a seguir mostra os dados do evento.</span><span class="sxs-lookup"><span data-stu-id="4044e-461">The following table shows the event data.</span></span>

|<span data-ttu-id="4044e-462">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="4044e-462">Field name</span></span>|<span data-ttu-id="4044e-463">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4044e-463">Data type</span></span>|<span data-ttu-id="4044e-464">Descrição</span><span class="sxs-lookup"><span data-stu-id="4044e-464">Description</span></span>|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|<span data-ttu-id="4044e-465">ID do thread</span><span class="sxs-lookup"><span data-stu-id="4044e-465">Thread ID</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4044e-466">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4044e-466">Unique ID for the instance of CoreCLR.</span></span>|
