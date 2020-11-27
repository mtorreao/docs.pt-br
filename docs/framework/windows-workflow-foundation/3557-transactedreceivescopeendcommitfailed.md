---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 4a4979047481687ef0d5c9d5891dec8f2826beed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263653"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="916c7-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="916c7-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>

## <a name="properties"></a><span data-ttu-id="916c7-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="916c7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="916c7-104">ID</span><span class="sxs-lookup"><span data-stu-id="916c7-104">ID</span></span>|<span data-ttu-id="916c7-105">3557</span><span class="sxs-lookup"><span data-stu-id="916c7-105">3557</span></span>|  
|<span data-ttu-id="916c7-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="916c7-106">Keywords</span></span>|<span data-ttu-id="916c7-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="916c7-107">WFServices</span></span>|  
|<span data-ttu-id="916c7-108">Nível</span><span class="sxs-lookup"><span data-stu-id="916c7-108">Level</span></span>|<span data-ttu-id="916c7-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="916c7-109">Information</span></span>|  
|<span data-ttu-id="916c7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="916c7-110">Channel</span></span>|<span data-ttu-id="916c7-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="916c7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="916c7-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="916c7-112">Description</span></span>  

 <span data-ttu-id="916c7-113">Indica que a chamada a EndCommit em um CommittableTransaction apresentou um TransactionException.</span><span class="sxs-lookup"><span data-stu-id="916c7-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="916c7-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="916c7-114">Message</span></span>  

 <span data-ttu-id="916c7-115">A chamada a EndCommit no CommittableTransaction com ID = “%1 " apresentou um TransactionException com a seguinte mensagem: “%2".</span><span class="sxs-lookup"><span data-stu-id="916c7-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="916c7-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="916c7-116">Details</span></span>  
  
|<span data-ttu-id="916c7-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="916c7-117">Data Item Name</span></span>|<span data-ttu-id="916c7-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="916c7-118">Data Item Type</span></span>|<span data-ttu-id="916c7-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="916c7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="916c7-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="916c7-120">TransactionId</span></span>|<span data-ttu-id="916c7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="916c7-121">xs:string</span></span>|<span data-ttu-id="916c7-122">A identificação do CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="916c7-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="916c7-123">Exceção</span><span class="sxs-lookup"><span data-stu-id="916c7-123">Exception</span></span>|<span data-ttu-id="916c7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="916c7-124">xs:string</span></span>|<span data-ttu-id="916c7-125">Os detalhes de exceção para a exceção</span><span class="sxs-lookup"><span data-stu-id="916c7-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="916c7-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="916c7-126">AppDomain</span></span>|<span data-ttu-id="916c7-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="916c7-127">xs:string</span></span>|<span data-ttu-id="916c7-128">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="916c7-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
