---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 61eae75de04f75b6ad6e78d16569595732b3d28f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273302"
---
# <a name="securitybindingelement"></a><span data-ttu-id="9397f-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9397f-102">SecurityBindingElement</span></span>

<span data-ttu-id="9397f-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9397f-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9397f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9397f-104">Syntax</span></span>  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9397f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9397f-105">Methods</span></span>  

 <span data-ttu-id="9397f-106">A classe SecurityBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="9397f-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9397f-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="9397f-107">Properties</span></span>  

 <span data-ttu-id="9397f-108">A classe SecurityBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="9397f-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="9397f-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9397f-109">DefaultAlgorithmSuite</span></span>  

 <span data-ttu-id="9397f-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9397f-110">Data type: string</span></span>  
  
 <span data-ttu-id="9397f-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="9397f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9397f-112">Especifica os algoritmos a serem usados com a associação.</span><span class="sxs-lookup"><span data-stu-id="9397f-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="9397f-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="9397f-113">IncludeTimestamp</span></span>  

 <span data-ttu-id="9397f-114">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="9397f-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="9397f-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="9397f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9397f-116">Um valor booliano que especifica se cada mensagem contém um carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="9397f-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="9397f-117">Keyentropiamode</span><span class="sxs-lookup"><span data-stu-id="9397f-117">KeyEntropyMode</span></span>  

 <span data-ttu-id="9397f-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9397f-118">Data type: string</span></span>  
  
 <span data-ttu-id="9397f-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="9397f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9397f-120">A fonte de entropia usada para criar chaves.</span><span class="sxs-lookup"><span data-stu-id="9397f-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="9397f-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9397f-121">LocalServiceSecuritySettings</span></span>  

 <span data-ttu-id="9397f-122">Tipo de dados: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9397f-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="9397f-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="9397f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9397f-124">As propriedades de segurança específicas de associação para o serviço local.</span><span class="sxs-lookup"><span data-stu-id="9397f-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="9397f-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="9397f-125">MessageSecurityVersion</span></span>  

 <span data-ttu-id="9397f-126">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9397f-126">Data type: string</span></span>  
  
 <span data-ttu-id="9397f-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="9397f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9397f-128">A versão usada para segurança de mensagem.</span><span class="sxs-lookup"><span data-stu-id="9397f-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="9397f-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="9397f-129">SecurityHeaderLayout</span></span>  

 <span data-ttu-id="9397f-130">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9397f-130">Data type: string</span></span>  
  
 <span data-ttu-id="9397f-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="9397f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9397f-132">A ordem dos elementos no cabeçalho de segurança para essa associação.</span><span class="sxs-lookup"><span data-stu-id="9397f-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9397f-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9397f-133">Requirements</span></span>  
  
|<span data-ttu-id="9397f-134">MOF</span><span class="sxs-lookup"><span data-stu-id="9397f-134">MOF</span></span>|<span data-ttu-id="9397f-135">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="9397f-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9397f-136">Namespace</span><span class="sxs-lookup"><span data-stu-id="9397f-136">Namespace</span></span>|<span data-ttu-id="9397f-137">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9397f-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9397f-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="9397f-138">See also</span></span>

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
