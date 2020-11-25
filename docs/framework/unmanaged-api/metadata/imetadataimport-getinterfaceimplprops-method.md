---
title: Método IMetaDataImport::GetInterfaceImplProps
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: e81816ce2194c2c1862cb997ad2c6e5baf301231
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703989"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="38163-102">Método IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="38163-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>

<span data-ttu-id="38163-103">Obtém um ponteiro para os tokens de metadados para o <xref:System.Type> que implementa o método especificado e para a interface que declara esse método.</span><span class="sxs-lookup"><span data-stu-id="38163-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="38163-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="38163-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38163-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="38163-105">Parameters</span></span>  

 `iiImpl`  
 <span data-ttu-id="38163-106">no O token de metadados que representa o método para o qual retornar os tokens de classe e de interface.</span><span class="sxs-lookup"><span data-stu-id="38163-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="38163-107">fora O token de metadados que representa a classe que implementa o método.</span><span class="sxs-lookup"><span data-stu-id="38163-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="38163-108">fora O token de metadados que representa a interface que define o método implementado.</span><span class="sxs-lookup"><span data-stu-id="38163-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="38163-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="38163-109">Remarks</span></span>

 <span data-ttu-id="38163-110">Você Obtém o valor para `iImpl` chamando o método [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) .</span><span class="sxs-lookup"><span data-stu-id="38163-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="38163-111">Por exemplo, suponha que uma classe tenha um `mdTypeDef` valor de token de 0x02000007 e que ele implemente três interfaces cujos tipos têm tokens:</span><span class="sxs-lookup"><span data-stu-id="38163-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="38163-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="38163-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="38163-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="38163-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="38163-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="38163-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="38163-115">Conceitualmente, essas informações são armazenadas em uma tabela de implementação de interface como:</span><span class="sxs-lookup"><span data-stu-id="38163-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="38163-116">Número da linha</span><span class="sxs-lookup"><span data-stu-id="38163-116">Row number</span></span> | <span data-ttu-id="38163-117">Token de classe</span><span class="sxs-lookup"><span data-stu-id="38163-117">Class token</span></span> | <span data-ttu-id="38163-118">Token de interface</span><span class="sxs-lookup"><span data-stu-id="38163-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="38163-119">4</span><span class="sxs-lookup"><span data-stu-id="38163-119">4</span></span>          |             |                 |
| <span data-ttu-id="38163-120">5</span><span class="sxs-lookup"><span data-stu-id="38163-120">5</span></span>          | <span data-ttu-id="38163-121">02000007</span><span class="sxs-lookup"><span data-stu-id="38163-121">02000007</span></span>    | <span data-ttu-id="38163-122">02000003</span><span class="sxs-lookup"><span data-stu-id="38163-122">02000003</span></span>        |
| <span data-ttu-id="38163-123">6</span><span class="sxs-lookup"><span data-stu-id="38163-123">6</span></span>          | <span data-ttu-id="38163-124">02000007</span><span class="sxs-lookup"><span data-stu-id="38163-124">02000007</span></span>    | <span data-ttu-id="38163-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="38163-125">0100000A</span></span>        |
| <span data-ttu-id="38163-126">7</span><span class="sxs-lookup"><span data-stu-id="38163-126">7</span></span>          |             |                 |
| <span data-ttu-id="38163-127">8</span><span class="sxs-lookup"><span data-stu-id="38163-127">8</span></span>          | <span data-ttu-id="38163-128">02000007</span><span class="sxs-lookup"><span data-stu-id="38163-128">02000007</span></span>    | <span data-ttu-id="38163-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="38163-129">0200001C</span></span>        |

<span data-ttu-id="38163-130">Lembre-se de que o token é um valor de 4 bytes:</span><span class="sxs-lookup"><span data-stu-id="38163-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="38163-131">Os 3 bytes inferiores contêm o número da linha, ou RID.</span><span class="sxs-lookup"><span data-stu-id="38163-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="38163-132">O byte superior mantém o tipo de token – 0x09 para `mdtInterfaceImpl` .</span><span class="sxs-lookup"><span data-stu-id="38163-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="38163-133">`GetInterfaceImplProps` Retorna as informações mantidas na linha cujo token você fornece no `iImpl` argumento.</span><span class="sxs-lookup"><span data-stu-id="38163-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="38163-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38163-134">Requirements</span></span>  

 <span data-ttu-id="38163-135">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38163-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38163-136">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="38163-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38163-137">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38163-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38163-138">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38163-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38163-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="38163-139">See also</span></span>

- [<span data-ttu-id="38163-140">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="38163-140">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="38163-141">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="38163-141">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
