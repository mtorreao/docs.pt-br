---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 806066a8845068413d2a52c78878f76b5f5fa34f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250366"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="09784-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="09784-102">OneWayBindingElement</span></span>

<span data-ttu-id="09784-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="09784-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09784-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="09784-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="09784-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="09784-105">Methods</span></span>  

 <span data-ttu-id="09784-106">A classe OneWayBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="09784-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="09784-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="09784-107">Properties</span></span>  

 <span data-ttu-id="09784-108">A classe OneWayBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="09784-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="09784-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="09784-109">ChannelPoolSettings</span></span>  

 <span data-ttu-id="09784-110">Tipo de dados: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="09784-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="09784-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="09784-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09784-112">As configurações do pool de canais.</span><span class="sxs-lookup"><span data-stu-id="09784-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="09784-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="09784-113">MaxAcceptedChannels</span></span>  

 <span data-ttu-id="09784-114">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="09784-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="09784-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="09784-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09784-116">O número máximo de canais aceitos.</span><span class="sxs-lookup"><span data-stu-id="09784-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="09784-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="09784-117">PacketRoutable</span></span>  

 <span data-ttu-id="09784-118">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="09784-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="09784-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="09784-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09784-120">Um valor que indica se o pacote é roteável.</span><span class="sxs-lookup"><span data-stu-id="09784-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09784-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09784-121">Requirements</span></span>  
  
|<span data-ttu-id="09784-122">MOF</span><span class="sxs-lookup"><span data-stu-id="09784-122">MOF</span></span>|<span data-ttu-id="09784-123">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="09784-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="09784-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="09784-124">Namespace</span></span>|<span data-ttu-id="09784-125">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="09784-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09784-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="09784-126">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
