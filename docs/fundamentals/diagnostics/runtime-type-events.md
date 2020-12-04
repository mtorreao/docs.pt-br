---
title: Tipos de eventos de tempo de execução do sistema
description: Consulte eventos de tempo de execução do .NET que coletam informações de diagnóstico específicas para o sistema de tipo .NET, como TypeLoadStart e TypeLoadStop.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- type system events (CoreCLR)
- ETW, EventPipe, LTTng type system events (CoreCLR)
ms.openlocfilehash: 8eee89cddb0098da2cb449a4be21945adac725e3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96585609"
---
# <a name="net-runtime-type-events"></a><span data-ttu-id="fe869-103">Eventos de tipo de tempo de execução .NET</span><span class="sxs-lookup"><span data-stu-id="fe869-103">.NET runtime type events</span></span>

<span data-ttu-id="fe869-104">Esses eventos coletam informações relacionadas aos tipos de carregamento.</span><span class="sxs-lookup"><span data-stu-id="fe869-104">These events collect information relating to loading types.</span></span> <span data-ttu-id="fe869-105">Para obter mais informações sobre como usar esses eventos para fins de diagnóstico, consulte [log e rastreamento de aplicativos .net](../../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="fe869-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="typeloadstart-event"></a><span data-ttu-id="fe869-106">Evento TypeLoadStart</span><span class="sxs-lookup"><span data-stu-id="fe869-106">TypeLoadStart Event</span></span>

|<span data-ttu-id="fe869-107">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="fe869-107">Keyword for raising the event</span></span>|<span data-ttu-id="fe869-108">Evento</span><span class="sxs-lookup"><span data-stu-id="fe869-108">Event</span></span>|<span data-ttu-id="fe869-109">Level</span><span class="sxs-lookup"><span data-stu-id="fe869-109">Level</span></span>|  
|-----------------------------------|-----------|-----------|  
|<span data-ttu-id="fe869-110">`TypeDiagnosticKeyword` (0x8000000000)</span><span class="sxs-lookup"><span data-stu-id="fe869-110">`TypeDiagnosticKeyword` (0x8000000000)</span></span>|<span data-ttu-id="fe869-111">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="fe869-111">Informational (4)</span></span>|  

|<span data-ttu-id="fe869-112">Evento</span><span class="sxs-lookup"><span data-stu-id="fe869-112">Event</span></span>|<span data-ttu-id="fe869-113">ID do evento</span><span class="sxs-lookup"><span data-stu-id="fe869-113">Event ID</span></span>|<span data-ttu-id="fe869-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe869-114">Description</span></span>|  
|-----------|--------------|-----------------|  
|`TypeLoadStart`|<span data-ttu-id="fe869-115">73</span><span class="sxs-lookup"><span data-stu-id="fe869-115">73</span></span>|<span data-ttu-id="fe869-116">Um carregamento de tipo foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="fe869-116">A type load has started.</span></span>|

|<span data-ttu-id="fe869-117">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="fe869-117">Field name</span></span>|<span data-ttu-id="fe869-118">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="fe869-118">Data type</span></span>|<span data-ttu-id="fe869-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe869-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|<span data-ttu-id="fe869-120">ID para a operação de carregamento de tipo.</span><span class="sxs-lookup"><span data-stu-id="fe869-120">ID for the type load operation.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="fe869-121">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="fe869-121">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="typeloadstop-event"></a><span data-ttu-id="fe869-122">Evento TypeLoadStop</span><span class="sxs-lookup"><span data-stu-id="fe869-122">TypeLoadStop Event</span></span>

|<span data-ttu-id="fe869-123">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="fe869-123">Keyword for raising the event</span></span>|<span data-ttu-id="fe869-124">Level</span><span class="sxs-lookup"><span data-stu-id="fe869-124">Level</span></span>|  
|-----------------------------------|-----------|-----------|  
|<span data-ttu-id="fe869-125">`TypeDiagnosticKeyword` (0x8000000000)</span><span class="sxs-lookup"><span data-stu-id="fe869-125">`TypeDiagnosticKeyword` (0x8000000000)</span></span>|<span data-ttu-id="fe869-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="fe869-126">Informational (4)</span></span>|  

|<span data-ttu-id="fe869-127">Evento</span><span class="sxs-lookup"><span data-stu-id="fe869-127">Event</span></span>|<span data-ttu-id="fe869-128">ID do evento</span><span class="sxs-lookup"><span data-stu-id="fe869-128">Event ID</span></span>|<span data-ttu-id="fe869-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe869-129">Description</span></span>|  
|-----------|--------------|-----------------|  
|`TypeLoadStop`|<span data-ttu-id="fe869-130">74</span><span class="sxs-lookup"><span data-stu-id="fe869-130">74</span></span>|<span data-ttu-id="fe869-131">Uma carga de tipo foi concluída.</span><span class="sxs-lookup"><span data-stu-id="fe869-131">A type load is finished.</span></span>|

|<span data-ttu-id="fe869-132">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="fe869-132">Field name</span></span>|<span data-ttu-id="fe869-133">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="fe869-133">Data type</span></span>|<span data-ttu-id="fe869-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe869-134">Description</span></span>|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|<span data-ttu-id="fe869-135">ID para a operação de carregamento de tipo (corresponde à TypeLoadStartID do evento TypeLoadStart correspondente).</span><span class="sxs-lookup"><span data-stu-id="fe869-135">ID for the type load operation (matches the corresponding TypeLoadStart event's TypeLoadStartID).</span></span>|
|`LoadLevel`|`win:UInt16`|<span data-ttu-id="fe869-136">Digite o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="fe869-136">Type load level.</span></span>|
|`TypeID`|`win:UInt64`|<span data-ttu-id="fe869-137">Ponteiro para a alça de tipo.</span><span class="sxs-lookup"><span data-stu-id="fe869-137">Pointer to the type handle.</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="fe869-138">Nome do tipo.</span><span class="sxs-lookup"><span data-stu-id="fe869-138">Name of the type.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="fe869-139">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="fe869-139">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
