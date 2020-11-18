---
title: Segurança e entrada do usuário
description: Seu código pode passar dados inseridos pelo usuário como parâmetros para outro código, o que pode afetar a segurança. Você pode fazer a verificação de intervalo para rejeitar a entrada problemática.
ms.date: 07/15/2020
helpviewer_keywords:
- security [.NET], user input
- user input, security
- secure coding, user input
- code security, user input
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
ms.openlocfilehash: e476db90dd1fd579f4ecfe3f2088cc76c955b9c0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824051"
---
# <a name="security-and-user-input"></a><span data-ttu-id="76b43-104">Segurança e entrada do usuário</span><span class="sxs-lookup"><span data-stu-id="76b43-104">Security and User Input</span></span>

<span data-ttu-id="76b43-105">Os dados do usuário, que são qualquer tipo de entrada (dados de uma solicitação da Web ou URL, entrada para controles de um aplicativo Microsoft Windows Forms e assim por diante) podem influenciar o código de forma adversa, pois geralmente esses dados são usados diretamente como parâmetros para chamar outro código.</span><span class="sxs-lookup"><span data-stu-id="76b43-105">User data, which is any kind of input (data from a Web request or URL, input to controls of a Microsoft Windows Forms application, and so on), can adversely influence code because often that data is used directly as parameters to call other code.</span></span> <span data-ttu-id="76b43-106">Essa situação é análoga ao código mal-intencionado que chama seu código com parâmetros estranhos e as mesmas precauções devem ser tomadas.</span><span class="sxs-lookup"><span data-stu-id="76b43-106">This situation is analogous to malicious code calling your code with strange parameters, and the same precautions should be taken.</span></span> <span data-ttu-id="76b43-107">A entrada do usuário é realmente mais difícil de se tornar segura, pois não há um quadro de pilha para rastrear a presença dos dados potencialmente não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="76b43-107">User input is actually harder to make safe because there is no stack frame to trace the presence of the potentially untrusted data.</span></span>

<span data-ttu-id="76b43-108">Esses são os bugs de segurança mais sutis e difíceis de serem encontrados porque, embora possam existir em código que pareça não estar relacionado à segurança, eles são um gateway para passar dados inválidos para outro código.</span><span class="sxs-lookup"><span data-stu-id="76b43-108">These are among the subtlest and hardest security bugs to find because, although they can exist in code that is seemingly unrelated to security, they are a gateway to pass bad data through to other code.</span></span> <span data-ttu-id="76b43-109">Para procurar esses bugs, siga qualquer tipo de dado de entrada, imagine o que é o intervalo de possíveis valores e considere se o código que vê esses dados pode lidar com todos esses casos.</span><span class="sxs-lookup"><span data-stu-id="76b43-109">To look for these bugs, follow any kind of input data, imagine what the range of possible values might be, and consider whether the code seeing this data can handle all those cases.</span></span> <span data-ttu-id="76b43-110">Você pode corrigir esses bugs por meio da verificação de intervalo e rejeitar qualquer entrada que o código não possa manipular.</span><span class="sxs-lookup"><span data-stu-id="76b43-110">You can fix these bugs through range checking and rejecting any input the code cannot handle.</span></span>

<span data-ttu-id="76b43-111">Algumas considerações importantes envolvendo os dados do usuário incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="76b43-111">Some important considerations involving user data include the following:</span></span>

- <span data-ttu-id="76b43-112">Qualquer dado de usuário em uma resposta de servidor é executado no contexto do site do servidor no cliente.</span><span class="sxs-lookup"><span data-stu-id="76b43-112">Any user data in a server response runs in the context of the server's site on the client.</span></span> <span data-ttu-id="76b43-113">Se o seu servidor Web usa dados de usuário e os insere na página da Web retornada, ele pode, por exemplo, incluir uma **\<script>** marca e executar como se fosse do servidor.</span><span class="sxs-lookup"><span data-stu-id="76b43-113">If your Web server takes user data and inserts it into the returned Web page, it might, for example, include a **\<script>** tag and run as if from the server.</span></span>

- <span data-ttu-id="76b43-114">Lembre-se de que o cliente pode solicitar qualquer URL.</span><span class="sxs-lookup"><span data-stu-id="76b43-114">Remember that the client can request any URL.</span></span>

- <span data-ttu-id="76b43-115">Considere caminhos complicados ou inválidos:</span><span class="sxs-lookup"><span data-stu-id="76b43-115">Consider tricky or invalid paths:</span></span>

  - <span data-ttu-id="76b43-116">.. \, caminhos extremamente longos.</span><span class="sxs-lookup"><span data-stu-id="76b43-116">..\ , extremely long paths.</span></span>

  - <span data-ttu-id="76b43-117">Uso de caracteres curinga (\*).</span><span class="sxs-lookup"><span data-stu-id="76b43-117">Use of wild card characters (\*).</span></span>

  - <span data-ttu-id="76b43-118">Expansão de token (% token%).</span><span class="sxs-lookup"><span data-stu-id="76b43-118">Token expansion (%token%).</span></span>

  - <span data-ttu-id="76b43-119">Formas estranhas de caminhos com significado especial.</span><span class="sxs-lookup"><span data-stu-id="76b43-119">Strange forms of paths with special meaning.</span></span>

  - <span data-ttu-id="76b43-120">Nomes de fluxo do sistema de arquivos alternativos, como `filename::$DATA` .</span><span class="sxs-lookup"><span data-stu-id="76b43-120">Alternate file system stream names such as `filename::$DATA`.</span></span>

  - <span data-ttu-id="76b43-121">Versões curtas de nomes de arquivo, como `longfi~1` para `longfilename` .</span><span class="sxs-lookup"><span data-stu-id="76b43-121">Short versions of file names such as `longfi~1` for `longfilename`.</span></span>

- <span data-ttu-id="76b43-122">Lembre-se de que Eval (UserData) pode fazer qualquer coisa.</span><span class="sxs-lookup"><span data-stu-id="76b43-122">Remember that Eval(userdata) can do anything.</span></span>

- <span data-ttu-id="76b43-123">Tenha cuidado com a associação tardia a um nome que inclua alguns dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="76b43-123">Be wary of late binding to a name that includes some user data.</span></span>

- <span data-ttu-id="76b43-124">Se você estiver lidando com dados da Web, considere as várias formas de escapes que são permitidas, incluindo:</span><span class="sxs-lookup"><span data-stu-id="76b43-124">If you are dealing with Web data, consider the various forms of escapes that are permissible, including:</span></span>

  - <span data-ttu-id="76b43-125">Escapes hexadecimais (% nn).</span><span class="sxs-lookup"><span data-stu-id="76b43-125">Hexadecimal escapes (%nn).</span></span>

  - <span data-ttu-id="76b43-126">Escapes Unicode (% nnn).</span><span class="sxs-lookup"><span data-stu-id="76b43-126">Unicode escapes (%nnn).</span></span>

  - <span data-ttu-id="76b43-127">Escapes UTF-8 longos (% nn% NN).</span><span class="sxs-lookup"><span data-stu-id="76b43-127">Overlong UTF-8 escapes (%nn%nn).</span></span>

  - <span data-ttu-id="76b43-128">Escapes duplos (% nn torna-se% mmnn, em que% mm é o escape para '% ').</span><span class="sxs-lookup"><span data-stu-id="76b43-128">Double escapes (%nn becomes %mmnn, where %mm is the escape for '%').</span></span>

- <span data-ttu-id="76b43-129">Tenha cuidado com nomes de usuário que possam ter mais de um formato canônico.</span><span class="sxs-lookup"><span data-stu-id="76b43-129">Be wary of user names that might have more than one canonical format.</span></span> <span data-ttu-id="76b43-130">Por exemplo, geralmente você pode usar o formulário de nome de usuário mydomain \\ *username* ou o *nome de usuário* @mydomain.example.com .</span><span class="sxs-lookup"><span data-stu-id="76b43-130">For example, you can often use either the MYDOMAIN\\*username* form or the *username*@mydomain.example.com form.</span></span>

## <a name="see-also"></a><span data-ttu-id="76b43-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="76b43-131">See also</span></span>

- [<span data-ttu-id="76b43-132">Diretrizes de codificação segura</span><span class="sxs-lookup"><span data-stu-id="76b43-132">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
- [<span data-ttu-id="76b43-133">Segurança de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76b43-133">ASP.NET Core Security</span></span>](/aspnet/core/security/)
