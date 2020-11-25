---
title: Método ICLRStrongName::GetHashFromFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: ff346d8f7ba321904a8d91079298b58039e6eb54
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727595"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="5f76a-102">Método ICLRStrongName::GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="5f76a-102">ICLRStrongName::GetHashFromFile Method</span></span>

<span data-ttu-id="5f76a-103">Gera um hash sobre o conteúdo do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="5f76a-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f76a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5f76a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f76a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5f76a-105">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="5f76a-106">no O nome do arquivo para hash.</span><span class="sxs-lookup"><span data-stu-id="5f76a-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="5f76a-107">[entrada, saída] O algoritmo a ser usado ao gerar o hash.</span><span class="sxs-lookup"><span data-stu-id="5f76a-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="5f76a-108">Os algoritmos válidos são aqueles definidos pelo CryptoAPI do Win32.</span><span class="sxs-lookup"><span data-stu-id="5f76a-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="5f76a-109">Se `piHashAlg` for definido como 0, o algoritmo padrão CALG_SHA-1 será usado.</span><span class="sxs-lookup"><span data-stu-id="5f76a-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="5f76a-110">fora Uma matriz de bytes que contém o hash gerado.</span><span class="sxs-lookup"><span data-stu-id="5f76a-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="5f76a-111">no O tamanho máximo do buffer que `pbHash` aponta para.</span><span class="sxs-lookup"><span data-stu-id="5f76a-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="5f76a-112">fora O tamanho, em bytes, do retornado `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="5f76a-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f76a-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="5f76a-113">Return Value</span></span>  

 <span data-ttu-id="5f76a-114">`S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).</span><span class="sxs-lookup"><span data-stu-id="5f76a-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f76a-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="5f76a-115">Remarks</span></span>  

 <span data-ttu-id="5f76a-116">Esse método é o mesmo que o método [ICLRStrongName:: GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md) , exceto que a especificação de nome de arquivo é ANSI em vez de Unicode.</span><span class="sxs-lookup"><span data-stu-id="5f76a-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f76a-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f76a-117">Requirements</span></span>  

 <span data-ttu-id="5f76a-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f76a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f76a-119">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="5f76a-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5f76a-120">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f76a-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f76a-121">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f76a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f76a-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="5f76a-122">See also</span></span>

- [<span data-ttu-id="5f76a-123">Método GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="5f76a-123">GetHashFromFileW Method</span></span>](iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="5f76a-124">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5f76a-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
