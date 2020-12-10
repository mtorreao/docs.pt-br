---
title: Elemento <appSettings> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: 66260d15768781b7fa3d9397b8e8a7d9ad68ab95
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009788"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="72c32-102">Elemento \<appSettings> para \<configuration></span><span class="sxs-lookup"><span data-stu-id="72c32-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="72c32-103">Contém configurações de aplicativo personalizadas.</span><span class="sxs-lookup"><span data-stu-id="72c32-103">Contains custom application settings.</span></span> <span data-ttu-id="72c32-104">Esta é uma seção de configuração predefinida fornecida pelo .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72c32-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<appSettings>**

## <a name="syntax"></a><span data-ttu-id="72c32-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="72c32-105">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="72c32-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="72c32-106">Attribute</span></span>

|           | <span data-ttu-id="72c32-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="72c32-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="72c32-108">**file**</span><span class="sxs-lookup"><span data-stu-id="72c32-108">**file**</span></span>  | <span data-ttu-id="72c32-109">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="72c32-109">Optional attribute.</span></span><br><br><span data-ttu-id="72c32-110">Especifica um caminho relativo para um arquivo externo que contém definições de configuração de aplicativo personalizadas.</span><span class="sxs-lookup"><span data-stu-id="72c32-110">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="72c32-111">O arquivo especificado contém o mesmo tipo de configurações que são especificadas nos **\<add>** elementos, e **\<remove>** **\<clear>** e usa o mesmo formato de par chave/valor que esses elementos.</span><span class="sxs-lookup"><span data-stu-id="72c32-111">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="72c32-112">O caminho especificado é relativo ao arquivo de configuração principal.</span><span class="sxs-lookup"><span data-stu-id="72c32-112">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="72c32-113">Para um aplicativo Windows Forms, essa é a pasta binária (como */bin/Debug*), não o local do arquivo de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="72c32-113">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="72c32-114">Para aplicativos Web Forms, o caminho é relativo à raiz do aplicativo, onde o arquivo de *web.config* está localizado.</span><span class="sxs-lookup"><span data-stu-id="72c32-114">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="72c32-115">O tempo de execução ignora o atributo se o arquivo especificado não puder ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="72c32-115">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="72c32-116">Elemento pai</span><span class="sxs-lookup"><span data-stu-id="72c32-116">Parent element</span></span>

|     | <span data-ttu-id="72c32-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="72c32-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="72c32-118">**\<configuration>** Elementos</span><span class="sxs-lookup"><span data-stu-id="72c32-118">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="72c32-119">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72c32-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="72c32-120">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="72c32-120">Child elements</span></span>

|     | <span data-ttu-id="72c32-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="72c32-121">Description</span></span> |
| --- | ----------- |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="72c32-122">Adiciona uma configuração de aplicativo personalizada.</span><span class="sxs-lookup"><span data-stu-id="72c32-122">Adds a custom application setting.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="72c32-123">Limpa todas as configurações de aplicativo definidas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="72c32-123">Clears all previously defined application settings.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="72c32-124">Remove uma configuração de aplicativo definida anteriormente.</span><span class="sxs-lookup"><span data-stu-id="72c32-124">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="72c32-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="72c32-125">Remarks</span></span>

<span data-ttu-id="72c32-126">O **\<appSettings>** elemento armazena informações de configuração de aplicativo personalizadas, como cadeias de conexão de banco de dados, caminhos de arquivo, URLs de serviço Web XML ou qualquer outra informação de configuração personalizada para um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="72c32-126">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="72c32-127">Os pares de chave/valor especificados no **\<appSettings>** elemento são acessados no código usando a <xref:System.Configuration.ConfigurationSettings> classe.</span><span class="sxs-lookup"><span data-stu-id="72c32-127">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="72c32-128">Você pode usar o atributo **File** no **\<appSettings>** elemento da *Web.config* e dos arquivos de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="72c32-128">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="72c32-129">Esse atributo especifica um arquivo de configuração que fornece configurações adicionais ou substitui as configurações especificadas no **\<appSettings>** elemento.</span><span class="sxs-lookup"><span data-stu-id="72c32-129">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="72c32-130">O atributo de **arquivo** pode ser usado em cenários de desenvolvimento de equipe de controle do código-fonte, como quando um usuário deseja substituir as configurações de projeto especificadas em um arquivo de configuração de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="72c32-130">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="72c32-131">Os arquivos de configuração especificados pelo atributo de **arquivo** devem ter um nó raiz **\<appSettings>** em vez de **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="72c32-131">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="72c32-132">Exemplo</span><span class="sxs-lookup"><span data-stu-id="72c32-132">Example</span></span>

<span data-ttu-id="72c32-133">O exemplo a seguir mostra um arquivo de configurações de aplicativo externo (*custom.config*) que define uma configuração de aplicativo personalizada:</span><span class="sxs-lookup"><span data-stu-id="72c32-133">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="72c32-134">O exemplo a seguir mostra um arquivo de configuração de aplicativo que consome a configuração no arquivo de configurações externas e define sua própria configuração de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="72c32-134">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="72c32-135">Arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="72c32-135">Configuration file</span></span>

<span data-ttu-id="72c32-136">Esse elemento pode ser usado no arquivo de configuração do aplicativo, no arquivo de configuração do computador (*Machine.config*) e *Web.config* arquivos que não estão no nível do diretório do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="72c32-136">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="72c32-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="72c32-137">See also</span></span>

- [<span data-ttu-id="72c32-138">Esquema do arquivo de configuração para o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="72c32-138">Configuration file schema for the .NET Framework</span></span>](../index.md)
