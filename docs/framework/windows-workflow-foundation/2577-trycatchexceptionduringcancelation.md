---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: 33c68984e88eaa5e3028899a7c3066c94a65e8eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271233"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="26126-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="26126-102">2577 - TryCatchExceptionDuringCancelation</span></span>

## <a name="properties"></a><span data-ttu-id="26126-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="26126-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26126-104">ID</span><span class="sxs-lookup"><span data-stu-id="26126-104">ID</span></span>|<span data-ttu-id="26126-105">2577</span><span class="sxs-lookup"><span data-stu-id="26126-105">2577</span></span>|  
|<span data-ttu-id="26126-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="26126-106">Keywords</span></span>|<span data-ttu-id="26126-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="26126-107">WFActivities</span></span>|  
|<span data-ttu-id="26126-108">Nível</span><span class="sxs-lookup"><span data-stu-id="26126-108">Level</span></span>|<span data-ttu-id="26126-109">Aviso</span><span class="sxs-lookup"><span data-stu-id="26126-109">Warning</span></span>|  
|<span data-ttu-id="26126-110">Canal</span><span class="sxs-lookup"><span data-stu-id="26126-110">Channel</span></span>|<span data-ttu-id="26126-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="26126-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="26126-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="26126-112">Description</span></span>  

 <span data-ttu-id="26126-113">Indica que uma atividade filho de atividade de TryCatch apresentou uma exceção durante o cancelar.</span><span class="sxs-lookup"><span data-stu-id="26126-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="26126-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="26126-114">Message</span></span>  

 <span data-ttu-id="26126-115">Uma atividade filho da atividade “%1 " de TryCatch apresentou uma exceção durante o cancelar.</span><span class="sxs-lookup"><span data-stu-id="26126-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="26126-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="26126-116">Details</span></span>  
  
|<span data-ttu-id="26126-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="26126-117">Data Item Name</span></span>|<span data-ttu-id="26126-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="26126-118">Data Item Type</span></span>|<span data-ttu-id="26126-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="26126-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="26126-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="26126-120">DisplayName</span></span>|<span data-ttu-id="26126-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="26126-121">xs:string</span></span>|<span data-ttu-id="26126-122">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="26126-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="26126-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="26126-123">AppDomain</span></span>|<span data-ttu-id="26126-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="26126-124">xs:string</span></span>|<span data-ttu-id="26126-125">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="26126-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
