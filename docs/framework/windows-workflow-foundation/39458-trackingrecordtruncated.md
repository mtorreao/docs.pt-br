---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: f02a34673c51be6e0b127a64e4622131575d836f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275886"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="2b3ea-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="2b3ea-102">39458 - TrackingRecordTruncated</span></span>

## <a name="properties"></a><span data-ttu-id="2b3ea-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="2b3ea-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b3ea-104">ID</span><span class="sxs-lookup"><span data-stu-id="2b3ea-104">ID</span></span>|<span data-ttu-id="2b3ea-105">39458</span><span class="sxs-lookup"><span data-stu-id="2b3ea-105">39458</span></span>|  
|<span data-ttu-id="2b3ea-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2b3ea-106">Keywords</span></span>|<span data-ttu-id="2b3ea-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="2b3ea-107">WFTracking</span></span>|  
|<span data-ttu-id="2b3ea-108">Nível</span><span class="sxs-lookup"><span data-stu-id="2b3ea-108">Level</span></span>|<span data-ttu-id="2b3ea-109">Aviso</span><span class="sxs-lookup"><span data-stu-id="2b3ea-109">Warning</span></span>|  
|<span data-ttu-id="2b3ea-110">Canal</span><span class="sxs-lookup"><span data-stu-id="2b3ea-110">Channel</span></span>|<span data-ttu-id="2b3ea-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="2b3ea-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2b3ea-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="2b3ea-112">Description</span></span>  

 <span data-ttu-id="2b3ea-113">Indica que um registro de rastreamento foi truncado.</span><span class="sxs-lookup"><span data-stu-id="2b3ea-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="2b3ea-114">Variáveis/anotações/dados do usuário serem removidos.</span><span class="sxs-lookup"><span data-stu-id="2b3ea-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2b3ea-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="2b3ea-115">Message</span></span>  

 <span data-ttu-id="2b3ea-116">Registro truncado %1 de rastreamento gravados para a sessão de ETW com provedor %2.</span><span class="sxs-lookup"><span data-stu-id="2b3ea-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="2b3ea-117">Dados de variáveis/anotações/usuários foram removidos</span><span class="sxs-lookup"><span data-stu-id="2b3ea-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="2b3ea-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2b3ea-118">Details</span></span>  
  
|<span data-ttu-id="2b3ea-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="2b3ea-119">Data Item Name</span></span>|<span data-ttu-id="2b3ea-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="2b3ea-120">Data Item Type</span></span>|<span data-ttu-id="2b3ea-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="2b3ea-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2b3ea-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="2b3ea-122">RecordNumber</span></span>|<span data-ttu-id="2b3ea-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b3ea-123">xs:string</span></span>|<span data-ttu-id="2b3ea-124">O número de registro controlando.</span><span class="sxs-lookup"><span data-stu-id="2b3ea-124">The tracking record number.</span></span>|  
|<span data-ttu-id="2b3ea-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="2b3ea-125">ProviderId</span></span>|<span data-ttu-id="2b3ea-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b3ea-126">xs:string</span></span>|<span data-ttu-id="2b3ea-127">A identificação do provedor de ETW</span><span class="sxs-lookup"><span data-stu-id="2b3ea-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="2b3ea-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2b3ea-128">AppDomain</span></span>|<span data-ttu-id="2b3ea-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b3ea-129">xs:string</span></span>|<span data-ttu-id="2b3ea-130">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2b3ea-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
