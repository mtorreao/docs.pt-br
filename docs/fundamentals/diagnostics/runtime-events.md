---
title: Eventos de tempo de execução
description: Examine os eventos de diagnóstico emitidos pelo tempo de execução do .NET (CoreCLR) que pode ser usado com ETW, LTTng ou EventPipe.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- runtime events (CoreCLR)
- ETW, EventPipe runtime events (CoreCLR)
ms.openlocfilehash: 33fa7275ce40934ce043b4d0dba5749c37515755
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96585613"
---
# <a name="net-runtime-events"></a><span data-ttu-id="cdddd-103">Eventos de tempo de execução do .NET</span><span class="sxs-lookup"><span data-stu-id="cdddd-103">.NET runtime events</span></span>

<span data-ttu-id="cdddd-104">O tempo de execução do .NET (CoreCLR) emite vários eventos que podem ser usados para diagnosticar problemas com seu aplicativo .NET que podem ser consumidos por meio de vários mecanismos, como, `ETW` `LTTng` e `EventPipe` .</span><span class="sxs-lookup"><span data-stu-id="cdddd-104">The .NET runtime (CoreCLR) emits various events that can be used to diagnose issues with your .NET application that can be consumed via various mechanisms such as `ETW`, `LTTng`, and `EventPipe`.</span></span>

<span data-ttu-id="cdddd-105">Este documento serve como uma referência nos eventos que são acionados pelo tempo de execução do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdddd-105">This document serves as a reference on the events that are fired by .NET Core runtime.</span></span>

<span data-ttu-id="cdddd-106">Para eventos de tempo de execução no .NET Framework, consulte [eventos de ETW do CLR](../../framework/performance/clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="cdddd-106">For runtime events in .NET Framework, see [CLR ETW Events](../../framework/performance/clr-etw-events.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cdddd-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="cdddd-107">In this section</span></span>

<span data-ttu-id="cdddd-108">[Eventos de contenção](runtime-contention-events.md)</span><span class="sxs-lookup"><span data-stu-id="cdddd-108">[Contention Events](runtime-contention-events.md)</span></span>\
<span data-ttu-id="cdddd-109">Esses eventos coletam informações sobre o monitoramento de contenções de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="cdddd-109">These events collect information about monitor lock contentions.</span></span>

<span data-ttu-id="cdddd-110">[Eventos de coleta de lixo](runtime-garbage-collection-events.md)</span><span class="sxs-lookup"><span data-stu-id="cdddd-110">[Garbage Collection Events](runtime-garbage-collection-events.md)</span></span>\
<span data-ttu-id="cdddd-111"> Esses eventos coletam informações referentes à coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="cdddd-111">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="cdddd-112">Eles ajudam no diagnóstico e na depuração, incluindo a determinação de quantas vezes a coleta de lixo foi executada, a quantidade de memória liberada durante a coleta de lixo etc.</span><span class="sxs-lookup"><span data-stu-id="cdddd-112">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, etc.</span></span>

<span data-ttu-id="cdddd-113">[Eventos de exceção](runtime-exception-events.md)</span><span class="sxs-lookup"><span data-stu-id="cdddd-113">[Exception Events](runtime-exception-events.md)</span></span>\
<span data-ttu-id="cdddd-114">Esses eventos de tempo de execução capturam informações sobre exceções que são geradas.</span><span class="sxs-lookup"><span data-stu-id="cdddd-114">These runtime events capture information about exceptions that are thrown.</span></span>

<span data-ttu-id="cdddd-115">[Eventos de interoperabilidade](runtime-interop-events.md)</span><span class="sxs-lookup"><span data-stu-id="cdddd-115">[Interop Events](runtime-interop-events.md)</span></span>\
<span data-ttu-id="cdddd-116">Esses eventos de tempo de execução capturam informações sobre a geração de stubs Common Intermediate Language (CIL).</span><span class="sxs-lookup"><span data-stu-id="cdddd-116">These runtime events capture information about Common Intermediate Language (CIL) stub generation.</span></span>

<span data-ttu-id="cdddd-117">[Eventos do carregador e do fichário](runtime-loader-binder-events.md)</span><span class="sxs-lookup"><span data-stu-id="cdddd-117">[Loader and Binder Events](runtime-loader-binder-events.md)</span></span>\
<span data-ttu-id="cdddd-118">Esses eventos coletam informações relacionadas ao carregamento e ao descarregamento de assemblies e módulos.</span><span class="sxs-lookup"><span data-stu-id="cdddd-118">These events collect information relating to loading and unloading assemblies and modules.</span></span>

<span data-ttu-id="cdddd-119">[Eventos de método](runtime-method-events.md)</span><span class="sxs-lookup"><span data-stu-id="cdddd-119">[Method Events](runtime-method-events.md)</span></span>\
<span data-ttu-id="cdddd-120"> Esses eventos coletam informações que são específicas para métodos.</span><span class="sxs-lookup"><span data-stu-id="cdddd-120">These events collect information that is specific to methods.</span></span> <span data-ttu-id="cdddd-121">A carga desses eventos é necessária para resolução de símbolos.</span><span class="sxs-lookup"><span data-stu-id="cdddd-121">The payload of these events is required for symbol resolution.</span></span> <span data-ttu-id="cdddd-122">Além disso, esses eventos fornecem informações úteis, como o número de vezes que um método foi chamado.</span><span class="sxs-lookup"><span data-stu-id="cdddd-122">In addition, these events provide helpful information such as the number of times a method was called.</span></span>

<span data-ttu-id="cdddd-123">[Eventos de thread](runtime-thread-events.md)</span><span class="sxs-lookup"><span data-stu-id="cdddd-123">[Thread Events](runtime-thread-events.md)</span></span>\
<span data-ttu-id="cdddd-124"> Esses eventos coletam informações sobre a função de trabalho e os threads de E/S.</span><span class="sxs-lookup"><span data-stu-id="cdddd-124">These events collect information about worker and I/O threads.</span></span>

<span data-ttu-id="cdddd-125">[Eventos de tipo](runtime-type-events.md)</span><span class="sxs-lookup"><span data-stu-id="cdddd-125">[Type Events](runtime-type-events.md)</span></span>\
<span data-ttu-id="cdddd-126">Esses eventos coletam informações sobre o sistema de tipos.</span><span class="sxs-lookup"><span data-stu-id="cdddd-126">These events collect information about the type system.</span></span>
