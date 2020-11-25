---
title: Enumeração AssemblyFlags
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: 561b4d68a574a2859286fb5f2e2d950518a9d29d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732769"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="1b562-102">Enumeração AssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="1b562-102">AssemblyFlags Enumeration</span></span>

<span data-ttu-id="1b562-103">Contém valores que descrevem os recursos de tempo de execução de um assembly.</span><span class="sxs-lookup"><span data-stu-id="1b562-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b562-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1b562-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1b562-105">Membros</span><span class="sxs-lookup"><span data-stu-id="1b562-105">Members</span></span>  
  
|<span data-ttu-id="1b562-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1b562-106">Member</span></span>|<span data-ttu-id="1b562-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="1b562-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="1b562-108">Especifica que as definições de tipo exportadas são implícitas dentro dos arquivos que compõem o assembly.</span><span class="sxs-lookup"><span data-stu-id="1b562-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="1b562-109">No .NET Framework versões 1,0 e 1,1, esse valor é sempre considerado definido.</span><span class="sxs-lookup"><span data-stu-id="1b562-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="1b562-110">Especifica que as definições de recursos são implícitas dentro dos arquivos que compõem o assembly.</span><span class="sxs-lookup"><span data-stu-id="1b562-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="1b562-111">No .NET Framework 1,0 e 1,1, esse valor é sempre considerado definido.</span><span class="sxs-lookup"><span data-stu-id="1b562-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="1b562-112">Especifica que o assembly não pode ser executado com outras versões se estiverem em execução no mesmo domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1b562-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="1b562-113">Especifica que o assembly não pode ser executado com outras versões se estiverem em execução no mesmo processo.</span><span class="sxs-lookup"><span data-stu-id="1b562-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="1b562-114">Especifica que o assembly não pode ser executado com outras versões se estiverem em execução no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="1b562-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b562-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="1b562-115">Remarks</span></span>  

 <span data-ttu-id="1b562-116">Os valores entre 0x0010 e 0x0070, inclusive, são usados para descrever os recursos de compatibilidade lado a lado do assembly referenciado.</span><span class="sxs-lookup"><span data-stu-id="1b562-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="1b562-117">Se nenhum desses valores for definido, o assembly será considerado compatível lado a lado.</span><span class="sxs-lookup"><span data-stu-id="1b562-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b562-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b562-118">Requirements</span></span>  

 <span data-ttu-id="1b562-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b562-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b562-120">**Cabeçalho:** MsCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1b562-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="1b562-121">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b562-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1b562-122">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b562-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b562-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="1b562-123">See also</span></span>

- [<span data-ttu-id="1b562-124">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="1b562-124">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="1b562-125">Interface IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="1b562-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
