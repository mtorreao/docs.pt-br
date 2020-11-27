---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: eb174d12731d7f1bc78f4d709cf043daf2346bd2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269789"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="a4b97-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="a4b97-102">BinaryMessageEncodingBindingElement</span></span>

<span data-ttu-id="a4b97-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="a4b97-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b97-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a4b97-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a4b97-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a4b97-105">Methods</span></span>  

 <span data-ttu-id="a4b97-106">A classe BinaryMessageEncodingBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="a4b97-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a4b97-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="a4b97-107">Properties</span></span>  

 <span data-ttu-id="a4b97-108">A classe BinaryMessageEncodingBindingElement tem as propriedades a seguir.</span><span class="sxs-lookup"><span data-stu-id="a4b97-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="a4b97-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="a4b97-109">MaxReadPoolSize</span></span>  

 <span data-ttu-id="a4b97-110">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="a4b97-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="a4b97-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a4b97-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4b97-112">Um inteiro que define quantas mensagens podem ser lidas simultaneamente sem alocar novos leitores.</span><span class="sxs-lookup"><span data-stu-id="a4b97-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="a4b97-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="a4b97-113">MaxSessionSize</span></span>  

 <span data-ttu-id="a4b97-114">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="a4b97-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="a4b97-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a4b97-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4b97-116">Um valor que especifica o tamanho, em bytes, do buffer usado para codificação.</span><span class="sxs-lookup"><span data-stu-id="a4b97-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="a4b97-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="a4b97-117">MaxWritePoolSize</span></span>  

 <span data-ttu-id="a4b97-118">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="a4b97-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="a4b97-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a4b97-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4b97-120">Um inteiro que define quantas mensagens podem ser enviadas simultaneamente sem alocar novos gravadores.</span><span class="sxs-lookup"><span data-stu-id="a4b97-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="a4b97-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="a4b97-121">ReaderQuotas</span></span>  

 <span data-ttu-id="a4b97-122">Tipo de dados: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="a4b97-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="a4b97-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a4b97-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4b97-124">As cotas dos leitores.</span><span class="sxs-lookup"><span data-stu-id="a4b97-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4b97-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4b97-125">Requirements</span></span>  
  
|<span data-ttu-id="a4b97-126">MOF</span><span class="sxs-lookup"><span data-stu-id="a4b97-126">MOF</span></span>|<span data-ttu-id="a4b97-127">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="a4b97-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a4b97-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="a4b97-128">Namespace</span></span>|<span data-ttu-id="a4b97-129">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a4b97-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4b97-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="a4b97-130">See also</span></span>

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
