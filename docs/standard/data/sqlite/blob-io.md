---
title: E/S de Blob
ms.date: 12/08/2020
description: Saiba como usar O recurso de e/s de BLOB do SQLite.
ms.openlocfilehash: 8b305669f3155d2366215e9a05beb5ed51533d81
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110039"
---
# <a name="blob-io"></a><span data-ttu-id="ecce4-103">E/S de Blob</span><span class="sxs-lookup"><span data-stu-id="ecce4-103">Blob I/O</span></span>

> [!NOTE]
> <span data-ttu-id="ecce4-104">A classe SqliteBlob foi adicionada na versão 3,0.</span><span class="sxs-lookup"><span data-stu-id="ecce4-104">The SqliteBlob class was added in version 3.0.</span></span>

<span data-ttu-id="ecce4-105">Você pode reduzir o uso de memória durante a leitura e a gravação de objetos grandes transmitindo os dados para dentro e fora dele.</span><span class="sxs-lookup"><span data-stu-id="ecce4-105">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="ecce4-106">Isso pode ser especialmente útil ao analisar ou transformar os dados.</span><span class="sxs-lookup"><span data-stu-id="ecce4-106">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="ecce4-107">Comece inserindo uma linha como normal.</span><span class="sxs-lookup"><span data-stu-id="ecce4-107">Start by inserting a row as normal.</span></span> <span data-ttu-id="ecce4-108">Use a `zeroblob()` função SQL para alocar espaço no banco de dados para conter o objeto grande.</span><span class="sxs-lookup"><span data-stu-id="ecce4-108">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="ecce4-109">A `last_insert_rowid()` função fornece uma maneira conveniente de obter seu ROWID.</span><span class="sxs-lookup"><span data-stu-id="ecce4-109">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="ecce4-110">Depois de inserir a linha, abra um fluxo para gravar o objeto grande usando <xref:Microsoft.Data.Sqlite.SqliteBlob> .</span><span class="sxs-lookup"><span data-stu-id="ecce4-110">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="ecce4-111">Para transmitir o objeto grande para fora do banco de dados, você deve selecionar o ROWID ou um de seus aliases, como mostrado aqui, além da coluna do objeto grande.</span><span class="sxs-lookup"><span data-stu-id="ecce4-111">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="ecce4-112">Se você não selecionar o ROWID, todo o objeto será carregado na memória.</span><span class="sxs-lookup"><span data-stu-id="ecce4-112">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="ecce4-113">O objeto retornado por `GetStream()` será um `SqliteBlob` quando feito corretamente.</span><span class="sxs-lookup"><span data-stu-id="ecce4-113">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
