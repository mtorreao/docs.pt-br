---
title: 'Como: implantar um aplicativo de integração COM+'
ms.date: 03/30/2017
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
ms.openlocfilehash: 5f2e64ed06b98db50259edf8ef307ce430b8be38
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289783"
---
# <a name="how-to-deploy-a-com-integration-application"></a><span data-ttu-id="b5af0-102">Como: implantar um aplicativo de integração COM+</span><span class="sxs-lookup"><span data-stu-id="b5af0-102">How to: Deploy a COM+ Integration Application</span></span>

<span data-ttu-id="b5af0-103">Depois de escrever um aplicativo de integração COM+, talvez você queira implantá-lo em outro computador.</span><span class="sxs-lookup"><span data-stu-id="b5af0-103">Once you have written a COM+ integration application, you may want to deploy it on another machine.</span></span> <span data-ttu-id="b5af0-104">Este tópico descreve como mover um aplicativo de integração COM+ de um computador para outro.</span><span class="sxs-lookup"><span data-stu-id="b5af0-104">This topic describes how to move a COM+ integration application from one machine to another.</span></span>  
  
### <a name="moving-a-com-hosted-integration-app"></a><span data-ttu-id="b5af0-105">Movendo um aplicativo de integração hospedado COM+</span><span class="sxs-lookup"><span data-stu-id="b5af0-105">Moving a COM+ hosted Integration App</span></span>  
  
1. <span data-ttu-id="b5af0-106">Verifique se o WCF está instalado em ambos os computadores.</span><span class="sxs-lookup"><span data-stu-id="b5af0-106">Ensure that WCF is installed on both machines.</span></span>  
  
2. <span data-ttu-id="b5af0-107">Exporte o aplicativo do computador A.</span><span class="sxs-lookup"><span data-stu-id="b5af0-107">Export the application from machine A.</span></span>  
  
3. <span data-ttu-id="b5af0-108">Importe o aplicativo no computador B.</span><span class="sxs-lookup"><span data-stu-id="b5af0-108">Import the application on machine B.</span></span>  
  
4. <span data-ttu-id="b5af0-109">Defina o diretório raiz do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b5af0-109">Set the Application Root Directory.</span></span> <span data-ttu-id="b5af0-110">Por convenção, é% PROGRAMfiles%/ComPlus Applications/{AppGUID}.</span><span class="sxs-lookup"><span data-stu-id="b5af0-110">By convention, this is %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span></span>  
  
5. <span data-ttu-id="b5af0-111">Copie o Application.config e os arquivos. manifest do aplicativo do diretório raiz do aplicativo no computador A para o diretório raiz do aplicativo no computador B.</span><span class="sxs-lookup"><span data-stu-id="b5af0-111">Copy the Application.config and Application.manifest files from the application root directory on machine A to the application root directory on machine B.</span></span>  
  
6. <span data-ttu-id="b5af0-112">Edite os endereços de ponto de extremidade de serviço no arquivo de Application.config no computador B para identificar o computador apropriado.</span><span class="sxs-lookup"><span data-stu-id="b5af0-112">Edit the service endpoint addresses in the Application.config file on machine B to identify the appropriate machine.</span></span> <span data-ttu-id="b5af0-113">Por exemplo, altere `http://machineA/MyService` para `http://machineB/MyService`.</span><span class="sxs-lookup"><span data-stu-id="b5af0-113">For example, change `http://machineA/MyService` to `http://machineB/MyService`.</span></span>  
  
### <a name="moving-a-web-hosted-integration-application"></a><span data-ttu-id="b5af0-114">Movendo um aplicativo de integração hospedado na Web</span><span class="sxs-lookup"><span data-stu-id="b5af0-114">Moving a Web-hosted integration application</span></span>  
  
1. <span data-ttu-id="b5af0-115">Verifique se o WCF está instalado em ambos os computadores.</span><span class="sxs-lookup"><span data-stu-id="b5af0-115">Ensure that WCF is installed on both machines.</span></span>  
  
2. <span data-ttu-id="b5af0-116">Exporte o aplicativo do computador A.</span><span class="sxs-lookup"><span data-stu-id="b5af0-116">Export the application from machine A.</span></span>  
  
3. <span data-ttu-id="b5af0-117">Importe o aplicativo no computador B.</span><span class="sxs-lookup"><span data-stu-id="b5af0-117">Import the application on machine B.</span></span>  
  
4. <span data-ttu-id="b5af0-118">Crie uma VRoot do IIS no computador B.</span><span class="sxs-lookup"><span data-stu-id="b5af0-118">Create an IIS vroot on machine B.</span></span>  
  
5. <span data-ttu-id="b5af0-119">Copie o arquivo. svc (ComponentName. svc) e o arquivo Web.config do vroot no computador a para o vroot recentemente criado no computador B.</span><span class="sxs-lookup"><span data-stu-id="b5af0-119">Copy the .svc file (componentName.svc) and the Web.config file from the vroot on machine A to the newly created vroot on machine B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5af0-120">Veja também</span><span class="sxs-lookup"><span data-stu-id="b5af0-120">See also</span></span>

- [<span data-ttu-id="b5af0-121">Visão geral da integração com aplicativos COM+</span><span class="sxs-lookup"><span data-stu-id="b5af0-121">Integrating with COM+ Applications Overview</span></span>](integrating-with-com-plus-applications-overview.md)
- [<span data-ttu-id="b5af0-122">Como: definir configurações de serviço de COM+</span><span class="sxs-lookup"><span data-stu-id="b5af0-122">How to: Configure COM+ Service Settings</span></span>](how-to-configure-com-service-settings.md)
- [<span data-ttu-id="b5af0-123">Como: usar a ferramenta de configuração do modelo de serviço COM+</span><span class="sxs-lookup"><span data-stu-id="b5af0-123">How to: Use the COM+ Service Model Configuration Tool</span></span>](how-to-use-the-com-service-model-configuration-tool.md)
