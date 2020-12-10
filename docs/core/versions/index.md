---
title: Como o tempo de execução .NET e o SDK têm controle de versão
description: Este artigo explica como o .NET SDK e o tempo de execução têm controle de versão (semelhante ao controle de versões semânticos).
ms.date: 12/07/2020
ms.openlocfilehash: 2fe0b162b52f1e4500ec87f7d5d92054cd569552
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009300"
---
# <a name="overview-of-how-net-is-versioned"></a><span data-ttu-id="41282-103">Visão geral de como o .NET tem controle de versão</span><span class="sxs-lookup"><span data-stu-id="41282-103">Overview of how .NET is versioned</span></span>

<span data-ttu-id="41282-104">O [tempo de execução do .net e o SDK do .net](../introduction.md#sdk-and-runtimes) adicionam novos recursos em frequências diferentes.</span><span class="sxs-lookup"><span data-stu-id="41282-104">The [.NET Runtime and the .NET SDK](../introduction.md#sdk-and-runtimes) add new features at different frequencies.</span></span> <span data-ttu-id="41282-105">Em geral, o SDK é atualizado com mais frequência do que o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="41282-105">In general, the SDK is updated more frequently than the Runtime.</span></span> <span data-ttu-id="41282-106">Este artigo explica o tempo de execução e os números de versão do SDK.</span><span class="sxs-lookup"><span data-stu-id="41282-106">This article explains the runtime and the SDK version numbers.</span></span>

## <a name="versioning-details"></a><span data-ttu-id="41282-107">Detalhes de controle de versão</span><span class="sxs-lookup"><span data-stu-id="41282-107">Versioning details</span></span>

<span data-ttu-id="41282-108">O tempo de execução do .NET tem uma abordagem principal/secundária/patch para o controle de versão que segue o [controle de versão semântico](#semantic-versioning).</span><span class="sxs-lookup"><span data-stu-id="41282-108">The .NET Runtime has a major/minor/patch approach to versioning that follows [semantic versioning](#semantic-versioning).</span></span>

<span data-ttu-id="41282-109">O SDK do .NET não segue o controle de versão semântico.</span><span class="sxs-lookup"><span data-stu-id="41282-109">The .NET SDK doesn't follow semantic versioning.</span></span> <span data-ttu-id="41282-110">O SDK do .NET libera mais rápido e seus números de versão devem comunicar o tempo de execução alinhado e as versões secundárias e de patch próprias do SDK.</span><span class="sxs-lookup"><span data-stu-id="41282-110">The .NET SDK releases faster and its version numbers must communicate both the aligned runtime and the SDK's own minor and patch releases.</span></span>

<span data-ttu-id="41282-111">As duas primeiras posições do número de versão do SDK do .NET são bloqueadas para o tempo de execução do .NET lançado com o.</span><span class="sxs-lookup"><span data-stu-id="41282-111">The first two positions of the .NET SDK version number are locked to the .NET Runtime it released with.</span></span> <span data-ttu-id="41282-112">Cada versão do SDK pode criar aplicativos para esse runtime ou qualquer versão inferior.</span><span class="sxs-lookup"><span data-stu-id="41282-112">Each version of the SDK can create applications for this runtime or any lower version.</span></span>

<span data-ttu-id="41282-113">A terceira posição do número de versão do SDK comunica o número de patch e da versão secundária.</span><span class="sxs-lookup"><span data-stu-id="41282-113">The third position of the SDK version number communicates both the minor and patch number.</span></span> <span data-ttu-id="41282-114">A versão secundária é multiplicada por 100.</span><span class="sxs-lookup"><span data-stu-id="41282-114">The minor version is multiplied by 100.</span></span> <span data-ttu-id="41282-115">Versão secundária 1, versão de patch 2 seria representada como 102.</span><span class="sxs-lookup"><span data-stu-id="41282-115">Minor version 1, patch version 2 would be represented as 102.</span></span> <span data-ttu-id="41282-116">Os últimos dois dígitos representam o número de patch.</span><span class="sxs-lookup"><span data-stu-id="41282-116">The final two digits represent the patch number.</span></span> <span data-ttu-id="41282-117">Por exemplo, aqui está uma possível sequência de números de versão de tempo de execução e SDK:</span><span class="sxs-lookup"><span data-stu-id="41282-117">For example, here's a possible sequence of runtime and SDK version numbers:</span></span>

| <span data-ttu-id="41282-118">Alterar</span><span class="sxs-lookup"><span data-stu-id="41282-118">Change</span></span>                | <span data-ttu-id="41282-119">Execução do .NET</span><span class="sxs-lookup"><span data-stu-id="41282-119">.NET Runtime</span></span>      | <span data-ttu-id="41282-120">SDK do .NET ( \* )</span><span class="sxs-lookup"><span data-stu-id="41282-120">.NET SDK (\*)</span></span>     |
|-----------------------|-------------------|-------------------|
| <span data-ttu-id="41282-121">Versão inicial</span><span class="sxs-lookup"><span data-stu-id="41282-121">Initial release</span></span>       | <span data-ttu-id="41282-122">2.2.0</span><span class="sxs-lookup"><span data-stu-id="41282-122">2.2.0</span></span>             | <span data-ttu-id="41282-123">2.2.100</span><span class="sxs-lookup"><span data-stu-id="41282-123">2.2.100</span></span>           |
| <span data-ttu-id="41282-124">Patch do SDK</span><span class="sxs-lookup"><span data-stu-id="41282-124">SDK Patch</span></span>             | <span data-ttu-id="41282-125">2.2.0</span><span class="sxs-lookup"><span data-stu-id="41282-125">2.2.0</span></span>             | <span data-ttu-id="41282-126">2.2.101</span><span class="sxs-lookup"><span data-stu-id="41282-126">2.2.101</span></span>           |
| <span data-ttu-id="41282-127">Runtime e Patch do SDK</span><span class="sxs-lookup"><span data-stu-id="41282-127">Runtime and SDK Patch</span></span> | <span data-ttu-id="41282-128">2.2.1</span><span class="sxs-lookup"><span data-stu-id="41282-128">2.2.1</span></span>             | <span data-ttu-id="41282-129">2.2.102</span><span class="sxs-lookup"><span data-stu-id="41282-129">2.2.102</span></span>           |
| <span data-ttu-id="41282-130">Alteração de Recurso do SDK</span><span class="sxs-lookup"><span data-stu-id="41282-130">SDK Feature change</span></span>    | <span data-ttu-id="41282-131">2.2.1</span><span class="sxs-lookup"><span data-stu-id="41282-131">2.2.1</span></span>             | <span data-ttu-id="41282-132">2.2.200</span><span class="sxs-lookup"><span data-stu-id="41282-132">2.2.200</span></span>           |

<span data-ttu-id="41282-133">OBSERVAÇÕES:</span><span class="sxs-lookup"><span data-stu-id="41282-133">NOTES:</span></span>

- <span data-ttu-id="41282-134">Se o SDK tiver 10 atualizações de recurso antes de uma atualização de recurso de runtime, os números de versão serão passados na série 1000 com números como 2.2.1000 de acordo com a versão do recurso 2.2.900 a seguir.</span><span class="sxs-lookup"><span data-stu-id="41282-134">If the SDK has 10 feature updates before a runtime feature update, version numbers roll into the 1000 series with numbers like 2.2.1000 as the feature release following 2.2.900.</span></span> <span data-ttu-id="41282-135">Essa situação não deve ocorrer.</span><span class="sxs-lookup"><span data-stu-id="41282-135">This situation isn't expected to occur.</span></span>
- <span data-ttu-id="41282-136">As versões de patch 99 sem uma versão do recurso não ocorrerão.</span><span class="sxs-lookup"><span data-stu-id="41282-136">99 patch releases without a feature release won't occur.</span></span> <span data-ttu-id="41282-137">Se uma versão se aproximar desse número, ela forçará uma versão do recurso.</span><span class="sxs-lookup"><span data-stu-id="41282-137">If a release approaches this number, it forces a feature release.</span></span>

<span data-ttu-id="41282-138">Você poderá ver mais detalhes na proposta inicial no repositório [dotnet/designs](https://github.com/dotnet/designs/pull/29).</span><span class="sxs-lookup"><span data-stu-id="41282-138">You can see more details in the initial proposal at the [dotnet/designs](https://github.com/dotnet/designs/pull/29) repository.</span></span>

## <a name="semantic-versioning"></a><span data-ttu-id="41282-139">Controle de versão semântico</span><span class="sxs-lookup"><span data-stu-id="41282-139">Semantic versioning</span></span>

<span data-ttu-id="41282-140">O *tempo de execução* do .net está em conformidade com o [controle de versão semântica (SemVer)](https://semver.org/), adotando o uso do `MAJOR.MINOR.PATCH` controle de versão, usando as várias partes do número de versão para descrever o grau e o tipo de alteração.</span><span class="sxs-lookup"><span data-stu-id="41282-140">The .NET *Runtime* roughly adheres to [Semantic Versioning (SemVer)](https://semver.org/), adopting the use of `MAJOR.MINOR.PATCH` versioning, using the various parts of the version number to describe the degree and type of change.</span></span>

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

<span data-ttu-id="41282-141">As partes `PRERELEASE` e `BUILDNUMBER` opcionais nunca farão parte das versões compatíveis e existem apenas em builds noturnos, compilados localmente de destinos de origem e versões prévias sem suporte.</span><span class="sxs-lookup"><span data-stu-id="41282-141">The optional `PRERELEASE` and `BUILDNUMBER` parts are never part of supported releases and only exist on nightly builds, local builds from source targets, and unsupported preview releases.</span></span>

### <a name="understand-runtime-version-number-changes"></a><span data-ttu-id="41282-142">Entender as alterações do número de versão do runtime</span><span class="sxs-lookup"><span data-stu-id="41282-142">Understand runtime version number changes</span></span>

<span data-ttu-id="41282-143">`MAJOR` é incrementado quando:</span><span class="sxs-lookup"><span data-stu-id="41282-143">`MAJOR` is incremented when:</span></span>

- <span data-ttu-id="41282-144">Ocorrem alterações significativas no produto ou uma nova direção de produto.</span><span class="sxs-lookup"><span data-stu-id="41282-144">Significant changes occur to the product, or a new product direction.</span></span>
- <span data-ttu-id="41282-145">Alterações da falha foram identificadas.</span><span class="sxs-lookup"><span data-stu-id="41282-145">Breaking changes were taken.</span></span> <span data-ttu-id="41282-146">Há um alto padrão para aceitar alterações da falha.</span><span class="sxs-lookup"><span data-stu-id="41282-146">There's a high bar to accepting breaking changes.</span></span>
- <span data-ttu-id="41282-147">Não há mais suporte para uma versão mais antiga.</span><span class="sxs-lookup"><span data-stu-id="41282-147">An old version is no longer supported.</span></span>
- <span data-ttu-id="41282-148">Uma versão `MAJOR` mais nova de uma dependência existente é adotada.</span><span class="sxs-lookup"><span data-stu-id="41282-148">A newer `MAJOR` version of an existing dependency is adopted.</span></span>

<span data-ttu-id="41282-149">`MINOR` é incrementado quando:</span><span class="sxs-lookup"><span data-stu-id="41282-149">`MINOR` is incremented when:</span></span>

- <span data-ttu-id="41282-150">Uma área de superfície de API pública é adicionada.</span><span class="sxs-lookup"><span data-stu-id="41282-150">Public API surface area is added.</span></span>
- <span data-ttu-id="41282-151">Um novo comportamento é adicionado.</span><span class="sxs-lookup"><span data-stu-id="41282-151">A new behavior is added.</span></span>
- <span data-ttu-id="41282-152">Uma versão `MINOR` mais nova de uma dependência existente é adotada.</span><span class="sxs-lookup"><span data-stu-id="41282-152">A newer `MINOR` version of an existing dependency is adopted.</span></span>
- <span data-ttu-id="41282-153">Uma nova dependência é introduzida.</span><span class="sxs-lookup"><span data-stu-id="41282-153">A new dependency is introduced.</span></span>

<span data-ttu-id="41282-154">`PATCH` é incrementado quando:</span><span class="sxs-lookup"><span data-stu-id="41282-154">`PATCH` is incremented when:</span></span>

- <span data-ttu-id="41282-155">Correções de bug são feitas.</span><span class="sxs-lookup"><span data-stu-id="41282-155">Bug fixes are made.</span></span>
- <span data-ttu-id="41282-156">O suporte para uma plataforma mais recente é adicionado.</span><span class="sxs-lookup"><span data-stu-id="41282-156">Support for a newer platform is added.</span></span>
- <span data-ttu-id="41282-157">Uma versão `PATCH` mais nova de uma dependência existente é adotada.</span><span class="sxs-lookup"><span data-stu-id="41282-157">A newer `PATCH` version of an existing dependency is adopted.</span></span>
- <span data-ttu-id="41282-158">Qualquer outra alteração que não se enquadre em um dos casos anteriores.</span><span class="sxs-lookup"><span data-stu-id="41282-158">Any other change doesn't fit one of the previous cases.</span></span>

<span data-ttu-id="41282-159">Quando há várias alterações, o elemento mais alto afetado por alterações individuais é incrementado e os seguintes são redefinidos como zero.</span><span class="sxs-lookup"><span data-stu-id="41282-159">When there are multiple changes, the highest element affected by individual changes is incremented, and the following ones are reset to zero.</span></span> <span data-ttu-id="41282-160">Por exemplo, quando `MAJOR` é incrementado, `MINOR` e `PATCH` são redefinidos como zero.</span><span class="sxs-lookup"><span data-stu-id="41282-160">For example, when `MAJOR` is incremented, `MINOR` and `PATCH` are reset to zero.</span></span> <span data-ttu-id="41282-161">Quando `MINOR` é incrementado, `PATCH` é redefinido como zero enquanto `MAJOR` permanece inalterado.</span><span class="sxs-lookup"><span data-stu-id="41282-161">When `MINOR` is incremented, `PATCH` is reset to zero while `MAJOR` is left untouched.</span></span>

## <a name="version-numbers-in-file-names"></a><span data-ttu-id="41282-162">Números de versão nos nomes de arquivo</span><span class="sxs-lookup"><span data-stu-id="41282-162">Version numbers in file names</span></span>

<span data-ttu-id="41282-163">Os arquivos baixados para .NET carregam a versão, por exemplo, `dotnet-sdk-2.1.300-win10-x64.exe` .</span><span class="sxs-lookup"><span data-stu-id="41282-163">The files downloaded for .NET carry the version, for example, `dotnet-sdk-2.1.300-win10-x64.exe`.</span></span>

### <a name="preview-versions"></a><span data-ttu-id="41282-164">Versões prévias</span><span class="sxs-lookup"><span data-stu-id="41282-164">Preview versions</span></span>

<span data-ttu-id="41282-165">As versões de visualização têm um `-preview[number]-([build]|"final")` anexado ao número de versão.</span><span class="sxs-lookup"><span data-stu-id="41282-165">Preview versions have a `-preview[number]-([build]|"final")` appended to the version number.</span></span> <span data-ttu-id="41282-166">Por exemplo, `2.0.0-preview1-final`.</span><span class="sxs-lookup"><span data-stu-id="41282-166">For example, `2.0.0-preview1-final`.</span></span>

### <a name="servicing-versions"></a><span data-ttu-id="41282-167">Versões de manutenção</span><span class="sxs-lookup"><span data-stu-id="41282-167">Servicing versions</span></span>

<span data-ttu-id="41282-168">Depois que uma versão sai, os branches de versão geralmente param de produzir builds diários e, em vez disso, iniciam a produção de builds de manutenção.</span><span class="sxs-lookup"><span data-stu-id="41282-168">After a release goes out, the release branches generally stop producing daily builds and instead start producing servicing builds.</span></span> <span data-ttu-id="41282-169">As versões de manutenção têm um `-servicing-[number]` anexado à versão.</span><span class="sxs-lookup"><span data-stu-id="41282-169">Servicing versions have a `-servicing-[number]` appended to the version.</span></span> <span data-ttu-id="41282-170">Por exemplo, `2.0.1-servicing-006924`.</span><span class="sxs-lookup"><span data-stu-id="41282-170">For example, `2.0.1-servicing-006924`.</span></span>

## <a name="relationship-to-net-standard-versions"></a><span data-ttu-id="41282-171">Relacionamento com versões do .NET Standard</span><span class="sxs-lookup"><span data-stu-id="41282-171">Relationship to .NET Standard versions</span></span>

<span data-ttu-id="41282-172">O .NET standard consiste em um assembly de referência do .NET.</span><span class="sxs-lookup"><span data-stu-id="41282-172">.NET Standard consists of a .NET reference assembly.</span></span> <span data-ttu-id="41282-173">Há várias implementações específicas para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="41282-173">There are multiple implementations specific to each platform.</span></span> <span data-ttu-id="41282-174">O assembly de referência contém a definição das APIs do .NET que fazem parte de uma determinada versão do .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="41282-174">The reference assembly contains the definition of .NET APIs which are part of a given .NET Standard version.</span></span> <span data-ttu-id="41282-175">Cada implementação atende o contrato do .NET Standard na plataforma específica.</span><span class="sxs-lookup"><span data-stu-id="41282-175">Each implementation fulfills the .NET Standard contract on the specific platform.</span></span>

<span data-ttu-id="41282-176">O assembly de referência do .NET Standard usa um esquema de controle de versão `MAJOR.MINOR`.</span><span class="sxs-lookup"><span data-stu-id="41282-176">The .NET Standard reference assembly uses a `MAJOR.MINOR` versioning scheme.</span></span> <span data-ttu-id="41282-177">O nível `PATCH` não é útil para o .NET Standard porque expõe apenas uma especificação de API (nenhuma implementação) e por definição, qualquer alteração à API representaria uma alteração no conjunto de recursos e, portanto, uma nova versão `MINOR`.</span><span class="sxs-lookup"><span data-stu-id="41282-177">`PATCH` level isn't useful for .NET Standard because it exposes only an API specification (no implementation) and by definition any change to the API would represent a change in the feature set, and thus a new `MINOR` version.</span></span>

<span data-ttu-id="41282-178">As implementações em cada plataforma podem ser atualizadas, normalmente como parte da versão de plataforma e isso, portanto, não é evidente para os programadores que usam o .NET Standard nessa plataforma.</span><span class="sxs-lookup"><span data-stu-id="41282-178">The implementations on each platform may be updated, typically as part of the platform release, and thus not evident to the programmers using .NET Standard on that platform.</span></span>

<span data-ttu-id="41282-179">Para obter mais informações, confira [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="41282-179">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41282-180">Confira também</span><span class="sxs-lookup"><span data-stu-id="41282-180">See also</span></span>

- [<span data-ttu-id="41282-181">Estruturas de destino</span><span class="sxs-lookup"><span data-stu-id="41282-181">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="41282-182">Empacotamento de distribuição do .NET</span><span class="sxs-lookup"><span data-stu-id="41282-182">.NET distribution packaging</span></span>](../distribution-packaging.md)
- [<span data-ttu-id="41282-183">Folha de fatos do ciclo de vida de suporte do .NET</span><span class="sxs-lookup"><span data-stu-id="41282-183">.NET Support Lifecycle Fact Sheet</span></span>](https://dotnet.microsoft.com/platform/support/policy)
- [<span data-ttu-id="41282-184">Imagens do Docker para .NET</span><span class="sxs-lookup"><span data-stu-id="41282-184">Docker images for .NET</span></span>](https://hub.docker.com/_/microsoft-dotnet/)
