---
title: Método IMetaDataImport2::EnumMethodSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 26b345567699c5780827ed835cff13069ea8f609
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702739"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="e6126-102">Método IMetaDataImport2::EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="e6126-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>

<span data-ttu-id="e6126-103">Obtém um enumerador para uma matriz de tokens de MethodSpec associados ao token MethodDef ou MemberRef especificado.</span><span class="sxs-lookup"><span data-stu-id="e6126-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6126-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e6126-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="e6126-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e6126-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="e6126-106">[entrada, saída] Um ponteiro para o enumerador para `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="e6126-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="e6126-107">no O token MemberRef ou MethodDef que representa o método cujos tokens de MethodSpec devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="e6126-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="e6126-108">Se o valor de `tk` for 0 (zero), todos os tokens de MethodSpec no escopo serão enumerados.</span><span class="sxs-lookup"><span data-stu-id="e6126-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="e6126-109">fora A matriz de tokens de MethodSpec a ser enumerada.</span><span class="sxs-lookup"><span data-stu-id="e6126-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e6126-110">no O número máximo solicitado de tokens a serem colocados `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="e6126-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="e6126-111">fora O número retornado de tokens colocados em `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="e6126-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6126-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="e6126-112">Return Value</span></span>  
  
|<span data-ttu-id="e6126-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6126-113">HRESULT</span></span>|<span data-ttu-id="e6126-114">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e6126-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e6126-115">`EnumMethodSpecs` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="e6126-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e6126-116">`phEnum` Não tem elementos de membro.</span><span class="sxs-lookup"><span data-stu-id="e6126-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="e6126-117">Nesse caso, `pcMethodSpecs` é definido como 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="e6126-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6126-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6126-118">Requirements</span></span>  

 <span data-ttu-id="e6126-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6126-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6126-120">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e6126-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6126-121">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6126-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e6126-122">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6126-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6126-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="e6126-123">See also</span></span>

- [<span data-ttu-id="e6126-124">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e6126-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="e6126-125">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e6126-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
