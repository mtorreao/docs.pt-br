---
title: Método IMetaDataImport2::GetVersionString
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
ms.openlocfilehash: 3e62b1177c0161883ad03086723cc43b71292df5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702554"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="08b5e-102">Método IMetaDataImport2::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="08b5e-102">IMetaDataImport2::GetVersionString Method</span></span>

<span data-ttu-id="08b5e-103">Obtém o número de versão do tempo de execução que foi usado para compilar o assembly.</span><span class="sxs-lookup"><span data-stu-id="08b5e-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08b5e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="08b5e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08b5e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="08b5e-105">Parameters</span></span>  

 `pwzBuf`  
 <span data-ttu-id="08b5e-106">fora Uma matriz para armazenar a cadeia de caracteres que especifica a versão.</span><span class="sxs-lookup"><span data-stu-id="08b5e-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="08b5e-107">no O tamanho, em caracteres largos, da `pwzBuf` matriz.</span><span class="sxs-lookup"><span data-stu-id="08b5e-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="08b5e-108">fora O número de caracteres largos, incluindo um terminador nulo, retornado na `pwzBuf` matriz.</span><span class="sxs-lookup"><span data-stu-id="08b5e-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08b5e-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="08b5e-109">Remarks</span></span>  

 <span data-ttu-id="08b5e-110">O `GetVersionString` método obtém a versão interna do escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="08b5e-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="08b5e-111">Se o escopo nunca tiver sido salvo, ele não terá uma versão interna e uma cadeia de caracteres vazia será retornada.</span><span class="sxs-lookup"><span data-stu-id="08b5e-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08b5e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08b5e-112">Requirements</span></span>  

 <span data-ttu-id="08b5e-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08b5e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08b5e-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="08b5e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08b5e-115">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08b5e-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08b5e-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08b5e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b5e-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="08b5e-117">See also</span></span>

- [<span data-ttu-id="08b5e-118">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="08b5e-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="08b5e-119">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="08b5e-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
