---
title: Interface IAppIdAuthority
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
ms.openlocfilehash: a344f2ab5d9a7aa92018c47ee7a162cd1721aeb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732106"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="fa24c-102">Interface IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="fa24c-102">IAppIdAuthority Interface</span></span>

<span data-ttu-id="fa24c-103">Fornece métodos que geram e comparam chaves para identidades e referências de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fa24c-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa24c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fa24c-104">Methods</span></span>  
  
|<span data-ttu-id="fa24c-105">Método</span><span class="sxs-lookup"><span data-stu-id="fa24c-105">Method</span></span>|<span data-ttu-id="fa24c-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="fa24c-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="fa24c-107">Obtém um valor que indica se as duas instâncias de [IDefinitionAppId](idefinitionappid-interface.md) especificadas são iguais.</span><span class="sxs-lookup"><span data-stu-id="fa24c-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="fa24c-108">Você pode passar o valor do sinalizador IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para ignorar suas respectivas informações de versão.</span><span class="sxs-lookup"><span data-stu-id="fa24c-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="fa24c-109">Obtém um valor que indica se as duas instâncias de [IReferenceAppId](ireferenceappid-interface.md) especificadas são iguais.</span><span class="sxs-lookup"><span data-stu-id="fa24c-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="fa24c-110">Você pode passar o valor do sinalizador IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para ignorar suas respectivas informações de versão.</span><span class="sxs-lookup"><span data-stu-id="fa24c-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="fa24c-111">Obtém um valor que indica se as duas definições de cadeia de caracteres especificadas são iguais.</span><span class="sxs-lookup"><span data-stu-id="fa24c-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="fa24c-112">Você pode passar o valor do sinalizador IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para ignorar suas respectivas informações de versão.</span><span class="sxs-lookup"><span data-stu-id="fa24c-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="fa24c-113">Obtém um valor que indica se as duas referências de cadeia de caracteres especificadas são iguais.</span><span class="sxs-lookup"><span data-stu-id="fa24c-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="fa24c-114">Você pode passar o valor do sinalizador IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para ignorar suas respectivas informações de versão.</span><span class="sxs-lookup"><span data-stu-id="fa24c-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="fa24c-115">Obtém um ponteiro de interface para uma instância gerada recentemente `IDefinitionAppId` que representa o assembly no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="fa24c-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="fa24c-116">Obtém um ponteiro de interface para um recém-criado `IReferenceAppId` que representa o assembly no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="fa24c-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="fa24c-117">Obtém uma versão de cadeia de caracteres do especificada `IDefinitionAppId` , usando os valores de sinalizador especificados.</span><span class="sxs-lookup"><span data-stu-id="fa24c-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="fa24c-118">Obtém um valor que indica se o especificado `IDefinitionAppId` e `IReferenceAppId` representa o mesmo assembly.</span><span class="sxs-lookup"><span data-stu-id="fa24c-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="fa24c-119">Obtém um valor que indica se a cadeia de caracteres de definição especificada e a cadeia de caracteres de referência representam o mesmo assembly.</span><span class="sxs-lookup"><span data-stu-id="fa24c-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="fa24c-120">Obtém uma chave de cadeia de caracteres que representa a `IDefinitionAppId` instância especificada.</span><span class="sxs-lookup"><span data-stu-id="fa24c-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="fa24c-121">Obtém uma chave de cadeia de caracteres que representa a `IReferenceAppId` instância especificada.</span><span class="sxs-lookup"><span data-stu-id="fa24c-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="fa24c-122">Obtém uma chave de hash para a `IDefinitionAppId` instância especificada.</span><span class="sxs-lookup"><span data-stu-id="fa24c-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="fa24c-123">Obtém uma chave de hash para a `IReferenceAppId` instância especificada.</span><span class="sxs-lookup"><span data-stu-id="fa24c-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="fa24c-124">Obtém uma versão de cadeia de caracteres do especificada `IReferenceAppId` , usando os valores de sinalizador especificados.</span><span class="sxs-lookup"><span data-stu-id="fa24c-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="fa24c-125">Obtém um ponteiro de interface para uma `IDefinitionAppId` instância que representa o assembly referenciado pela chave de cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="fa24c-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="fa24c-126">Obtém um ponteiro de interface para uma `IReferenceAppId` instância que representa o assembly referenciado pela chave de cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="fa24c-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa24c-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa24c-127">Requirements</span></span>  

 <span data-ttu-id="fa24c-128">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa24c-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa24c-129">**Cabeçalho:** Isolamento. h</span><span class="sxs-lookup"><span data-stu-id="fa24c-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="fa24c-130">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa24c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa24c-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="fa24c-131">See also</span></span>

- [<span data-ttu-id="fa24c-132">Interfaces de fusão</span><span class="sxs-lookup"><span data-stu-id="fa24c-132">Fusion Interfaces</span></span>](fusion-interfaces.md)
