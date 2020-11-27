---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 5e6a5f9d21435fee8309bd222443407e50ec2cee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263601"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="a3bfe-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="a3bfe-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>

## <a name="properties"></a><span data-ttu-id="a3bfe-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="a3bfe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3bfe-104">ID</span><span class="sxs-lookup"><span data-stu-id="a3bfe-104">ID</span></span>|<span data-ttu-id="a3bfe-105">3551</span><span class="sxs-lookup"><span data-stu-id="a3bfe-105">3551</span></span>|  
|<span data-ttu-id="a3bfe-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a3bfe-106">Keywords</span></span>|<span data-ttu-id="a3bfe-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="a3bfe-107">WFServices</span></span>|  
|<span data-ttu-id="a3bfe-108">Nível</span><span class="sxs-lookup"><span data-stu-id="a3bfe-108">Level</span></span>|<span data-ttu-id="a3bfe-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="a3bfe-109">Information</span></span>|  
|<span data-ttu-id="a3bfe-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a3bfe-110">Channel</span></span>|<span data-ttu-id="a3bfe-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="a3bfe-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a3bfe-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="a3bfe-112">Description</span></span>  

 <span data-ttu-id="a3bfe-113">Indica que uma ressunção do indexador falhou.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="a3bfe-114">O armazenados em buffer recebe a operação será tentada novamente quando a instância do serviço está pronta para processar esta operação específico.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a3bfe-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="a3bfe-115">Message</span></span>  

 <span data-ttu-id="a3bfe-116">A operação “%2 " na instância “%1 " do serviço não pode ser executada no momento.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="a3bfe-117">Outra tentativa será feita quando a instância de serviço estiver pronta para processar esse operação específica.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a3bfe-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a3bfe-118">Details</span></span>  
  
|<span data-ttu-id="a3bfe-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="a3bfe-119">Data Item Name</span></span>|<span data-ttu-id="a3bfe-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="a3bfe-120">Data Item Type</span></span>|<span data-ttu-id="a3bfe-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="a3bfe-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a3bfe-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="a3bfe-122">OperationName</span></span>|<span data-ttu-id="a3bfe-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="a3bfe-123">xs:string</span></span>|<span data-ttu-id="a3bfe-124">O nome da operação.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-124">The name of the operation.</span></span>|  
|<span data-ttu-id="a3bfe-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="a3bfe-125">ServiceInstanceId</span></span>|<span data-ttu-id="a3bfe-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="a3bfe-126">xs:string</span></span>|<span data-ttu-id="a3bfe-127">A identificação da instância do serviço.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="a3bfe-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a3bfe-128">AppDomain</span></span>|<span data-ttu-id="a3bfe-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="a3bfe-129">xs:string</span></span>|<span data-ttu-id="a3bfe-130">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
