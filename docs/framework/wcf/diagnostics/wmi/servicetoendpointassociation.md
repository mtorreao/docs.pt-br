---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 6e20556541b1aa48e7dfc6a8cde97e1bc477457e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273939"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="3b6fd-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="3b6fd-102">ServiceToEndpointAssociation</span></span>

<span data-ttu-id="3b6fd-103">Mapeia um serviço para um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="3b6fd-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b6fd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3b6fd-104">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3b6fd-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3b6fd-105">Methods</span></span>  

 <span data-ttu-id="3b6fd-106">A classe ServiceToEndpointAssociation não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="3b6fd-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3b6fd-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="3b6fd-107">Properties</span></span>  

 <span data-ttu-id="3b6fd-108">A classe ServiceToEndpointAssociation tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="3b6fd-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="3b6fd-109">ref</span><span class="sxs-lookup"><span data-stu-id="3b6fd-109">ref</span></span>  

 <span data-ttu-id="3b6fd-110">Tipo de dados: serviço</span><span class="sxs-lookup"><span data-stu-id="3b6fd-110">Data type: Service</span></span>  
  
 <span data-ttu-id="3b6fd-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="3b6fd-111">Access type: Read-only</span></span>  
<span data-ttu-id="3b6fd-112">Qualificadores: Chave</span><span class="sxs-lookup"><span data-stu-id="3b6fd-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="3b6fd-113">O serviço associado ao ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="3b6fd-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="3b6fd-114">ref</span><span class="sxs-lookup"><span data-stu-id="3b6fd-114">ref</span></span>  

 <span data-ttu-id="3b6fd-115">Tipo de dados: ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="3b6fd-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="3b6fd-116">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="3b6fd-116">Access type: Read-only</span></span>  
<span data-ttu-id="3b6fd-117">Qualificadores: Chave</span><span class="sxs-lookup"><span data-stu-id="3b6fd-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="3b6fd-118">O ponto de extremidade associado ao serviço.</span><span class="sxs-lookup"><span data-stu-id="3b6fd-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b6fd-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b6fd-119">Requirements</span></span>  
  
|<span data-ttu-id="3b6fd-120">MOF</span><span class="sxs-lookup"><span data-stu-id="3b6fd-120">MOF</span></span>|<span data-ttu-id="3b6fd-121">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="3b6fd-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3b6fd-122">Namespace</span><span class="sxs-lookup"><span data-stu-id="3b6fd-122">Namespace</span></span>|<span data-ttu-id="3b6fd-123">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3b6fd-123">Defined in root\ServiceModel</span></span>|
