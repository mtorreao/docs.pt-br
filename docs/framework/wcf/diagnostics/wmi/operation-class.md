---
title: Classe de operação
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 6b47d933dc84813532398830c92c95210208a709
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269152"
---
# <a name="operation-class"></a><span data-ttu-id="15216-102">Classe de operação</span><span class="sxs-lookup"><span data-stu-id="15216-102">Operation class</span></span>

<span data-ttu-id="15216-103">Operação</span><span class="sxs-lookup"><span data-stu-id="15216-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15216-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="15216-104">Syntax</span></span>  
  
```csharp
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="15216-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="15216-105">Methods</span></span>  

 <span data-ttu-id="15216-106">A classe Operation não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="15216-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="15216-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="15216-107">Properties</span></span>  

 <span data-ttu-id="15216-108">A classe Operation tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="15216-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="15216-109">Ação</span><span class="sxs-lookup"><span data-stu-id="15216-109">Action</span></span>  

 <span data-ttu-id="15216-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="15216-110">Data type: string</span></span>  
  
 <span data-ttu-id="15216-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-112">A ação de WS-Addressing da mensagem de solicitação.</span><span class="sxs-lookup"><span data-stu-id="15216-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="15216-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="15216-113">AsyncPattern</span></span>  

 <span data-ttu-id="15216-114">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="15216-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="15216-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-116">Indica que uma operação é implementada de forma assíncrona usando um `Begin` par de método [colchetes de abertura/fechamento] e `End` [colchetes de abertura/fechamento] em um contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="15216-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="15216-117">Comportamentos</span><span class="sxs-lookup"><span data-stu-id="15216-117">Behaviors</span></span>  

 <span data-ttu-id="15216-118">Tipo de dados: matriz de comportamento</span><span class="sxs-lookup"><span data-stu-id="15216-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="15216-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-120">Os comportamentos associados a esta operação.</span><span class="sxs-lookup"><span data-stu-id="15216-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="15216-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="15216-121">IsCallback</span></span>  

 <span data-ttu-id="15216-122">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="15216-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="15216-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-124">True quando a operação for uma operação de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="15216-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="15216-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="15216-125">IsInitiating</span></span>  

 <span data-ttu-id="15216-126">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="15216-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="15216-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-128">Indica se o método implementa uma operação que pode iniciar uma sessão no servidor.</span><span class="sxs-lookup"><span data-stu-id="15216-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="15216-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="15216-129">IsOneWay</span></span>  

 <span data-ttu-id="15216-130">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="15216-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="15216-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-132">Indica se uma operação retorna uma mensagem de resposta.</span><span class="sxs-lookup"><span data-stu-id="15216-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="15216-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="15216-133">IsTerminating</span></span>  

 <span data-ttu-id="15216-134">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="15216-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="15216-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-136">Indica se uma operação retorna uma mensagem de resposta.</span><span class="sxs-lookup"><span data-stu-id="15216-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="15216-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="15216-137">MethodSignature</span></span>  

 <span data-ttu-id="15216-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="15216-138">Data type: string</span></span>  
  
 <span data-ttu-id="15216-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-140">A assinatura do método da operação.</span><span class="sxs-lookup"><span data-stu-id="15216-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="15216-141">Nome</span><span class="sxs-lookup"><span data-stu-id="15216-141">Name</span></span>  

 <span data-ttu-id="15216-142">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="15216-142">Data type: string</span></span>  
  
 <span data-ttu-id="15216-143">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-144">O nome da operação.</span><span class="sxs-lookup"><span data-stu-id="15216-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="15216-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="15216-145">ParameterTypes</span></span>  

 <span data-ttu-id="15216-146">Tipo de dados: matriz de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="15216-146">Data type: string array</span></span>  
  
 <span data-ttu-id="15216-147">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-148">Os tipos dos parâmetros da operação.</span><span class="sxs-lookup"><span data-stu-id="15216-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="15216-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="15216-149">ReplyAction</span></span>  

 <span data-ttu-id="15216-150">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="15216-150">Data type: string</span></span>  
  
 <span data-ttu-id="15216-151">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-152">O valor da ação SOAP para a mensagem de resposta da operação.</span><span class="sxs-lookup"><span data-stu-id="15216-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="15216-153">Tipoderetorno</span><span class="sxs-lookup"><span data-stu-id="15216-153">ReturnType</span></span>  

 <span data-ttu-id="15216-154">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="15216-154">Data type: string</span></span>  
  
 <span data-ttu-id="15216-155">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15216-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15216-156">O tipo de retorno da operação.</span><span class="sxs-lookup"><span data-stu-id="15216-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15216-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15216-157">Requirements</span></span>  
  
|<span data-ttu-id="15216-158">MOF</span><span class="sxs-lookup"><span data-stu-id="15216-158">MOF</span></span>|<span data-ttu-id="15216-159">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="15216-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="15216-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="15216-160">Namespace</span></span>|<span data-ttu-id="15216-161">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="15216-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15216-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="15216-162">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
