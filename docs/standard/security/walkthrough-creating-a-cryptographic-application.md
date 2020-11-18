---
title: 'Passo a passo: criar um aplicativo criptográfico'
description: Percorra a criação de um aplicativo criptográfico. Saiba como criptografar e descriptografar o conteúdo em um aplicativo Windows Forms.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET], example
- cryptography [NET], cryptographic application example
- cryptography [NET], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
ms.openlocfilehash: 70218d60abb336cdb35fc2e89e62a50b6bd79c67
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830552"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="3c705-104">Passo a passo: criar um aplicativo criptográfico</span><span class="sxs-lookup"><span data-stu-id="3c705-104">Walkthrough: Creating a Cryptographic Application</span></span>

> [!NOTE]
> <span data-ttu-id="3c705-105">Este artigo aplica-se ao Windows.</span><span class="sxs-lookup"><span data-stu-id="3c705-105">This article applies to Windows.</span></span>
>
> <span data-ttu-id="3c705-106">Para obter informações sobre ASP.NET Core, consulte [proteção de dados do ASP.NET Core](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="3c705-106">For information about ASP.NET Core, see [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span></span>

<span data-ttu-id="3c705-107">Este tutorial demonstra como criptografar e descriptografar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3c705-107">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="3c705-108">Os exemplos de código são projetados para um aplicativo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3c705-108">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="3c705-109">Este aplicativo não demonstra cenários do mundo real, como o uso de cartões inteligentes.</span><span class="sxs-lookup"><span data-stu-id="3c705-109">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="3c705-110">Em vez disso, ele demonstra os conceitos básicos de criptografia e descriptografia.</span><span class="sxs-lookup"><span data-stu-id="3c705-110">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
<span data-ttu-id="3c705-111">Este tutorial usa as seguintes diretrizes para criptografia:</span><span class="sxs-lookup"><span data-stu-id="3c705-111">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="3c705-112">Use a <xref:System.Security.Cryptography.Aes> classe, um algoritmo simétrico, para criptografar e descriptografar dados usando seu automaticamente gerado <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> e <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A> .</span><span class="sxs-lookup"><span data-stu-id="3c705-112">Use the <xref:System.Security.Cryptography.Aes> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="3c705-113">Use o <xref:System.Security.Cryptography.RSA> algoritmo assimétrico para criptografar e descriptografar a chave para os dados criptografados pelo <xref:System.Security.Cryptography.Aes> .</span><span class="sxs-lookup"><span data-stu-id="3c705-113">Use the <xref:System.Security.Cryptography.RSA> asymmetric algorithm to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.Aes>.</span></span> <span data-ttu-id="3c705-114">Os algoritmos assimétricos são mais bem usados para quantidades menores de dados, como uma chave.</span><span class="sxs-lookup"><span data-stu-id="3c705-114">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3c705-115">Se você quiser proteger os dados em seu computador em vez de trocar o conteúdo criptografado por outras pessoas, considere usar a <xref:System.Security.Cryptography.ProtectedData> classe.</span><span class="sxs-lookup"><span data-stu-id="3c705-115">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> class.</span></span>  
  
 <span data-ttu-id="3c705-116">A tabela a seguir resume as tarefas de criptografia neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3c705-116">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="3c705-117">Tarefa</span><span class="sxs-lookup"><span data-stu-id="3c705-117">Task</span></span>|<span data-ttu-id="3c705-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c705-118">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="3c705-119">Criando um aplicativo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c705-119">Creating a Windows Forms application</span></span>|<span data-ttu-id="3c705-120">Lista os controles que são necessários para executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c705-120">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="3c705-121">Declarando objetos globais</span><span class="sxs-lookup"><span data-stu-id="3c705-121">Declaring global objects</span></span>|<span data-ttu-id="3c705-122">Declara as variáveis de caminho da cadeia de caracteres, o <xref:System.Security.Cryptography.CspParameters> e o <xref:System.Security.Cryptography.RSACryptoServiceProvider> para ter o contexto global da <xref:System.Windows.Forms.Form> classe.</span><span class="sxs-lookup"><span data-stu-id="3c705-122">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="3c705-123">Criando uma chave assimétrica</span><span class="sxs-lookup"><span data-stu-id="3c705-123">Creating an asymmetric key</span></span>|<span data-ttu-id="3c705-124">Cria um par de valor de chave pública e privada assimétrica e atribui a ele um nome de contêiner de chave.</span><span class="sxs-lookup"><span data-stu-id="3c705-124">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="3c705-125">Criptografando um arquivo</span><span class="sxs-lookup"><span data-stu-id="3c705-125">Encrypting a file</span></span>|<span data-ttu-id="3c705-126">Exibe uma caixa de diálogo para selecionar um arquivo para criptografia e criptografa o arquivo.</span><span class="sxs-lookup"><span data-stu-id="3c705-126">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="3c705-127">Descriptografando um arquivo</span><span class="sxs-lookup"><span data-stu-id="3c705-127">Decrypting a file</span></span>|<span data-ttu-id="3c705-128">Exibe uma caixa de diálogo para selecionar um arquivo criptografado para descriptografia e descriptografar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="3c705-128">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="3c705-129">Obtendo uma chave privada</span><span class="sxs-lookup"><span data-stu-id="3c705-129">Getting a private key</span></span>|<span data-ttu-id="3c705-130">Obtém o par de chaves completo usando o nome do contêiner de chave.</span><span class="sxs-lookup"><span data-stu-id="3c705-130">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="3c705-131">Exportando uma chave pública</span><span class="sxs-lookup"><span data-stu-id="3c705-131">Exporting a public key</span></span>|<span data-ttu-id="3c705-132">Salva a chave em um arquivo XML somente com parâmetros públicos.</span><span class="sxs-lookup"><span data-stu-id="3c705-132">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="3c705-133">Importando uma chave pública</span><span class="sxs-lookup"><span data-stu-id="3c705-133">Importing a public key</span></span>|<span data-ttu-id="3c705-134">Carrega a chave de um arquivo XML no contêiner de chave.</span><span class="sxs-lookup"><span data-stu-id="3c705-134">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="3c705-135">Testando o aplicativo</span><span class="sxs-lookup"><span data-stu-id="3c705-135">Testing the application</span></span>|<span data-ttu-id="3c705-136">Lista os procedimentos para testar este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c705-136">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="3c705-137">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3c705-137">Prerequisites</span></span>  

<span data-ttu-id="3c705-138">Você precisará dos seguintes componentes para concluir este passo a passo:</span><span class="sxs-lookup"><span data-stu-id="3c705-138">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="3c705-139">Referências aos namespaces <xref:System.IO> e <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="3c705-139">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="3c705-140">Criando um aplicativo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c705-140">Creating a Windows Forms Application</span></span>  

<span data-ttu-id="3c705-141">A maioria dos exemplos de código neste passo a passos é projetada para ser manipuladores de eventos para controles de botão.</span><span class="sxs-lookup"><span data-stu-id="3c705-141">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="3c705-142">A tabela a seguir lista os controles necessários para o aplicativo de exemplo e seus nomes necessários para corresponder aos exemplos de código.</span><span class="sxs-lookup"><span data-stu-id="3c705-142">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="3c705-143">Control</span><span class="sxs-lookup"><span data-stu-id="3c705-143">Control</span></span>|<span data-ttu-id="3c705-144">Nome</span><span class="sxs-lookup"><span data-stu-id="3c705-144">Name</span></span>|<span data-ttu-id="3c705-145">Propriedade Text (conforme necessário)</span><span class="sxs-lookup"><span data-stu-id="3c705-145">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="3c705-146">Criptografar arquivo</span><span class="sxs-lookup"><span data-stu-id="3c705-146">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="3c705-147">Descriptografar arquivo</span><span class="sxs-lookup"><span data-stu-id="3c705-147">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="3c705-148">Criar chaves</span><span class="sxs-lookup"><span data-stu-id="3c705-148">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="3c705-149">Exportar chave pública</span><span class="sxs-lookup"><span data-stu-id="3c705-149">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="3c705-150">Importar chave pública</span><span class="sxs-lookup"><span data-stu-id="3c705-150">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="3c705-151">Obter chave privada</span><span class="sxs-lookup"><span data-stu-id="3c705-151">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="3c705-152">Chave não definida</span><span class="sxs-lookup"><span data-stu-id="3c705-152">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="3c705-153">Clique duas vezes nos botões no designer do Visual Studio para criar seus manipuladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="3c705-153">Double-click the buttons in the Visual Studio designer to create their event handlers.</span></span>
  
## <a name="declaring-global-objects"></a><span data-ttu-id="3c705-154">Declarando objetos globais</span><span class="sxs-lookup"><span data-stu-id="3c705-154">Declaring Global Objects</span></span>  

<span data-ttu-id="3c705-155">Adicione o código a seguir ao construtor do formulário.</span><span class="sxs-lookup"><span data-stu-id="3c705-155">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="3c705-156">Edite as variáveis de cadeia de caracteres para seu ambiente e preferências.</span><span class="sxs-lookup"><span data-stu-id="3c705-156">Edit the string variables for your environment and preferences.</span></span>  
  
[!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
[!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="3c705-157">Criando uma chave assimétrica</span><span class="sxs-lookup"><span data-stu-id="3c705-157">Creating an Asymmetric Key</span></span>  

<span data-ttu-id="3c705-158">Essa tarefa cria uma chave assimétrica que criptografa e descriptografa a <xref:System.Security.Cryptography.Aes> chave.</span><span class="sxs-lookup"><span data-stu-id="3c705-158">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.Aes> key.</span></span> <span data-ttu-id="3c705-159">Essa chave foi usada para criptografar o conteúdo e exibe o nome do contêiner de chave no controle rótulo.</span><span class="sxs-lookup"><span data-stu-id="3c705-159">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="3c705-160">Adicione o código a seguir como o `Click` manipulador de eventos para o `Create Keys` botão ( `buttonCreateAsmKeys_Click` ).</span><span class="sxs-lookup"><span data-stu-id="3c705-160">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="3c705-161">Criptografando um arquivo</span><span class="sxs-lookup"><span data-stu-id="3c705-161">Encrypting a File</span></span>  

<span data-ttu-id="3c705-162">Essa tarefa envolve dois métodos: o método manipulador de eventos para o `Encrypt File` botão ( `buttonEncryptFile_Click` ) e o `EncryptFile` método.</span><span class="sxs-lookup"><span data-stu-id="3c705-162">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="3c705-163">O primeiro método exibe uma caixa de diálogo para selecionar um arquivo e passa o nome do arquivo para o segundo método, que executa a criptografia.</span><span class="sxs-lookup"><span data-stu-id="3c705-163">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
<span data-ttu-id="3c705-164">O conteúdo criptografado, a chave e o IV são todos salvos em um <xref:System.IO.FileStream> , que é conhecido como o pacote de criptografia.</span><span class="sxs-lookup"><span data-stu-id="3c705-164">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
<span data-ttu-id="3c705-165">O `EncryptFile` método faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3c705-165">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="3c705-166">Cria um <xref:System.Security.Cryptography.Aes> algoritmo simétrico para criptografar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3c705-166">Creates a <xref:System.Security.Cryptography.Aes> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="3c705-167">Cria um <xref:System.Security.Cryptography.RSACryptoServiceProvider> objeto para criptografar a <xref:System.Security.Cryptography.Aes> chave.</span><span class="sxs-lookup"><span data-stu-id="3c705-167">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.Aes> key.</span></span>  
  
3. <span data-ttu-id="3c705-168">Usa um <xref:System.Security.Cryptography.CryptoStream> objeto para ler e criptografar o <xref:System.IO.FileStream> do arquivo de origem, em blocos de bytes, em um <xref:System.IO.FileStream> objeto de destino para o arquivo criptografado.</span><span class="sxs-lookup"><span data-stu-id="3c705-168">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="3c705-169">Determina os comprimentos da chave criptografada e IV e cria matrizes de bytes de seus valores de comprimento.</span><span class="sxs-lookup"><span data-stu-id="3c705-169">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="3c705-170">Grava a chave, o IV e seus valores de comprimento para o pacote criptografado.</span><span class="sxs-lookup"><span data-stu-id="3c705-170">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="3c705-171">O pacote de criptografia usa o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="3c705-171">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="3c705-172">Comprimento da chave, bytes 0-3</span><span class="sxs-lookup"><span data-stu-id="3c705-172">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="3c705-173">Comprimento de IV, bytes 4-7</span><span class="sxs-lookup"><span data-stu-id="3c705-173">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="3c705-174">Chave criptografada</span><span class="sxs-lookup"><span data-stu-id="3c705-174">Encrypted key</span></span>  
  
- <span data-ttu-id="3c705-175">IV</span><span class="sxs-lookup"><span data-stu-id="3c705-175">IV</span></span>  
  
- <span data-ttu-id="3c705-176">Texto cifrado</span><span class="sxs-lookup"><span data-stu-id="3c705-176">Cipher text</span></span>  
  
 <span data-ttu-id="3c705-177">Você pode usar os comprimentos da chave e do IV para determinar os pontos de partida e os comprimentos de todas as partes do pacote de criptografia, que podem ser usados para descriptografar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="3c705-177">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="3c705-178">Adicione o código a seguir como o `Click` manipulador de eventos para o `Encrypt File` botão ( `buttonEncryptFile_Click` ).</span><span class="sxs-lookup"><span data-stu-id="3c705-178">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="3c705-179">Adicione o seguinte `EncryptFile` método ao formulário.</span><span class="sxs-lookup"><span data-stu-id="3c705-179">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="3c705-180">Descriptografando um arquivo</span><span class="sxs-lookup"><span data-stu-id="3c705-180">Decrypting a File</span></span>  

<span data-ttu-id="3c705-181">Essa tarefa envolve dois métodos, o método manipulador de eventos para o `Decrypt File` botão ( `buttonDecryptFile_Click` ) e o `DecryptFile` método.</span><span class="sxs-lookup"><span data-stu-id="3c705-181">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="3c705-182">O primeiro método exibe uma caixa de diálogo para selecionar um arquivo e passa seu nome de arquivo para o segundo método, que executa a descriptografia.</span><span class="sxs-lookup"><span data-stu-id="3c705-182">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
<span data-ttu-id="3c705-183">O `Decrypt` método faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3c705-183">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="3c705-184">Cria um <xref:System.Security.Cryptography.Aes> algoritmo simétrico para descriptografar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3c705-184">Creates an <xref:System.Security.Cryptography.Aes> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="3c705-185">Lê os primeiros oito bytes do <xref:System.IO.FileStream> pacote criptografado em matrizes de bytes para obter os comprimentos da chave criptografada e o IV.</span><span class="sxs-lookup"><span data-stu-id="3c705-185">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="3c705-186">Extrai a chave e o IV do pacote de criptografia em matrizes de bytes.</span><span class="sxs-lookup"><span data-stu-id="3c705-186">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="3c705-187">Cria um <xref:System.Security.Cryptography.RSACryptoServiceProvider> objeto para descriptografar a <xref:System.Security.Cryptography.Aes> chave.</span><span class="sxs-lookup"><span data-stu-id="3c705-187">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.Aes> key.</span></span>  
  
5. <span data-ttu-id="3c705-188">Usa um <xref:System.Security.Cryptography.CryptoStream> objeto para ler e descriptografar a seção de texto cifrado do <xref:System.IO.FileStream> pacote de criptografia, em blocos de bytes, no <xref:System.IO.FileStream> objeto do arquivo descriptografado.</span><span class="sxs-lookup"><span data-stu-id="3c705-188">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="3c705-189">Quando isso for concluído, a descriptografia será concluída.</span><span class="sxs-lookup"><span data-stu-id="3c705-189">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="3c705-190">Adicione o código a seguir como o `Click` manipulador de eventos para o `Decrypt File` botão.</span><span class="sxs-lookup"><span data-stu-id="3c705-190">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="3c705-191">Adicione o seguinte `DecryptFile` método ao formulário.</span><span class="sxs-lookup"><span data-stu-id="3c705-191">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="3c705-192">Exportando uma chave pública</span><span class="sxs-lookup"><span data-stu-id="3c705-192">Exporting a Public Key</span></span>

<span data-ttu-id="3c705-193">Essa tarefa salva a chave criada pelo `Create Keys` botão em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3c705-193">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="3c705-194">Ele exporta apenas os parâmetros públicos.</span><span class="sxs-lookup"><span data-stu-id="3c705-194">It exports only the public parameters.</span></span>  
  
<span data-ttu-id="3c705-195">Essa tarefa simula o cenário de Alice dando a Bob sua chave pública para que ele possa criptografar arquivos.</span><span class="sxs-lookup"><span data-stu-id="3c705-195">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="3c705-196">Ele e outros que tenham essa chave pública não poderão descriptografá-los porque não têm o par de chaves completo com parâmetros privados.</span><span class="sxs-lookup"><span data-stu-id="3c705-196">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
<span data-ttu-id="3c705-197">Adicione o código a seguir como o `Click` manipulador de eventos para o `Export Public Key` botão ( `buttonExportPublicKey_Click` ).</span><span class="sxs-lookup"><span data-stu-id="3c705-197">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
[!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="3c705-198">Importando uma chave pública</span><span class="sxs-lookup"><span data-stu-id="3c705-198">Importing a Public Key</span></span>

<span data-ttu-id="3c705-199">Essa tarefa carrega a chave somente com parâmetros públicos, conforme criado pelo `Export Public Key` botão e o define como o nome do contêiner de chave.</span><span class="sxs-lookup"><span data-stu-id="3c705-199">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
<span data-ttu-id="3c705-200">Esta tarefa simula o cenário de Bob carregando a chave de Alice com apenas parâmetros públicos, portanto, ele pode criptografar arquivos.</span><span class="sxs-lookup"><span data-stu-id="3c705-200">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
<span data-ttu-id="3c705-201">Adicione o código a seguir como o `Click` manipulador de eventos para o `Import Public Key` botão ( `buttonImportPublicKey_Click` ).</span><span class="sxs-lookup"><span data-stu-id="3c705-201">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
[!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="3c705-202">Obtendo uma chave privada</span><span class="sxs-lookup"><span data-stu-id="3c705-202">Getting a Private Key</span></span>  

<span data-ttu-id="3c705-203">Essa tarefa define o nome do contêiner de chave como o nome da chave criada usando o `Create Keys` botão.</span><span class="sxs-lookup"><span data-stu-id="3c705-203">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="3c705-204">O contêiner de chave conterá o par de chaves completo com parâmetros privados.</span><span class="sxs-lookup"><span data-stu-id="3c705-204">The key container will contain the full key pair with private parameters.</span></span>  
  
<span data-ttu-id="3c705-205">Esta tarefa simula o cenário de Alice usando sua chave privada para descriptografar arquivos criptografados por Bob.</span><span class="sxs-lookup"><span data-stu-id="3c705-205">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
<span data-ttu-id="3c705-206">Adicione o código a seguir como o `Click` manipulador de eventos para o `Get Private Key` botão ( `buttonGetPrivateKey_Click` ).</span><span class="sxs-lookup"><span data-stu-id="3c705-206">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
[!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="3c705-207">Testando o aplicativo</span><span class="sxs-lookup"><span data-stu-id="3c705-207">Testing the Application</span></span>

<span data-ttu-id="3c705-208">Depois de criar o aplicativo, execute os seguintes cenários de teste.</span><span class="sxs-lookup"><span data-stu-id="3c705-208">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="3c705-209">Para criar chaves, criptografar e descriptografar</span><span class="sxs-lookup"><span data-stu-id="3c705-209">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="3c705-210">Clique no botão `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="3c705-210">Click the `Create Keys` button.</span></span> <span data-ttu-id="3c705-211">O rótulo exibe o nome da chave e mostra que ele é um par de chaves completo.</span><span class="sxs-lookup"><span data-stu-id="3c705-211">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="3c705-212">Clique no botão `Export Public Key`.</span><span class="sxs-lookup"><span data-stu-id="3c705-212">Click the `Export Public Key` button.</span></span> <span data-ttu-id="3c705-213">Observe que a exportação dos parâmetros de chave pública não altera a chave atual.</span><span class="sxs-lookup"><span data-stu-id="3c705-213">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="3c705-214">Clique no `Encrypt File` botão e selecione um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3c705-214">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="3c705-215">Clique no `Decrypt File` botão e selecione o arquivo que acabou de ser criptografado.</span><span class="sxs-lookup"><span data-stu-id="3c705-215">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="3c705-216">Examine o arquivo apenas descriptografado.</span><span class="sxs-lookup"><span data-stu-id="3c705-216">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="3c705-217">Feche o aplicativo e reinicie-o para testar a recuperação de contêineres de chave persistentes no próximo cenário.</span><span class="sxs-lookup"><span data-stu-id="3c705-217">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="3c705-218">Para criptografar usando a chave pública</span><span class="sxs-lookup"><span data-stu-id="3c705-218">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="3c705-219">Clique no botão `Import Public Key`.</span><span class="sxs-lookup"><span data-stu-id="3c705-219">Click the `Import Public Key` button.</span></span> <span data-ttu-id="3c705-220">O rótulo exibe o nome da chave e mostra que ele é somente público.</span><span class="sxs-lookup"><span data-stu-id="3c705-220">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="3c705-221">Clique no `Encrypt File` botão e selecione um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3c705-221">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="3c705-222">Clique no `Decrypt File` botão e selecione o arquivo que acabou de ser criptografado.</span><span class="sxs-lookup"><span data-stu-id="3c705-222">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="3c705-223">Isso irá falhar porque você deve ter a chave privada para descriptografar.</span><span class="sxs-lookup"><span data-stu-id="3c705-223">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="3c705-224">Este cenário demonstra como ter apenas a chave pública para criptografar um arquivo para outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="3c705-224">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="3c705-225">Normalmente, essa pessoa daria apenas a chave pública e a chave privada para a descriptografia.</span><span class="sxs-lookup"><span data-stu-id="3c705-225">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="3c705-226">Para descriptografar usando a chave privada</span><span class="sxs-lookup"><span data-stu-id="3c705-226">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="3c705-227">Clique no botão `Get Private Key`.</span><span class="sxs-lookup"><span data-stu-id="3c705-227">Click the `Get Private Key` button.</span></span> <span data-ttu-id="3c705-228">O rótulo exibe o nome da chave e mostra se ele é o par de chaves completo.</span><span class="sxs-lookup"><span data-stu-id="3c705-228">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="3c705-229">Clique no `Decrypt File` botão e selecione o arquivo que acabou de ser criptografado.</span><span class="sxs-lookup"><span data-stu-id="3c705-229">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="3c705-230">Isso será bem-sucedido porque você tem o par de chaves completo a ser descriptografado.</span><span class="sxs-lookup"><span data-stu-id="3c705-230">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c705-231">Confira também</span><span class="sxs-lookup"><span data-stu-id="3c705-231">See also</span></span>

- <span data-ttu-id="3c705-232">[Modelo de criptografia](cryptography-model.md) – descreve como a criptografia é implementada na biblioteca de classes base.</span><span class="sxs-lookup"><span data-stu-id="3c705-232">[Cryptography Model](cryptography-model.md) - Describes how cryptography is implemented in the base class library.</span></span>
- [<span data-ttu-id="3c705-233">Serviços criptográficos</span><span class="sxs-lookup"><span data-stu-id="3c705-233">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="3c705-234">Criptografia de plataforma cruzada</span><span class="sxs-lookup"><span data-stu-id="3c705-234">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="3c705-235">Proteção de dados do ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c705-235">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
