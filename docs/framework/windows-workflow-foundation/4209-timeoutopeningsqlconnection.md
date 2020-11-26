---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: 9aa8cdffebb0cdf8b1e8225a394edf78ecf032b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238672"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="e5969-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="e5969-102">4209 - TimeoutOpeningSqlConnection</span></span>

## <a name="properties"></a><span data-ttu-id="e5969-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="e5969-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5969-104">ID</span><span class="sxs-lookup"><span data-stu-id="e5969-104">ID</span></span>|<span data-ttu-id="e5969-105">4209</span><span class="sxs-lookup"><span data-stu-id="e5969-105">4209</span></span>|  
|<span data-ttu-id="e5969-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="e5969-106">Keywords</span></span>|<span data-ttu-id="e5969-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="e5969-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="e5969-108">Nível</span><span class="sxs-lookup"><span data-stu-id="e5969-108">Level</span></span>|<span data-ttu-id="e5969-109">Erro do</span><span class="sxs-lookup"><span data-stu-id="e5969-109">Error</span></span>|  
|<span data-ttu-id="e5969-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e5969-110">Channel</span></span>|<span data-ttu-id="e5969-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="e5969-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e5969-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5969-112">Description</span></span>  

 <span data-ttu-id="e5969-113">Indica que um tempo limite foi encontrado ao tentar abrir uma conexão SQL.</span><span class="sxs-lookup"><span data-stu-id="e5969-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e5969-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="e5969-114">Message</span></span>  

 <span data-ttu-id="e5969-115">O tempo limite está tentando abrir uma conexão de SQL.</span><span class="sxs-lookup"><span data-stu-id="e5969-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="e5969-116">A operação não concluiu dentro do tempo limite distribuído de %1.</span><span class="sxs-lookup"><span data-stu-id="e5969-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="e5969-117">O tempo determinado para essa operação pode ter sido uma parte de um tempo limite maior.</span><span class="sxs-lookup"><span data-stu-id="e5969-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e5969-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e5969-118">Details</span></span>  
  
|<span data-ttu-id="e5969-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="e5969-119">Data Item Name</span></span>|<span data-ttu-id="e5969-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="e5969-120">Data Item Type</span></span>|<span data-ttu-id="e5969-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5969-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e5969-122">Tempo limite</span><span class="sxs-lookup"><span data-stu-id="e5969-122">Timeout</span></span>|<span data-ttu-id="e5969-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e5969-123">xs:string</span></span>|<span data-ttu-id="e5969-124">O valor de tempo limite para abrir a conexão SQL.</span><span class="sxs-lookup"><span data-stu-id="e5969-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="e5969-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e5969-125">AppDomain</span></span>|<span data-ttu-id="e5969-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e5969-126">xs:string</span></span>|<span data-ttu-id="e5969-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e5969-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
