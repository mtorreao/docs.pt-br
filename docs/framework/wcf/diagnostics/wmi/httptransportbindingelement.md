---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 2be32591c4844cc6d5d0f02916dd1563bb15dc2a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288782"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="f2559-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f2559-102">HttpTransportBindingElement</span></span>

<span data-ttu-id="f2559-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f2559-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2559-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f2559-104">Syntax</span></span>  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f2559-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f2559-105">Methods</span></span>  

 <span data-ttu-id="f2559-106">A classe HttpTransportBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="f2559-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f2559-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="f2559-107">Properties</span></span>  

 <span data-ttu-id="f2559-108">A classe HttpTransportBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="f2559-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="f2559-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="f2559-109">AllowCookies</span></span>  

 <span data-ttu-id="f2559-110">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="f2559-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="f2559-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-112">Um valor que indica se o cliente aceita cookies e os propaga em solicitações futuras.</span><span class="sxs-lookup"><span data-stu-id="f2559-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="f2559-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="f2559-113">AuthenticationScheme</span></span>  

 <span data-ttu-id="f2559-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f2559-114">Data type: string</span></span>  
  
 <span data-ttu-id="f2559-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-116">O esquema de autenticação usado para autenticar solicitações de cliente sendo processadas por um ouvinte HTTP.</span><span class="sxs-lookup"><span data-stu-id="f2559-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="f2559-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="f2559-117">BypassProxyOnLocal</span></span>  

 <span data-ttu-id="f2559-118">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="f2559-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="f2559-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-120">Um valor que indica se os proxies são ignorados para endereços locais.</span><span class="sxs-lookup"><span data-stu-id="f2559-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="f2559-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="f2559-121">HostNameComparisonMode</span></span>  

 <span data-ttu-id="f2559-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f2559-122">Data type: string</span></span>  
  
 <span data-ttu-id="f2559-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-124">Um valor que indica se o nome do host é usado para acessar o serviço ao fazer a correspondência no URI.</span><span class="sxs-lookup"><span data-stu-id="f2559-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="f2559-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="f2559-125">KeepAliveEnabled</span></span>  

 <span data-ttu-id="f2559-126">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="f2559-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="f2559-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-128">Quando habilitadas, as conexões HTTP são mantidas ativas, independentemente do nível de atividade.</span><span class="sxs-lookup"><span data-stu-id="f2559-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="f2559-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="f2559-129">MaxBufferSize</span></span>  

 <span data-ttu-id="f2559-130">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="f2559-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="f2559-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-132">O tamanho máximo do pool de buffers.</span><span class="sxs-lookup"><span data-stu-id="f2559-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="f2559-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="f2559-133">ProxyAddress</span></span>  

 <span data-ttu-id="f2559-134">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f2559-134">Data type: string</span></span>  
  
 <span data-ttu-id="f2559-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-136">Um URI que contém o endereço do proxy a ser usado para solicitações HTTP.</span><span class="sxs-lookup"><span data-stu-id="f2559-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="f2559-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="f2559-137">ProxyAuthenticationScheme</span></span>  

 <span data-ttu-id="f2559-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f2559-138">Data type: string</span></span>  
  
 <span data-ttu-id="f2559-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-140">O esquema de autenticação usado para autenticar solicitações de cliente sendo processadas por um proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="f2559-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="f2559-141">Realm</span><span class="sxs-lookup"><span data-stu-id="f2559-141">Realm</span></span>  

 <span data-ttu-id="f2559-142">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f2559-142">Data type: string</span></span>  
  
 <span data-ttu-id="f2559-143">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-144">O realm de autenticação.</span><span class="sxs-lookup"><span data-stu-id="f2559-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="f2559-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="f2559-145">TransferMode</span></span>  

 <span data-ttu-id="f2559-146">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f2559-146">Data type: string</span></span>  
  
 <span data-ttu-id="f2559-147">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-148">Um valor que especifica se as mensagens são armazenadas em buffer ou transmitidas ou uma solicitação ou resposta.</span><span class="sxs-lookup"><span data-stu-id="f2559-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="f2559-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="f2559-149">UnsafeConnectionNtlmAuthentication</span></span>  

 <span data-ttu-id="f2559-150">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="f2559-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="f2559-151">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-152">Um valor que indica se o compartilhamento de conexão não segura está habilitado no servidor.</span><span class="sxs-lookup"><span data-stu-id="f2559-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="f2559-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="f2559-153">UseDefaultWebProxy</span></span>  

 <span data-ttu-id="f2559-154">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="f2559-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="f2559-155">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f2559-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2559-156">Um valor que indica se as configurações de proxy de todo o computador são usadas em vez das configurações específicas do usuário.</span><span class="sxs-lookup"><span data-stu-id="f2559-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2559-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2559-157">Requirements</span></span>  
  
|<span data-ttu-id="f2559-158">MOF</span><span class="sxs-lookup"><span data-stu-id="f2559-158">MOF</span></span>|<span data-ttu-id="f2559-159">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="f2559-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f2559-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="f2559-160">Namespace</span></span>|<span data-ttu-id="f2559-161">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f2559-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2559-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="f2559-162">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
