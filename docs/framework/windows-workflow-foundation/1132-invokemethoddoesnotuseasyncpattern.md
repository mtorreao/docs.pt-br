---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 9249bdd0fe996ee7c1b04783ac8fef2c48063cc0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294151"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="b8acc-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="b8acc-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="b8acc-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="b8acc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8acc-104">ID</span><span class="sxs-lookup"><span data-stu-id="b8acc-104">ID</span></span>|<span data-ttu-id="b8acc-105">1132</span><span class="sxs-lookup"><span data-stu-id="b8acc-105">1132</span></span>|  
|<span data-ttu-id="b8acc-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="b8acc-106">Keywords</span></span>|<span data-ttu-id="b8acc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b8acc-107">WFRuntime</span></span>|  
|<span data-ttu-id="b8acc-108">Nível</span><span class="sxs-lookup"><span data-stu-id="b8acc-108">Level</span></span>|<span data-ttu-id="b8acc-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="b8acc-109">Information</span></span>|  
|<span data-ttu-id="b8acc-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b8acc-110">Channel</span></span>|<span data-ttu-id="b8acc-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="b8acc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b8acc-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b8acc-112">Description</span></span>  

 <span data-ttu-id="b8acc-113">Durante a etapa de CacheMetadata, a atividade de InvokeMethod indica que não está usando o padrão de async ao chamar o método.</span><span class="sxs-lookup"><span data-stu-id="b8acc-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b8acc-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="b8acc-114">Message</span></span>  

 <span data-ttu-id="b8acc-115">InvokeMethod “%1" - o método não usa o padrão assíncrono.</span><span class="sxs-lookup"><span data-stu-id="b8acc-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b8acc-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b8acc-116">Details</span></span>  
  
|<span data-ttu-id="b8acc-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="b8acc-117">Data Item Name</span></span>|<span data-ttu-id="b8acc-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="b8acc-118">Data Item Type</span></span>|<span data-ttu-id="b8acc-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="b8acc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b8acc-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="b8acc-120">InvokeMethod</span></span>|<span data-ttu-id="b8acc-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b8acc-121">xs:string</span></span>|<span data-ttu-id="b8acc-122">O nome para exibição de atividade de InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="b8acc-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="b8acc-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b8acc-123">AppDomain</span></span>|<span data-ttu-id="b8acc-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b8acc-124">xs:string</span></span>|<span data-ttu-id="b8acc-125">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b8acc-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
