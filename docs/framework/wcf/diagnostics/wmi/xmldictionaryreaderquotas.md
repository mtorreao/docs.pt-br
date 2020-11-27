---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: c5bb7813a680c89eb90f4ccf4ed6f09a831c8095
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262197"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="7ca9f-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="7ca9f-102">XmlDictionaryReaderQuotas</span></span>

<span data-ttu-id="7ca9f-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="7ca9f-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ca9f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7ca9f-104">Syntax</span></span>  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7ca9f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7ca9f-105">Methods</span></span>  

 <span data-ttu-id="7ca9f-106">A classe XmlDictionaryReaderQuotas não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="7ca9f-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7ca9f-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="7ca9f-107">Properties</span></span>  

 <span data-ttu-id="7ca9f-108">A classe XmlDictionaryReaderQuotas tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="7ca9f-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="7ca9f-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="7ca9f-109">MaxArrayLength</span></span>  

 <span data-ttu-id="7ca9f-110">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="7ca9f-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="7ca9f-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7ca9f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ca9f-112">A extensão máxima permitida da matriz.</span><span class="sxs-lookup"><span data-stu-id="7ca9f-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="7ca9f-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="7ca9f-113">MaxBytesPerRead</span></span>  

 <span data-ttu-id="7ca9f-114">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="7ca9f-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="7ca9f-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7ca9f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ca9f-116">O máximo de bytes permitidos retornados para cada leitura.</span><span class="sxs-lookup"><span data-stu-id="7ca9f-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="7ca9f-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="7ca9f-117">MaxDepth</span></span>  

 <span data-ttu-id="7ca9f-118">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="7ca9f-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="7ca9f-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7ca9f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ca9f-120">A profundidade máxima do nó aninhado para cada leitura.</span><span class="sxs-lookup"><span data-stu-id="7ca9f-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="7ca9f-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="7ca9f-121">MaxNameTableCharCount</span></span>  

 <span data-ttu-id="7ca9f-122">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="7ca9f-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="7ca9f-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7ca9f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ca9f-124">O máximo de caracteres permitidos no nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="7ca9f-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="7ca9f-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="7ca9f-125">MaxStringContentLength</span></span>  

 <span data-ttu-id="7ca9f-126">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="7ca9f-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="7ca9f-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7ca9f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ca9f-128">O máximo de caracteres permitidos no conteúdo do elemento XML.</span><span class="sxs-lookup"><span data-stu-id="7ca9f-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ca9f-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ca9f-129">Requirements</span></span>  
  
|<span data-ttu-id="7ca9f-130">MOF</span><span class="sxs-lookup"><span data-stu-id="7ca9f-130">MOF</span></span>|<span data-ttu-id="7ca9f-131">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="7ca9f-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7ca9f-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="7ca9f-132">Namespace</span></span>|<span data-ttu-id="7ca9f-133">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7ca9f-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ca9f-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="7ca9f-134">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
