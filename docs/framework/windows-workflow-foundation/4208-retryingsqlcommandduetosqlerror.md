---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: 088754cb15c2e55faa1d43a1da1c79ddcddd69f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280410"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="33093-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="33093-102">4208 - RetryingSqlCommandDueToSqlError</span></span>

## <a name="properties"></a><span data-ttu-id="33093-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="33093-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33093-104">ID</span><span class="sxs-lookup"><span data-stu-id="33093-104">ID</span></span>|<span data-ttu-id="33093-105">4208</span><span class="sxs-lookup"><span data-stu-id="33093-105">4208</span></span>|  
|<span data-ttu-id="33093-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="33093-106">Keywords</span></span>|<span data-ttu-id="33093-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="33093-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="33093-108">Nível</span><span class="sxs-lookup"><span data-stu-id="33093-108">Level</span></span>|<span data-ttu-id="33093-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="33093-109">Information</span></span>|  
|<span data-ttu-id="33093-110">Canal</span><span class="sxs-lookup"><span data-stu-id="33093-110">Channel</span></span>|<span data-ttu-id="33093-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="33093-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="33093-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="33093-112">Description</span></span>  

 <span data-ttu-id="33093-113">Indica que o provedor SQL é experimentando de novo um comando SQL devido a um erro SQL.</span><span class="sxs-lookup"><span data-stu-id="33093-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="33093-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="33093-114">Message</span></span>  

 <span data-ttu-id="33093-115">Experimentando de novo um comando SQL por causa do erro número %1. SQL.</span><span class="sxs-lookup"><span data-stu-id="33093-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="33093-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="33093-116">Details</span></span>  
  
|<span data-ttu-id="33093-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="33093-117">Data Item Name</span></span>|<span data-ttu-id="33093-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="33093-118">Data Item Type</span></span>|<span data-ttu-id="33093-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="33093-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="33093-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="33093-120">ErrorNumber</span></span>|<span data-ttu-id="33093-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="33093-121">xs:string</span></span>|<span data-ttu-id="33093-122">O número do erro SQL.</span><span class="sxs-lookup"><span data-stu-id="33093-122">The SQL error number.</span></span>|  
|<span data-ttu-id="33093-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="33093-123">AppDomain</span></span>|<span data-ttu-id="33093-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="33093-124">xs:string</span></span>|<span data-ttu-id="33093-125">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="33093-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
