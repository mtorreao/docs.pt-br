---
title: Exceções de hospedagem
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: 342420f10ed53e4f4786ed9506cfde5fbfcfc957
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263328"
---
# <a name="hosting-exceptions"></a>Exceções de hospedagem

Este tópico lista todas as exceções geradas pela hospedagem.  
  
## <a name="exception-list"></a>Lista de exceções  
  
|Código do recurso|Cadeia de caracteres de recurso|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|O URI completo não é permitido. Não são permitidos URIs completos para a API de ServiceHostingEnvironment. EnsureServiceAvailable. Use um caminho virtual para o serviço correspondente.|  
|Hosting_BuildProviderCouldNotCreateType|O tipo CLR especificado não pode ser carregado durante a compilação do serviço. Verifique se esse tipo está definido em um arquivo de origem localizado no \\ diretório \ App_Code do aplicativo, contido em um assembly compilado localizado no diretório \bin do aplicativo \\ , ou presente em um assembly instalado no cache de assembly global. O nome do tipo diferencia maiúsculas de minúsculas. Os diretórios como \\ \ App_Code e \\ \Bin devem estar localizados no diretório raiz do aplicativo. Os \\ diretórios \ App_Code e \\ \Bin não podem ser aninhados em subdiretórios.|
