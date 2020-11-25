---
title: Estrutura ASSEMBLYMETADATA
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 8071c3f43775975de37e3255582b6fc8f13f7de3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732773"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="820f2-102">Estrutura ASSEMBLYMETADATA</span><span class="sxs-lookup"><span data-stu-id="820f2-102">ASSEMBLYMETADATA Structure</span></span>

<span data-ttu-id="820f2-103">Contém informações sobre o assembly referenciado, incluindo sua versão e seu nível de suporte para localidades, processadores e sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="820f2-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="820f2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="820f2-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="820f2-105">Membros</span><span class="sxs-lookup"><span data-stu-id="820f2-105">Members</span></span>  
  
|<span data-ttu-id="820f2-106">Membro</span><span class="sxs-lookup"><span data-stu-id="820f2-106">Member</span></span>|<span data-ttu-id="820f2-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="820f2-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="820f2-108">O número de versão principal do assembly referenciado.</span><span class="sxs-lookup"><span data-stu-id="820f2-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="820f2-109">Esse valor não pode ser zero.</span><span class="sxs-lookup"><span data-stu-id="820f2-109">This value cannot be zero.</span></span> <span data-ttu-id="820f2-110">Se todos os bits de `usMajorVersion` estiverem definidos, a versão principal não será especificada.</span><span class="sxs-lookup"><span data-stu-id="820f2-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="820f2-111">O número de versão secundária do assembly referenciado.</span><span class="sxs-lookup"><span data-stu-id="820f2-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="820f2-112">Esse valor não pode ser zero.</span><span class="sxs-lookup"><span data-stu-id="820f2-112">This value cannot be zero.</span></span> <span data-ttu-id="820f2-113">Se todos os bits de `usMinorVersion` estiverem definidos, a versão secundária não será especificada.</span><span class="sxs-lookup"><span data-stu-id="820f2-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="820f2-114">O número de Build do assembly referenciado.</span><span class="sxs-lookup"><span data-stu-id="820f2-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="820f2-115">Esse valor não pode ser zero.</span><span class="sxs-lookup"><span data-stu-id="820f2-115">This value cannot be zero.</span></span> <span data-ttu-id="820f2-116">Se todos os bits de `usBuildNumber` estiverem definidos, o número de Build não será especificado.</span><span class="sxs-lookup"><span data-stu-id="820f2-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="820f2-117">O número de revisão do assembly referenciado.</span><span class="sxs-lookup"><span data-stu-id="820f2-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="820f2-118">Esse valor não pode ser zero.</span><span class="sxs-lookup"><span data-stu-id="820f2-118">This value cannot be zero.</span></span> <span data-ttu-id="820f2-119">Se todos os bits de `usRevisionNumber` estiverem definidos, o número de revisão não será especificado.</span><span class="sxs-lookup"><span data-stu-id="820f2-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="820f2-120">Uma lista de nomes de localidade que estão em conformidade com a especificação RFC1766, separados por ponto e vírgula, especificando as localidades com suporte no assembly referenciado.</span><span class="sxs-lookup"><span data-stu-id="820f2-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="820f2-121">Um valor nulo indica independência de localidade.</span><span class="sxs-lookup"><span data-stu-id="820f2-121">A null value indicates locale independence.</span></span> <span data-ttu-id="820f2-122">**Observação:**  No .NET Framework versão 1,0, você não pode especificar mais de uma localidade.</span><span class="sxs-lookup"><span data-stu-id="820f2-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="820f2-123">O tamanho em caracteres largos de `szLocale` .</span><span class="sxs-lookup"><span data-stu-id="820f2-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="820f2-124">Uma matriz de identificadores, conforme definido em Winnt. h, para os tipos de processador que são suportados pelo assembly referenciado.</span><span class="sxs-lookup"><span data-stu-id="820f2-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="820f2-125">Um valor nulo indica independência do processador.</span><span class="sxs-lookup"><span data-stu-id="820f2-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="820f2-126">O comprimento da matriz `rdwProcessor`.</span><span class="sxs-lookup"><span data-stu-id="820f2-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="820f2-127">Uma matriz de instâncias de [OSInfo](osinfo-structure.md) que especificam os sistemas operacionais com suporte no assembly referenciado.</span><span class="sxs-lookup"><span data-stu-id="820f2-127">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="820f2-128">Um valor nulo indica a independência do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="820f2-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="820f2-129">O comprimento da matriz `rOS`.</span><span class="sxs-lookup"><span data-stu-id="820f2-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="820f2-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="820f2-130">Requirements</span></span>  

 <span data-ttu-id="820f2-131">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="820f2-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="820f2-132">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="820f2-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="820f2-133">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="820f2-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="820f2-134">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="820f2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="820f2-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="820f2-135">See also</span></span>

- [<span data-ttu-id="820f2-136">Estruturas de metadados</span><span class="sxs-lookup"><span data-stu-id="820f2-136">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="820f2-137">Interface IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="820f2-137">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="820f2-138">Estrutura OSINFO</span><span class="sxs-lookup"><span data-stu-id="820f2-138">OSINFO Structure</span></span>](osinfo-structure.md)
