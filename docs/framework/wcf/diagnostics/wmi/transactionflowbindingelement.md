---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 577502d1cd3d81784cb9b1eb3b249376b8ffa6b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234889"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="79a4e-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="79a4e-102">TransactionFlowBindingElement</span></span>

<span data-ttu-id="79a4e-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="79a4e-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a4e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="79a4e-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="79a4e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="79a4e-105">Methods</span></span>  

 <span data-ttu-id="79a4e-106">A classe TransactionFlowBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="79a4e-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="79a4e-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="79a4e-107">Properties</span></span>  

 <span data-ttu-id="79a4e-108">A classe TransactionFlowBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="79a4e-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="79a4e-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="79a4e-109">IssuedTokens</span></span>  

 <span data-ttu-id="79a4e-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="79a4e-110">Data type: string</span></span>  
  
 <span data-ttu-id="79a4e-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="79a4e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79a4e-112">Especifica o requisito para um cabeçalho de tokens de segurança emitidos (IssuedTokens de WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="79a4e-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="79a4e-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="79a4e-113">TransactionProtocol</span></span>  

 <span data-ttu-id="79a4e-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="79a4e-114">Data type: string</span></span>  
  
 <span data-ttu-id="79a4e-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="79a4e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79a4e-116">O protocolo de transações usado pelo serviço para o fluxo de transações.</span><span class="sxs-lookup"><span data-stu-id="79a4e-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="79a4e-117">Transactions</span><span class="sxs-lookup"><span data-stu-id="79a4e-117">Transactions</span></span>  

 <span data-ttu-id="79a4e-118">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="79a4e-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="79a4e-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="79a4e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79a4e-120">Indica se há suporte para a transação de entrada.</span><span class="sxs-lookup"><span data-stu-id="79a4e-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79a4e-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79a4e-121">Requirements</span></span>  
  
|<span data-ttu-id="79a4e-122">MOF</span><span class="sxs-lookup"><span data-stu-id="79a4e-122">MOF</span></span>|<span data-ttu-id="79a4e-123">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="79a4e-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="79a4e-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="79a4e-124">Namespace</span></span>|<span data-ttu-id="79a4e-125">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="79a4e-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79a4e-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="79a4e-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
