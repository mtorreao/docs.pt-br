---
title: Método ICLRMetadataLocator::GetMetadata
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
ms.openlocfilehash: f0ba2342e9704ba06dd1d3612f699298c734a5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723513"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="f0b92-102">Método ICLRMetadataLocator::GetMetadata</span><span class="sxs-lookup"><span data-stu-id="f0b92-102">ICLRMetadataLocator::GetMetadata Method</span></span>

<span data-ttu-id="f0b92-103">Chamado pelos serviços de acesso a dados do Common Language Runtime (CLR) para recuperar os metadados de uma imagem.</span><span class="sxs-lookup"><span data-stu-id="f0b92-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0b92-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f0b92-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0b92-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f0b92-105">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="f0b92-106">no Uma cadeia de caracteres que especifica o caminho do arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="f0b92-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="f0b92-107">no O carimbo de data/hora do arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="f0b92-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="f0b92-108">no O tamanho do arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="f0b92-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="f0b92-109">no O identificador global exclusivo da imagem.</span><span class="sxs-lookup"><span data-stu-id="f0b92-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="f0b92-110">no O endereço virtual relativo (RVA) dos metadados.</span><span class="sxs-lookup"><span data-stu-id="f0b92-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="f0b92-111">O endereço é relativo ao endereço base da imagem.</span><span class="sxs-lookup"><span data-stu-id="f0b92-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="f0b92-112">no Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f0b92-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="f0b92-113">no O tamanho do buffer no qual os metadados são colocados.</span><span class="sxs-lookup"><span data-stu-id="f0b92-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="f0b92-114">fora O buffer no qual os metadados são colocados.</span><span class="sxs-lookup"><span data-stu-id="f0b92-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="f0b92-115">fora O tamanho dos metadados retornados.</span><span class="sxs-lookup"><span data-stu-id="f0b92-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0b92-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="f0b92-116">Remarks</span></span>  

 <span data-ttu-id="f0b92-117">Este método é implementado pelo autor do aplicativo de depuração.</span><span class="sxs-lookup"><span data-stu-id="f0b92-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0b92-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0b92-118">Requirements</span></span>  

 <span data-ttu-id="f0b92-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0b92-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0b92-120">**Cabeçalho:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="f0b92-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f0b92-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0b92-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0b92-122">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0b92-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b92-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="f0b92-123">See also</span></span>

- [<span data-ttu-id="f0b92-124">Interface ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="f0b92-124">ICLRMetadataLocator Interface</span></span>](iclrmetadatalocator-interface.md)
