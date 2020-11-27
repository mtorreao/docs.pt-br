---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 9da8f77ee8ea5dc8b22ac5c0cb5113e906c5dc78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262262"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="5f0ac-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="5f0ac-102">ServiceSecurityAuditBehavior</span></span>

<span data-ttu-id="5f0ac-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="5f0ac-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f0ac-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5f0ac-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5f0ac-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5f0ac-105">Methods</span></span>  

 <span data-ttu-id="5f0ac-106">A classe ServiceSecurityAuditBehavior não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="5f0ac-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5f0ac-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="5f0ac-107">Properties</span></span>  

 <span data-ttu-id="5f0ac-108">A classe ServiceSecurityAuditBehavior tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="5f0ac-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="5f0ac-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="5f0ac-109">AuditLogLocation</span></span>  

 <span data-ttu-id="5f0ac-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5f0ac-110">Data type: string</span></span>  
  
 <span data-ttu-id="5f0ac-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="5f0ac-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f0ac-112">O local do log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5f0ac-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="5f0ac-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="5f0ac-113">MessageAuthenticationAuditLevel</span></span>  

 <span data-ttu-id="5f0ac-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5f0ac-114">Data type: string</span></span>  
  
 <span data-ttu-id="5f0ac-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="5f0ac-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f0ac-116">O tipo de nível de autenticação de mensagem que é usado para registrar em log eventos de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5f0ac-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="5f0ac-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="5f0ac-117">ServiceAuthorizationAuditLevel</span></span>  

 <span data-ttu-id="5f0ac-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5f0ac-118">Data type: string</span></span>  
  
 <span data-ttu-id="5f0ac-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="5f0ac-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f0ac-120">Os tipos de eventos de autorização que são registrados no log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5f0ac-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="5f0ac-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="5f0ac-121">SuppressAuditFailure</span></span>  

 <span data-ttu-id="5f0ac-122">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="5f0ac-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="5f0ac-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="5f0ac-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f0ac-124">Um valor booliano que especifica o comportamento para suprimir falhas de gravação no log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5f0ac-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f0ac-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f0ac-125">Requirements</span></span>  
  
|<span data-ttu-id="5f0ac-126">MOF</span><span class="sxs-lookup"><span data-stu-id="5f0ac-126">MOF</span></span>|<span data-ttu-id="5f0ac-127">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="5f0ac-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5f0ac-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="5f0ac-128">Namespace</span></span>|<span data-ttu-id="5f0ac-129">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5f0ac-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f0ac-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="5f0ac-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
