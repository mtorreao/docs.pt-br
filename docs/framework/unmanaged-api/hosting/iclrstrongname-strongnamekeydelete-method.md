---
title: Método ICLRStrongName::StrongNameKeyDelete
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
ms.openlocfilehash: 46345ae570673c9c9c0c58fb6edea1464ba8dd91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671688"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="38d7a-102">Método ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="38d7a-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>

<span data-ttu-id="38d7a-103">Exclui o contêiner de chave especificado.</span><span class="sxs-lookup"><span data-stu-id="38d7a-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d7a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="38d7a-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38d7a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="38d7a-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="38d7a-106">no O nome do contêiner de chave a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="38d7a-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38d7a-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="38d7a-107">Return Value</span></span>  

 <span data-ttu-id="38d7a-108">`S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).</span><span class="sxs-lookup"><span data-stu-id="38d7a-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38d7a-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="38d7a-109">Remarks</span></span>  

 <span data-ttu-id="38d7a-110">Use o método [ICLRStrongName:: StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) para importar um par de chaves pública/privada para um contêiner.</span><span class="sxs-lookup"><span data-stu-id="38d7a-110">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38d7a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38d7a-111">Requirements</span></span>  

 <span data-ttu-id="38d7a-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38d7a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38d7a-113">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="38d7a-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="38d7a-114">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38d7a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38d7a-115">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38d7a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d7a-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="38d7a-116">See also</span></span>

- [<span data-ttu-id="38d7a-117">Método StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="38d7a-117">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="38d7a-118">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="38d7a-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
