---
title: Gerando classes de tipo de dados por meio de XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: a7920a8c8c4f279dd3fc52029c5da5e9b685efe2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238243"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="9b44a-102">Gerando classes de tipo de dados por meio de XML</span><span class="sxs-lookup"><span data-stu-id="9b44a-102">Generating Data Type Classes from XML</span></span>

<span data-ttu-id="9b44a-103">O .NET Framework 4,5 inclui um novo recurso para gerar classes de tipo de dados do XML.</span><span class="sxs-lookup"><span data-stu-id="9b44a-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="9b44a-104">Este tópico descreve como gerar automaticamente tipos de dados para o RSS feed do blog do .NET.</span><span class="sxs-lookup"><span data-stu-id="9b44a-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="9b44a-105">Obtendo o XML do feed RSS do blog do .NET</span><span class="sxs-lookup"><span data-stu-id="9b44a-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="9b44a-106">No Internet Explorer, navegue até o [RSS feed do blog do .net](https://devblogs.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="9b44a-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="9b44a-107">Clique com o botão direito do mouse na página e selecione **Exibir origem**.</span><span class="sxs-lookup"><span data-stu-id="9b44a-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="9b44a-108">Copie o texto do feed pressionando **Ctrl + a** para selecionar todo o texto e **Ctrl + C** para copiar.</span><span class="sxs-lookup"><span data-stu-id="9b44a-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="9b44a-109">Criando os tipos de dados</span><span class="sxs-lookup"><span data-stu-id="9b44a-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="9b44a-110">Abra um arquivo de código no qual o proxy deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="9b44a-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="9b44a-111">Esse arquivo deve fazer parte de um projeto .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="9b44a-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="9b44a-112">Coloque o cursor em um local no arquivo fora de qualquer classe existente.</span><span class="sxs-lookup"><span data-stu-id="9b44a-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="9b44a-113">Selecione **Editar**, **colar especial** e **colar XML como classes**.</span><span class="sxs-lookup"><span data-stu-id="9b44a-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="9b44a-114">Classes chamadas `link` , `rss` , `rssChannel` , `rssChannelImage` `rssChannelItem` e `rssChannelItemGuid` são criadas com os membros necessários para acessar os elementos no RSS feed.</span><span class="sxs-lookup"><span data-stu-id="9b44a-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="9b44a-115">Usando as classes geradas</span><span class="sxs-lookup"><span data-stu-id="9b44a-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="9b44a-116">Depois que as classes são geradas, elas podem ser usadas em código como qualquer outra classe.</span><span class="sxs-lookup"><span data-stu-id="9b44a-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="9b44a-117">O exemplo de código a seguir retorna uma nova instância da `rssChannelImage` classe.</span><span class="sxs-lookup"><span data-stu-id="9b44a-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
