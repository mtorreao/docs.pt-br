---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 9cac7192d5c34de55fe0bd6a4921a41387e985f8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250431"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="ce017-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="ce017-102">MustUnderstandBehavior</span></span>

<span data-ttu-id="ce017-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="ce017-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce017-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ce017-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ce017-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ce017-105">Methods</span></span>  

 <span data-ttu-id="ce017-106">A classe MustUnderstandBehavior não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="ce017-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ce017-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="ce017-107">Properties</span></span>  

 <span data-ttu-id="ce017-108">A classe MustUnderstandBehavior tem a seguinte propriedade:</span><span class="sxs-lookup"><span data-stu-id="ce017-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="ce017-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="ce017-109">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="ce017-110">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="ce017-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="ce017-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="ce017-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ce017-112">Quando `true` , todos os cabeçalhos SOAP com o `MustUnderstand` atributo que não são tratados fazem com que o comportamento gere uma exceção.</span><span class="sxs-lookup"><span data-stu-id="ce017-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce017-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce017-113">Requirements</span></span>  
  
|<span data-ttu-id="ce017-114">MOF</span><span class="sxs-lookup"><span data-stu-id="ce017-114">MOF</span></span>|<span data-ttu-id="ce017-115">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="ce017-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ce017-116">Namespace</span><span class="sxs-lookup"><span data-stu-id="ce017-116">Namespace</span></span>|<span data-ttu-id="ce017-117">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ce017-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce017-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="ce017-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
