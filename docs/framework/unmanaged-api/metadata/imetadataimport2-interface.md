---
title: Interface IMetaDataImport2
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: a845ecfde6583d625d2a8f165443344ff9e40d05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702539"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="419b9-102">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="419b9-102">IMetaDataImport2 Interface</span></span>

<span data-ttu-id="419b9-103">Estende a interface [IMetaDataImport](imetadataimport-interface.md) para fornecer a capacidade de trabalhar com tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="419b9-103">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="419b9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="419b9-104">Methods</span></span>  
  
|<span data-ttu-id="419b9-105">Método</span><span class="sxs-lookup"><span data-stu-id="419b9-105">Method</span></span>|<span data-ttu-id="419b9-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="419b9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="419b9-107">Método EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="419b9-107">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="419b9-108">Obtém um enumerador para uma matriz de restrições de parâmetro genérico associadas ao parâmetro genérico representado pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="419b9-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="419b9-109">Método EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="419b9-109">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="419b9-110">Obtém um enumerador para uma matriz de tokens de parâmetro genéricos associados ao TypeDef ou token MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="419b9-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="419b9-111">Método EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="419b9-111">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="419b9-112">Obtém um enumerador para uma matriz de tokens de MethodSpec associados ao token MethodDef ou MemberRef especificado.</span><span class="sxs-lookup"><span data-stu-id="419b9-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="419b9-113">Método GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="419b9-113">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="419b9-114">Obtém os metadados associados à restrição de parâmetro genérico representada pelo token de restrição especificado.</span><span class="sxs-lookup"><span data-stu-id="419b9-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="419b9-115">Método GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="419b9-115">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="419b9-116">Obtém os metadados associados ao parâmetro genérico representado pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="419b9-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="419b9-117">Método GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="419b9-117">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="419b9-118">Obtém a assinatura de metadados do método referenciado pelo token de MethodSpec especificado.</span><span class="sxs-lookup"><span data-stu-id="419b9-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="419b9-119">Método GetPEKind</span><span class="sxs-lookup"><span data-stu-id="419b9-119">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="419b9-120">Obtém um valor que identifica a natureza do código em um arquivo executável portátil (PE), normalmente um arquivo DLL ou EXE, definido no escopo de metadados atual</span><span class="sxs-lookup"><span data-stu-id="419b9-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="419b9-121">Método GetVersionString</span><span class="sxs-lookup"><span data-stu-id="419b9-121">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="419b9-122">Obtém o número de versão do tempo de execução que foi usado para compilar o assembly.</span><span class="sxs-lookup"><span data-stu-id="419b9-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="419b9-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="419b9-123">Requirements</span></span>  

 <span data-ttu-id="419b9-124">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="419b9-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="419b9-125">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="419b9-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="419b9-126">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="419b9-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="419b9-127">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="419b9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419b9-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="419b9-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="419b9-129">Interfaces de metadados</span><span class="sxs-lookup"><span data-stu-id="419b9-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="419b9-130">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="419b9-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
