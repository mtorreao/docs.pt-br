---
title: Alterações significativas na biblioteca do .NET
description: Lista as alterações significativas nas principais bibliotecas do .NET para as versões 1.0-3.0 do .NET Core.
ms.date: 07/27/2020
ms.openlocfilehash: 092ff36a5e07c9e226fe2a67d5e7cfd391e9d16b
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366873"
---
# <a name="core-net-libraries-breaking-changes-in-net-core-10-30"></a><span data-ttu-id="b19e9-103">Principais bibliotecas do .NET que violam as alterações no .NET Core 1.0-3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-103">Core .NET libraries breaking changes in .NET Core 1.0-3.0</span></span>

<span data-ttu-id="b19e9-104">As principais bibliotecas do .NET fornecem os primitivos e outros tipos gerais usados pelo .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b19e9-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="b19e9-105">As seguintes alterações significativas estão documentadas nesta página:</span><span class="sxs-lookup"><span data-stu-id="b19e9-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="b19e9-106">Alteração significativa</span><span class="sxs-lookup"><span data-stu-id="b19e9-106">Breaking change</span></span> | <span data-ttu-id="b19e9-107">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="b19e9-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="b19e9-108">Passar GroupCollection para métodos de extensão assumindo IEnumerable \<T> requer ambiguidade</span><span class="sxs-lookup"><span data-stu-id="b19e9-108">Passing GroupCollection to extension methods taking IEnumerable\<T> requires disambiguation</span></span>](#passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation) | <span data-ttu-id="b19e9-109">3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-109">3.0</span></span> |
| [<span data-ttu-id="b19e9-110">As APIs que relatam versão agora relatam produto e não versão de arquivo</span><span class="sxs-lookup"><span data-stu-id="b19e9-110">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="b19e9-111">3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-111">3.0</span></span> |
| [<span data-ttu-id="b19e9-112">Instâncias EncoderFallbackBuffer personalizadas não podem retornar recursivamente</span><span class="sxs-lookup"><span data-stu-id="b19e9-112">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="b19e9-113">3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-113">3.0</span></span> |
| [<span data-ttu-id="b19e9-114">Alterações de comportamento de análise e formatação de ponto flutuante</span><span class="sxs-lookup"><span data-stu-id="b19e9-114">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="b19e9-115">3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-115">3.0</span></span> |
| [<span data-ttu-id="b19e9-116">Operações de análise de ponto flutuante não falham mais ou geram uma estourexception</span><span class="sxs-lookup"><span data-stu-id="b19e9-116">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="b19e9-117">3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-117">3.0</span></span> |
| [<span data-ttu-id="b19e9-118">InvalidAsynchronousStateException movido para outro assembly</span><span class="sxs-lookup"><span data-stu-id="b19e9-118">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="b19e9-119">3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-119">3.0</span></span> |
| [<span data-ttu-id="b19e9-120">A substituição de sequências de bytes UTF-8 mal formados segue as diretrizes de Unicode</span><span class="sxs-lookup"><span data-stu-id="b19e9-120">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="b19e9-121">3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-121">3.0</span></span> |
| [<span data-ttu-id="b19e9-122">TypeDescriptionProviderAttribute movido para outro assembly</span><span class="sxs-lookup"><span data-stu-id="b19e9-122">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="b19e9-123">3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-123">3.0</span></span> |
| [<span data-ttu-id="b19e9-124">O ZipArchiveEntry não lida mais com os arquivos mortos com tamanhos de entrada inconsistentes</span><span class="sxs-lookup"><span data-stu-id="b19e9-124">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="b19e9-125">3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-125">3.0</span></span> |
| [<span data-ttu-id="b19e9-126">FieldInfo. SetValue gera uma exceção para campos estáticos somente de inicialização</span><span class="sxs-lookup"><span data-stu-id="b19e9-126">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="b19e9-127">3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-127">3.0</span></span> |
| [<span data-ttu-id="b19e9-128">Campos privados adicionados aos tipos de struct internos</span><span class="sxs-lookup"><span data-stu-id="b19e9-128">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="b19e9-129">2.1</span><span class="sxs-lookup"><span data-stu-id="b19e9-129">2.1</span></span> |
| [<span data-ttu-id="b19e9-130">Alteração no valor padrão de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="b19e9-130">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="b19e9-131">2.1</span><span class="sxs-lookup"><span data-stu-id="b19e9-131">2.1</span></span> |
| [<span data-ttu-id="b19e9-132">Versões do OpenSSL no macOS</span><span class="sxs-lookup"><span data-stu-id="b19e9-132">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="b19e9-133">2.1</span><span class="sxs-lookup"><span data-stu-id="b19e9-133">2.1</span></span> |
| [<span data-ttu-id="b19e9-134">UnauthorizedAccessException gerado por FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="b19e9-134">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="b19e9-135">1.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-135">1.0</span></span> |
| [<span data-ttu-id="b19e9-136">Tratamento de exceções de estado de processo corrompido não é suportado</span><span class="sxs-lookup"><span data-stu-id="b19e9-136">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="b19e9-137">1.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-137">1.0</span></span> |
| [<span data-ttu-id="b19e9-138">As propriedades UriBuilder não precedem mais os caracteres à esquerda</span><span class="sxs-lookup"><span data-stu-id="b19e9-138">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="b19e9-139">1.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-139">1.0</span></span> |
| [<span data-ttu-id="b19e9-140">Process. StartInfo gera InvalidOperationException para processos que você não iniciou</span><span class="sxs-lookup"><span data-stu-id="b19e9-140">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="b19e9-141">1.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-141">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="b19e9-142">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-142">.NET Core 3.0</span></span>

[!INCLUDE [disambiguate-generic-type-for-groupcollection](../../../includes/core-changes/corefx/3.0/disambiguate-generic-type-for-groupcollection.md)]

***

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

<span data-ttu-id="b19e9-143">\*\*_</span><span class="sxs-lookup"><span data-stu-id="b19e9-143">\*\*_</span></span>

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

_*_

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

_*_

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

_*_

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

_*_

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

_*_

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

_*_

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

_*_

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="b19e9-144">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b19e9-144">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a><span data-ttu-id="b19e9-145">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b19e9-145">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

<span data-ttu-id="b19e9-146">_\*\*</span><span class="sxs-lookup"><span data-stu-id="b19e9-146">_\*\*</span></span>
