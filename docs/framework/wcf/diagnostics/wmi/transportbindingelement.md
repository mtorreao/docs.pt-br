---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 45bfcd069391156bc85cc4c26f2b172770197a9e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234837"
---
# <a name="transportbindingelement"></a><span data-ttu-id="ec228-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec228-102">TransportBindingElement</span></span>

<span data-ttu-id="ec228-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec228-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec228-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ec228-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ec228-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ec228-105">Methods</span></span>  

 <span data-ttu-id="ec228-106">A classe TransportBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="ec228-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ec228-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="ec228-107">Properties</span></span>  

 <span data-ttu-id="ec228-108">A classe TransportBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="ec228-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="ec228-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="ec228-109">ManualAddressing</span></span>  

 <span data-ttu-id="ec228-110">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="ec228-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="ec228-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="ec228-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ec228-112">Um valor booliano que especifica se o usuário deseja assumir o controle do endereçamento de mensagens.</span><span class="sxs-lookup"><span data-stu-id="ec228-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="ec228-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ec228-113">MaxBufferPoolSize</span></span>  

 <span data-ttu-id="ec228-114">Tipo de dados: sint64</span><span class="sxs-lookup"><span data-stu-id="ec228-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="ec228-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="ec228-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ec228-116">O tamanho máximo do pool de buffers para a associação.</span><span class="sxs-lookup"><span data-stu-id="ec228-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="ec228-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ec228-117">MaxReceivedMessageSize</span></span>  

 <span data-ttu-id="ec228-118">Tipo de dados: sint64</span><span class="sxs-lookup"><span data-stu-id="ec228-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="ec228-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="ec228-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ec228-120">O tamanho máximo de uma mensagem que é processada por essa associação.</span><span class="sxs-lookup"><span data-stu-id="ec228-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="ec228-121">Esquema</span><span class="sxs-lookup"><span data-stu-id="ec228-121">Scheme</span></span>  

 <span data-ttu-id="ec228-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ec228-122">Data type: string</span></span>  
  
 <span data-ttu-id="ec228-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="ec228-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ec228-124">O esquema de URI para o transporte.</span><span class="sxs-lookup"><span data-stu-id="ec228-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec228-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec228-125">Requirements</span></span>  
  
|<span data-ttu-id="ec228-126">MOF</span><span class="sxs-lookup"><span data-stu-id="ec228-126">MOF</span></span>|<span data-ttu-id="ec228-127">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="ec228-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ec228-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="ec228-128">Namespace</span></span>|<span data-ttu-id="ec228-129">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ec228-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec228-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="ec228-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
