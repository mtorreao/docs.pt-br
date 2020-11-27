---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: c3174e70d42385923674a3db5f696a0f64eda29f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295348"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="efee8-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="efee8-102">CoordinatorRecoveryLogEntryCorrupt</span></span>

<span data-ttu-id="efee8-103">ID: 139</span><span class="sxs-lookup"><span data-stu-id="efee8-103">Id: 139</span></span>  
  
 <span data-ttu-id="efee8-104">Gravidade: Erro</span><span class="sxs-lookup"><span data-stu-id="efee8-104">Severity: Error</span></span>  
  
 <span data-ttu-id="efee8-105">Categoria: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="efee8-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="efee8-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="efee8-106">Description</span></span>  

 <span data-ttu-id="efee8-107">Esse evento indica que uma entrada de log de recuperação do coordenador foi corrompida e não pôde ser desserializada.</span><span class="sxs-lookup"><span data-stu-id="efee8-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="efee8-108">A perda de dados pode resultar desse erro.</span><span class="sxs-lookup"><span data-stu-id="efee8-108">Data loss may result from this error.</span></span> <span data-ttu-id="efee8-109">O evento lista a ID da transação, os dados de recuperação (codificado na Base64), a exceção, o nome do processo e a ID do processo.</span><span class="sxs-lookup"><span data-stu-id="efee8-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efee8-110">Veja também</span><span class="sxs-lookup"><span data-stu-id="efee8-110">See also</span></span>

- [<span data-ttu-id="efee8-111">Log de eventos</span><span class="sxs-lookup"><span data-stu-id="efee8-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="efee8-112">Referência geral de eventos</span><span class="sxs-lookup"><span data-stu-id="efee8-112">Events General Reference</span></span>](events-general-reference.md)
