---
title: Eventos de tempo de execução de exceção
description: Consulte eventos de tempo de execução do .NET que coletam informações de diagnóstico específicas para exceções e tratamento de exceções.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- exception events (CoreCLR)
- exception handling events (CoreCLR)
- ETW, EventPipe, LTTng exception events (CoreCLR)
ms.openlocfilehash: f4f63c8469f9c734b872ddaec8d1d7f7f0427576
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96585631"
---
# <a name="net-runtime-exception-events"></a><span data-ttu-id="34c4c-103">Eventos de exceção de tempo de execução .NET</span><span class="sxs-lookup"><span data-stu-id="34c4c-103">.NET runtime exception events</span></span>

<span data-ttu-id="34c4c-104">Esses eventos de tempo de execução capturam informações sobre exceções que são geradas.</span><span class="sxs-lookup"><span data-stu-id="34c4c-104">These runtime events capture information about exceptions that are thrown.</span></span> <span data-ttu-id="34c4c-105">Para obter mais informações sobre como usar esses eventos para fins de diagnóstico, consulte [log e rastreamento de aplicativos .net](../../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="34c4c-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="exceptionthrown_v1-event"></a><span data-ttu-id="34c4c-106">ExceptionThrown_V1 evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-106">ExceptionThrown_V1 event</span></span>

|<span data-ttu-id="34c4c-107">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-107">Keyword for raising the event</span></span>|<span data-ttu-id="34c4c-108">Level</span><span class="sxs-lookup"><span data-stu-id="34c4c-108">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="34c4c-109">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="34c4c-109">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="34c4c-110">Erro (1)</span><span class="sxs-lookup"><span data-stu-id="34c4c-110">Error (1)</span></span>|

 <span data-ttu-id="34c4c-111">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="34c4c-111">The following table shows event information.</span></span>

|<span data-ttu-id="34c4c-112">Evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-112">Event</span></span>|<span data-ttu-id="34c4c-113">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-113">Event ID</span></span>|<span data-ttu-id="34c4c-114">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="34c4c-114">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionThrown_V1`|<span data-ttu-id="34c4c-115">80</span><span class="sxs-lookup"><span data-stu-id="34c4c-115">80</span></span>|<span data-ttu-id="34c4c-116">Uma exceção gerenciada é gerada.</span><span class="sxs-lookup"><span data-stu-id="34c4c-116">A managed exception is thrown.</span></span>|

|<span data-ttu-id="34c4c-117">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="34c4c-117">Field name</span></span>|<span data-ttu-id="34c4c-118">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="34c4c-118">Data type</span></span>|<span data-ttu-id="34c4c-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="34c4c-119">Description</span></span>|
|----------------|---------------|-----------------|
|`ExceptionType`|`win:UnicodeString`|<span data-ttu-id="34c4c-120">Tipo da exceção; por exemplo, `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="34c4c-120">Type of the exception; for example, `System.NullReferenceException`.</span></span>|
|`ExceptionMessage`|`win:UnicodeString`|<span data-ttu-id="34c4c-121">A mensagem de exceção real.</span><span class="sxs-lookup"><span data-stu-id="34c4c-121">Actual exception message.</span></span>|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="34c4c-122">Ponteiro de instrução em que ocorreu a exceção.</span><span class="sxs-lookup"><span data-stu-id="34c4c-122">Instruction pointer where exception occurred.</span></span>|
|`ExceptionHR`|`win:UInt32`|<span data-ttu-id="34c4c-123">Exceção [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span><span class="sxs-lookup"><span data-stu-id="34c4c-123">Exception [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|
|`ExceptionFlags`|`win:UInt16`|<span data-ttu-id="34c4c-124">`0x01`: HasInnerException.</span><span class="sxs-lookup"><span data-stu-id="34c4c-124">`0x01`: HasInnerException.</span></span><br /><br /> <span data-ttu-id="34c4c-125">`0x02`: Isaninhaexception.</span><span class="sxs-lookup"><span data-stu-id="34c4c-125">`0x02`: IsNestedException.</span></span><br /><br /> <span data-ttu-id="34c4c-126">`0x04`: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="34c4c-126">`0x04`: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="34c4c-127">`0x08`: IsCorruptedStateException (indica que o estado do processo está corrompido; consulte [tratamento de exceções de estado corrompido](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="34c4c-127">`0x08`: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="34c4c-128">`0x10`: IsCLSCompliant (uma exceção derivada de <xref:System.Exception> é compatível com CLS; caso contrário, não é compatível com CLS).</span><span class="sxs-lookup"><span data-stu-id="34c4c-128">`0x10`: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="34c4c-129">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="34c4c-129">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptioncatchstart-event"></a><span data-ttu-id="34c4c-130">Evento ExceptionCatchStart</span><span class="sxs-lookup"><span data-stu-id="34c4c-130">ExceptionCatchStart event</span></span>

<span data-ttu-id="34c4c-131">Esse evento é emitido quando um manipulador de catch de exceção gerenciada começa.</span><span class="sxs-lookup"><span data-stu-id="34c4c-131">This event is emitted when a managed exception catch handler begins.</span></span>

|<span data-ttu-id="34c4c-132">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-132">Keyword for raising the event</span></span>|<span data-ttu-id="34c4c-133">Level</span><span class="sxs-lookup"><span data-stu-id="34c4c-133">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="34c4c-134">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="34c4c-134">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="34c4c-135">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="34c4c-135">Informational (4)</span></span>|

 <span data-ttu-id="34c4c-136">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="34c4c-136">The following table shows event information.</span></span>

|<span data-ttu-id="34c4c-137">Evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-137">Event</span></span>|<span data-ttu-id="34c4c-138">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-138">Event ID</span></span>|<span data-ttu-id="34c4c-139">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="34c4c-139">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionCatchStart`|<span data-ttu-id="34c4c-140">250</span><span class="sxs-lookup"><span data-stu-id="34c4c-140">250</span></span>|<span data-ttu-id="34c4c-141">Uma exceção gerenciada é tratada pelo tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="34c4c-141">A managed exception is handled by the runtime.</span></span>|

|<span data-ttu-id="34c4c-142">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="34c4c-142">Field name</span></span>|<span data-ttu-id="34c4c-143">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="34c4c-143">Data type</span></span>|<span data-ttu-id="34c4c-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="34c4c-144">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="34c4c-145">Ponteiro de instrução em que ocorreu a exceção.</span><span class="sxs-lookup"><span data-stu-id="34c4c-145">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="34c4c-146">Ponteiro para o descritor de método no método em que ocorreu a exceção.</span><span class="sxs-lookup"><span data-stu-id="34c4c-146">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="34c4c-147">Nome do método em que ocorreu a exceção.</span><span class="sxs-lookup"><span data-stu-id="34c4c-147">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="34c4c-148">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="34c4c-148">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptioncatchstop-event"></a><span data-ttu-id="34c4c-149">Evento ExceptionCatchStop</span><span class="sxs-lookup"><span data-stu-id="34c4c-149">ExceptionCatchStop event</span></span>

<span data-ttu-id="34c4c-150">Esse evento é emitido quando um manipulador de captura de exceção gerenciada termina.</span><span class="sxs-lookup"><span data-stu-id="34c4c-150">This event is emitted when a managed exception catch handler ends.</span></span>

|<span data-ttu-id="34c4c-151">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-151">Keyword for raising the event</span></span>|<span data-ttu-id="34c4c-152">Level</span><span class="sxs-lookup"><span data-stu-id="34c4c-152">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="34c4c-153">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="34c4c-153">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="34c4c-154">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="34c4c-154">Informational (4)</span></span>|

 <span data-ttu-id="34c4c-155">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="34c4c-155">The following table shows event information.</span></span>

|<span data-ttu-id="34c4c-156">Evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-156">Event</span></span>|<span data-ttu-id="34c4c-157">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-157">Event ID</span></span>|<span data-ttu-id="34c4c-158">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="34c4c-158">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionCatchStop`|<span data-ttu-id="34c4c-159">251</span><span class="sxs-lookup"><span data-stu-id="34c4c-159">251</span></span>|<span data-ttu-id="34c4c-160">Um manipulador de captura de exceção gerenciada é feito.</span><span class="sxs-lookup"><span data-stu-id="34c4c-160">A managed exception catch handler is done.</span></span>|

## <a name="exceptionfinallystart-event"></a><span data-ttu-id="34c4c-161">Evento ExceptionFinallyStart</span><span class="sxs-lookup"><span data-stu-id="34c4c-161">ExceptionFinallyStart event</span></span>

<span data-ttu-id="34c4c-162">Esse evento é emitido quando um manipulador de exceção gerenciada finally é iniciado.</span><span class="sxs-lookup"><span data-stu-id="34c4c-162">This event is emitted when a managed exception finally handler begins.</span></span>

|<span data-ttu-id="34c4c-163">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-163">Keyword for raising the event</span></span>|<span data-ttu-id="34c4c-164">Level</span><span class="sxs-lookup"><span data-stu-id="34c4c-164">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="34c4c-165">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="34c4c-165">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="34c4c-166">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="34c4c-166">Informational (4)</span></span>|

 <span data-ttu-id="34c4c-167">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="34c4c-167">The following table shows event information.</span></span>

|<span data-ttu-id="34c4c-168">Evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-168">Event</span></span>|<span data-ttu-id="34c4c-169">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-169">Event ID</span></span>|<span data-ttu-id="34c4c-170">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="34c4c-170">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFinallyStart`|<span data-ttu-id="34c4c-171">252</span><span class="sxs-lookup"><span data-stu-id="34c4c-171">252</span></span>|<span data-ttu-id="34c4c-172">Uma exceção gerenciada é tratada pelo tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="34c4c-172">A managed exception is handled by the runtime.</span></span>|

|<span data-ttu-id="34c4c-173">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="34c4c-173">Field name</span></span>|<span data-ttu-id="34c4c-174">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="34c4c-174">Data type</span></span>|<span data-ttu-id="34c4c-175">Descrição</span><span class="sxs-lookup"><span data-stu-id="34c4c-175">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="34c4c-176">Ponteiro de instrução em que ocorreu a exceção.</span><span class="sxs-lookup"><span data-stu-id="34c4c-176">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="34c4c-177">Ponteiro para o descritor de método no método em que ocorreu a exceção.</span><span class="sxs-lookup"><span data-stu-id="34c4c-177">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="34c4c-178">Nome do método em que ocorreu a exceção.</span><span class="sxs-lookup"><span data-stu-id="34c4c-178">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="34c4c-179">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="34c4c-179">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptionfinallystop-event"></a><span data-ttu-id="34c4c-180">Evento ExceptionFinallyStop</span><span class="sxs-lookup"><span data-stu-id="34c4c-180">ExceptionFinallyStop event</span></span>

<span data-ttu-id="34c4c-181">Esse evento é emitido quando um manipulador de captura de exceção gerenciada termina.</span><span class="sxs-lookup"><span data-stu-id="34c4c-181">This event is emitted when a managed exception catch handler ends.</span></span>

|<span data-ttu-id="34c4c-182">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-182">Keyword for raising the event</span></span>|<span data-ttu-id="34c4c-183">Level</span><span class="sxs-lookup"><span data-stu-id="34c4c-183">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="34c4c-184">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="34c4c-184">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="34c4c-185">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="34c4c-185">Informational (4)</span></span>|

 <span data-ttu-id="34c4c-186">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="34c4c-186">The following table shows event information.</span></span>

|<span data-ttu-id="34c4c-187">Evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-187">Event</span></span>|<span data-ttu-id="34c4c-188">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-188">Event ID</span></span>|<span data-ttu-id="34c4c-189">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="34c4c-189">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFinallyStop`|<span data-ttu-id="34c4c-190">253</span><span class="sxs-lookup"><span data-stu-id="34c4c-190">253</span></span>|<span data-ttu-id="34c4c-191">Um manipulador de exceção gerenciada finally é feito.</span><span class="sxs-lookup"><span data-stu-id="34c4c-191">A managed exception finally handler is done.</span></span>|

## <a name="exceptionfilterstart-event"></a><span data-ttu-id="34c4c-192">Evento ExceptionFilterStart</span><span class="sxs-lookup"><span data-stu-id="34c4c-192">ExceptionFilterStart event</span></span>

<span data-ttu-id="34c4c-193">Esse evento é emitido quando uma filtragem de exceção gerenciada é iniciada.</span><span class="sxs-lookup"><span data-stu-id="34c4c-193">This event is emitted when a managed exception filtering begins.</span></span>

|<span data-ttu-id="34c4c-194">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-194">Keyword for raising the event</span></span>|<span data-ttu-id="34c4c-195">Level</span><span class="sxs-lookup"><span data-stu-id="34c4c-195">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="34c4c-196">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="34c4c-196">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="34c4c-197">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="34c4c-197">Informational (4)</span></span>|

 <span data-ttu-id="34c4c-198">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="34c4c-198">The following table shows event information.</span></span>

|<span data-ttu-id="34c4c-199">Evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-199">Event</span></span>|<span data-ttu-id="34c4c-200">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-200">Event ID</span></span>|<span data-ttu-id="34c4c-201">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="34c4c-201">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFilterStart`|<span data-ttu-id="34c4c-202">254</span><span class="sxs-lookup"><span data-stu-id="34c4c-202">254</span></span>|<span data-ttu-id="34c4c-203">Uma filtragem de exceção gerenciada começa.</span><span class="sxs-lookup"><span data-stu-id="34c4c-203">A managed exception filtering begins.</span></span>|

|<span data-ttu-id="34c4c-204">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="34c4c-204">Field name</span></span>|<span data-ttu-id="34c4c-205">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="34c4c-205">Data type</span></span>|<span data-ttu-id="34c4c-206">Descrição</span><span class="sxs-lookup"><span data-stu-id="34c4c-206">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="34c4c-207">Ponteiro de instrução em que ocorreu a exceção.</span><span class="sxs-lookup"><span data-stu-id="34c4c-207">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="34c4c-208">Ponteiro para o descritor de método no método em que ocorreu a exceção.</span><span class="sxs-lookup"><span data-stu-id="34c4c-208">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="34c4c-209">Nome do método em que ocorreu a exceção.</span><span class="sxs-lookup"><span data-stu-id="34c4c-209">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="34c4c-210">ID exclusiva para a instância do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="34c4c-210">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="exceptionfilterstop-event"></a><span data-ttu-id="34c4c-211">Evento ExceptionFilterStop</span><span class="sxs-lookup"><span data-stu-id="34c4c-211">ExceptionFilterStop event</span></span>

<span data-ttu-id="34c4c-212">Esse evento é emitido quando uma filtragem de exceção gerenciada termina.</span><span class="sxs-lookup"><span data-stu-id="34c4c-212">This event is emitted when a managed exception filtering ends.</span></span>

|<span data-ttu-id="34c4c-213">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-213">Keyword for raising the event</span></span>|<span data-ttu-id="34c4c-214">Level</span><span class="sxs-lookup"><span data-stu-id="34c4c-214">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="34c4c-215">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="34c4c-215">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="34c4c-216">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="34c4c-216">Informational (4)</span></span>|

 <span data-ttu-id="34c4c-217">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="34c4c-217">The following table shows event information.</span></span>

|<span data-ttu-id="34c4c-218">Evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-218">Event</span></span>|<span data-ttu-id="34c4c-219">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-219">Event ID</span></span>|<span data-ttu-id="34c4c-220">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="34c4c-220">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFilteringStart`|<span data-ttu-id="34c4c-221">255</span><span class="sxs-lookup"><span data-stu-id="34c4c-221">255</span></span>|<span data-ttu-id="34c4c-222">Uma filtragem de exceção gerenciada termina.</span><span class="sxs-lookup"><span data-stu-id="34c4c-222">A managed exception filtering ends.</span></span>|

## <a name="exceptionthrownstop-event"></a><span data-ttu-id="34c4c-223">Evento ExceptionThrownStop</span><span class="sxs-lookup"><span data-stu-id="34c4c-223">ExceptionThrownStop event</span></span>

<span data-ttu-id="34c4c-224">Esse evento é emitido quando o tempo de execução é realizado tratando uma exceção gerenciada que foi lançada.</span><span class="sxs-lookup"><span data-stu-id="34c4c-224">This event is emitted when the runtime is done handling a managed exception that was thrown.</span></span>

|<span data-ttu-id="34c4c-225">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-225">Keyword for raising the event</span></span>|<span data-ttu-id="34c4c-226">Level</span><span class="sxs-lookup"><span data-stu-id="34c4c-226">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="34c4c-227">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="34c4c-227">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="34c4c-228">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="34c4c-228">Informational (4)</span></span>|
  
 <span data-ttu-id="34c4c-229">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="34c4c-229">The following table shows event information.</span></span>

|<span data-ttu-id="34c4c-230">Evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-230">Event</span></span>|<span data-ttu-id="34c4c-231">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34c4c-231">Event ID</span></span>|<span data-ttu-id="34c4c-232">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="34c4c-232">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionThrownStop`|<span data-ttu-id="34c4c-233">256</span><span class="sxs-lookup"><span data-stu-id="34c4c-233">256</span></span>|<span data-ttu-id="34c4c-234">Uma filtragem de exceção gerenciada termina.</span><span class="sxs-lookup"><span data-stu-id="34c4c-234">A managed exception filtering ends.</span></span>|
