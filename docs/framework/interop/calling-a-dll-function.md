---
title: Chamando uma função de DLL
description: Examine os problemas sobre como chamar uma função DLL que pode parecer confusa. O processo de chamada de função difere dependendo se o tipo de retorno é blittable.
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 09dd9d30c29660231feee6c624a025ade1fda1d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282945"
---
# <a name="calling-a-dll-function"></a><span data-ttu-id="6c8fb-104">Chamando uma função de DLL</span><span class="sxs-lookup"><span data-stu-id="6c8fb-104">Calling a DLL Function</span></span>

<span data-ttu-id="6c8fb-105">Embora a chamada a funções de DLL não gerenciadas seja quase idêntica à chamada de outro código gerenciado, há diferenças que podem fazer com que as funções de DLL pareçam confusas a princípio.</span><span class="sxs-lookup"><span data-stu-id="6c8fb-105">Although calling unmanaged DLL functions is nearly identical to calling other managed code, there are differences that can make DLL functions seem confusing at first.</span></span> <span data-ttu-id="6c8fb-106">Esta seção apresenta tópicos que descrevem alguns dos problemas incomuns relacionados a chamadas.</span><span class="sxs-lookup"><span data-stu-id="6c8fb-106">This section introduces topics that describe some of the unusual calling-related issues.</span></span>  
  
 <span data-ttu-id="6c8fb-107">Estruturas retornadas de chamadas de invocação de plataforma devem ser tipos de dados que têm a mesma representação em um código gerenciado e não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="6c8fb-107">Structures that are returned from platform invoke calls must be data types that have the same representation in managed and unmanaged code.</span></span> <span data-ttu-id="6c8fb-108">Esses tipos são chamados de *tipos blittable* porque não exigem conversão (consulte [Tipos blittable e não blittable](blittable-and-non-blittable-types.md)).</span><span class="sxs-lookup"><span data-stu-id="6c8fb-108">Such types are called *blittable types* because they do not require conversion (see [Blittable and Non-Blittable Types](blittable-and-non-blittable-types.md)).</span></span> <span data-ttu-id="6c8fb-109">Para chamar uma função que tem uma estrutura não blittable como seu tipo de retorno, é possível definir um tipo de auxiliar blittable do mesmo tamanho do tipo não blittable e converter os dados depois que a função é retornada.</span><span class="sxs-lookup"><span data-stu-id="6c8fb-109">To call a function that has a non-blittable structure as its return type, you can define a blittable helper type of the same size as the non-blittable type and convert the data after the function returns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c8fb-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6c8fb-110">In This Section</span></span>  

 [<span data-ttu-id="6c8fb-111">Passando estruturas</span><span class="sxs-lookup"><span data-stu-id="6c8fb-111">Passing Structures</span></span>](passing-structures.md)  
 <span data-ttu-id="6c8fb-112">Identifica os problemas de passar estruturas de dados com um layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="6c8fb-112">Identifies the issues of passing data structures with a predefined layout.</span></span>  
  
 [<span data-ttu-id="6c8fb-113">Funções de retorno de chamada</span><span class="sxs-lookup"><span data-stu-id="6c8fb-113">Callback Functions</span></span>](callback-functions.md)  
 <span data-ttu-id="6c8fb-114">Fornece informações básicas sobre as funções de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="6c8fb-114">Provides basic information about callback functions.</span></span>  
  
 [<span data-ttu-id="6c8fb-115">Como: Implementar funções de retorno de chamada</span><span class="sxs-lookup"><span data-stu-id="6c8fb-115">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)  
 <span data-ttu-id="6c8fb-116">Descreve como implementar funções de retorno de chamada em um código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="6c8fb-116">Describes how to implement callback functions in managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6c8fb-117">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="6c8fb-117">Related Sections</span></span>  

 [<span data-ttu-id="6c8fb-118">Consumindo funções de DLL não gerenciadas</span><span class="sxs-lookup"><span data-stu-id="6c8fb-118">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="6c8fb-119">Descreve como chamar funções de DLL não gerenciadas usando a invocação de plataforma.</span><span class="sxs-lookup"><span data-stu-id="6c8fb-119">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="6c8fb-120">Marshaling de dados com invocação de plataforma</span><span class="sxs-lookup"><span data-stu-id="6c8fb-120">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="6c8fb-121">Descreve como declarar parâmetros de método e passar argumentos para funções exportadas por bibliotecas não gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="6c8fb-121">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>
