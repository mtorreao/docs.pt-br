---
title: Função GetHashFromHandle
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: 904dcb707e704cfec2dba4e6587f7e3acaf7b538
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732319"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="836ca-102">Função GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="836ca-102">GetHashFromHandle Function</span></span>

<span data-ttu-id="836ca-103">Gera um hash sobre o conteúdo do arquivo com o identificador de arquivo especificado, usando o algoritmo de hash especificado.</span><span class="sxs-lookup"><span data-stu-id="836ca-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="836ca-104">Esta função foi preterida.</span><span class="sxs-lookup"><span data-stu-id="836ca-104">This function has been deprecated.</span></span> <span data-ttu-id="836ca-105">Em vez disso, use o método [ICLRStrongName:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) .</span><span class="sxs-lookup"><span data-stu-id="836ca-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="836ca-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="836ca-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="836ca-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="836ca-107">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="836ca-108">no O identificador do arquivo a ser transformado em hash.</span><span class="sxs-lookup"><span data-stu-id="836ca-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="836ca-109">[entrada, saída] Uma constante que especifica o algoritmo de hash.</span><span class="sxs-lookup"><span data-stu-id="836ca-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="836ca-110">Use zero para o algoritmo padrão.</span><span class="sxs-lookup"><span data-stu-id="836ca-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="836ca-111">fora O buffer de hash retornado.</span><span class="sxs-lookup"><span data-stu-id="836ca-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="836ca-112">no O tamanho máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="836ca-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="836ca-113">fora O tamanho, em bytes, do retornado `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="836ca-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="836ca-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="836ca-114">Requirements</span></span>  

 <span data-ttu-id="836ca-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="836ca-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="836ca-116">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="836ca-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="836ca-117">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="836ca-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="836ca-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="836ca-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="836ca-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="836ca-119">See also</span></span>

- [<span data-ttu-id="836ca-120">Método GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="836ca-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="836ca-121">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="836ca-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
