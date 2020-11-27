---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8422e1adf9a8914b631431eba5c9c0ed058cd0f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258017"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="4d271-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="4d271-102">NamedPipeConnectionPoolSettings</span></span>

<span data-ttu-id="4d271-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="4d271-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d271-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4d271-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4d271-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4d271-105">Methods</span></span>  

 <span data-ttu-id="4d271-106">A classe NamedPipeConnectionPoolSettings não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="4d271-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4d271-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="4d271-107">Properties</span></span>  

 <span data-ttu-id="4d271-108">A classe NamedPipeConnectionPoolSettings tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="4d271-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="4d271-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="4d271-109">GroupName</span></span>  

 <span data-ttu-id="4d271-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4d271-110">Data type: string</span></span>  
  
 <span data-ttu-id="4d271-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4d271-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d271-112">O nome do grupo do pool de conexão usado pelo elemento de associação.</span><span class="sxs-lookup"><span data-stu-id="4d271-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="4d271-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="4d271-113">IdleTimeout</span></span>  

 <span data-ttu-id="4d271-114">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="4d271-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="4d271-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4d271-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d271-116">O tempo máximo que a conexão pode ficar ociosa antes de ser desconectada.</span><span class="sxs-lookup"><span data-stu-id="4d271-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="4d271-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="4d271-117">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="4d271-118">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="4d271-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="4d271-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="4d271-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d271-120">O número máximo de conexões de saída para cada ponto de extremidade no cliente.</span><span class="sxs-lookup"><span data-stu-id="4d271-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d271-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d271-121">Requirements</span></span>  
  
|<span data-ttu-id="4d271-122">MOF</span><span class="sxs-lookup"><span data-stu-id="4d271-122">MOF</span></span>|<span data-ttu-id="4d271-123">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="4d271-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4d271-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="4d271-124">Namespace</span></span>|<span data-ttu-id="4d271-125">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4d271-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d271-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="4d271-126">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
