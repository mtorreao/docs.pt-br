---
title: 'Alteração significativa: nenhuma investigação de sufixo A/W em plataformas não Windows'
description: Saiba mais sobre a alteração significativa de interoperabilidade no .NET 5,0 em que os sufixos não são mais adicionados aos nomes de exportação de função durante a investigação de P/Invokes em plataformas que não são do Windows.
ms.date: 08/13/2020
ms.openlocfilehash: a4c612a81796faf80fa257df21232a54f7b95431
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760413"
---
# <a name="no-aw-suffix-probing-on-non-windows-platforms"></a><span data-ttu-id="7d494-103">Nenhuma investigação de sufixo A/W em plataformas não Windows</span><span class="sxs-lookup"><span data-stu-id="7d494-103">No A/W suffix probing on non-Windows platforms</span></span>

<span data-ttu-id="7d494-104">Os tempos de execução do .NET não adicionam mais um `A` `W` sufixo ou aos nomes de exportação de função durante a investigação de P/Invokes em plataformas não Windows.</span><span class="sxs-lookup"><span data-stu-id="7d494-104">The .NET runtimes no longer add an `A` or `W` suffix to function export names during probing for P/Invokes on non-Windows platforms.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7d494-105">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="7d494-105">Version introduced</span></span>

<span data-ttu-id="7d494-106">5.0</span><span class="sxs-lookup"><span data-stu-id="7d494-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="7d494-107">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="7d494-107">Change description</span></span>

<span data-ttu-id="7d494-108">O [Windows tem uma convenção](/windows/win32/intl/conventions-for-function-prototypes) de adicionar `A` um `W` sufixo ou para SDK do Windows nomes de função, que correspondem à página de código do Windows e às versões Unicode, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="7d494-108">[Windows has a convention](/windows/win32/intl/conventions-for-function-prototypes) of adding an `A` or `W` suffix to Windows SDK function names, which correspond to the Windows code page and Unicode versions, respectively.</span></span>

<span data-ttu-id="7d494-109">Nas versões anteriores do .NET, os tempos de execução do CoreCLR e do mono adicionam um `A` `W` sufixo ou ao nome de exportação durante a descoberta de exportação para P/Invokes *em todas as plataformas*.</span><span class="sxs-lookup"><span data-stu-id="7d494-109">In previous versions of .NET, both the CoreCLR and Mono runtimes add an `A` or `W` suffix to the export name during export discovery for P/Invokes *on all platforms*.</span></span>

<span data-ttu-id="7d494-110">No .NET 5,0 e versões posteriores, `A` um `W` sufixo ou é adicionado ao nome de exportação durante a descoberta *de exportação somente no Windows*.</span><span class="sxs-lookup"><span data-stu-id="7d494-110">In .NET 5.0 and later versions, an `A` or `W` suffix is added to the export name during export discovery *on Windows only*.</span></span> <span data-ttu-id="7d494-111">Em plataformas UNIX, o sufixo não é adicionado.</span><span class="sxs-lookup"><span data-stu-id="7d494-111">On Unix platforms, the suffix is not added.</span></span> <span data-ttu-id="7d494-112">A semântica de ambos os tempos de execução na plataforma Windows permanece inalterada.</span><span class="sxs-lookup"><span data-stu-id="7d494-112">The semantics of both runtimes on the Windows platform remain unchanged.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="7d494-113">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="7d494-113">Reason for change</span></span>

<span data-ttu-id="7d494-114">Essa alteração foi feita para simplificar a investigação de plataforma cruzada.</span><span class="sxs-lookup"><span data-stu-id="7d494-114">This change was made to simplify cross-platform probing.</span></span> <span data-ttu-id="7d494-115">É uma sobrecarga que não deve ser incorrida, Considerando que plataformas não Windows não contêm essa semântica.</span><span class="sxs-lookup"><span data-stu-id="7d494-115">It's overhead that shouldn't be incurred, given that non-Windows platforms don't contain this semantic.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7d494-116">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="7d494-116">Recommended action</span></span>

<span data-ttu-id="7d494-117">Para atenuar a alteração, você pode adicionar manualmente o sufixo desejado em plataformas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="7d494-117">To mitigate the change, you can manually add the desired suffix on non-Windows platforms.</span></span> <span data-ttu-id="7d494-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7d494-118">For example:</span></span>

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

## <a name="affected-apis"></a><span data-ttu-id="7d494-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="7d494-119">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

### Category

Interop

-->
