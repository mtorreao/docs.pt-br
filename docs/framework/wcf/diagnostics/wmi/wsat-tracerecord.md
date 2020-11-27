---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 0409277821a7cca3f97fcec1bb383aba9583a1f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262210"
---
# <a name="wsat_tracerecord"></a><span data-ttu-id="d1fa7-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="d1fa7-102">WSAT_TraceRecord</span></span>

<span data-ttu-id="d1fa7-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="d1fa7-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1fa7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d1fa7-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d1fa7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d1fa7-105">Methods</span></span>  

 <span data-ttu-id="d1fa7-106">A classe WSAT_TraceRecord não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="d1fa7-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d1fa7-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="d1fa7-107">Properties</span></span>  

 <span data-ttu-id="d1fa7-108">A classe WSAT_TraceRecord tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="d1fa7-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="d1fa7-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="d1fa7-109">ActivityID</span></span>  

 <span data-ttu-id="d1fa7-110">Tipo de dados: objeto</span><span class="sxs-lookup"><span data-stu-id="d1fa7-110">Data type: object</span></span>  
<span data-ttu-id="d1fa7-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="d1fa7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1fa7-112">A ID da atividade do registro de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="d1fa7-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="d1fa7-113">EventID</span><span class="sxs-lookup"><span data-stu-id="d1fa7-113">EventID</span></span>  

 <span data-ttu-id="d1fa7-114">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="d1fa7-114">Data type: sint32</span></span>  
<span data-ttu-id="d1fa7-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="d1fa7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1fa7-116">A ID de evento do registro de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="d1fa7-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="d1fa7-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="d1fa7-117">TraceRecord</span></span>  

 <span data-ttu-id="d1fa7-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d1fa7-118">Data type: string</span></span>  
<span data-ttu-id="d1fa7-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="d1fa7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1fa7-120">Registro de rastreamento</span><span class="sxs-lookup"><span data-stu-id="d1fa7-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1fa7-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1fa7-121">Requirements</span></span>  
  
|<span data-ttu-id="d1fa7-122">MOF</span><span class="sxs-lookup"><span data-stu-id="d1fa7-122">MOF</span></span>|<span data-ttu-id="d1fa7-123">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="d1fa7-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d1fa7-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="d1fa7-124">Namespace</span></span>|<span data-ttu-id="d1fa7-125">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d1fa7-125">Defined in root\ServiceModel</span></span>|
