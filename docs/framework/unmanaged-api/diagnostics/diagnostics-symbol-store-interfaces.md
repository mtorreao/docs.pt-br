---
title: Interfaces de armazenamento de símbolo de diagnóstico
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
ms.openlocfilehash: e376544a9d428ce5110a7e38b92a8e830f574664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725177"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="34d5a-102">Interfaces de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="34d5a-102">Diagnostics Symbol Store Interfaces</span></span>

<span data-ttu-id="34d5a-103">Este tópico descreve as interfaces não gerenciadas que permitem que um compilador gere informações de símbolo para uso por um depurador.</span><span class="sxs-lookup"><span data-stu-id="34d5a-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34d5a-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="34d5a-104">In This Section</span></span>  

 [<span data-ttu-id="34d5a-105">Interface IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="34d5a-105">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)  
 <span data-ttu-id="34d5a-106">Fornece métodos que exibem informações de associação atuais sobre o aplicativo em execução.</span><span class="sxs-lookup"><span data-stu-id="34d5a-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="34d5a-107">Interface IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="34d5a-107">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)  
 <span data-ttu-id="34d5a-108">Define a interface para uma anexação automática do depurador invocado pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="34d5a-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="34d5a-109">Interface INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="34d5a-109">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)  
 <span data-ttu-id="34d5a-110">Declara métodos para registrar e cancelar o registro de uma fonte de notificação de conexão.</span><span class="sxs-lookup"><span data-stu-id="34d5a-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="34d5a-111">Interface INotifySink2</span><span class="sxs-lookup"><span data-stu-id="34d5a-111">INotifySink2 Interface</span></span>](inotifysink2-interface.md)  
 <span data-ttu-id="34d5a-112">Declara métodos para notificação de coletor.</span><span class="sxs-lookup"><span data-stu-id="34d5a-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="34d5a-113">Interface INotifySource2</span><span class="sxs-lookup"><span data-stu-id="34d5a-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)  
 <span data-ttu-id="34d5a-114">Declara um método para definir filtros de notificação.</span><span class="sxs-lookup"><span data-stu-id="34d5a-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="34d5a-115">Interface ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="34d5a-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="34d5a-116">Fornece informações para o recurso Editar e continuar.</span><span class="sxs-lookup"><span data-stu-id="34d5a-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="34d5a-117">Interface ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="34d5a-117">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="34d5a-118">Essa interface é o complemento de leitura para a [interface ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="34d5a-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="34d5a-119">Interface ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="34d5a-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="34d5a-120">Permite a definição de informações opcionais de método Async por símbolo de método.</span><span class="sxs-lookup"><span data-stu-id="34d5a-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="34d5a-121">Deve ser usado com um método aberto (ou seja, entre chamadas para o [método OpenMethod](isymunmanagedwriter-openmethod-method.md)e o [método CloseMethod](isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="34d5a-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="34d5a-122">Interface ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="34d5a-122">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)  
 <span data-ttu-id="34d5a-123">Representa um associador de símbolo para o código não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="34d5a-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="34d5a-124">Interface ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="34d5a-124">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="34d5a-125">Representa um fichário de símbolo para código não gerenciado e estende a `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="34d5a-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="34d5a-126">Interface ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="34d5a-126">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="34d5a-127">Representa um fichário de símbolo para código não gerenciado e estende a `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="34d5a-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="34d5a-128">Interface ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="34d5a-128">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)  
 <span data-ttu-id="34d5a-129">Fornece acesso a constantes não gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="34d5a-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="34d5a-130">Interface ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="34d5a-130">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)  
 <span data-ttu-id="34d5a-131">Descartes de recursos não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="34d5a-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="34d5a-132">Interface ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="34d5a-132">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)  
 <span data-ttu-id="34d5a-133">Representa um documento referenciado por um repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="34d5a-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="34d5a-134">Interface ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="34d5a-134">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="34d5a-135">Fornece métodos para gravar em um documento referenciado por um repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="34d5a-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="34d5a-136">Interface ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="34d5a-136">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="34d5a-137">Fornece métodos para o recurso Editar e continuar.</span><span class="sxs-lookup"><span data-stu-id="34d5a-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="34d5a-138">Interface ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="34d5a-138">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)  
 <span data-ttu-id="34d5a-139">Representa um método dentro do repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="34d5a-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="34d5a-140">Interface ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="34d5a-140">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)  
 <span data-ttu-id="34d5a-141">Representa um namespace.</span><span class="sxs-lookup"><span data-stu-id="34d5a-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="34d5a-142">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="34d5a-142">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)  
 <span data-ttu-id="34d5a-143">Representa um leitor de símbolo que fornece acesso a documentos, métodos e variáveis em um repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="34d5a-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="34d5a-144">Interface ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="34d5a-144">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)  
 <span data-ttu-id="34d5a-145">Obtém um método de leitor de símbolos dado um token de método e um número de versão de edição e cópia.</span><span class="sxs-lookup"><span data-stu-id="34d5a-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="34d5a-146">Interface ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="34d5a-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="34d5a-147">Fornece métodos que recebem informações de pesquisa de símbolo.</span><span class="sxs-lookup"><span data-stu-id="34d5a-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="34d5a-148">Interface ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="34d5a-148">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)  
 <span data-ttu-id="34d5a-149">Representa um escopo léxico dentro de um método.</span><span class="sxs-lookup"><span data-stu-id="34d5a-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="34d5a-150">Interface ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="34d5a-150">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)  
 <span data-ttu-id="34d5a-151">Representa um escopo léxico dentro de um método e estende a `ISymUnmanagedScope` interface com métodos que obtêm informações sobre constantes definidas no escopo.</span><span class="sxs-lookup"><span data-stu-id="34d5a-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="34d5a-152">Interface ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="34d5a-152">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="34d5a-153">Fornece dados do servidor de origem para um módulo.</span><span class="sxs-lookup"><span data-stu-id="34d5a-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="34d5a-154">Interface ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="34d5a-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="34d5a-155">Fornece métodos que obtêm informações sobre o caminho de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="34d5a-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="34d5a-156">Interface ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="34d5a-156">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)  
 <span data-ttu-id="34d5a-157">Representa uma variável, como um parâmetro, uma variável local ou um campo.</span><span class="sxs-lookup"><span data-stu-id="34d5a-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="34d5a-158">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="34d5a-158">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)  
 <span data-ttu-id="34d5a-159">Representa um gravador de símbolo e fornece métodos para definir documentos, pontos de sequência, escopos lexicais e variáveis.</span><span class="sxs-lookup"><span data-stu-id="34d5a-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="34d5a-160">Interface ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="34d5a-160">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="34d5a-161">Representa um gravador de símbolo e fornece métodos para definir documentos, pontos de sequência, escopos lexicais e variáveis.</span><span class="sxs-lookup"><span data-stu-id="34d5a-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="34d5a-162">Estende a `ISymUnmanagedWriter` interface.</span><span class="sxs-lookup"><span data-stu-id="34d5a-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="34d5a-163">Interface ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="34d5a-163">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="34d5a-164">Representa um gravador de símbolo e fornece métodos para definir documentos, pontos de sequência, escopos lexicais e variáveis.</span><span class="sxs-lookup"><span data-stu-id="34d5a-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="34d5a-165">Estende a `ISymUnmanagedWriter` interface.</span><span class="sxs-lookup"><span data-stu-id="34d5a-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="34d5a-166">Interface ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="34d5a-166">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="34d5a-167">Interface ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="34d5a-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="34d5a-168">Interface ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="34d5a-168">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="34d5a-169">Interface ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="34d5a-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="34d5a-170">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="34d5a-170">Related Sections</span></span>  

 [<span data-ttu-id="34d5a-171">Enumerações de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="34d5a-171">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="34d5a-172">Estruturas de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="34d5a-172">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="34d5a-173">Depuração</span><span class="sxs-lookup"><span data-stu-id="34d5a-173">Debugging</span></span>](../debugging/index.md)
