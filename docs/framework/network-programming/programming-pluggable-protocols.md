---
title: Programando protocolos conectáveis
description: Saiba como as classes abstract WebRequest e WebResponse dão suporte a protocolos conectáveis, que permitem que um aplicativo obtenha dados sem especificar um protocolo.
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- WebResponse class, pluggable protocols
- sending data, pluggable protocols
- network resources, pluggable protocols
- Internet, pluggable protocols
- programming pluggable protocols
- pluggable protocols, programming
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
ms.openlocfilehash: a3f8106b238c28de77362e73aa26667209f6b517
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263172"
---
# <a name="programming-pluggable-protocols"></a><span data-ttu-id="7906c-103">Programando protocolos conectáveis</span><span class="sxs-lookup"><span data-stu-id="7906c-103">Programming Pluggable Protocols</span></span>

<span data-ttu-id="7906c-104">As classes abstratas <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> fornecem a base para protocolos conectáveis.</span><span class="sxs-lookup"><span data-stu-id="7906c-104">The abstract <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide the base for pluggable protocols.</span></span> <span data-ttu-id="7906c-105">Derivando classes específicas de protocolo de <xref:System.Net.WebRequest> e de <xref:System.Net.WebResponse>, um aplicativo pode solicitar dados de um recurso de Internet e ler a resposta sem especificar o protocolo que está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="7906c-105">By deriving protocol-specific classes from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, an application can request data from an Internet resource and read the response without specifying the protocol being used.</span></span>  
  
 <span data-ttu-id="7906c-106">Antes de criar um <xref:System.Net.WebRequest> específico de protocolo, você deve registrar o respectivo método Create.</span><span class="sxs-lookup"><span data-stu-id="7906c-106">Before you can create a protocol-specific <xref:System.Net.WebRequest>, you must register its Create method.</span></span> <span data-ttu-id="7906c-107">Use o método <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> estático de <xref:System.Net.WebRequest> para registrar um <xref:System.Net.WebRequest> descendente para lidar com um conjunto de solicitações para um determinado esquema de Internet, para um esquema e servidor ou para um esquema, servidor e caminho.</span><span class="sxs-lookup"><span data-stu-id="7906c-107">Use the static <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> method of <xref:System.Net.WebRequest> to register a <xref:System.Net.WebRequest> descendant to handle a set of requests to a particular Internet scheme, to a scheme and server, or to a scheme, server, and path.</span></span>  
  
 <span data-ttu-id="7906c-108">Na maioria dos casos, você será capaz de enviar e receber dados usando os métodos e propriedades da classe <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="7906c-108">In most cases you will be able to send and receive data using the methods and properties of the <xref:System.Net.WebRequest> class.</span></span> <span data-ttu-id="7906c-109">No entanto, se você precisar acessar propriedades específicas de protocolo, você pode fazer conversão de tipo de um <xref:System.Net.WebRequest> para uma instância de classe derivada específica.</span><span class="sxs-lookup"><span data-stu-id="7906c-109">However, if you need to access protocol-specific properties, you can typecast a <xref:System.Net.WebRequest> to a specific derived-class instance.</span></span>  
  
 <span data-ttu-id="7906c-110">Para tirar proveito dos protocolos conectáveis, seus descendentes de <xref:System.Net.WebRequest> devem fornecer uma transação de solicitação e resposta padrão que não requer que propriedades específicas de protocolo sejam definidas.</span><span class="sxs-lookup"><span data-stu-id="7906c-110">To take advantage of pluggable protocols, your <xref:System.Net.WebRequest> descendants must provide a default request-and-response transaction that does not require protocol-specific properties to be set.</span></span> <span data-ttu-id="7906c-111">Por exemplo, a classe <xref:System.Net.HttpWebRequest> que implementa a classe <xref:System.Net.WebRequest> para HTTP, fornece uma solicitação `GET` por padrão e retorna um <xref:System.Net.HttpWebResponse> que contém o fluxo retornado do servidor Web.</span><span class="sxs-lookup"><span data-stu-id="7906c-111">For example, the <xref:System.Net.HttpWebRequest> class, which implements the <xref:System.Net.WebRequest> class for HTTP, provides a `GET` request by default and returns an <xref:System.Net.HttpWebResponse> that contains the stream returned from the Web server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7906c-112">Veja também</span><span class="sxs-lookup"><span data-stu-id="7906c-112">See also</span></span>

- [<span data-ttu-id="7906c-113">Derivando de WebRequest</span><span class="sxs-lookup"><span data-stu-id="7906c-113">Deriving from WebRequest</span></span>](deriving-from-webrequest.md)
- [<span data-ttu-id="7906c-114">Derivando de WebResponse</span><span class="sxs-lookup"><span data-stu-id="7906c-114">Deriving from WebResponse</span></span>](deriving-from-webresponse.md)
- [<span data-ttu-id="7906c-115">Programação de rede no .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7906c-115">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="7906c-116">Como: Fazer a conversão de tipo de uma WebRequest para acessar propriedades específicas de protocolo</span><span class="sxs-lookup"><span data-stu-id="7906c-116">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>](how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)
