---
title: Enviar um trabalho .NET para Apache Spark para o Azure HDInsight
description: Saiba como enviar um trabalho .NET para Apache Spark para o Azure HDInsight usando Spark-Submit e Apache Livy.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 74be4ecf33a9a881633da0630fa1c1a4bf0b19c6
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688157"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a><span data-ttu-id="66258-103">Enviar um trabalho .NET para Apache Spark para o Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="66258-103">Submit a .NET for Apache Spark job to Azure HDInsight</span></span>

<span data-ttu-id="66258-104">Há duas maneiras de implantar seu .NET para Apache Spark trabalho para o HDInsight: `spark-submit` e o Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="66258-104">There are two ways to deploy your .NET for Apache Spark job to HDInsight: `spark-submit` and Apache Livy.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="66258-105">Implantar usando Spark-Submit</span><span class="sxs-lookup"><span data-stu-id="66258-105">Deploy using spark-submit</span></span>

<span data-ttu-id="66258-106">Você pode usar o comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabalhos do .NET para Apache Spark para o Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="66258-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>

1. <span data-ttu-id="66258-107">Navegue até o cluster HDInsight Spark no portal do Azure e, em seguida, selecione **SSH + logon do cluster**.</span><span class="sxs-lookup"><span data-stu-id="66258-107">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="66258-108">Copie as informações de logon SSH e cole o logon em um terminal.</span><span class="sxs-lookup"><span data-stu-id="66258-108">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="66258-109">Entre no cluster usando a senha que você definiu durante a criação do cluster.</span><span class="sxs-lookup"><span data-stu-id="66258-109">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="66258-110">Você deve ver as mensagens com boas-vindas ao Ubuntu e ao Spark.</span><span class="sxs-lookup"><span data-stu-id="66258-110">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="66258-111">Use o comando **Spark-Submit** para executar seu aplicativo em seu cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="66258-111">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="66258-112">Lembre-se de substituir **MyContainer** e **mystorageaccount** no script de exemplo pelos nomes reais do contêiner de BLOB e da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="66258-112">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span> <span data-ttu-id="66258-113">Lembre-se também de substituir o jar Microsoft-Spark pela versão do Spark e .NET por Apache Spark sendo usado.</span><span class="sxs-lookup"><span data-stu-id="66258-113">Also remember to replace the microsoft-spark jar with the version of Spark and .NET for Apache Spark being used.</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a><span data-ttu-id="66258-114">Implantar usando o Apache Livy</span><span class="sxs-lookup"><span data-stu-id="66258-114">Deploy using Apache Livy</span></span>

<span data-ttu-id="66258-115">Você pode usar o [Apache Livy](https://livy.incubator.apache.org/), a API REST do Apache Spark, para enviar trabalhos do .NET para Apache Spark a um cluster do Azure HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="66258-115">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="66258-116">Para obter mais informações, consulte [Trabalhos remotos com o Apache Livy](/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="66258-116">For more information, see [Remote jobs with Apache Livy](/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="66258-117">Você pode executar o comando a seguir no Linux usando `curl`:</span><span class="sxs-lookup"><span data-stu-id="66258-117">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="66258-118">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="66258-118">Next steps</span></span>

* [<span data-ttu-id="66258-119">Introdução ao .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="66258-119">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="66258-120">Implantar um aplicativo .NET para Apache Spark no Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="66258-120">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="66258-121">Documentação do HDInsight</span><span class="sxs-lookup"><span data-stu-id="66258-121">HDInsight Documentation</span></span>](/azure/hdinsight/)
