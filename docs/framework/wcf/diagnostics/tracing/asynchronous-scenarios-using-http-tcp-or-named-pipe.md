---
title: Cenários assíncronos usando HTTP, TCP ou pipe nomeado
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 00213c8d117f4319d7e29312dd0b9805d916231a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244139"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="6da8c-102">Cenários assíncronos usando HTTP, TCP ou pipe nomeado</span><span class="sxs-lookup"><span data-stu-id="6da8c-102">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>

<span data-ttu-id="6da8c-103">Este tópico descreve as atividades e transferências para diferentes cenários assíncronos de solicitação/resposta, com solicitações multi-threaded usando HTTP, TCP ou pipe nomeado.</span><span class="sxs-lookup"><span data-stu-id="6da8c-103">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="6da8c-104">Solicitação/resposta assíncrona sem erros</span><span class="sxs-lookup"><span data-stu-id="6da8c-104">Asynchronous Request/Reply without Errors</span></span>  

 <span data-ttu-id="6da8c-105">Esta seção descreve as atividades e transferências para um cenário de solicitação/resposta assíncrona, com clientes multithread.</span><span class="sxs-lookup"><span data-stu-id="6da8c-105">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="6da8c-106">A atividade do chamador é encerrada quando `beginCall` retorna e `endCall` retorna.</span><span class="sxs-lookup"><span data-stu-id="6da8c-106">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="6da8c-107">Se um retorno de chamada for chamado, o retorno de chamada retornará.</span><span class="sxs-lookup"><span data-stu-id="6da8c-107">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="6da8c-108">A atividade chamada termina quando `beginCall` retorna, `endCall` retorna ou quando o retorno de chamada retorna se foi chamado a partir dessa atividade.</span><span class="sxs-lookup"><span data-stu-id="6da8c-108">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="6da8c-109">Cliente assíncrono sem retorno de chamada</span><span class="sxs-lookup"><span data-stu-id="6da8c-109">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="6da8c-110">A propagação está habilitada em ambos os lados, usando HTTP</span><span class="sxs-lookup"><span data-stu-id="6da8c-110">Propagation is Enabled on Both Sides, using HTTP</span></span>  

 ![Cliente assíncrono sem nenhum retorno de chamada, em que propagateActivity está definido como true em ambos os lados.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)
  
 <span data-ttu-id="6da8c-112">Se `propagateActivity=true` , ProcessMessage indica a atividade processAction a ser transferida.</span><span class="sxs-lookup"><span data-stu-id="6da8c-112">If `propagateActivity=true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="6da8c-113">Para cenários baseados em HTTP, ReceiveBytes é invocado na primeira mensagem a ser enviada e existe durante o tempo de vida da solicitação.</span><span class="sxs-lookup"><span data-stu-id="6da8c-113">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="6da8c-114">A propagação está desabilitada em qualquer um dos lados, usando HTTP</span><span class="sxs-lookup"><span data-stu-id="6da8c-114">Propagation is Disabled on Either Sides, using HTTP</span></span>  

 <span data-ttu-id="6da8c-115">Se `propagateActivity=false` , em ambos os lados, ProcessMessage não indicar qual atividade processAction será transferida.</span><span class="sxs-lookup"><span data-stu-id="6da8c-115">If `propagateActivity=false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="6da8c-116">Portanto, uma nova atividade processAction temporária com uma nova ID é invocada.</span><span class="sxs-lookup"><span data-stu-id="6da8c-116">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="6da8c-117">Quando a resposta assíncrona é correspondida à solicitação no código de ServiceModel, a ID da atividade pode ser recuperada do contexto local.</span><span class="sxs-lookup"><span data-stu-id="6da8c-117">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="6da8c-118">A atividade processAction real pode ser transferida para com essa ID.</span><span class="sxs-lookup"><span data-stu-id="6da8c-118">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![Cliente assíncrono sem nenhum retorno de chamada, em que propagateActivity está definido como false em ambos os lados.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  

 <span data-ttu-id="6da8c-120">Para cenários baseados em HTTP, ReceiveBytes é invocado na primeira mensagem a ser enviada e existe durante o tempo de vida da solicitação.</span><span class="sxs-lookup"><span data-stu-id="6da8c-120">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="6da8c-121">Uma atividade processar ação é criada em um cliente assíncrono quando `propagateActivity=false` no chamador ou receptor, e quando a mensagem de resposta não inclui um cabeçalho de ação.</span><span class="sxs-lookup"><span data-stu-id="6da8c-121">A Process Action activity is created on an asynchronous client when `propagateActivity=false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="6da8c-122">A propagação é habilitada em ambos os lados, usando TCP ou pipe nomeado</span><span class="sxs-lookup"><span data-stu-id="6da8c-122">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  

 ![Cliente assíncrono sem nenhum retorno de chamada, em que propagateActivity está definido como true em ambos os lados e pipe nomeado/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 <span data-ttu-id="6da8c-124">Para um cenário baseado em Named-Pipe ou TCP, ReceiveBytes é invocado quando o cliente é aberto e existe durante o tempo de vida da conexão.</span><span class="sxs-lookup"><span data-stu-id="6da8c-124">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="6da8c-125">Semelhante à primeira imagem, If `propagateActivity=true` , ProcessMessage indica a atividade processAction a ser transferida.</span><span class="sxs-lookup"><span data-stu-id="6da8c-125">Similar to the first image, if `propagateActivity=true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="6da8c-126">A propagação está desabilitada em qualquer um dos lados, usando TCP ou pipe nomeado</span><span class="sxs-lookup"><span data-stu-id="6da8c-126">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  

 <span data-ttu-id="6da8c-127">Para um cenário baseado em Named-Pipe ou TCP, ReceiveBytes é invocado quando o cliente é aberto e existe durante o tempo de vida da conexão.</span><span class="sxs-lookup"><span data-stu-id="6da8c-127">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="6da8c-128">Semelhante à segunda imagem, se estiver `propagateActivity=false` em ambos os lados, ProcessMessage não indica qual atividade processAction transferir para.</span><span class="sxs-lookup"><span data-stu-id="6da8c-128">Similar to the second image, if `propagateActivity=false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="6da8c-129">Portanto, uma nova atividade processAction temporária com uma nova ID é invocada.</span><span class="sxs-lookup"><span data-stu-id="6da8c-129">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="6da8c-130">Quando a resposta assíncrona é correspondida à solicitação no código de ServiceModel, a ID da atividade pode ser recuperada do contexto local.</span><span class="sxs-lookup"><span data-stu-id="6da8c-130">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="6da8c-131">A atividade processAction real pode ser transferida para com essa ID.</span><span class="sxs-lookup"><span data-stu-id="6da8c-131">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![Cliente assíncrono sem nenhum retorno de chamada em que propagateActivity está definido como false em ambos os lados e pipe nomeado/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  

### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="6da8c-133">Cliente assíncrono com retorno de chamada</span><span class="sxs-lookup"><span data-stu-id="6da8c-133">Asynchronous client with Callback</span></span>  

 <span data-ttu-id="6da8c-134">Esse cenário adiciona as atividades G e A ', para o retorno de chamada e e `endCall` suas transferências para dentro/para fora.</span><span class="sxs-lookup"><span data-stu-id="6da8c-134">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="6da8c-135">Esta seção demonstra apenas o uso de HTTP com o `propagateActivity` = `true` .</span><span class="sxs-lookup"><span data-stu-id="6da8c-135">This section only demonstrates using HTTP with `propagateActivity`=`true`.</span></span> <span data-ttu-id="6da8c-136">No entanto, as atividades e transferências adicionais também se aplicam aos outros casos (ou seja, `propagateActivity` = `false` usando TCP ou pipe nomeado).</span><span class="sxs-lookup"><span data-stu-id="6da8c-136">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="6da8c-137">O retorno de chamada cria uma nova atividade (G) quando o cliente chama o código do usuário para notificar que os resultados estão prontos.</span><span class="sxs-lookup"><span data-stu-id="6da8c-137">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="6da8c-138">Em seguida, o código do usuário chama `endCall` o retorno de chamada (como mostrado na Figura 5) ou fora do retorno de chamada (Figura 6).</span><span class="sxs-lookup"><span data-stu-id="6da8c-138">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="6da8c-139">Como não é conhecido qual atividade do usuário `endCall` está sendo chamada, essa atividade é rotulada `A’` .</span><span class="sxs-lookup"><span data-stu-id="6da8c-139">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="6da8c-140">É possível que um ' possa ser idêntico ou diferente de um.</span><span class="sxs-lookup"><span data-stu-id="6da8c-140">It is possible that A’ can be identical to or different from A.</span></span>  
  
 ![Mostra um cliente assíncrono com retorno de chamada, EndCall em chamada de retorno.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  

 ![Mostra um cliente assíncrono com retorno de chamada, EndCall externo.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  

### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="6da8c-143">Servidor assíncrono com retorno de chamada</span><span class="sxs-lookup"><span data-stu-id="6da8c-143">Asynchronous Server with Callback</span></span>  

 ![Mostra um servidor assíncrono com retorno de chamada.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  

 <span data-ttu-id="6da8c-145">A pilha de canais retorna de volta o cliente na mensagem de recebimento: os rastreamentos para esse processamento são emitidos na própria atividade ProcessRequest.</span><span class="sxs-lookup"><span data-stu-id="6da8c-145">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="6da8c-146">Solicitação/resposta assíncrona com erros</span><span class="sxs-lookup"><span data-stu-id="6da8c-146">Asynchronous Request/Reply with Errors</span></span>  

 <span data-ttu-id="6da8c-147">Erros de mensagem de falha são recebidos durante `endCall` .</span><span class="sxs-lookup"><span data-stu-id="6da8c-147">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="6da8c-148">Caso contrário, as atividades e transferências são semelhantes aos cenários anteriores.</span><span class="sxs-lookup"><span data-stu-id="6da8c-148">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="6da8c-149">One-Way assíncrona com ou sem erros</span><span class="sxs-lookup"><span data-stu-id="6da8c-149">Asynchronous One-Way with or without Errors</span></span>  

 <span data-ttu-id="6da8c-150">Nenhuma resposta ou falha é retornada ao cliente.</span><span class="sxs-lookup"><span data-stu-id="6da8c-150">No response or fault is returned to the client.</span></span>
