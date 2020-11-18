---
title: Chamando métodos assíncronos usando IAsyncResult
ms.date: 03/30/2017
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 20aafd45c323a609b3cc7fb5a1a6378d43548fcb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830448"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>Chamando métodos assíncronos usando IAsyncResult

Os tipos nas bibliotecas .NET e bibliotecas de classe de terceiros podem fornecer métodos que permitem que um aplicativo continue a execução enquanto executa operações assíncronas em threads diferentes do thread do aplicativo principal. As seções a seguir descrevem e fornecem exemplos de código que demonstram diferentes maneiras de chamar métodos assíncronos que usam o padrão de design <xref:System.IAsyncResult>.  
  
- [Bloqueio da execução do aplicativo encerrando uma operação assíncrona](blocking-application-execution-by-ending-an-async-operation.md).  
  
- [Bloqueando a execução do aplicativo usando um AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).  
  
- [Sondando o status de uma operação assíncrona](polling-for-the-status-of-an-asynchronous-operation.md).  
  
- [Usando um delegado AsyncCallback para finalizar uma operação assíncrona](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>Confira também

- [Padrão assíncrono baseado em evento (EAP)](event-based-asynchronous-pattern-eap.md)
- [Visão geral do padrão assíncrono baseado em evento](event-based-asynchronous-pattern-overview.md)
