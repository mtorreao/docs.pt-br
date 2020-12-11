---
title: Cadeias de conexão
ms.date: 12/08/2020
description: As palavras-chave e os valores com suporte das cadeias de conexão.
ms.openlocfilehash: 35283664c4ac3985d4f517fde77644ab2a891120
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110735"
---
# <a name="connection-strings"></a><span data-ttu-id="19004-103">Cadeias de conexão</span><span class="sxs-lookup"><span data-stu-id="19004-103">Connection strings</span></span>

<span data-ttu-id="19004-104">Uma cadeia de conexão é usada para especificar como se conectar ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="19004-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="19004-105">As cadeias de conexão em Microsoft. Data. sqlite seguem a [sintaxe ADO.net](../../../framework/data/adonet/connection-strings.md) padrão como uma lista de palavras-chave e valores separados por ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="19004-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="19004-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="19004-106">Keywords</span></span>

<span data-ttu-id="19004-107">As palavras-chave da cadeia de conexão a seguir podem ser usadas com Microsoft. Data. sqlite:</span><span class="sxs-lookup"><span data-stu-id="19004-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="19004-108">Fonte de dados</span><span class="sxs-lookup"><span data-stu-id="19004-108">Data source</span></span>

<span data-ttu-id="19004-109">O caminho do arquivo de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="19004-109">The path to the database file.</span></span> <span data-ttu-id="19004-110">*DataSource* (sem espaço) e *nome de arquivo* são aliases dessa palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="19004-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="19004-111">O SQLite trata caminhos relativos ao diretório de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="19004-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="19004-112">Caminhos absolutos também podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="19004-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="19004-113">Se **estiver vazio**, o SQLite criará um banco de dados temporário em disco que é excluído quando a conexão é fechada.</span><span class="sxs-lookup"><span data-stu-id="19004-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="19004-114">Se `:memory:` , um banco de dados na memória é usado.</span><span class="sxs-lookup"><span data-stu-id="19004-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="19004-115">Para obter mais informações, consulte [bancos de dados na memória](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="19004-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="19004-116">Os caminhos que começam com a `|DataDirectory|` cadeia de caracteres de substituição são tratados da mesma forma que os caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="19004-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="19004-117">Se definido, os caminhos são feitos em relação ao valor da propriedade de domínio do aplicativo DataDirectory.</span><span class="sxs-lookup"><span data-stu-id="19004-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="19004-118">Essa palavra-chave também dá suporte a [nomes de fileuri](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="19004-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="19004-119">Mode</span><span class="sxs-lookup"><span data-stu-id="19004-119">Mode</span></span>

<span data-ttu-id="19004-120">O modo de conexão.</span><span class="sxs-lookup"><span data-stu-id="19004-120">The connection mode.</span></span>

| <span data-ttu-id="19004-121">Valor</span><span class="sxs-lookup"><span data-stu-id="19004-121">Value</span></span>           | <span data-ttu-id="19004-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="19004-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="19004-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="19004-123">ReadWriteCreate</span></span> | <span data-ttu-id="19004-124">Abre o banco de dados para leitura e gravação e cria-o se ele não existir.</span><span class="sxs-lookup"><span data-stu-id="19004-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="19004-125">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="19004-125">This is the default.</span></span> |
| <span data-ttu-id="19004-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="19004-126">ReadWrite</span></span>       | <span data-ttu-id="19004-127">Abre o banco de dados para leitura e gravação.</span><span class="sxs-lookup"><span data-stu-id="19004-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="19004-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="19004-128">ReadOnly</span></span>        | <span data-ttu-id="19004-129">Abre o banco de dados no modo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="19004-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="19004-130">Memória</span><span class="sxs-lookup"><span data-stu-id="19004-130">Memory</span></span>          | <span data-ttu-id="19004-131">Abre um banco de dados na memória.</span><span class="sxs-lookup"><span data-stu-id="19004-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="19004-132">Cache</span><span class="sxs-lookup"><span data-stu-id="19004-132">Cache</span></span>

<span data-ttu-id="19004-133">O modo de cache usado pela conexão.</span><span class="sxs-lookup"><span data-stu-id="19004-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="19004-134">Valor</span><span class="sxs-lookup"><span data-stu-id="19004-134">Value</span></span>   | <span data-ttu-id="19004-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="19004-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="19004-136">Padrão</span><span class="sxs-lookup"><span data-stu-id="19004-136">Default</span></span> | <span data-ttu-id="19004-137">Usa o modo padrão da biblioteca SQLite subjacente.</span><span class="sxs-lookup"><span data-stu-id="19004-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="19004-138">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="19004-138">This is the default.</span></span>                   |
| <span data-ttu-id="19004-139">Privados</span><span class="sxs-lookup"><span data-stu-id="19004-139">Private</span></span> | <span data-ttu-id="19004-140">Cada conexão usa um cache privado.</span><span class="sxs-lookup"><span data-stu-id="19004-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="19004-141">Compartilhada</span><span class="sxs-lookup"><span data-stu-id="19004-141">Shared</span></span>  | <span data-ttu-id="19004-142">As conexões compartilham um cache.</span><span class="sxs-lookup"><span data-stu-id="19004-142">Connections share a cache.</span></span> <span data-ttu-id="19004-143">Esse modo pode alterar o comportamento do bloqueio de transação e tabela.</span><span class="sxs-lookup"><span data-stu-id="19004-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="19004-144">Senha</span><span class="sxs-lookup"><span data-stu-id="19004-144">Password</span></span>

<span data-ttu-id="19004-145">A chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="19004-145">The encryption key.</span></span> <span data-ttu-id="19004-146">Quando especificado, `PRAGMA key` é enviado imediatamente após a abertura da conexão.</span><span class="sxs-lookup"><span data-stu-id="19004-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="19004-147">A senha não tem efeito quando a criptografia não tem suporte da biblioteca SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="19004-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

> [!NOTE]
> <span data-ttu-id="19004-148">A palavra-chave password foi adicionada na versão 3,0.</span><span class="sxs-lookup"><span data-stu-id="19004-148">The Password keyword was added in version 3.0.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="19004-149">Chaves estrangeiras</span><span class="sxs-lookup"><span data-stu-id="19004-149">Foreign Keys</span></span>

<span data-ttu-id="19004-150">Um valor que indica se as restrições de chave estrangeira devem ser habilitadas.</span><span class="sxs-lookup"><span data-stu-id="19004-150">A value indicating whether to enable foreign key constraints.</span></span>

> [!NOTE]
> <span data-ttu-id="19004-151">A palavra-chave Foreign Keys foi adicionada na versão 3,0.</span><span class="sxs-lookup"><span data-stu-id="19004-151">The Foreign Keys keyword was added in version 3.0.</span></span>

| <span data-ttu-id="19004-152">Valor</span><span class="sxs-lookup"><span data-stu-id="19004-152">Value</span></span>   | <span data-ttu-id="19004-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="19004-153">Description</span></span>
| ------- | --- |
| <span data-ttu-id="19004-154">True</span><span class="sxs-lookup"><span data-stu-id="19004-154">True</span></span>    | <span data-ttu-id="19004-155">Envia `PRAGMA foreign_keys = 1` imediatamente após a abertura da conexão.</span><span class="sxs-lookup"><span data-stu-id="19004-155">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="19004-156">Falso</span><span class="sxs-lookup"><span data-stu-id="19004-156">False</span></span>   | <span data-ttu-id="19004-157">Envia `PRAGMA foreign_keys = 0` imediatamente após a abertura da conexão.</span><span class="sxs-lookup"><span data-stu-id="19004-157">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="19004-158">(vazio)</span><span class="sxs-lookup"><span data-stu-id="19004-158">(empty)</span></span> | <span data-ttu-id="19004-159">Não envia `PRAGMA foreign_keys` .</span><span class="sxs-lookup"><span data-stu-id="19004-159">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="19004-160">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="19004-160">This is the default.</span></span> |

<span data-ttu-id="19004-161">Não há necessidade de habilitar chaves estrangeiras se, como em e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS foi usado para compilar a biblioteca SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="19004-161">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="19004-162">Gatilhos recursivos</span><span class="sxs-lookup"><span data-stu-id="19004-162">Recursive triggers</span></span>

<span data-ttu-id="19004-163">Um valor que indica se os gatilhos recursivos devem ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="19004-163">A value that indicates whether to enable recursive triggers.</span></span>

> [!NOTE]
> <span data-ttu-id="19004-164">A palavra-chave triggers recursivos foi adicionada na versão 3,0.</span><span class="sxs-lookup"><span data-stu-id="19004-164">The Recursive Triggers keyword was added in version 3.0.</span></span>

| <span data-ttu-id="19004-165">Valor</span><span class="sxs-lookup"><span data-stu-id="19004-165">Value</span></span> | <span data-ttu-id="19004-166">Descrição</span><span class="sxs-lookup"><span data-stu-id="19004-166">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="19004-167">True</span><span class="sxs-lookup"><span data-stu-id="19004-167">True</span></span>  | <span data-ttu-id="19004-168">Envia `PRAGMA recursive_triggers` imediatamente após a abertura da conexão.</span><span class="sxs-lookup"><span data-stu-id="19004-168">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="19004-169">Falso</span><span class="sxs-lookup"><span data-stu-id="19004-169">False</span></span> | <span data-ttu-id="19004-170">Não envia `PRAGMA recursive_triggers` .</span><span class="sxs-lookup"><span data-stu-id="19004-170">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="19004-171">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="19004-171">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="19004-172">Construtor de cadeia de conexão</span><span class="sxs-lookup"><span data-stu-id="19004-172">Connection string builder</span></span>

<span data-ttu-id="19004-173">Você pode usar <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> como uma maneira fortemente tipada de criar cadeias de conexão.</span><span class="sxs-lookup"><span data-stu-id="19004-173">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="19004-174">Ele também pode ser usado para evitar ataques de injeção de cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="19004-174">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="19004-175">Exemplos</span><span class="sxs-lookup"><span data-stu-id="19004-175">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="19004-176">Basic</span><span class="sxs-lookup"><span data-stu-id="19004-176">Basic</span></span>

<span data-ttu-id="19004-177">Uma cadeia de conexão básica com um cache compartilhado para simultaneidade aprimorada.</span><span class="sxs-lookup"><span data-stu-id="19004-177">A basic connection string with a shared cache for improved concurrency.</span></span>

```connectionstring
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="19004-178">Criptografado</span><span class="sxs-lookup"><span data-stu-id="19004-178">Encrypted</span></span>

<span data-ttu-id="19004-179">Um banco de dados criptografado.</span><span class="sxs-lookup"><span data-stu-id="19004-179">An encrypted database.</span></span>

```connectionstring
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="19004-180">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19004-180">Read-only</span></span>

<span data-ttu-id="19004-181">Um banco de dados somente leitura que não pode ser modificado pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="19004-181">A read-only database that cannot be modified by the app.</span></span>

```connectionstring
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="19004-182">Na memória</span><span class="sxs-lookup"><span data-stu-id="19004-182">In-memory</span></span>

<span data-ttu-id="19004-183">Um banco de dados privado na memória.</span><span class="sxs-lookup"><span data-stu-id="19004-183">A private, in-memory database.</span></span>

```connectionstring
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="19004-184">Compartilhável na memória</span><span class="sxs-lookup"><span data-stu-id="19004-184">Sharable in-memory</span></span>

<span data-ttu-id="19004-185">Um banco de dados compartilhável e na memória identificado pelo nome *compartilhável*.</span><span class="sxs-lookup"><span data-stu-id="19004-185">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```connectionstring
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="19004-186">Veja também</span><span class="sxs-lookup"><span data-stu-id="19004-186">See also</span></span>

* [<span data-ttu-id="19004-187">Cadeias de conexão em ADO.NET</span><span class="sxs-lookup"><span data-stu-id="19004-187">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="19004-188">Bancos de dados na memória</span><span class="sxs-lookup"><span data-stu-id="19004-188">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="19004-189">Transações</span><span class="sxs-lookup"><span data-stu-id="19004-189">Transactions</span></span>](transactions.md)
