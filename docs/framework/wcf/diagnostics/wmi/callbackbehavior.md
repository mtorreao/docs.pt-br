---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: cec9005a099247671dbebaacc0b242ca8d7a0144
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269642"
---
# <a name="callbackbehavior"></a><span data-ttu-id="8e539-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="8e539-102">CallbackBehavior</span></span>

<span data-ttu-id="8e539-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="8e539-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e539-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8e539-104">Syntax</span></span>  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8e539-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8e539-105">Methods</span></span>  

 <span data-ttu-id="8e539-106">A classe CallbackBehavior não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="8e539-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8e539-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="8e539-107">Properties</span></span>  

 <span data-ttu-id="8e539-108">A classe CallbackBehavior tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="8e539-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="8e539-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="8e539-109">AutomaticSessionShutdown</span></span>  

 <span data-ttu-id="8e539-110">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="8e539-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="8e539-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8e539-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e539-112">Quando true, a sessão é fechada automaticamente quando um serviço fecha uma sessão duplex.</span><span class="sxs-lookup"><span data-stu-id="8e539-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="8e539-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="8e539-113">ConcurrencyMode</span></span>  

 <span data-ttu-id="8e539-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8e539-114">Data type: string</span></span>  
<span data-ttu-id="8e539-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8e539-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e539-116">Especifica se o serviço dá suporte a um thread, vários threads ou chamadas reentrantes.</span><span class="sxs-lookup"><span data-stu-id="8e539-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="8e539-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="8e539-117">IgnoreExtensionDataObject</span></span>  

 <span data-ttu-id="8e539-118">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="8e539-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="8e539-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8e539-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e539-120">Um valor que especifica se os dados de serialização desconhecidos devem ser enviados para a conexão.</span><span class="sxs-lookup"><span data-stu-id="8e539-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="8e539-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="8e539-121">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="8e539-122">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="8e539-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="8e539-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8e539-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e539-124">Quando habilitado, os detalhes sobre as exceções no retorno de chamada são anexados às falhas retornadas ao serviço.</span><span class="sxs-lookup"><span data-stu-id="8e539-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="8e539-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="8e539-125">MaxItemsInObjectGraph</span></span>  

 <span data-ttu-id="8e539-126">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="8e539-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="8e539-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8e539-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e539-128">O número máximo de itens permitidos em um objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="8e539-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="8e539-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="8e539-129">UseSynchronizationContext</span></span>  

 <span data-ttu-id="8e539-130">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="8e539-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="8e539-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8e539-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e539-132">Especifica se o contexto de sincronização atual deve ser usado para escolher o thread de execução.</span><span class="sxs-lookup"><span data-stu-id="8e539-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="8e539-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="8e539-133">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="8e539-134">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="8e539-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="8e539-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8e539-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e539-136">Especifica se o sistema ou o aplicativo impõe o processamento de cabeçalho MustUnderstand SOAP.</span><span class="sxs-lookup"><span data-stu-id="8e539-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e539-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e539-137">Requirements</span></span>  
  
|<span data-ttu-id="8e539-138">MOF</span><span class="sxs-lookup"><span data-stu-id="8e539-138">MOF</span></span>|<span data-ttu-id="8e539-139">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="8e539-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8e539-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="8e539-140">Namespace</span></span>|<span data-ttu-id="8e539-141">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8e539-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e539-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e539-142">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
