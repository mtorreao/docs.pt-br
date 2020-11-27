---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: de00cac851e4c6d0fd6df16f3a01b65bb5f43415
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294671"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="1b513-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1b513-102">TcpConnectionPoolSettings</span></span>

<span data-ttu-id="1b513-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1b513-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b513-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1b513-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1b513-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1b513-105">Methods</span></span>  

 <span data-ttu-id="1b513-106">A classe TcpConnectionPoolSettings não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="1b513-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1b513-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="1b513-107">Properties</span></span>  

 <span data-ttu-id="1b513-108">A classe TcpConnectionPoolSettings tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="1b513-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="1b513-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="1b513-109">GroupName</span></span>  

 <span data-ttu-id="1b513-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1b513-110">Data type: string</span></span>  
  
 <span data-ttu-id="1b513-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="1b513-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b513-112">O nome do grupo do pool de conexão usado pelo elemento de associação.</span><span class="sxs-lookup"><span data-stu-id="1b513-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="1b513-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="1b513-113">IdleTimeout</span></span>  

 <span data-ttu-id="1b513-114">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="1b513-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="1b513-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="1b513-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b513-116">O tempo máximo que a conexão pode ficar ociosa antes de ser desconectada.</span><span class="sxs-lookup"><span data-stu-id="1b513-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="1b513-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="1b513-117">LeaseTimeout</span></span>  

 <span data-ttu-id="1b513-118">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="1b513-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="1b513-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="1b513-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b513-120">O tempo máximo para que a operação de concessão seja concluída antes de atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="1b513-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="1b513-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="1b513-121">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="1b513-122">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="1b513-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="1b513-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="1b513-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b513-124">O número máximo de conexões de saída para cada ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="1b513-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b513-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b513-125">Requirements</span></span>  
  
|<span data-ttu-id="1b513-126">MOF</span><span class="sxs-lookup"><span data-stu-id="1b513-126">MOF</span></span>|<span data-ttu-id="1b513-127">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="1b513-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1b513-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="1b513-128">Namespace</span></span>|<span data-ttu-id="1b513-129">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1b513-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b513-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="1b513-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
