---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: b72bd3903b7139c4adf2a8bd0ced6c34e7285640
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274290"
---
# <a name="binding"></a><span data-ttu-id="effb6-102">Associação</span><span class="sxs-lookup"><span data-stu-id="effb6-102">Binding</span></span>

<span data-ttu-id="effb6-103">Associação WMI</span><span class="sxs-lookup"><span data-stu-id="effb6-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="effb6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="effb6-104">Syntax</span></span>  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="effb6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="effb6-105">Methods</span></span>  

 <span data-ttu-id="effb6-106">A classe de associação não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="effb6-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="effb6-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="effb6-107">Properties</span></span>  

 <span data-ttu-id="effb6-108">A classe de associação tem as propriedades a seguir.</span><span class="sxs-lookup"><span data-stu-id="effb6-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="effb6-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="effb6-109">BindingElements</span></span>  

 <span data-ttu-id="effb6-110">Tipo de dados: matriz BindingElement</span><span class="sxs-lookup"><span data-stu-id="effb6-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="effb6-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="effb6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="effb6-112">A coleção de elementos de associação implementados pela associação.</span><span class="sxs-lookup"><span data-stu-id="effb6-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="effb6-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="effb6-113">CloseTimeout</span></span>  

 <span data-ttu-id="effb6-114">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="effb6-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="effb6-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="effb6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="effb6-116">O intervalo de tempo fornecido para a conclusão de uma operação de fechamento.</span><span class="sxs-lookup"><span data-stu-id="effb6-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="effb6-117">Nome</span><span class="sxs-lookup"><span data-stu-id="effb6-117">Name</span></span>  

 <span data-ttu-id="effb6-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="effb6-118">Data type: string</span></span>  
  
 <span data-ttu-id="effb6-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="effb6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="effb6-120">O nome da associação.</span><span class="sxs-lookup"><span data-stu-id="effb6-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="effb6-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="effb6-121">Namespace</span></span>  

 <span data-ttu-id="effb6-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="effb6-122">Data type: string</span></span>  
  
 <span data-ttu-id="effb6-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="effb6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="effb6-124">O namespace XML da associação.</span><span class="sxs-lookup"><span data-stu-id="effb6-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="effb6-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="effb6-125">OpenTimeout</span></span>  

 <span data-ttu-id="effb6-126">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="effb6-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="effb6-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="effb6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="effb6-128">O intervalo de tempo fornecido para a conclusão de uma operação de abertura.</span><span class="sxs-lookup"><span data-stu-id="effb6-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="effb6-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="effb6-129">ReceiveTimeout</span></span>  

 <span data-ttu-id="effb6-130">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="effb6-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="effb6-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="effb6-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="effb6-132">O intervalo de tempo fornecido para a conclusão de uma operação de recebimento.</span><span class="sxs-lookup"><span data-stu-id="effb6-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="effb6-133">Esquema</span><span class="sxs-lookup"><span data-stu-id="effb6-133">Scheme</span></span>  

 <span data-ttu-id="effb6-134">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="effb6-134">Data type: string</span></span>  
  
 <span data-ttu-id="effb6-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="effb6-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="effb6-136">O esquema de transporte de URI que é usado pelas fábricas de canal e ouvinte criadas pela associação.</span><span class="sxs-lookup"><span data-stu-id="effb6-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="effb6-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="effb6-137">SendTimeout</span></span>  

 <span data-ttu-id="effb6-138">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="effb6-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="effb6-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="effb6-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="effb6-140">O intervalo de tempo fornecido para a conclusão de uma operação de envio.</span><span class="sxs-lookup"><span data-stu-id="effb6-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="effb6-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="effb6-141">Requirements</span></span>  
  
|<span data-ttu-id="effb6-142">MOF</span><span class="sxs-lookup"><span data-stu-id="effb6-142">MOF</span></span>|<span data-ttu-id="effb6-143">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="effb6-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="effb6-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="effb6-144">Namespace</span></span>|<span data-ttu-id="effb6-145">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="effb6-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="effb6-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="effb6-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
