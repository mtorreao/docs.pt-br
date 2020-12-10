---
ms.openlocfilehash: dfa8235fcfd868b80d3a610bddb492899519e289
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009041"
---
### <a name="xml-parsing-changes"></a><span data-ttu-id="fc236-101">Alterações de análise de XML</span><span class="sxs-lookup"><span data-stu-id="fc236-101">XML parsing changes</span></span>

| <span data-ttu-id="fc236-102">Nome</span><span class="sxs-lookup"><span data-stu-id="fc236-102">Name</span></span>    | <span data-ttu-id="fc236-103">Valor</span><span class="sxs-lookup"><span data-stu-id="fc236-103">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="fc236-104">Escopo</span><span class="sxs-lookup"><span data-stu-id="fc236-104">Scope</span></span>   | <span data-ttu-id="fc236-105">Secundária</span><span class="sxs-lookup"><span data-stu-id="fc236-105">Minor</span></span>   |
| <span data-ttu-id="fc236-106">Versão</span><span class="sxs-lookup"><span data-stu-id="fc236-106">Version</span></span> | <span data-ttu-id="fc236-107">4.5.2</span><span class="sxs-lookup"><span data-stu-id="fc236-107">4.5.2</span></span>   |
| <span data-ttu-id="fc236-108">Type</span><span class="sxs-lookup"><span data-stu-id="fc236-108">Type</span></span>    | <span data-ttu-id="fc236-109">Runtime</span><span class="sxs-lookup"><span data-stu-id="fc236-109">Runtime</span></span> |

#### <a name="details"></a><span data-ttu-id="fc236-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fc236-110">Details</span></span>

<span data-ttu-id="fc236-111">Por motivos de segurança, as seguintes alterações foram introduzidas em APIS de análise de XML:</span><span class="sxs-lookup"><span data-stu-id="fc236-111">For security reasons, the following changes were introduced into XML parsing APIS:</span></span>

- <span data-ttu-id="fc236-112"><xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType> é definido como 10 milhões quando <xref:System.Xml.XmlReaderSettings> é inicializado.</span><span class="sxs-lookup"><span data-stu-id="fc236-112"><xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType> is set to 10 million when <xref:System.Xml.XmlReaderSettings> is initialized.</span></span>
- <span data-ttu-id="fc236-113"><xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType> é definido como `null` por padrão.</span><span class="sxs-lookup"><span data-stu-id="fc236-113"><xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType> is set to `null` by default.</span></span>

> [!NOTE]
> <span data-ttu-id="fc236-114"><xref:System.Xml.XmlReaderSettings> é usado por todos os analisadores XML, portanto, embora essa alteração ajude o <xref:System.Xml.XmlReader> caso, ela também afeta outros cenários.</span><span class="sxs-lookup"><span data-stu-id="fc236-114"><xref:System.Xml.XmlReaderSettings> is used by all XML parsers, so while this change helps the <xref:System.Xml.XmlReader> case, it also affects other scenarios.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fc236-115">Sugestão</span><span class="sxs-lookup"><span data-stu-id="fc236-115">Suggestion</span></span>

<span data-ttu-id="fc236-116">Para reverter para o comportamento anterior, você pode definir um valor no registro.</span><span class="sxs-lookup"><span data-stu-id="fc236-116">To revert to the previous behavior, you can set a value in the registry.</span></span> <span data-ttu-id="fc236-117">Adicione um valor DWORD chamado `EnableLegacyXmlSettings` à `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` chave do registro e defina seu valor como `1` .</span><span class="sxs-lookup"><span data-stu-id="fc236-117">Add a DWORD value named `EnableLegacyXmlSettings` to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` registry key, and set its value to `1`.</span></span> <span data-ttu-id="fc236-118">Você também pode adicionar o valor do registro no hive do HKEY_CURRENT_USER em vez disso.</span><span class="sxs-lookup"><span data-stu-id="fc236-118">You can also add the registry value in the HKEY_CURRENT_USER hive instead.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fc236-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="fc236-119">Affected APIs</span></span>

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName>
- <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=fullName>

<span data-ttu-id="fc236-120">Além disso, qualquer API XML que depende <xref:System.Xml.XmlResolver> , direta ou indiretamente, é afetada.</span><span class="sxs-lookup"><span data-stu-id="fc236-120">In addition, any XML API that depends on <xref:System.Xml.XmlResolver>, either directly or indirectly, is affected.</span></span>

<!--

#### Affected APIs

- `P:System.Xml.XmlReaderSettings.MaxCharactersFromEntities`
- `P:System.Xml.XmlReaderSettings.XmlResolver`

-->
