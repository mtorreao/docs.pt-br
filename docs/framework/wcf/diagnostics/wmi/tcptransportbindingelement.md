---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6af85d62fffada95537494692b8694f42d7a2932
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290082"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="aa8a4-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="aa8a4-102">TcpTransportBindingElement</span></span>

<span data-ttu-id="aa8a4-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="aa8a4-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa8a4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aa8a4-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="aa8a4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="aa8a4-105">Methods</span></span>  

 <span data-ttu-id="aa8a4-106">A classe TcpTransportBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="aa8a4-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="aa8a4-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="aa8a4-107">Properties</span></span>  

 <span data-ttu-id="aa8a4-108">A classe TcpTransportBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="aa8a4-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="aa8a4-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="aa8a4-109">ConnectionPoolSettings</span></span>  

 <span data-ttu-id="aa8a4-110">Tipo de dados: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="aa8a4-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="aa8a4-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="aa8a4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aa8a4-112">As configurações do pool de conexões.</span><span class="sxs-lookup"><span data-stu-id="aa8a4-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="aa8a4-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="aa8a4-113">ListenBacklog</span></span>  

 <span data-ttu-id="aa8a4-114">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="aa8a4-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="aa8a4-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="aa8a4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aa8a4-116">O número máximo de solicitações de conexão em fila que podem estar pendentes.</span><span class="sxs-lookup"><span data-stu-id="aa8a4-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="aa8a4-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="aa8a4-117">PortSharingEnabled</span></span>  

 <span data-ttu-id="aa8a4-118">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="aa8a4-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="aa8a4-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="aa8a4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aa8a4-120">Um valor booliano que especifica se o compartilhamento de porta TCP está habilitado para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="aa8a4-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="aa8a4-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="aa8a4-121">TeredoEnabled</span></span>  

 <span data-ttu-id="aa8a4-122">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="aa8a4-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="aa8a4-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="aa8a4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aa8a4-124">Um valor booliano que especifica se Teredo (uma tecnologia para endereçar clientes que estão atrás de firewalls) está habilitado.</span><span class="sxs-lookup"><span data-stu-id="aa8a4-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa8a4-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa8a4-125">Requirements</span></span>  
  
|<span data-ttu-id="aa8a4-126">MOF</span><span class="sxs-lookup"><span data-stu-id="aa8a4-126">MOF</span></span>|<span data-ttu-id="aa8a4-127">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="aa8a4-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="aa8a4-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="aa8a4-128">Namespace</span></span>|<span data-ttu-id="aa8a4-129">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aa8a4-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa8a4-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="aa8a4-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
