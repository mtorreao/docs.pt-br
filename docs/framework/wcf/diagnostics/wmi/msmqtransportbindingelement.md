---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 6590c5188e4e1758987a75fbd007099703ea6bc5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250418"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="7823d-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="7823d-102">MsmqTransportBindingElement</span></span>

<span data-ttu-id="7823d-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="7823d-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7823d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7823d-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7823d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7823d-105">Methods</span></span>  

 <span data-ttu-id="7823d-106">A classe MsmqTransportBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="7823d-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7823d-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="7823d-107">Properties</span></span>  

 <span data-ttu-id="7823d-108">A classe MsmqTransportBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="7823d-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="7823d-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="7823d-109">MaxPoolSize</span></span>  

 <span data-ttu-id="7823d-110">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="7823d-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="7823d-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7823d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7823d-112">O tamanho máximo do pool que contém objetos de mensagem MSMQ internos.</span><span class="sxs-lookup"><span data-stu-id="7823d-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="7823d-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="7823d-113">QueueTransferProtocol</span></span>  

 <span data-ttu-id="7823d-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="7823d-114">Data type: string</span></span>  
  
 <span data-ttu-id="7823d-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7823d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7823d-116">Um valor de enumeração que indica o transporte de canal de comunicação na fila que essa associação usa.</span><span class="sxs-lookup"><span data-stu-id="7823d-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="7823d-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="7823d-117">UseActiveDirectory</span></span>  

 <span data-ttu-id="7823d-118">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="7823d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="7823d-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7823d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7823d-120">Retorna um valor booliano que indica se os endereços da fila devem ser convertidos usando o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7823d-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7823d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7823d-121">Requirements</span></span>  
  
|<span data-ttu-id="7823d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="7823d-122">MOF</span></span>|<span data-ttu-id="7823d-123">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="7823d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7823d-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="7823d-124">Namespace</span></span>|<span data-ttu-id="7823d-125">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7823d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7823d-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="7823d-126">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
