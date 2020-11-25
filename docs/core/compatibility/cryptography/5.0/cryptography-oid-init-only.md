---
title: 'Alteração significativa: Cryptography. OID é funcionalmente somente init'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que os setters de propriedade na classe Cryptography. Oid agora lançam uma exceção se você tentar alterar um valor.
ms.date: 08/16/2020
ms.openlocfilehash: a3b5a393e2a84f7c9a60c2a821ecfda9c6acd2e3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760336"
---
# <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a><span data-ttu-id="9295e-103">System. Security. Cryptography. OID é funcionalmente somente init</span><span class="sxs-lookup"><span data-stu-id="9295e-103">System.Security.Cryptography.Oid is functionally init-only</span></span>

<span data-ttu-id="9295e-104">A <xref:System.Security.Cryptography.Oid?displayProperty=fullName> classe, que é usada para representar valores de identificador de objeto ASN. 1 e seus nomes "amigáveis", anteriormente era totalmente mutável.</span><span class="sxs-lookup"><span data-stu-id="9295e-104">The <xref:System.Security.Cryptography.Oid?displayProperty=fullName> class, which is used to represent ASN.1 Object Identifier values and their "friendly" names, was previously fully mutable.</span></span> <span data-ttu-id="9295e-105">Essa imutabilidade costuma ser despercebida ou surgiu como uma surpresa.</span><span class="sxs-lookup"><span data-stu-id="9295e-105">This mutability was often overlooked or came as a surprise.</span></span> <span data-ttu-id="9295e-106">Os setters de propriedade agora lançam um <xref:System.PlatformNotSupportedException> quando você tenta alterar o valor depois que ele já foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="9295e-106">The property setters now throw a <xref:System.PlatformNotSupportedException> when you attempt to change the value after it's already been assigned.</span></span>

## <a name="change-description"></a><span data-ttu-id="9295e-107">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="9295e-107">Change description</span></span>

<span data-ttu-id="9295e-108">Em versões anteriores, os setters de propriedade em <xref:System.Security.Cryptography.Oid> podem ser usados para alterar o valor das <xref:System.Security.Cryptography.Oid.FriendlyName> <xref:System.Security.Cryptography.Oid.Value> Propriedades e.</span><span class="sxs-lookup"><span data-stu-id="9295e-108">In previous versions, the property setters on <xref:System.Security.Cryptography.Oid> can be used to change the value of the <xref:System.Security.Cryptography.Oid.FriendlyName> and <xref:System.Security.Cryptography.Oid.Value> properties.</span></span>

<span data-ttu-id="9295e-109">No .NET 5,0 e versões posteriores, os setters de propriedade só podem ser usados para inicializar o valor.</span><span class="sxs-lookup"><span data-stu-id="9295e-109">In .NET 5.0 and later versions, the property setters can only be used to initialize the value.</span></span> <span data-ttu-id="9295e-110">Depois que a propriedade tiver um valor, de um construtor ou de uma chamada anterior para o setter de propriedade, o setter da propriedade sempre lançará um <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="9295e-110">Once the property has a value, either from a constructor or a previous call to the property setter, the property setter always throws a <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="9295e-111">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="9295e-111">Reason for change</span></span>

<span data-ttu-id="9295e-112">Essa alteração permite a reutilização de <xref:System.Security.Cryptography.Oid> objetos como parte dos valores de retorno em APIs públicas para reduzir os perfis de alocação de objetos.</span><span class="sxs-lookup"><span data-stu-id="9295e-112">This change enables the reuse of <xref:System.Security.Cryptography.Oid> objects as part of return values in public APIs to reduce object allocation profiles.</span></span> <span data-ttu-id="9295e-113">Ele evita a necessidade de criar cópias "defensivas" temporárias quando <xref:System.Security.Cryptography.Oid> os valores são usados como entradas.</span><span class="sxs-lookup"><span data-stu-id="9295e-113">It avoids the need to create temporary "defensive" copies when <xref:System.Security.Cryptography.Oid> values are used as inputs.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="9295e-114">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="9295e-114">Version introduced</span></span>

<span data-ttu-id="9295e-115">5.0</span><span class="sxs-lookup"><span data-stu-id="9295e-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="9295e-116">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="9295e-116">Recommended action</span></span>

<span data-ttu-id="9295e-117">Evite usar os <xref:System.Security.Cryptography.Oid> setters de propriedade diferentes de para a inicialização do objeto.</span><span class="sxs-lookup"><span data-stu-id="9295e-117">Avoid using the <xref:System.Security.Cryptography.Oid> property setters other than for object initialization.</span></span> <span data-ttu-id="9295e-118">Para representar um novo valor, use uma nova instância em vez de alterar o valor em um objeto existente.</span><span class="sxs-lookup"><span data-stu-id="9295e-118">To represent a new value, use a new instance instead of changing the value on an existing object.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="9295e-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="9295e-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

### Category

Cryptography

-->
