---
title: Classe base de NativeActivity
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: d875f62dacadb2baf6b5d7e93ddb2933aed9cdb0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274953"
---
# <a name="nativeactivity-base-class"></a><span data-ttu-id="a5a52-102">Classe base de NativeActivity</span><span class="sxs-lookup"><span data-stu-id="a5a52-102">NativeActivity Base Class</span></span>

<span data-ttu-id="a5a52-103"><xref:System.Activities.NativeActivity> é uma classe abstrata com um construtor protegido.</span><span class="sxs-lookup"><span data-stu-id="a5a52-103"><xref:System.Activities.NativeActivity> is an abstract class with a protected constructor.</span></span> <span data-ttu-id="a5a52-104">Como <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> é usado para gravar o comportamento obrigatório implementando um método de <xref:System.Activities.NativeActivity.Execute%2A> .</span><span class="sxs-lookup"><span data-stu-id="a5a52-104">Like <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> is used for writing imperative behavior by implementing an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span> <span data-ttu-id="a5a52-105">Ao contrário de <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> tem acesso a todos os recursos expostos em runtime de fluxo de trabalho através do objeto de <xref:System.Activities.NativeActivityContext> passado para o método de <xref:System.Activities.NativeActivity.Execute%2A> .</span><span class="sxs-lookup"><span data-stu-id="a5a52-105">Unlike <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> has access to all of the exposed features of the workflow runtime through the <xref:System.Activities.NativeActivityContext> object passed to the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

## <a name="using-nativeactivitycontext"></a><span data-ttu-id="a5a52-106">Usando NativeActivityContext</span><span class="sxs-lookup"><span data-stu-id="a5a52-106">Using NativeActivityContext</span></span>

 <span data-ttu-id="a5a52-107">Recursos de runtime de fluxo de trabalho podem ser acessados de dentro do método de <xref:System.Activities.NativeActivity.Execute%2A> usando membros de parâmetro de `context` , do tipo <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="a5a52-107">Features of the workflow runtime can be accessed from within the <xref:System.Activities.NativeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.NativeActivityContext>.</span></span> <span data-ttu-id="a5a52-108">Os recursos <xref:System.Activities.NativeActivityContext> direto disponível incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5a52-108">The features available through <xref:System.Activities.NativeActivityContext> include the following:</span></span>

- <span data-ttu-id="a5a52-109">Obter e definir os argumentos e variáveis.</span><span class="sxs-lookup"><span data-stu-id="a5a52-109">Getting and setting of arguments and variables.</span></span>

- <span data-ttu-id="a5a52-110">Atividades filhos de programação com <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span><span class="sxs-lookup"><span data-stu-id="a5a52-110">Scheduling child activities with <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span></span>

- <span data-ttu-id="a5a52-111">Anulando a execução da atividade usando <xref:System.Activities.NativeActivityContext.Abort%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5a52-111">Aborting activity execution using <xref:System.Activities.NativeActivityContext.Abort%2A>.</span></span>

- <span data-ttu-id="a5a52-112">Cancelando a execução filho usando <xref:System.Activities.NativeActivityContext.CancelChild%2A> e <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5a52-112">Canceling child execution using <xref:System.Activities.NativeActivityContext.CancelChild%2A> and <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.</span></span>

- <span data-ttu-id="a5a52-113">Acesso aos indicadores de atividade usando métodos como <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>, e <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5a52-113">Access to activity bookmarks using such methods as <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>, and <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.</span></span>

- <span data-ttu-id="a5a52-114">Recursos personalizados de rastreamento que usam <xref:System.Activities.CodeActivityContext.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5a52-114">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="a5a52-115">Acesso às propriedades de execução da atividade e propriedades de valor usando <xref:System.Activities.CodeActivityContext.GetProperty%2A> e <xref:System.Activities.NativeActivityContext.GetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5a52-115">Access to the activity’s execution properties and value properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A> and <xref:System.Activities.NativeActivityContext.GetValue%2A>.</span></span>

- <span data-ttu-id="a5a52-116">Ações e funções de atividade de programação usando o <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> e o <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5a52-116">Scheduling activity actions and functions using <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> and <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.</span></span>

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a><span data-ttu-id="a5a52-117">Para criar uma atividade personalizado que herda de NativeActivity</span><span class="sxs-lookup"><span data-stu-id="a5a52-117">To create a custom activity that inherits from NativeActivity</span></span>

1. <span data-ttu-id="a5a52-118">OpenVisual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="a5a52-118">OpenVisual Studio 2010.</span></span>

2. <span data-ttu-id="a5a52-119">Selecione **arquivo**, **novo** e **projeto**.</span><span class="sxs-lookup"><span data-stu-id="a5a52-119">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="a5a52-120">Selecione **fluxo de trabalho 4,0** em **Visual C#** na janela **tipos de projeto** e selecione o nó **v2010** .</span><span class="sxs-lookup"><span data-stu-id="a5a52-120">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="a5a52-121">Selecione **biblioteca de atividades** na janela **modelos** .</span><span class="sxs-lookup"><span data-stu-id="a5a52-121">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="a5a52-122">Nomeie o novo projeto HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="a5a52-122">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="a5a52-123">Clique com o botão direito do mouse em Atividade1. XAML no projeto HelloActivity e selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="a5a52-123">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="a5a52-124">Clique com o botão direito do mouse no projeto HelloActivity e selecione **Adicionar** e, em seguida, **classe**.</span><span class="sxs-lookup"><span data-stu-id="a5a52-124">Right-click the HelloActivity project and select **Add**, and then **Class**.</span></span> <span data-ttu-id="a5a52-125">Nomeie a nova classe HelloActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="a5a52-125">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="a5a52-126">No arquivo de HelloActivity.cs, adicione as seguintes diretivas de `using` .</span><span class="sxs-lookup"><span data-stu-id="a5a52-126">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="a5a52-127">Faça a nova classe herdar de <xref:System.Activities.NativeActivity> adicionando uma classe base para a declaração de classe.</span><span class="sxs-lookup"><span data-stu-id="a5a52-127">Make the new class inherit from <xref:System.Activities.NativeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. <span data-ttu-id="a5a52-128">Adicionar funcionalidade à classe adicionando um método de <xref:System.Activities.NativeActivity.Execute%2A> .</span><span class="sxs-lookup"><span data-stu-id="a5a52-128">Add functionality to the class by adding an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="a5a52-129">Substitua o método de <xref:System.Activities.NativeActivity.CacheMetadata%2A> e chamar o método apropriado no para permitir que o runtime de fluxo de trabalho aprender sobre variáveis personalizados, os argumentos, os filhos, e os representantes de atividade.</span><span class="sxs-lookup"><span data-stu-id="a5a52-129">Override the <xref:System.Activities.NativeActivity.CacheMetadata%2A> method and call the appropriate Add method to let the workflow runtime know about the custom activity’s variables, arguments, children, and delegates.</span></span> <span data-ttu-id="a5a52-130">Para obter mais informações consulte a classe de <xref:System.Activities.NativeActivityMetadata> .</span><span class="sxs-lookup"><span data-stu-id="a5a52-130">For more information see the <xref:System.Activities.NativeActivityMetadata> class.</span></span>

9. <span data-ttu-id="a5a52-131">Use o objeto de <xref:System.Activities.NativeActivityContext> para agendar um indexador.</span><span class="sxs-lookup"><span data-stu-id="a5a52-131">Use the <xref:System.Activities.NativeActivityContext> object to schedule a bookmark.</span></span> <span data-ttu-id="a5a52-132">Consulte <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> para obter detalhes sobre como criar, agendar, e retomar um indexador.</span><span class="sxs-lookup"><span data-stu-id="a5a52-132">See <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> for details on how to create, schedule, and resume a bookmark.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```
