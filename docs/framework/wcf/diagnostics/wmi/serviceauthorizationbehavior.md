---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: d3625865484568746888ef0638d9a8501e610bef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273198"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="78fb2-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="78fb2-102">ServiceAuthorizationBehavior</span></span>

<span data-ttu-id="78fb2-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="78fb2-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78fb2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="78fb2-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="78fb2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="78fb2-105">Methods</span></span>  

 <span data-ttu-id="78fb2-106">A classe ServiceAuthorizationBehavior não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="78fb2-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="78fb2-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="78fb2-107">Properties</span></span>  

 <span data-ttu-id="78fb2-108">A classe ServiceAuthorizationBehavior tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="78fb2-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="78fb2-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="78fb2-109">ImpersonateCallerForAllOperations</span></span>  

 <span data-ttu-id="78fb2-110">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="78fb2-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="78fb2-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="78fb2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="78fb2-112">Um valor que controla se o serviço tenta representar usando as credenciais fornecidas pela mensagem de entrada.</span><span class="sxs-lookup"><span data-stu-id="78fb2-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="78fb2-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="78fb2-113">PrincipalPermissionMode</span></span>  

 <span data-ttu-id="78fb2-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="78fb2-114">Data type: string</span></span>  
  
 <span data-ttu-id="78fb2-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="78fb2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="78fb2-116">A entidade de segurança usada para executar operações no servidor.</span><span class="sxs-lookup"><span data-stu-id="78fb2-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="78fb2-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="78fb2-117">RoleProvider</span></span>  

 <span data-ttu-id="78fb2-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="78fb2-118">Data type: string</span></span>  
  
 <span data-ttu-id="78fb2-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="78fb2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="78fb2-120">O nome do provedor de função ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="78fb2-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="78fb2-121">Objectauthorizationmanager</span><span class="sxs-lookup"><span data-stu-id="78fb2-121">ServiceAuthorizationManager</span></span>  

 <span data-ttu-id="78fb2-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="78fb2-122">Data type: string</span></span>  
  
 <span data-ttu-id="78fb2-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="78fb2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="78fb2-124">O Gerenciador de autorização usado para autorização personalizada.</span><span class="sxs-lookup"><span data-stu-id="78fb2-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78fb2-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78fb2-125">Requirements</span></span>  
  
|<span data-ttu-id="78fb2-126">MOF</span><span class="sxs-lookup"><span data-stu-id="78fb2-126">MOF</span></span>|<span data-ttu-id="78fb2-127">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="78fb2-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="78fb2-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="78fb2-128">Namespace</span></span>|<span data-ttu-id="78fb2-129">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="78fb2-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78fb2-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="78fb2-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
