---
title: Método ICLRStrongName::StrongNameKeyInstall
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
ms.openlocfilehash: 7e0c689dad0c288e3af3a3d64ee1bba1c44053c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674522"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="b28f6-102">Método ICLRStrongName::StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="b28f6-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>

<span data-ttu-id="b28f6-103">Importa um par de chaves públicas/privadas em um contêiner.</span><span class="sxs-lookup"><span data-stu-id="b28f6-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28f6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b28f6-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b28f6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b28f6-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="b28f6-106">no O nome do contêiner de chave.</span><span class="sxs-lookup"><span data-stu-id="b28f6-106">[in] The name of the key container.</span></span> <span data-ttu-id="b28f6-107">`wszKeyContainer` deve ser uma cadeia de caracteres não vazia.</span><span class="sxs-lookup"><span data-stu-id="b28f6-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="b28f6-108">no O par de chaves binárias.</span><span class="sxs-lookup"><span data-stu-id="b28f6-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="b28f6-109">no O tamanho, em bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="b28f6-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b28f6-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="b28f6-110">Return Value</span></span>  

 <span data-ttu-id="b28f6-111">`S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).</span><span class="sxs-lookup"><span data-stu-id="b28f6-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b28f6-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="b28f6-112">Remarks</span></span>  

 <span data-ttu-id="b28f6-113">Use o método [ICLRStrongName:: StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) para excluir o contêiner de chave.</span><span class="sxs-lookup"><span data-stu-id="b28f6-113">Use the [ICLRStrongName::StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b28f6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b28f6-114">Requirements</span></span>  

 <span data-ttu-id="b28f6-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b28f6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b28f6-116">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="b28f6-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b28f6-117">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b28f6-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b28f6-118">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b28f6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28f6-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="b28f6-119">See also</span></span>

- [<span data-ttu-id="b28f6-120">Método StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="b28f6-120">StrongNameKeyDelete Method</span></span>](iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="b28f6-121">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b28f6-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
