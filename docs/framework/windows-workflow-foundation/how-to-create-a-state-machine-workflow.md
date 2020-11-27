---
title: 'Como: criar um fluxo de trabalho da máquina de estado'
description: Este artigo cria um fluxo de trabalho que usa atividades internas, como a atividade StateMachine e atividades personalizadas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 9df911779422ca2710686963a040a95258db8891
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248913"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="49b41-103">Como: criar um fluxo de trabalho da máquina de estado</span><span class="sxs-lookup"><span data-stu-id="49b41-103">How to: Create a State Machine Workflow</span></span>

<span data-ttu-id="49b41-104">Os fluxos de trabalho podem ser construídos a partir de atividades internas assim como as atividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="49b41-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="49b41-105">Este tópico percorre a criação de um fluxo de trabalho que usa atividades internas, como a <xref:System.Activities.Statements.StateMachine> atividade, e as atividades personalizadas do tópico [como criar uma atividade](how-to-create-an-activity.md) anterior.</span><span class="sxs-lookup"><span data-stu-id="49b41-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="49b41-106">O fluxo de trabalho modela um jogo de palpite de número.</span><span class="sxs-lookup"><span data-stu-id="49b41-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49b41-107">Cada tópico do tutorial de Introdução depende dos tópicos anteriores.</span><span class="sxs-lookup"><span data-stu-id="49b41-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="49b41-108">Para concluir este tópico, você deve primeiro concluir [como: criar uma atividade](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="49b41-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49b41-109">Para baixar uma versão completa do tutorial, consulte [Windows Workflow Foundation (WF45) – introdução tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="49b41-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="49b41-110">Para criar o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="49b41-110">To create the workflow</span></span>  
  
1. <span data-ttu-id="49b41-111">Clique com o botão direito do mouse em **NumberGuessWorkflowActivities** em **Gerenciador de soluções** e selecione **Adicionar**, **novo item**.</span><span class="sxs-lookup"><span data-stu-id="49b41-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="49b41-112">No nó **itens comuns** **instalados**, selecione fluxo de **trabalho**.</span><span class="sxs-lookup"><span data-stu-id="49b41-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="49b41-113">Selecione **Atividade** na lista **Fluxo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="49b41-113">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="49b41-114">Digite `StateMachineNumberGuessWorkflow` na caixa **nome** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="49b41-114">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="49b41-115">Arraste uma atividade **StateMachine** da seção **máquina de estado** da caixa de **ferramentas** e solte-a no rótulo **soltar atividade aqui** na superfície de design do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="49b41-115">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="49b41-116">Para criar as variáveis e os argumentos do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="49b41-116">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="49b41-117">Clique duas vezes em **StateMachineNumberGuessWorkflow. XAML** em **Gerenciador de soluções** para exibir o fluxo de trabalho no designer, se ele ainda não estiver sendo exibido.</span><span class="sxs-lookup"><span data-stu-id="49b41-117">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="49b41-118">Clique em **argumentos** no lado inferior esquerdo do designer de fluxo de trabalho para exibir o painel **argumentos** .</span><span class="sxs-lookup"><span data-stu-id="49b41-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="49b41-119">Clique em **Criar Argumento**.</span><span class="sxs-lookup"><span data-stu-id="49b41-119">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="49b41-120">Digite na `MaxNumber` caixa **nome** , selecione **em na** lista suspensa **direção** , selecione **Int32** na lista suspensa tipo de **argumento** e pressione ENTER para salvar o argumento...</span><span class="sxs-lookup"><span data-stu-id="49b41-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="49b41-121">Clique em **Criar Argumento**.</span><span class="sxs-lookup"><span data-stu-id="49b41-121">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="49b41-122">Digite `Turns` na caixa de **nome** que está abaixo do argumento recém-adicionado `MaxNumber` , selecione **fora** na lista suspensa **direção** , selecione **Int32** na lista suspensa tipo de **argumento** e, em seguida, pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="49b41-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="49b41-123">Clique em **Argumentos** no lado inferior esquerdo do designer de atividade para fechar o painel **Argumentos**.</span><span class="sxs-lookup"><span data-stu-id="49b41-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="49b41-124">Clique em **variáveis** no lado inferior esquerdo do designer de fluxo de trabalho para exibir o painel **variáveis** .</span><span class="sxs-lookup"><span data-stu-id="49b41-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="49b41-125">Clique em **Criar Variável**.</span><span class="sxs-lookup"><span data-stu-id="49b41-125">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="49b41-126">Se nenhuma caixa **criar variável** for exibida, clique na <xref:System.Activities.Statements.StateMachine> atividade na superfície do designer de fluxo de trabalho para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="49b41-126">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="49b41-127">Digite `Guess` na caixa **nome** , selecione **Int32** na lista suspensa **tipo de variável** e pressione ENTER para salvar a variável.</span><span class="sxs-lookup"><span data-stu-id="49b41-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="49b41-128">Clique em **Criar Variável**.</span><span class="sxs-lookup"><span data-stu-id="49b41-128">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="49b41-129">Digite `Target` na caixa **nome** , selecione **Int32** na lista suspensa **tipo de variável** e pressione ENTER para salvar a variável.</span><span class="sxs-lookup"><span data-stu-id="49b41-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="49b41-130">Clique em **Variáveis** no lado inferior esquerdo do designer de atividade para fechar o painel **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="49b41-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="49b41-131">Para adicionar as atividades de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="49b41-131">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="49b41-132">Clique em **State1** para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="49b41-132">Click **State1** to select it.</span></span> <span data-ttu-id="49b41-133">Na **janela Propriedades**, altere o **DisplayName** para `Initialize Target` .</span><span class="sxs-lookup"><span data-stu-id="49b41-133">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="49b41-134">Se a **janela Propriedades** não for exibida, selecione **janela Propriedades** no menu **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="49b41-134">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="49b41-135">Clique duas vezes no estado de destino de **inicialização** renomeado recentemente no designer de fluxo de trabalho para expandi-lo.</span><span class="sxs-lookup"><span data-stu-id="49b41-135">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="49b41-136">Arraste uma atividade **atribuir** da seção **primitivas** da caixa de **ferramentas** e solte-a na seção **entrada** do estado.</span><span class="sxs-lookup"><span data-stu-id="49b41-136">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="49b41-137">Digite `Target` na caixa **para** e a expressão a seguir na caixa **Inserir uma expressão C#** ou **Inserir uma expressão VB** .</span><span class="sxs-lookup"><span data-stu-id="49b41-137">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="49b41-138">Se a janela da **Caixa de Ferramentas** não abrir, selecione **Caixa de Ferramentas** no menu **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="49b41-138">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="49b41-139">Retorne à exibição de máquina de estado geral no designer de fluxo de trabalho clicando em **StateMachine** na exibição de navegação estrutural na parte superior do designer de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="49b41-139">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="49b41-140">Arraste uma atividade de **estado** da seção **máquina de estado** da **caixa de ferramentas** para o designer de fluxo de trabalho e passe o mouse sobre o estado de destino de **inicialização** .</span><span class="sxs-lookup"><span data-stu-id="49b41-140">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="49b41-141">Observe que quatro triângulos aparecerão em torno do estado de **inicialização de destino** quando o novo estado estiver sobre ele.</span><span class="sxs-lookup"><span data-stu-id="49b41-141">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="49b41-142">Descarte o novo estado no triângulo imediatamente abaixo do estado de **inicialização de destino** .</span><span class="sxs-lookup"><span data-stu-id="49b41-142">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="49b41-143">Isso coloca o novo estado no fluxo de trabalho e cria uma transição do estado de **destino de inicialização** para o novo estado.</span><span class="sxs-lookup"><span data-stu-id="49b41-143">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="49b41-144">Clique em **State1** para selecioná-lo, altere o **DisplayName** para `Enter Guess` e clique duas vezes no estado no designer de fluxo de trabalho para expandi-lo.</span><span class="sxs-lookup"><span data-stu-id="49b41-144">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="49b41-145">Arraste uma atividade **WriteLine** da seção **primitivas** da caixa de **ferramentas** e solte-a na seção **entrada** do estado.</span><span class="sxs-lookup"><span data-stu-id="49b41-145">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="49b41-146">Digite a expressão a seguir na caixa de propriedade **texto** de **WriteLine**.</span><span class="sxs-lookup"><span data-stu-id="49b41-146">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="49b41-147">Arraste uma atividade **assign** da seção **primitivas** da caixa de **ferramentas** e solte na seção **sair** do estado.</span><span class="sxs-lookup"><span data-stu-id="49b41-147">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="49b41-148">Digite `Turns` na caixa **para** e `Turns + 1` na caixa **Inserir uma expressão C#** ou **Inserir uma expressão VB** .</span><span class="sxs-lookup"><span data-stu-id="49b41-148">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="49b41-149">Retorne à exibição de máquina de estado geral no designer de fluxo de trabalho clicando em **StateMachine** na exibição de navegação estrutural na parte superior do designer de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="49b41-149">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="49b41-150">Arraste uma atividade **FinalState** da seção **máquina de estado** da **caixa de ferramentas**, passe o mouse sobre o estado de **adivinhação Enter** e solte-o no triângulo que aparece à direita do estado de **estimativa Enter** para que uma transição seja criada entre **Enter estimativa** e **FinalState**.</span><span class="sxs-lookup"><span data-stu-id="49b41-150">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="49b41-151">O nome padrão da transição é **T2**.</span><span class="sxs-lookup"><span data-stu-id="49b41-151">The default name of the transition is **T2**.</span></span> <span data-ttu-id="49b41-152">Clique na transição no designer de fluxo de trabalho para selecioná-la e defina seu **DisplayName** como **palpite correto**.</span><span class="sxs-lookup"><span data-stu-id="49b41-152">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="49b41-153">Em seguida, clique e selecione o **FinalState** e arraste-o para a direita para que haja espaço para que o nome de transição completo seja exibido sem sobreposição de qualquer um dos dois Estados.</span><span class="sxs-lookup"><span data-stu-id="49b41-153">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="49b41-154">Isso facilitará a conclusão das etapas restantes no tutorial.</span><span class="sxs-lookup"><span data-stu-id="49b41-154">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="49b41-155">Clique duas vezes na transição **correta de adivinhação** renomeada no designer de fluxo de trabalho para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="49b41-155">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="49b41-156">Arraste uma atividade **ReadInt** da seção **NumberGuessWorkflowActivities** da caixa de **ferramentas** e solte-a na seção **gatilho** da transição.</span><span class="sxs-lookup"><span data-stu-id="49b41-156">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="49b41-157">Na **janela Propriedades** da atividade **ReadInt** , digite `"EnterGuess"` incluindo as aspas na caixa valor da propriedade **BookmarkName** e digite `Guess` na caixa valor da propriedade de **resultado**</span><span class="sxs-lookup"><span data-stu-id="49b41-157">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="49b41-158">Digite a expressão a seguir na caixa de valor da propriedade **Condition** da transição **correta** .</span><span class="sxs-lookup"><span data-stu-id="49b41-158">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="49b41-159">Retorne à exibição de máquina de estado geral no designer de fluxo de trabalho clicando em **StateMachine** na exibição de navegação estrutural na parte superior do designer de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="49b41-159">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="49b41-160">Uma transição ocorre quando o evento de gatilho é recebido e o <xref:System.Activities.Statements.Transition.Condition%2A>, se houver, é avaliado como `True`.</span><span class="sxs-lookup"><span data-stu-id="49b41-160">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="49b41-161">Para essa transição, se o usuário `Guess` corresponder ao gerado aleatoriamente `Target` , o controle passará para o **FinalState** e o fluxo de trabalho será concluído.</span><span class="sxs-lookup"><span data-stu-id="49b41-161">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="49b41-162">Dependendo se a estimativa está correta, o fluxo de trabalho deve fazer a transição para o **FinalState** ou de volta para o estado de **adivinhação Enter** para outra tentativa.</span><span class="sxs-lookup"><span data-stu-id="49b41-162">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="49b41-163">Ambas as transições compartilham o mesmo gatilho de aguardando que a adivinhação do usuário seja recebida por meio da atividade **ReadInt** .</span><span class="sxs-lookup"><span data-stu-id="49b41-163">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="49b41-164">Isso é chamado de uma transição compartilhada.</span><span class="sxs-lookup"><span data-stu-id="49b41-164">This is called a shared transition.</span></span> <span data-ttu-id="49b41-165">Para criar uma transição compartilhada, clique no círculo que indica o início da transição de **adivinhação correta** e arraste-a para o estado desejado.</span><span class="sxs-lookup"><span data-stu-id="49b41-165">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="49b41-166">Nesse caso, a transição é uma transição automática, portanto, arraste o ponto inicial da transição de **adivinhação correta** e solte-a de volta na parte inferior do estado de **adivinhação Enter** .</span><span class="sxs-lookup"><span data-stu-id="49b41-166">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="49b41-167">Depois de criar a transição, selecione-a no designer de fluxo de trabalho e defina sua propriedade **DisplayName** como **adivinhar incorreta**.</span><span class="sxs-lookup"><span data-stu-id="49b41-167">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="49b41-168">As transições compartilhadas também podem ser criadas de dentro do designer de transição clicando em **Adicionar transição de gatilho compartilhado** na parte inferior do designer de transição e, em seguida, selecionando o estado de destino desejado na lista suspensa **Estados disponíveis para conexão** .</span><span class="sxs-lookup"><span data-stu-id="49b41-168">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="49b41-169">Observe que se <xref:System.Activities.Statements.Transition.Condition%2A> de uma transição for avaliada como `false` (ou todas as condições de uma transição do gatilho compartilhada for avaliada como `false`), a transição não ocorrerá e todos os gatilhos para todas as transições de estado serão reprogramados.</span><span class="sxs-lookup"><span data-stu-id="49b41-169">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="49b41-170">Neste tutorial, essa situação não pode ocorrer devido à maneira como as condições são configuradas (temos ações específicas para se o palpite está correto ou incorreto).</span><span class="sxs-lookup"><span data-stu-id="49b41-170">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="49b41-171">Clique duas vezes em **adivinhar transição incorreta** no designer de fluxo de trabalho para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="49b41-171">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="49b41-172">Observe que o **gatilho** já está definido como a mesma atividade **ReadInt** que foi usada pela transição de **adivinhação correta** .</span><span class="sxs-lookup"><span data-stu-id="49b41-172">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="49b41-173">Digite a expressão a seguir na caixa valor da propriedade de **condição** .</span><span class="sxs-lookup"><span data-stu-id="49b41-173">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="49b41-174">Arraste uma atividade **If** da seção **fluxo de controle** da **caixa de ferramentas** e solte-a na seção **ação** da transição.</span><span class="sxs-lookup"><span data-stu-id="49b41-174">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="49b41-175">Digite a expressão a seguir na caixa de valor da propriedade **condição** **If** da atividade.</span><span class="sxs-lookup"><span data-stu-id="49b41-175">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
24. <span data-ttu-id="49b41-176">Arraste duas atividades **WriteLine** da seção **primitivas** da caixa de **ferramentas** e solte-as para que uma esteja na seção **em seguida** da atividade **se** e outra esteja na seção **else** .</span><span class="sxs-lookup"><span data-stu-id="49b41-176">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="49b41-177">Clique na atividade **WriteLine** na seção **em seguida** para selecioná-la e digite a expressão a seguir na caixa valor da propriedade de **texto** .</span><span class="sxs-lookup"><span data-stu-id="49b41-177">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="49b41-178">Clique na atividade **WriteLine** na seção **else** para selecioná-la e digite a expressão a seguir na caixa valor da propriedade de **texto** .</span><span class="sxs-lookup"><span data-stu-id="49b41-178">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="49b41-179">Retorne à exibição de máquina de estado geral no designer de fluxo de trabalho clicando em **StateMachine** na exibição de navegação estrutural na parte superior do designer de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="49b41-179">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="49b41-180">O exemplo a seguir ilustra o fluxo de trabalho concluído.</span><span class="sxs-lookup"><span data-stu-id="49b41-180">The following example illustrates the completed workflow.</span></span>  
  
     ![Ilustração que mostra o fluxo de trabalho da máquina de estado concluído.](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="49b41-182">Para compilar o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="49b41-182">To build the workflow</span></span>  
  
1. <span data-ttu-id="49b41-183">Pressione CTRL+SHIFT+B para criar a solução.</span><span class="sxs-lookup"><span data-stu-id="49b41-183">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="49b41-184">Para obter instruções sobre como executar o fluxo de trabalho, consulte o próximo tópico [como: executar um fluxo de trabalho](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="49b41-184">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="49b41-185">Se você já tiver concluído a etapa [como executar um fluxo de trabalho](how-to-run-a-workflow.md) com um estilo diferente de fluxo de trabalho e desejar executá-lo usando o fluxo de trabalho da máquina de estado nesta etapa, pule para a seção [para criar e executar o aplicativo](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [como executar um fluxo de trabalho](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="49b41-185">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b41-186">Veja também</span><span class="sxs-lookup"><span data-stu-id="49b41-186">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="49b41-187">Programação do Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="49b41-187">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="49b41-188">Criando fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="49b41-188">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="49b41-189">Guia de introdução ao tutorial</span><span class="sxs-lookup"><span data-stu-id="49b41-189">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="49b41-190">Como: criar uma atividade</span><span class="sxs-lookup"><span data-stu-id="49b41-190">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="49b41-191">Como: executar um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="49b41-191">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
