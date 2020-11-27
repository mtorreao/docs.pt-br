---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 61605d666911cce277bcebbb0a2f803e9a5dcfeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261300"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="e0640-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="e0640-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>

## <a name="properties"></a><span data-ttu-id="e0640-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="e0640-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0640-104">ID</span><span class="sxs-lookup"><span data-stu-id="e0640-104">ID</span></span>|<span data-ttu-id="e0640-105">3550</span><span class="sxs-lookup"><span data-stu-id="e0640-105">3550</span></span>|  
|<span data-ttu-id="e0640-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="e0640-106">Keywords</span></span>|<span data-ttu-id="e0640-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="e0640-107">WFServices</span></span>|  
|<span data-ttu-id="e0640-108">Nível</span><span class="sxs-lookup"><span data-stu-id="e0640-108">Level</span></span>|<span data-ttu-id="e0640-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="e0640-109">Information</span></span>|  
|<span data-ttu-id="e0640-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e0640-110">Channel</span></span>|<span data-ttu-id="e0640-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="e0640-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0640-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0640-112">Description</span></span>  

 <span data-ttu-id="e0640-113">Indica que um armazenados em buffer recebe falhou.</span><span class="sxs-lookup"><span data-stu-id="e0640-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="e0640-114">A operação será tentada novamente quando a instância do serviço está pronta para processar esta operação específico.</span><span class="sxs-lookup"><span data-stu-id="e0640-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e0640-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="e0640-115">Message</span></span>  

 <span data-ttu-id="e0640-116">A operação “%1 " não pode ser executada no momento.</span><span class="sxs-lookup"><span data-stu-id="e0640-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="e0640-117">Outra tentativa será feita quando a instância de serviço estiver pronta para processar esse operação específica.</span><span class="sxs-lookup"><span data-stu-id="e0640-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e0640-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e0640-118">Details</span></span>  
  
|<span data-ttu-id="e0640-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="e0640-119">Data Item Name</span></span>|<span data-ttu-id="e0640-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="e0640-120">Data Item Type</span></span>|<span data-ttu-id="e0640-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0640-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e0640-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="e0640-122">OperationName</span></span>|<span data-ttu-id="e0640-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0640-123">xs:string</span></span>|<span data-ttu-id="e0640-124">O nome da operação.</span><span class="sxs-lookup"><span data-stu-id="e0640-124">The name of the operation.</span></span>|  
|<span data-ttu-id="e0640-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e0640-125">AppDomain</span></span>|<span data-ttu-id="e0640-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0640-126">xs:string</span></span>|<span data-ttu-id="e0640-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e0640-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
