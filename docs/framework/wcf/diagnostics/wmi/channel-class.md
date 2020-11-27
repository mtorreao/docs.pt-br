---
title: Classe de canal
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: a920636e7df9609b12834366b1488c80122f9fca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274225"
---
# <a name="channel-class"></a><span data-ttu-id="a5244-102">Classe de canal</span><span class="sxs-lookup"><span data-stu-id="a5244-102">Channel class</span></span>

<span data-ttu-id="a5244-103">Canal</span><span class="sxs-lookup"><span data-stu-id="a5244-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5244-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a5244-104">Syntax</span></span>  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a5244-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a5244-105">Methods</span></span>  

 <span data-ttu-id="a5244-106">A classe Channel não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="a5244-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a5244-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="a5244-107">Properties</span></span>  

 <span data-ttu-id="a5244-108">A classe Channel tem as propriedades a seguir.</span><span class="sxs-lookup"><span data-stu-id="a5244-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="a5244-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="a5244-109">LocalAddress</span></span>  

 <span data-ttu-id="a5244-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a5244-110">Data type: string</span></span>  
  
 <span data-ttu-id="a5244-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a5244-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5244-112">O ponto de extremidade local para o canal.</span><span class="sxs-lookup"><span data-stu-id="a5244-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a5244-113">ref</span><span class="sxs-lookup"><span data-stu-id="a5244-113">ref</span></span>  

 <span data-ttu-id="a5244-114">Tipo de dados: ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="a5244-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="a5244-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a5244-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5244-116">Uma referência ao ponto de extremidade ao qual o canal se conecta.</span><span class="sxs-lookup"><span data-stu-id="a5244-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="a5244-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="a5244-117">RemoteAddress</span></span>  

 <span data-ttu-id="a5244-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a5244-118">Data type: string</span></span>  
  
 <span data-ttu-id="a5244-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a5244-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5244-120">O endereço remoto associado ao canal.</span><span class="sxs-lookup"><span data-stu-id="a5244-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="a5244-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="a5244-121">SessionId</span></span>  

 <span data-ttu-id="a5244-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a5244-122">Data type: string</span></span>  
  
 <span data-ttu-id="a5244-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a5244-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5244-124">A ID da sessão atual, se houver.</span><span class="sxs-lookup"><span data-stu-id="a5244-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="a5244-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="a5244-125">Type</span></span>  

 <span data-ttu-id="a5244-126">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a5244-126">Data type: string</span></span>  
  
 <span data-ttu-id="a5244-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a5244-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5244-128">O tipo do canal.</span><span class="sxs-lookup"><span data-stu-id="a5244-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5244-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5244-129">Requirements</span></span>  
  
|<span data-ttu-id="a5244-130">MOF</span><span class="sxs-lookup"><span data-stu-id="a5244-130">MOF</span></span>|<span data-ttu-id="a5244-131">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="a5244-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a5244-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="a5244-132">Namespace</span></span>|<span data-ttu-id="a5244-133">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a5244-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5244-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="a5244-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
