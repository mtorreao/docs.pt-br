---
title: 'Mitigação: método X509CertificateClaimSet.FindClaims'
description: Saiba como o método X509CertificateClaimSet. FindClaims foi alterado para aplicativos direcionados .NET Framework 4.6.1.
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
ms.openlocfilehash: ed9e345f9e48156f37f493caa78e6b3901cecf23
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253564"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="39d18-103">Mitigação: método X509CertificateClaimSet.FindClaims</span><span class="sxs-lookup"><span data-stu-id="39d18-103">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>

<span data-ttu-id="39d18-104">A partir de aplicativos direcionados .NET Framework 4.6.1, o <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> método tentará corresponder o `claimType` argumento com todas as entradas DNS em seu campo San.</span><span class="sxs-lookup"><span data-stu-id="39d18-104">Starting with apps that target .NET Framework 4.6.1, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="39d18-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="39d18-105">Impact</span></span>  

 <span data-ttu-id="39d18-106">Essa alteração afeta somente os aplicativos que se destinam a versões do .NET Framework, começando pelo .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="39d18-106">This change only affects apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>  
  
 <span data-ttu-id="39d18-107">Para aplicativos direcionados a versões anteriores do .NET Framework, o método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> tenta corresponder o argumento `claimType` apenas com a última entrada DNS.</span><span class="sxs-lookup"><span data-stu-id="39d18-107">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="39d18-108">Atenuação</span><span class="sxs-lookup"><span data-stu-id="39d18-108">Mitigation</span></span>  

 <span data-ttu-id="39d18-109">Se essa alteração for indesejável, os aplicativos que se destinam a versões do .NET Framework a partir do .NET Framework 4.6.1 podem recusar isso adicionando a configuração a seguir à [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) seção do arquivo de configuração do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="39d18-109">If this change is undesirable, apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1 can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />
</runtime>  
```  
  
 <span data-ttu-id="39d18-110">Além disso, os aplicativos que se destinam a versões anteriores do .NET Framework, mas que estão sendo executados no .NET Framework 4.6.1 e versões posteriores podem aceitar esse comportamento, adicionando a configuração a seguir à [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) seção do arquivo de configuração do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="39d18-110">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="39d18-111">Veja também</span><span class="sxs-lookup"><span data-stu-id="39d18-111">See also</span></span>

- [<span data-ttu-id="39d18-112">Compatibilidade de aplicativos</span><span class="sxs-lookup"><span data-stu-id="39d18-112">Application compatibility</span></span>](application-compatibility.md)
