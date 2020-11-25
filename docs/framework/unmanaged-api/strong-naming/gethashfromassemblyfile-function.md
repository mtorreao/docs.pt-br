---
title: Função GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
ms.openlocfilehash: caefc9773b0d208f8b20847b664f7bc017d2c076
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730988"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="f00e5-102">Função GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="f00e5-102">GetHashFromAssemblyFile Function</span></span>

<span data-ttu-id="f00e5-103">Obtém um hash do arquivo do assembly especificado, usando o algoritmo de hash especificado.</span><span class="sxs-lookup"><span data-stu-id="f00e5-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="f00e5-104">Esta função foi preterida.</span><span class="sxs-lookup"><span data-stu-id="f00e5-104">This function has been deprecated.</span></span> <span data-ttu-id="f00e5-105">Em vez disso, use o método [ICLRStrongName:: GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f00e5-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f00e5-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f00e5-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f00e5-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f00e5-107">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="f00e5-108">no O caminho para o arquivo a ser transformado em hash.</span><span class="sxs-lookup"><span data-stu-id="f00e5-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f00e5-109">[entrada, saída] Uma constante que especifica o algoritmo de hash.</span><span class="sxs-lookup"><span data-stu-id="f00e5-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f00e5-110">Use zero para o algoritmo de hash padrão.</span><span class="sxs-lookup"><span data-stu-id="f00e5-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f00e5-111">fora O buffer de hash retornado.</span><span class="sxs-lookup"><span data-stu-id="f00e5-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f00e5-112">no O tamanho máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="f00e5-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f00e5-113">fora O tamanho retornado, em bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="f00e5-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f00e5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f00e5-114">Requirements</span></span>  

 <span data-ttu-id="f00e5-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f00e5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f00e5-116">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="f00e5-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f00e5-117">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f00e5-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f00e5-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f00e5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f00e5-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="f00e5-119">See also</span></span>

- [<span data-ttu-id="f00e5-120">Método GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="f00e5-120">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="f00e5-121">Método GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="f00e5-121">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="f00e5-122">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f00e5-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
