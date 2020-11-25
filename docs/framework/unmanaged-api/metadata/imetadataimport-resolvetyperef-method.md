---
title: Método IMetaDataImport::ResolveTypeRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
ms.openlocfilehash: 76c5519a6cd1b8994e2f869281f13d8269e89fde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702817"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="d9aa9-102">Método IMetaDataImport::ResolveTypeRef</span><span class="sxs-lookup"><span data-stu-id="d9aa9-102">IMetaDataImport::ResolveTypeRef Method</span></span>

<span data-ttu-id="d9aa9-103">Resolve uma <xref:System.Type> referência representada pelo token TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9aa9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d9aa9-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9aa9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d9aa9-105">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="d9aa9-106">no O token de metadados TypeRef para retornar as informações de tipo referenciadas.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="d9aa9-107">no O IID da interface a ser retornada `ppIScope` .</span><span class="sxs-lookup"><span data-stu-id="d9aa9-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="d9aa9-108">Normalmente, isso seria IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="d9aa9-109">fora Uma interface para o escopo do módulo no qual o tipo referenciado é definido.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="d9aa9-110">fora Um ponteiro para um token de TypeDef que representa o tipo referenciado.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9aa9-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="d9aa9-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d9aa9-112">Não use esse método se vários domínios de aplicativo forem carregados.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="d9aa9-113">O método não respeita os limites do domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="d9aa9-114">Se várias versões de um assembly forem carregadas e contiverem o mesmo tipo com o mesmo namespace, o método retornará o escopo do módulo do primeiro tipo que encontrar.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="d9aa9-115">O `ResolveTypeRef` método procura a definição de tipo em outros módulos.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="d9aa9-116">Se a definição de tipo for encontrada, `ResolveTypeRef` retorna uma interface para esse escopo de módulo, bem como o token de typedef para o tipo.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="d9aa9-117">Se a referência de tipo a ser resolvida tiver um escopo de resolução de AssemblyRef, o `ResolveTypeRef` método procurará uma correspondência somente nos escopos de metadados que já foram abertos com chamadas para o método [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) ou para o método [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d9aa9-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="d9aa9-118">Isso ocorre porque o `ResolveTypeRef` não pode determinar apenas o escopo de AssemblyRef em que no disco ou no cache de assembly global o assembly está armazenado.</span><span class="sxs-lookup"><span data-stu-id="d9aa9-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9aa9-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9aa9-119">Requirements</span></span>  

 <span data-ttu-id="d9aa9-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9aa9-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9aa9-121">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d9aa9-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9aa9-122">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9aa9-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9aa9-123">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9aa9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9aa9-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="d9aa9-124">See also</span></span>

- [<span data-ttu-id="d9aa9-125">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d9aa9-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d9aa9-126">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d9aa9-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
