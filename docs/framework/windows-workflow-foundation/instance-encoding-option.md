---
title: Padrão de codificação de instância
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: 416394eb346a7c82385da32a89bd54179b255cd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279890"
---
# <a name="instance-encoding-option"></a>Padrão de codificação de instância

A propriedade de **opção de codificação de instância** do repositório da instância do fluxo de trabalho SQL permite especificar se o provedor de persistência do SQL deve compactar as informações de estado da instância do fluxo de trabalho usando o algoritmo gzip antes de salvar as informações no banco de dados de persistência. Os valores permitidos para essa propriedade são: GZip e quaisquer. O valor padrão é Nenhum. A lista a seguir descreve as opções.  
  
1. **Gzip**. O provedor de persistência codificação informações de estado usando o algoritmo de GZip antes de manter informações de estado na base de dados de persistência.  
  
2. **None**. O provedor de persistência não codificação informações de estado antes de salvar informações na base de dados de persistência.  
  
 Informações de estado da instância de fluxo de trabalho de codificação que usa o GZip reduz o consumo de memória na base de dados SQL e também reduz o consumo de rede se o base de dados reside em um outro computador na rede do computador no qual o host serviço de fluxo de trabalho está sendo executado. Uma orientação geral é definir a propriedade da **opção de codificação da instância** como **None** se o estado da instância do fluxo de trabalho for pequeno.
