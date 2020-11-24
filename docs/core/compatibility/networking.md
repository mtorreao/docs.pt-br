---
title: Alterações de quebra de rede
description: Lista as alterações significativas em rede no .NET Core 2,0 e 3,0.
ms.date: 05/05/2020
ms.openlocfilehash: 761c6481888bcb8e91f7b4212355aca067632495
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689206"
---
# <a name="networking-breaking-changes-in-net-core-20-and-30"></a><span data-ttu-id="fe39c-103">Alterações de quebra de rede no .NET Core 2,0 e 3,0</span><span class="sxs-lookup"><span data-stu-id="fe39c-103">Networking breaking changes in .NET Core 2.0 and 3.0</span></span>

<span data-ttu-id="fe39c-104">As seguintes alterações significativas estão documentadas nesta página:</span><span class="sxs-lookup"><span data-stu-id="fe39c-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="fe39c-105">Alteração significativa</span><span class="sxs-lookup"><span data-stu-id="fe39c-105">Breaking change</span></span> | <span data-ttu-id="fe39c-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="fe39c-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="fe39c-107">Valor padrão de HttpRequestMessage. Version alterado para 1,1</span><span class="sxs-lookup"><span data-stu-id="fe39c-107">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="fe39c-108">3.0</span><span class="sxs-lookup"><span data-stu-id="fe39c-108">3.0</span></span> |
| [<span data-ttu-id="fe39c-109">WebClient. CancelAsync nem sempre cancela imediatamente</span><span class="sxs-lookup"><span data-stu-id="fe39c-109">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="fe39c-110">2,0</span><span class="sxs-lookup"><span data-stu-id="fe39c-110">2.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="fe39c-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fe39c-111">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="fe39c-112">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fe39c-112">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
