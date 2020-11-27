---
title: 'Como: expor um feed como Atom e RSS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fe374932-67f5-487d-9325-f868812b92e4
ms.openlocfilehash: 1b03434e4f9552b714b40d54ba36c8468d0e2ccd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265356"
---
# <a name="how-to-expose-a-feed-as-both-atom-and-rss"></a><span data-ttu-id="4d07b-102">Como: expor um feed como Atom e RSS</span><span class="sxs-lookup"><span data-stu-id="4d07b-102">How to: Expose a Feed as Both Atom and RSS</span></span>

<span data-ttu-id="4d07b-103">Windows Communication Foundation (WCF) permite que você crie um serviço que expõe um feed de distribuição.</span><span class="sxs-lookup"><span data-stu-id="4d07b-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="4d07b-104">Este tópico discute como criar um serviço de distribuição que expõe um feed de distribuição usando o Atom 1,0 e o RSS 2,0.</span><span class="sxs-lookup"><span data-stu-id="4d07b-104">This topic discusses how to create a syndication service that exposes a syndication feed using both Atom 1.0 and RSS 2.0.</span></span> <span data-ttu-id="4d07b-105">Esse serviço expõe um ponto de extremidade que pode retornar um formato de distribuição.</span><span class="sxs-lookup"><span data-stu-id="4d07b-105">This service exposes one endpoint that can return either syndication format.</span></span> <span data-ttu-id="4d07b-106">Para simplificar, o serviço usado neste exemplo é hospedado internamente.</span><span class="sxs-lookup"><span data-stu-id="4d07b-106">For simplicity the service used in this sample is self hosted.</span></span> <span data-ttu-id="4d07b-107">Em um ambiente de produção, um serviço desse tipo seria hospedado no IIS ou WAS.</span><span class="sxs-lookup"><span data-stu-id="4d07b-107">In a production environment a service of this type would be hosted under IIS or WAS.</span></span> <span data-ttu-id="4d07b-108">Para obter mais informações sobre as diferentes opções de hospedagem do WCF, consulte [Hosting](hosting.md).</span><span class="sxs-lookup"><span data-stu-id="4d07b-108">For more information about the different WCF hosting options, see [Hosting](hosting.md).</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="4d07b-109">Para criar um serviço de distribuição básico</span><span class="sxs-lookup"><span data-stu-id="4d07b-109">To create a basic syndication service</span></span>  
  
1. <span data-ttu-id="4d07b-110">Defina um contrato de serviço usando uma interface marcada com o <xref:System.ServiceModel.Web.WebGetAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="4d07b-110">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="4d07b-111">Cada operação exposta como um feed de agregação retorna um <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> objeto.</span><span class="sxs-lookup"><span data-stu-id="4d07b-111">Each operation that is exposed as a syndication feed returns a <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> object.</span></span> <span data-ttu-id="4d07b-112">Observe os parâmetros para o <xref:System.ServiceModel.Web.WebGetAttribute> .</span><span class="sxs-lookup"><span data-stu-id="4d07b-112">Note the parameters for the <xref:System.ServiceModel.Web.WebGetAttribute>.</span></span> <span data-ttu-id="4d07b-113">`UriTemplate` Especifica a URL usada para invocar esta operação de serviço.</span><span class="sxs-lookup"><span data-stu-id="4d07b-113">`UriTemplate` specifies the URL used to invoke this service operation.</span></span> <span data-ttu-id="4d07b-114">A cadeia de caracteres para esse parâmetro contém literais e uma variável entre chaves ({*Format*}).</span><span class="sxs-lookup"><span data-stu-id="4d07b-114">The string for this parameter contains literals and a variable in braces ({*format*}).</span></span> <span data-ttu-id="4d07b-115">Essa variável corresponde ao parâmetro da operação de serviço `format` .</span><span class="sxs-lookup"><span data-stu-id="4d07b-115">This variable corresponds to the service operation's `format` parameter.</span></span> <span data-ttu-id="4d07b-116">Para obter mais informações, consulte <xref:System.UriTemplate>.</span><span class="sxs-lookup"><span data-stu-id="4d07b-116">For more information, see <xref:System.UriTemplate>.</span></span> <span data-ttu-id="4d07b-117">`BodyStyle` afeta como as mensagens enviadas e recebidas por essa operação de serviço são gravadas.</span><span class="sxs-lookup"><span data-stu-id="4d07b-117">`BodyStyle` affects how the messages that this service operation sends and receives are written.</span></span> <span data-ttu-id="4d07b-118"><xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> Especifica que os dados enviados para e dessa operação de serviço não são encapsulados por elementos XML definidos pela infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="4d07b-118"><xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> specifies that the data sent to and from this service operation are not wrapped by infrastructure-defined XML elements.</span></span> <span data-ttu-id="4d07b-119">Para obter mais informações, consulte <xref:System.ServiceModel.Web.WebMessageBodyStyle>.</span><span class="sxs-lookup"><span data-stu-id="4d07b-119">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle>.</span></span>  
  
     [!code-csharp[htAtomRss#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#0)]
     [!code-vb[htAtomRss#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#0)]  
  
    > [!NOTE]
    > <span data-ttu-id="4d07b-120">Use o <xref:System.ServiceModel.ServiceKnownTypeAttribute> para especificar os tipos que são retornados pelas operações de serviço nesta interface.</span><span class="sxs-lookup"><span data-stu-id="4d07b-120">Use the <xref:System.ServiceModel.ServiceKnownTypeAttribute> to specify the types that are returned by the service operations in this interface.</span></span>  
  
2. <span data-ttu-id="4d07b-121">Implemente o contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="4d07b-121">Implement the service contract.</span></span>  
  
     [!code-csharp[htAtomRss#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#1)]
     [!code-vb[htAtomRss#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#1)]  
  
3. <span data-ttu-id="4d07b-122">Crie um <xref:System.ServiceModel.Syndication.SyndicationFeed> objeto e adicione um autor, uma categoria e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="4d07b-122">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htAtomRss#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#2)]
     [!code-vb[htAtomRss#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#2)]  
  
4. <span data-ttu-id="4d07b-123">Crie vários <xref:System.ServiceModel.Syndication.SyndicationItem> objetos.</span><span class="sxs-lookup"><span data-stu-id="4d07b-123">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htAtomRss#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#3)]
     [!code-vb[htAtomRss#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#3)]  
  
5. <span data-ttu-id="4d07b-124">Adicione os <xref:System.ServiceModel.Syndication.SyndicationItem> objetos ao feed.</span><span class="sxs-lookup"><span data-stu-id="4d07b-124">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> objects to the feed.</span></span>  
  
     [!code-csharp[htAtomRss#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#4)]
     [!code-vb[htAtomRss#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#4)]  
  
6. <span data-ttu-id="4d07b-125">Use o parâmetro format para retornar o formato solicitado.</span><span class="sxs-lookup"><span data-stu-id="4d07b-125">Use the format parameter to return the requested format.</span></span>  
  
     [!code-csharp[htAtomRss#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#5)]
     [!code-vb[htAtomRss#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="4d07b-126">Para hospedar o serviço</span><span class="sxs-lookup"><span data-stu-id="4d07b-126">To host the service</span></span>  
  
1. <span data-ttu-id="4d07b-127">Crie um objeto <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4d07b-127">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span> <span data-ttu-id="4d07b-128">A <xref:System.ServiceModel.Web.WebServiceHost> classe adiciona automaticamente um ponto de extremidade no endereço base do serviço, a menos que um seja especificado no código ou na configuração.</span><span class="sxs-lookup"><span data-stu-id="4d07b-128">The <xref:System.ServiceModel.Web.WebServiceHost> class automatically adds an endpoint at the service's base address unless one is specified in code or configuration.</span></span> <span data-ttu-id="4d07b-129">Neste exemplo, nenhum ponto de extremidade é especificado, portanto, o ponto de extremidades padrão é exposto.</span><span class="sxs-lookup"><span data-stu-id="4d07b-129">In this sample, no endpoints are specified so the default endpoint is exposed.</span></span>  
  
     [!code-csharp[htAtomRss#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#6)]
     [!code-vb[htAtomRss#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#6)]  
  
2. <span data-ttu-id="4d07b-130">Abra o host de serviço, carregue o feed do serviço, exiba o feed e aguarde até que o usuário pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="4d07b-130">Open the service host, load the feed from the service, display the feed, and wait for the user to press ENTER.</span></span>  
  
     [!code-csharp[htAtomRss#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#8)]
     [!code-vb[htAtomRss#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="4d07b-131">Para chamar getblog com um HTTP GET</span><span class="sxs-lookup"><span data-stu-id="4d07b-131">To call GetBlog with an HTTP GET</span></span>  
  
1. <span data-ttu-id="4d07b-132">Abra o Internet Explorer, digite a seguinte URL e pressione ENTER: `http://localhost:8000/BlogService/GetBlog` .</span><span class="sxs-lookup"><span data-stu-id="4d07b-132">Open Internet Explorer, type the following URL, and press ENTER: `http://localhost:8000/BlogService/GetBlog`.</span></span>
  
     <span data-ttu-id="4d07b-133">A URL contém o endereço base do serviço ( `http://localhost:8000/BlogService` ), o endereço relativo do ponto de extremidade e a operação de serviço a ser chamada.</span><span class="sxs-lookup"><span data-stu-id="4d07b-133">The URL contains the base address of the service (`http://localhost:8000/BlogService`), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="4d07b-134">Para chamar getblog () do código</span><span class="sxs-lookup"><span data-stu-id="4d07b-134">To call GetBlog() from code</span></span>  
  
1. <span data-ttu-id="4d07b-135">Crie um <xref:System.Xml.XmlReader> com o endereço base e o método que você está chamando.</span><span class="sxs-lookup"><span data-stu-id="4d07b-135">Create an <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htAtomRss#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#9)]
     [!code-vb[htAtomRss#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#9)]  
  
2. <span data-ttu-id="4d07b-136">Chame o <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> método estático, passando o <xref:System.Xml.XmlReader> que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="4d07b-136">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htAtomRss#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#10)]
     [!code-vb[htAtomRss#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#10)]  
  
     <span data-ttu-id="4d07b-137">Isso invoca a operação de serviço e popula um novo <xref:System.ServiceModel.Syndication.SyndicationFeed> com o formatador retornado da operação de serviço.</span><span class="sxs-lookup"><span data-stu-id="4d07b-137">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3. <span data-ttu-id="4d07b-138">Acessar o objeto feed.</span><span class="sxs-lookup"><span data-stu-id="4d07b-138">Access the feed object.</span></span>  
  
     [!code-csharp[htAtomRss#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#11)]
     [!code-vb[htAtomRss#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="4d07b-139">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4d07b-139">Example</span></span>  

 <span data-ttu-id="4d07b-140">A seguir está a listagem completa de códigos deste exemplo.</span><span class="sxs-lookup"><span data-stu-id="4d07b-140">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htAtomRss#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d07b-141">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="4d07b-141">Compiling the Code</span></span>  

 <span data-ttu-id="4d07b-142">Ao compilar o código anterior, referencie System.ServiceModel.dll e System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="4d07b-142">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d07b-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="4d07b-143">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
