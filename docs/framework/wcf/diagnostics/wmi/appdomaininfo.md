---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: c5c44f4d8f6d93443802d5e1950c4d850976c5b6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291122"
---
# <a name="appdomaininfo"></a><span data-ttu-id="4fb0e-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="4fb0e-102">AppDomainInfo</span></span>

<span data-ttu-id="4fb0e-103">Informações de domínio do aplicativo</span><span class="sxs-lookup"><span data-stu-id="4fb0e-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fb0e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4fb0e-104">Syntax</span></span>  
  
```csharp
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4fb0e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4fb0e-105">Methods</span></span>  

 <span data-ttu-id="4fb0e-106">A classe AppDomainInfo não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4fb0e-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="4fb0e-107">Properties</span></span>  

 <span data-ttu-id="4fb0e-108">A classe AppDomainInfo tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="4fb0e-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="4fb0e-109">AppDomainid</span><span class="sxs-lookup"><span data-stu-id="4fb0e-109">AppDomainId</span></span>  

 <span data-ttu-id="4fb0e-110">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="4fb0e-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="4fb0e-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4fb0e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fb0e-112">A ID do AppDomain.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="4fb0e-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="4fb0e-113">IsDefault</span></span>  

 <span data-ttu-id="4fb0e-114">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="4fb0e-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fb0e-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4fb0e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fb0e-116">Indica se AppDomain é o AppDomain padrão.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="4fb0e-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="4fb0e-117">LogMalformedMessages</span></span>  

 <span data-ttu-id="4fb0e-118">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="4fb0e-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fb0e-119">Tipo de acesso: Leitura/Gravação</span><span class="sxs-lookup"><span data-stu-id="4fb0e-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="4fb0e-120">Um valor que especifica se as mensagens malformadas são registradas.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="4fb0e-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="4fb0e-121">LogMessagesAtServiceLevel</span></span>  

 <span data-ttu-id="4fb0e-122">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="4fb0e-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fb0e-123">Tipo de acesso: Leitura/Gravação</span><span class="sxs-lookup"><span data-stu-id="4fb0e-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="4fb0e-124">Um valor que especifica se as mensagens são rastreadas no nível de serviço (antes das transformações relacionadas à criptografia e ao transporte).</span><span class="sxs-lookup"><span data-stu-id="4fb0e-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="4fb0e-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="4fb0e-125">LogMessagesAtTransportLevel</span></span>  

 <span data-ttu-id="4fb0e-126">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="4fb0e-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fb0e-127">Tipo de acesso: Leitura/Gravação</span><span class="sxs-lookup"><span data-stu-id="4fb0e-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="4fb0e-128">Um valor que especifica se as mensagens são rastreadas no nível de transporte.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="4fb0e-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="4fb0e-129">MessageLoggingTraceListeners</span></span>  

 <span data-ttu-id="4fb0e-130">Tipo de dados: matriz TraceListener</span><span class="sxs-lookup"><span data-stu-id="4fb0e-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="4fb0e-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4fb0e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fb0e-132">Os ouvintes de rastreamento de coleção que ouvem a origem de rastreamento System. WMI. MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="4fb0e-133">Nome</span><span class="sxs-lookup"><span data-stu-id="4fb0e-133">Name</span></span>  

 <span data-ttu-id="4fb0e-134">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4fb0e-134">Data type: string</span></span>  
  
 <span data-ttu-id="4fb0e-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4fb0e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fb0e-136">O nome do AppDomain.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="4fb0e-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="4fb0e-137">PerformanceCounters</span></span>  

 <span data-ttu-id="4fb0e-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4fb0e-138">Data type: string</span></span>  
  
 <span data-ttu-id="4fb0e-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4fb0e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fb0e-140">O escopo dos contadores de desempenho ativos no AppDomain.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="4fb0e-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="4fb0e-141">ProcessId</span></span>  

 <span data-ttu-id="4fb0e-142">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="4fb0e-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="4fb0e-143">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4fb0e-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fb0e-144">A ID do processo.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="4fb0e-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="4fb0e-145">ServiceConfigPath</span></span>  

 <span data-ttu-id="4fb0e-146">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4fb0e-146">Data type: string</span></span>  
  
 <span data-ttu-id="4fb0e-147">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4fb0e-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fb0e-148">O caminho para a configuração do serviço.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="4fb0e-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="4fb0e-149">TraceLevel</span></span>  

 <span data-ttu-id="4fb0e-150">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4fb0e-150">Data type: string</span></span>  
  
 <span data-ttu-id="4fb0e-151">Tipo de acesso: Leitura/Gravação</span><span class="sxs-lookup"><span data-stu-id="4fb0e-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="4fb0e-152">O nível de rastreamento da origem do rastreamento System. WMI.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="4fb0e-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="4fb0e-153">ServiceModelTraceListeners</span></span>  

 <span data-ttu-id="4fb0e-154">Tipo de dados: matriz TraceListener</span><span class="sxs-lookup"><span data-stu-id="4fb0e-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="4fb0e-155">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4fb0e-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fb0e-156">Uma coleção de ouvintes da origem de rastreamento System. ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fb0e-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fb0e-157">Requirements</span></span>  
  
|<span data-ttu-id="4fb0e-158">MOF</span><span class="sxs-lookup"><span data-stu-id="4fb0e-158">MOF</span></span>|<span data-ttu-id="4fb0e-159">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="4fb0e-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4fb0e-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="4fb0e-160">Namespace</span></span>|<span data-ttu-id="4fb0e-161">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4fb0e-161">Defined in root\ServiceModel</span></span>|
