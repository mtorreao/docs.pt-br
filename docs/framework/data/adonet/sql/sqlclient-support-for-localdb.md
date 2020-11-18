---
title: Suporte do SqlClient para LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 55ab1346de6f5c14f15d01344a984c18edf30e02
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824474"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="33bea-102">Suporte do SqlClient para LocalDB</span><span class="sxs-lookup"><span data-stu-id="33bea-102">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="33bea-103">Este artigo discute como se conectar a um banco de dados LocalDB.</span><span class="sxs-lookup"><span data-stu-id="33bea-103">This article discusses how to connect to a LocalDB database.</span></span> <span data-ttu-id="33bea-104">LocalDB é uma versão leve do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33bea-104">LocalDB is a lightweight version of SQL Server.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="33bea-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="33bea-105">Remarks</span></span>
  
 <span data-ttu-id="33bea-106">Para resumir o que você pode fazer com o LocalDB:</span><span class="sxs-lookup"><span data-stu-id="33bea-106">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="33bea-107">Crie e inicie instâncias do LocalDB com sqllocaldb.exe ou seu arquivo app.config.</span><span class="sxs-lookup"><span data-stu-id="33bea-107">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="33bea-108">Use sqlcmd.exe para adicionar e modificar bancos de dados em uma instância do LocalDB.</span><span class="sxs-lookup"><span data-stu-id="33bea-108">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="33bea-109">Por exemplo, `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="33bea-109">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="33bea-110">Use a palavra-chave da cadeia de conexão `AttachDBFilename` para adicionar um banco de dados à instância do LocalDB.</span><span class="sxs-lookup"><span data-stu-id="33bea-110">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="33bea-111">Ao usar `AttachDBFilename`, se você não especificar o nome do banco de dados com a palavra-chave da cadeia de conexão `Database`, o banco de dados será removido da instância do LocalDB quando o aplicativo for fechado.</span><span class="sxs-lookup"><span data-stu-id="33bea-111">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="33bea-112">Especifique uma instância do LocalDB em sua cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="33bea-112">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="33bea-113">Por exemplo, o nome da instância é `myInstance`, a cadeia de conexão incluiria:</span><span class="sxs-lookup"><span data-stu-id="33bea-113">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="33bea-114">`User Instance=True` não é permitido ao se conectar a um banco de dados LocalDB.</span><span class="sxs-lookup"><span data-stu-id="33bea-114">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
<span data-ttu-id="33bea-115">Para obter informações sobre como instalar o LocalDB, consulte [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).</span><span class="sxs-lookup"><span data-stu-id="33bea-115">For information about installing LocalDB, see [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).</span></span>
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="33bea-116">Criar programaticamente uma instância nomeada</span><span class="sxs-lookup"><span data-stu-id="33bea-116">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="33bea-117">Um aplicativo pode criar uma instância nomeada e especificar um banco de dados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="33bea-117">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="33bea-118">Especifique as instâncias LocalDB a serem criadas no arquivo app.config, da maneira a seguir.</span><span class="sxs-lookup"><span data-stu-id="33bea-118">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="33bea-119">O número de versão da instância deve ser igual ao número de versão da sua instalação do LocalDB.</span><span class="sxs-lookup"><span data-stu-id="33bea-119">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
- <span data-ttu-id="33bea-120">Especifique o nome da instância que usa a palavra-chave da cadeia de conexão `server`.</span><span class="sxs-lookup"><span data-stu-id="33bea-120">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="33bea-121">O nome da instância especificado na palavra-chave da cadeia de conexão `server` deve corresponder ao nome especificado no arquivo app.config.</span><span class="sxs-lookup"><span data-stu-id="33bea-121">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="33bea-122">Use a palavra-chave da cadeia de conexão `AttachDBFilename` para especificar o arquivo .MDF.</span><span class="sxs-lookup"><span data-stu-id="33bea-122">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33bea-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="33bea-123">See also</span></span>

- [<span data-ttu-id="33bea-124">Recursos de SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="33bea-124">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="33bea-125">Visão geral do ADO.NET</span><span class="sxs-lookup"><span data-stu-id="33bea-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
