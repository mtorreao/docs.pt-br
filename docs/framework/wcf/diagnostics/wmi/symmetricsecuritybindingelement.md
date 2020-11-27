---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: c618b5b41790b04a84b4c50fe47baa2c0cb05ab2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274095"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="9ebf7-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9ebf7-102">SymmetricSecurityBindingElement</span></span>

<span data-ttu-id="9ebf7-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9ebf7-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ebf7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9ebf7-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9ebf7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9ebf7-105">Methods</span></span>  

 <span data-ttu-id="9ebf7-106">A classe SymmetricSecurityBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9ebf7-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="9ebf7-107">Properties</span></span>  

 <span data-ttu-id="9ebf7-108">A classe SymmetricSecurityBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="9ebf7-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="9ebf7-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="9ebf7-109">MessageProtectionOrder</span></span>  

 <span data-ttu-id="9ebf7-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9ebf7-110">Data type: string</span></span>  
  
 <span data-ttu-id="9ebf7-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="9ebf7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ebf7-112">A ordem de criptografia e assinatura de mensagem para esta associação.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="9ebf7-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="9ebf7-113">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="9ebf7-114">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="9ebf7-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="9ebf7-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="9ebf7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ebf7-116">Se a associação requer confirmação de assinatura.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ebf7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ebf7-117">Requirements</span></span>  
  
|<span data-ttu-id="9ebf7-118">MOF</span><span class="sxs-lookup"><span data-stu-id="9ebf7-118">MOF</span></span>|<span data-ttu-id="9ebf7-119">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9ebf7-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="9ebf7-120">Namespace</span></span>|<span data-ttu-id="9ebf7-121">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9ebf7-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ebf7-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="9ebf7-122">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
