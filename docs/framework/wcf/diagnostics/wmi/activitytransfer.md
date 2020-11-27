---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291109"
---
# <a name="activitytransfer"></a><span data-ttu-id="27c80-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="27c80-102">ActivityTransfer</span></span>

<span data-ttu-id="27c80-103">Evento de transferência de atividade</span><span class="sxs-lookup"><span data-stu-id="27c80-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c80-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="27c80-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="27c80-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="27c80-105">Methods</span></span>  

 <span data-ttu-id="27c80-106">A classe ActivityTransfer não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="27c80-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="27c80-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="27c80-107">Properties</span></span>  

 <span data-ttu-id="27c80-108">A classe ActivityTransfer tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="27c80-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="27c80-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="27c80-109">ActivityID</span></span>  
  
- <span data-ttu-id="27c80-110">Tipo de dados: objeto</span><span class="sxs-lookup"><span data-stu-id="27c80-110">Data type: object</span></span>  
    <span data-ttu-id="27c80-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="27c80-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="27c80-112">ID da atividade</span><span class="sxs-lookup"><span data-stu-id="27c80-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="27c80-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="27c80-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="27c80-114">Tipo de dados: objeto</span><span class="sxs-lookup"><span data-stu-id="27c80-114">Data type: object</span></span>  
    <span data-ttu-id="27c80-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="27c80-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="27c80-116">ID da atividade relacionada</span><span class="sxs-lookup"><span data-stu-id="27c80-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27c80-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27c80-117">Requirements</span></span>  
  
|<span data-ttu-id="27c80-118">MOF</span><span class="sxs-lookup"><span data-stu-id="27c80-118">MOF</span></span>|<span data-ttu-id="27c80-119">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="27c80-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="27c80-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="27c80-120">Namespace</span></span>|<span data-ttu-id="27c80-121">Definido em root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="27c80-121">Defined in root\ServiceModel.</span></span>|
