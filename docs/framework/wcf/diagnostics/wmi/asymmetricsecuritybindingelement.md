---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 00485ff80a0064e700d99203de3aa581d3761f30
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255722"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="f0b23-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f0b23-102">AsymmetricSecurityBindingElement</span></span>

<span data-ttu-id="f0b23-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f0b23-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0b23-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f0b23-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f0b23-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f0b23-105">Methods</span></span>  

 <span data-ttu-id="f0b23-106">A classe AsymmetricSecurityBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="f0b23-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f0b23-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="f0b23-107">Properties</span></span>  

 <span data-ttu-id="f0b23-108">A classe AsymmetricSecurityBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="f0b23-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="f0b23-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="f0b23-109">MessageProtectionOrder</span></span>  

 <span data-ttu-id="f0b23-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f0b23-110">Data type: string</span></span>  
  
 <span data-ttu-id="f0b23-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f0b23-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0b23-112">A ordem de criptografia e assinatura de mensagem para esta associação.</span><span class="sxs-lookup"><span data-stu-id="f0b23-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="f0b23-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="f0b23-113">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="f0b23-114">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="f0b23-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="f0b23-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f0b23-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0b23-116">Se a associação requer confirmação de assinatura.</span><span class="sxs-lookup"><span data-stu-id="f0b23-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0b23-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0b23-117">Requirements</span></span>  
  
|<span data-ttu-id="f0b23-118">MOF</span><span class="sxs-lookup"><span data-stu-id="f0b23-118">MOF</span></span>|<span data-ttu-id="f0b23-119">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="f0b23-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f0b23-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="f0b23-120">Namespace</span></span>|<span data-ttu-id="f0b23-121">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f0b23-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0b23-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="f0b23-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
