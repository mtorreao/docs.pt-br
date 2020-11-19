---
title: Usando o Azure Key Vault para proteger segredos no momento da produção
description: Segurança em microsserviços e aplicativos Web do .NET – o Azure Key Vault é uma excelente maneira de lidar com os segredos do aplicativo que são totalmente controlados pelos administradores. Os administradores podem até mesmo atribuir e revogar os valores de desenvolvimento sem que os desenvolvedores precisam lidar com eles.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: d2d3690c0c8787ace6bcdfacbdb612f9ef957b98
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916236"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="655c0-104">Usar o Azure Key Vault para proteger os segredos no tempo de produção</span><span class="sxs-lookup"><span data-stu-id="655c0-104">Use Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="655c0-105">Os segredos armazenados como variáveis de ambiente ou armazenados pela ferramenta Secret Manager ainda são armazenados localmente e descriptografados no computador.</span><span class="sxs-lookup"><span data-stu-id="655c0-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="655c0-106">Uma opção mais segura para armazenar segredos é o [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), que oferece um local seguro e central para armazenar chaves e segredos.</span><span class="sxs-lookup"><span data-stu-id="655c0-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="655c0-107">O **Azure.Extensions.AspNetCore.Configuração.** O pacote de segredos permite que um aplicativo ASP.NET Core Leia informações de configuração de Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="655c0-107">The **Azure.Extensions.AspNetCore.Configuration.Secrets** package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="655c0-108">Para começar a usar os segredos de um Azure Key Vault, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="655c0-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

1. <span data-ttu-id="655c0-109">Registre seu aplicativo como um aplicativo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="655c0-109">Register your application as an Azure AD application.</span></span> <span data-ttu-id="655c0-110">(O acesso aos cofres de chaves é gerenciado pelo Azure AD.) Isso pode ser feito por meio do portal de gerenciamento do Azure. </span><span class="sxs-lookup"><span data-stu-id="655c0-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>\

   <span data-ttu-id="655c0-111">Ou, se você desejar que seu aplicativo seja autenticado usando um certificado em vez de um segredo do cliente ou senha, use o cmdlet do PowerShell [New-AzADApplication](/powershell/module/az.resources/new-azadapplication).</span><span class="sxs-lookup"><span data-stu-id="655c0-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzADApplication](/powershell/module/az.resources/new-azadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="655c0-112">O certificado que você registrar com o Azure Key Vault precisa apenas de sua chave pública.</span><span class="sxs-lookup"><span data-stu-id="655c0-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="655c0-113">O aplicativo usará a chave privada.</span><span class="sxs-lookup"><span data-stu-id="655c0-113">Your application will use the private key.</span></span>

2. <span data-ttu-id="655c0-114">Permita que o aplicativo registrado acesse o Key Vault criando uma entidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="655c0-114">Give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="655c0-115">É possível fazer isso usando os seguintes comandos do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="655c0-115">You can do this using the following PowerShell commands:</span></span>

   ```powershell
   $sp = New-AzADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. <span data-ttu-id="655c0-116">Inclua o cofre de chaves como uma fonte de configuração em seu aplicativo chamando o método de extensão AzureKeyVaultConfigurationExtensions. AddAzureKeyVault ao criar uma <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> instância.</span><span class="sxs-lookup"><span data-stu-id="655c0-116">Include the key vault as a configuration source in your application by calling the AzureKeyVaultConfigurationExtensions.AddAzureKeyVault extension method when you create an <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> instance.</span></span>

<span data-ttu-id="655c0-117">Observe que a chamada de `AddAzureKeyVault` requer a ID do aplicativo que foi registrada e permitiu acesso ao Key Vault nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="655c0-117">Note that calling `AddAzureKeyVault` requires the application ID that was registered and given access to the key vault in the previous steps.</span></span> <span data-ttu-id="655c0-118">Ou, primeiro, você pode executar o comando CLI do Azure: `az login` e, em seguida, usar uma sobrecarga do `AddAzureKeyVault` que usa um DefaultAzureCredential no lugar do cliente.</span><span class="sxs-lookup"><span data-stu-id="655c0-118">Or you can firstly running the Azure CLI command: `az login`, then using an overload of `AddAzureKeyVault` that takes a DefaultAzureCredential in place of the client.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="655c0-119">É recomendável registrar Azure Key Vault como o último provedor de configuração, para que ele possa substituir os valores de configuração dos provedores anteriores.</span><span class="sxs-lookup"><span data-stu-id="655c0-119">We recommend that you register Azure Key Vault as the last configuration provider, so it can override configuration values from previous providers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="655c0-120">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="655c0-120">Additional resources</span></span>

- <span data-ttu-id="655c0-121">**Usando Azure Key Vault para proteger os segredos do aplicativo** </span><span class="sxs-lookup"><span data-stu-id="655c0-121">**Using Azure Key Vault to protect application secrets** </span></span>\
  [https://docs.microsoft.com/azure/architecture/multitenant-identity](/azure/architecture/multitenant-identity-keyvault)

- <span data-ttu-id="655c0-122">**Armazenamento seguro de segredos do aplicativo durante o desenvolvimento** </span><span class="sxs-lookup"><span data-stu-id="655c0-122">**Safe storage of app secrets during development** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/app-secrets](/aspnet/core/security/app-secrets)

- <span data-ttu-id="655c0-123">**Configurando a proteção de dados** </span><span class="sxs-lookup"><span data-stu-id="655c0-123">**Configuring data protection** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview](/aspnet/core/security/data-protection/configuration/overview)

- <span data-ttu-id="655c0-124">**Tempo de vida e gerenciamento de chaves de proteção de dados no ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="655c0-124">**Data Protection key management and lifetime in ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings](/aspnet/core/security/data-protection/configuration/default-settings)

- <span data-ttu-id="655c0-125">**Microsoft.Extensions.Configuração** Repositório GitHub.</span><span class="sxs-lookup"><span data-stu-id="655c0-125">**Microsoft.Extensions.Configuration** GitHub repository.</span></span> \
  <https://github.com/dotnet/extensions/tree/master/src/Configuration>

>[!div class="step-by-step"]
><span data-ttu-id="655c0-126">[Anterior](developer-app-secrets-storage.md) 
> [Avançar](../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="655c0-126">[Previous](developer-app-secrets-storage.md)
[Next](../key-takeaways.md)</span></span>
