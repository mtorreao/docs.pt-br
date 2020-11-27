---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 2de417e4a4f5c6197551c1408da6907e2fa7c635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268996"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="cf3fa-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="cf3fa-102">PeerSecuritySettings</span></span>

<span data-ttu-id="cf3fa-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="cf3fa-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf3fa-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cf3fa-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cf3fa-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cf3fa-105">Methods</span></span>  

 <span data-ttu-id="cf3fa-106">A classe PeerSecuritySettings não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="cf3fa-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cf3fa-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="cf3fa-107">Properties</span></span>  

 <span data-ttu-id="cf3fa-108">A classe PeerSecuritySettings tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="cf3fa-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="cf3fa-109">Mode</span><span class="sxs-lookup"><span data-stu-id="cf3fa-109">Mode</span></span>  

 <span data-ttu-id="cf3fa-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf3fa-110">Data type: string</span></span>  
  
 <span data-ttu-id="cf3fa-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="cf3fa-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf3fa-112">Se a segurança em nível de transporte e nível de mensagem são usadas por um ponto de extremidade configurado com a associação.</span><span class="sxs-lookup"><span data-stu-id="cf3fa-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="cf3fa-113">Transport</span><span class="sxs-lookup"><span data-stu-id="cf3fa-113">Transport</span></span>  

 <span data-ttu-id="cf3fa-114">Tipo de dados: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="cf3fa-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="cf3fa-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="cf3fa-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf3fa-116">Configurações de segurança de transporte.</span><span class="sxs-lookup"><span data-stu-id="cf3fa-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf3fa-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf3fa-117">Requirements</span></span>  
  
|<span data-ttu-id="cf3fa-118">MOF</span><span class="sxs-lookup"><span data-stu-id="cf3fa-118">MOF</span></span>|<span data-ttu-id="cf3fa-119">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="cf3fa-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cf3fa-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="cf3fa-120">Namespace</span></span>|<span data-ttu-id="cf3fa-121">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cf3fa-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf3fa-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="cf3fa-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
