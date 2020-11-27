---
title: Comunicação assíncrona
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: db5a8f415479967d7579357bd0c8058c7fb961c5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255839"
---
# <a name="asynchronous-communication"></a>Comunicação assíncrona

Este exemplo demonstra como a comunicação entre dois serviços diferentes de Windows Workflow Foundation (WF) é feita de forma assíncrona por padrão.  
  
## <a name="demonstrates"></a>Demonstra  

 Comunicação assíncrona entre os serviços de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .  
  
## <a name="discussion"></a>Discussão  

 Este exemplo mostra como a comunicação entre aplicativos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] é feita de forma assíncrona usando as atividades de mensagem fornecidas pelo.NET Framework.  
  
 Esse exemplo consiste em três projetos.  
  
 CreditCheckService  
 Esse serviço recebe a pontuação de crédito de uma pessoa específico ou o valor do item para adquirir, e então decidir se o crédito é dado a pessoa.  
  
 RentalApprovalService  
 Esse serviço recebe um aplicativo de uma pessoa que é a necessidade de qualquer crédito. Esse serviço se comunica de forma assíncrona com `CreditCheckService` para decidir se o aplicativo de crédito é válido.  
  
 Cliente  
 O cliente se comunica com forma `RentalApprovalService` para saber se o crédito é certo.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Para configurar, compilar, e executar o exemplo  
  
1. Clique com o botão direito do mouse na solução **AsynchronousCommunication** e selecione **Propriedades**.  
  
2. Em **Propriedades comuns**, selecione **projeto de inicialização** e selecione **vários projetos de inicialização**.  
  
3. Mova **RentalApprovalService** para a primeira posição na lista, seguida por **CreditCheckService**, seguido pelo **cliente**. Defina a ação **Iniciar** em todos os três projetos.  
  
4. Clique em **OK** e pressione F5 para executar o exemplo.  
  
> [!IMPORTANT]
> Os exemplos podem já estar instalados no seu computador. Verifique o seguinte diretório (padrão) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se esse diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos de Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para baixar todos os Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos. Este exemplo está localizado no seguinte diretório.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
