---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ae6a3448896cb206bce8867daf7104c3e484ecc8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269009"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="df03c-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="df03c-102">PeerTransportBindingElement</span></span>

<span data-ttu-id="df03c-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="df03c-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df03c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df03c-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="df03c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="df03c-105">Methods</span></span>  

 <span data-ttu-id="df03c-106">A classe PeerTransportBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="df03c-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="df03c-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="df03c-107">Properties</span></span>  

 <span data-ttu-id="df03c-108">A classe PeerTransportBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="df03c-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="df03c-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="df03c-109">ListenIPAddress</span></span>  

 <span data-ttu-id="df03c-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="df03c-110">Data type: string</span></span>  
  
 <span data-ttu-id="df03c-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="df03c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df03c-112">O endereço IP no qual o nó par escuta mensagens.</span><span class="sxs-lookup"><span data-stu-id="df03c-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="df03c-113">Porta</span><span class="sxs-lookup"><span data-stu-id="df03c-113">Port</span></span>  

 <span data-ttu-id="df03c-114">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="df03c-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="df03c-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="df03c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df03c-116">A porta da interface de rede na qual essa associação processa mensagens de canal de mesmo nível.</span><span class="sxs-lookup"><span data-stu-id="df03c-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="df03c-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="df03c-117">Security</span></span>  

 <span data-ttu-id="df03c-118">Tipo de dados: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="df03c-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="df03c-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="df03c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df03c-120">Configurações de segurança de transporte de pares.</span><span class="sxs-lookup"><span data-stu-id="df03c-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df03c-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df03c-121">Requirements</span></span>  
  
|<span data-ttu-id="df03c-122">MOF</span><span class="sxs-lookup"><span data-stu-id="df03c-122">MOF</span></span>|<span data-ttu-id="df03c-123">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="df03c-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="df03c-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="df03c-124">Namespace</span></span>|<span data-ttu-id="df03c-125">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="df03c-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df03c-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="df03c-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
