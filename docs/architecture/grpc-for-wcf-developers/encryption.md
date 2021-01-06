---
title: Criptografia e segurança de rede-gRPC para desenvolvedores do WCF
description: Algumas observações sobre segurança de rede e criptografia no gRPC
ms.date: 12/15/2020
ms.openlocfilehash: 0735158ed69ce425c4f00eed6c42689b888a1885
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938618"
---
# <a name="encryption-and-network-security"></a>Criptografia e segurança de rede

O WCF (modelo de segurança de rede para Windows Communication Foundation) é extensivo e complexo. Ele inclui segurança em nível de transporte usando HTTPS ou TLS via TCP e segurança em nível de mensagem usando a especificação de WS-Security para criptografar mensagens individuais.

gRPC deixa a rede segura para o protocolo HTTP/2 subjacente, que você pode proteger usando certificados TLS.

Navegadores da Web insistem no uso de conexões TLS para HTTP/2, mas com a maioria dos clientes programáticos, incluindo. NET `HttpClient` , pode usar http/2 em conexões não criptografadas. `HttpClient` o requer criptografia por padrão, mas você pode substituir esse comportamento usando uma <xref:System.AppContext> opção.

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

Para APIs públicas, você sempre deve usar conexões TLS e fornecer certificados válidos para seus serviços de uma autoridade SSL apropriada. O [LetsEncrypt](https://letsencrypt.org) fornece certificados SSL gratuitos e automatizados, e a maioria das infra-estruturas de hospedagem atualmente dá suporte ao padrão LetsEncrypt com plug-ins ou extensões comuns.

Para serviços internos em uma rede corporativa, você ainda deve considerar o uso do TLS para proteger o tráfego de rede de e para seus serviços gRPCs.

Se você precisar usar o TLS explícito entre os serviços em execução no kubernetes, considere usar uma autoridade de certificação no cluster e um controlador do Gerenciador de certificados como [CERT-Manager](https://docs.cert-manager.io/en/latest/). Você pode atribuir certificados automaticamente aos serviços no momento da implantação.

>[!div class="step-by-step"]
>[Anterior](channel-credentials.md) 
> [Avançar](grpc-in-production.md)
