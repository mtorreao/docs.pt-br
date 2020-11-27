---
title: Utilização do associador de serialização
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 061afb94d97e3d8a1222e6de9932344fb3ebbe59
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294892"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="90d35-102">Utilização do associador de serialização</span><span class="sxs-lookup"><span data-stu-id="90d35-102">Usage of Serialization Binder</span></span>

<span data-ttu-id="90d35-103">Este exemplo mostra como usar o <xref:System.Runtime.Serialization.SerializationBinder> para alterar a versão de um tipo genérico quando ele é serializado.</span><span class="sxs-lookup"><span data-stu-id="90d35-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="90d35-104">Demonstra</span><span class="sxs-lookup"><span data-stu-id="90d35-104">Demonstrates</span></span>  

 <span data-ttu-id="90d35-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="90d35-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="90d35-106">Discussão</span><span class="sxs-lookup"><span data-stu-id="90d35-106">Discussion</span></span>  

 <span data-ttu-id="90d35-107">Este exemplo mostra como duas entidades que se destinam a diferentes versões do .NET Framework podem se comunicar usando o formatador binário e o associador de serialização.</span><span class="sxs-lookup"><span data-stu-id="90d35-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="90d35-108">Este exemplo foi desenvolvido usando a comunicação remota do .NET.</span><span class="sxs-lookup"><span data-stu-id="90d35-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="90d35-109">Ele consiste em um servidor de destino .NET Framework 4, que implementa um contrato com tipos genéricos e dois clientes diferentes, um direcionamento .NET Framework 2,0 e outro direcionamento .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="90d35-109">It consists of a server targeting .NET Framework 4, which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting .NET Framework 4.</span></span>  
  
 <span data-ttu-id="90d35-110">O servidor anexa um <xref:System.Runtime.Serialization.SerializationBinder> ao formatador binário para poder alterar a versão dos tipos de acordo com a serialização, para que ambos os clientes possam desserializar esses tipos corretamente.</span><span class="sxs-lookup"><span data-stu-id="90d35-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="90d35-111">Para configurar, compilar e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="90d35-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="90d35-112">Para executar o cliente, clique com o botão direito do mouse na solução, SBGenericsVTS (6 projetos) e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="90d35-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="90d35-113">Em **Propriedades comuns**, selecione **projeto de inicialização** e, em seguida, selecione **vários projetos de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="90d35-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="90d35-114">Selecione primeiro **servidor** , em seguida, **Client20** e **Client40**.</span><span class="sxs-lookup"><span data-stu-id="90d35-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="90d35-115">Selecione a ação **Iniciar** para esses três projetos e deixe o REST definido como **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="90d35-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="90d35-116">Clique em **OK** e pressione F5 para executar o exemplo.</span><span class="sxs-lookup"><span data-stu-id="90d35-116">Click **OK** and then press F5 to run the sample.</span></span>
