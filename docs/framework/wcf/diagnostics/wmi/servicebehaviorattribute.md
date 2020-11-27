---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: e3716d42d479bcbdfd900b4fd2e335576a71574b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295594"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="53ca0-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="53ca0-102">ServiceBehaviorAttribute</span></span>

<span data-ttu-id="53ca0-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="53ca0-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53ca0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="53ca0-104">Syntax</span></span>  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="53ca0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="53ca0-105">Methods</span></span>  

 <span data-ttu-id="53ca0-106">A classe ServiceBehaviorAttribute não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="53ca0-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="53ca0-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="53ca0-107">Properties</span></span>  

 <span data-ttu-id="53ca0-108">A classe ServiceBehaviorAttribute tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="53ca0-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="53ca0-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="53ca0-109">AutomaticSessionShutdown</span></span>  

 <span data-ttu-id="53ca0-110">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="53ca0-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="53ca0-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-112">Indica se uma sessão será fechada automaticamente quando um cliente fechar uma sessão de saída.</span><span class="sxs-lookup"><span data-stu-id="53ca0-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="53ca0-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="53ca0-113">ConcurrencyMode</span></span>  

 <span data-ttu-id="53ca0-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="53ca0-114">Data type: string</span></span>  
<span data-ttu-id="53ca0-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-116">Indica se um serviço dá suporte a um thread, a vários threads ou a chamadas reentrantes.</span><span class="sxs-lookup"><span data-stu-id="53ca0-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="53ca0-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="53ca0-117">ConfigurationName</span></span>  

 <span data-ttu-id="53ca0-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="53ca0-118">Data type: string</span></span>  
  
 <span data-ttu-id="53ca0-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-120">O nome da configuração do serviço.</span><span class="sxs-lookup"><span data-stu-id="53ca0-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="53ca0-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="53ca0-121">IgnoreExtensionDataObject</span></span>  

 <span data-ttu-id="53ca0-122">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="53ca0-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="53ca0-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-124">Especifica se é para enviar dados de serialização desconhecidos para a conexão.</span><span class="sxs-lookup"><span data-stu-id="53ca0-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="53ca0-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="53ca0-125">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="53ca0-126">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="53ca0-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="53ca0-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-128">Especifica se as informações de exceção gerenciadas devem ser incluídas nos detalhes de falhas de SOAP retornadas aos clientes para fins de depuração.</span><span class="sxs-lookup"><span data-stu-id="53ca0-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="53ca0-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="53ca0-129">InstanceContextMode</span></span>  

 <span data-ttu-id="53ca0-130">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="53ca0-130">Data type: string</span></span>  
  
 <span data-ttu-id="53ca0-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-132">Especifica quando um novo objeto de serviço é criado.</span><span class="sxs-lookup"><span data-stu-id="53ca0-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="53ca0-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="53ca0-133">MaxItemsInObjectGraph</span></span>  

 <span data-ttu-id="53ca0-134">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="53ca0-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="53ca0-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-136">O número máximo de itens permitidos em um objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="53ca0-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="53ca0-137">Nome</span><span class="sxs-lookup"><span data-stu-id="53ca0-137">Name</span></span>  

 <span data-ttu-id="53ca0-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="53ca0-138">Data type: string</span></span>  
  
 <span data-ttu-id="53ca0-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-140">O atributo Name do serviço no WSDL.</span><span class="sxs-lookup"><span data-stu-id="53ca0-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="53ca0-141">Namespace</span><span class="sxs-lookup"><span data-stu-id="53ca0-141">Namespace</span></span>  

 <span data-ttu-id="53ca0-142">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="53ca0-142">Data type: string</span></span>  
  
 <span data-ttu-id="53ca0-143">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-144">O namespace de destino do serviço no WSDL.</span><span class="sxs-lookup"><span data-stu-id="53ca0-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="53ca0-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="53ca0-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  

 <span data-ttu-id="53ca0-146">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="53ca0-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="53ca0-147">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-148">Especifica se o objeto de serviço é reciclado quando a transação atual é concluída.</span><span class="sxs-lookup"><span data-stu-id="53ca0-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="53ca0-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="53ca0-149">TransactionAutoCompleteOnSessionClose</span></span>  

 <span data-ttu-id="53ca0-150">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="53ca0-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="53ca0-151">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-152">Especifica se as transações pendentes são concluídas quando a sessão atual é fechada.</span><span class="sxs-lookup"><span data-stu-id="53ca0-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="53ca0-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="53ca0-153">TransactionIsolationLevel</span></span>  

 <span data-ttu-id="53ca0-154">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="53ca0-154">Data type: string</span></span>  
  
 <span data-ttu-id="53ca0-155">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-156">Especifica o nível de isolamento da transação.</span><span class="sxs-lookup"><span data-stu-id="53ca0-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="53ca0-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="53ca0-157">TransactionTimeout</span></span>  

 <span data-ttu-id="53ca0-158">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="53ca0-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="53ca0-159">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-160">O período no qual uma transação deve ser concluída.</span><span class="sxs-lookup"><span data-stu-id="53ca0-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="53ca0-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="53ca0-161">UseSynchronizationContext</span></span>  

 <span data-ttu-id="53ca0-162">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="53ca0-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="53ca0-163">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-164">Especifica se o contexto de sincronização atual deve ser usado para escolher a execução do thread.</span><span class="sxs-lookup"><span data-stu-id="53ca0-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="53ca0-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="53ca0-165">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="53ca0-166">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="53ca0-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="53ca0-167">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="53ca0-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53ca0-168">Especifica se o sistema ou o aplicativo impõe o processamento de cabeçalho MustUnderstand SOAP.</span><span class="sxs-lookup"><span data-stu-id="53ca0-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53ca0-169">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53ca0-169">Requirements</span></span>  
  
|<span data-ttu-id="53ca0-170">MOF</span><span class="sxs-lookup"><span data-stu-id="53ca0-170">MOF</span></span>|<span data-ttu-id="53ca0-171">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="53ca0-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="53ca0-172">Namespace</span><span class="sxs-lookup"><span data-stu-id="53ca0-172">Namespace</span></span>|<span data-ttu-id="53ca0-173">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="53ca0-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53ca0-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="53ca0-174">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
