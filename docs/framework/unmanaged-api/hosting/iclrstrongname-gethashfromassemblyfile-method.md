---
title: Método ICLRStrongName::GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
ms.openlocfilehash: 0a15a4d237f63da54615ee1801e6cd39620e8274
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727855"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="ccc15-102">Método ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="ccc15-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>

<span data-ttu-id="ccc15-103">Obtém um hash do arquivo do assembly especificado, usando o algoritmo de hash especificado.</span><span class="sxs-lookup"><span data-stu-id="ccc15-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc15-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ccc15-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccc15-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ccc15-105">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="ccc15-106">no O caminho para o arquivo a ser transformado em hash.</span><span class="sxs-lookup"><span data-stu-id="ccc15-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ccc15-107">[entrada, saída] Uma constante que especifica o algoritmo de hash.</span><span class="sxs-lookup"><span data-stu-id="ccc15-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="ccc15-108">Use zero para o algoritmo de hash padrão.</span><span class="sxs-lookup"><span data-stu-id="ccc15-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ccc15-109">fora O buffer de hash retornado.</span><span class="sxs-lookup"><span data-stu-id="ccc15-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ccc15-110">no O tamanho máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="ccc15-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ccc15-111">fora O tamanho retornado, em bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="ccc15-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccc15-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="ccc15-112">Return Value</span></span>  

 <span data-ttu-id="ccc15-113">`S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).</span><span class="sxs-lookup"><span data-stu-id="ccc15-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccc15-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccc15-114">Requirements</span></span>  

 <span data-ttu-id="ccc15-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccc15-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccc15-116">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="ccc15-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ccc15-117">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccc15-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccc15-118">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccc15-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc15-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="ccc15-119">See also</span></span>

- [<span data-ttu-id="ccc15-120">Método GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="ccc15-120">GetHashFromAssemblyFileW Method</span></span>](iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="ccc15-121">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ccc15-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
