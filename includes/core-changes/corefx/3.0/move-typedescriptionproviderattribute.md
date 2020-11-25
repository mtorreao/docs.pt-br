---
ms.openlocfilehash: 7a2617f27dfd6bb527ff6d408fae6382075f24ae
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031964"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a><span data-ttu-id="31bba-101">TypeDescriptionProviderAttribute movido para outro assembly</span><span class="sxs-lookup"><span data-stu-id="31bba-101">TypeDescriptionProviderAttribute moved to another assembly</span></span>

<span data-ttu-id="31bba-102">A <xref:System.ComponentModel.TypeDescriptionProviderAttribute> classe foi movida.</span><span class="sxs-lookup"><span data-stu-id="31bba-102">The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="31bba-103">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="31bba-103">Change description</span></span>

<span data-ttu-id="31bba-104">No .NET Core 2,2 e versões anteriores, a <xref:System.ComponentModel.TypeDescriptionProviderAttribute> classe é encontrada no assembly *System. ComponentModel. TypeConverter* .</span><span class="sxs-lookup"><span data-stu-id="31bba-104">In .NET Core 2.2 and earlier versions, The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="31bba-105">A partir do .NET Core 3,0, ele é encontrado no assembly *System. ObjectModel* .</span><span class="sxs-lookup"><span data-stu-id="31bba-105">Starting with .NET Core 3.0, it is found in the *System.ObjectModel* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="31bba-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="31bba-106">Version introduced</span></span>

<span data-ttu-id="31bba-107">3.0</span><span class="sxs-lookup"><span data-stu-id="31bba-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="31bba-108">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="31bba-108">Recommended action</span></span>

<span data-ttu-id="31bba-109">Essa alteração afeta apenas os aplicativos que usam a reflexão para carregar o <xref:System.ComponentModel.TypeDescriptionProviderAttribute> tipo chamando um método como <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> ou uma sobrecarga de <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> que assume que o tipo está em um assembly específico.</span><span class="sxs-lookup"><span data-stu-id="31bba-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.TypeDescriptionProviderAttribute> type by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="31bba-110">Se esse for o caso, o assembly referenciado na chamada do método deverá ser atualizado para refletir o novo local do assembly do tipo.</span><span class="sxs-lookup"><span data-stu-id="31bba-110">If that is the case, the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="31bba-111">Categoria</span><span class="sxs-lookup"><span data-stu-id="31bba-111">Category</span></span>

<span data-ttu-id="31bba-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31bba-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="31bba-113">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="31bba-113">Affected APIs</span></span>

<span data-ttu-id="31bba-114">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="31bba-114">None.</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
