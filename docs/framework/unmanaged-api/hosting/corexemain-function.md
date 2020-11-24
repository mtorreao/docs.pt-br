---
title: Função _CorExeMain
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
ms.openlocfilehash: af1d0e2039024a51341e30bec497c581a0bcacb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673664"
---
# <a name="_corexemain-function"></a><span data-ttu-id="2c84c-102">Função _CorExeMain</span><span class="sxs-lookup"><span data-stu-id="2c84c-102">_CorExeMain Function</span></span>

<span data-ttu-id="2c84c-103">Inicializa o Common Language Runtime (CLR), localiza o ponto de entrada gerenciado no cabeçalho CLR do assembly executável e começa a execução.</span><span class="sxs-lookup"><span data-stu-id="2c84c-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c84c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2c84c-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2c84c-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="2c84c-105">Remarks</span></span>  

 <span data-ttu-id="2c84c-106">Essa função é chamada pelo carregador em processos criados a partir de assemblies executáveis gerenciados.</span><span class="sxs-lookup"><span data-stu-id="2c84c-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="2c84c-107">Para assemblies DLL, o carregador chama a função [_CorDllMain](cordllmain-function.md) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="2c84c-107">For DLL assemblies, the loader calls the [_CorDllMain](cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="2c84c-108">O carregador do sistema operacional chama esse método, independentemente do ponto de entrada especificado no arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="2c84c-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="2c84c-109">No Windows 98, Windows ME, Windows NT e Windows 2000, a `_CorExeMain` função é chamada indiretamente por meio de uma correção no carregador do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2c84c-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="2c84c-110">Em todas as outras versões do Windows, ele é chamado diretamente pelo carregador do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2c84c-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="2c84c-111">Para obter informações adicionais, consulte a seção comentários no tópico [_CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="2c84c-111">For additional information, see the Remarks section in the [_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c84c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c84c-112">Requirements</span></span>  

 <span data-ttu-id="2c84c-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c84c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c84c-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2c84c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c84c-115">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c84c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c84c-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c84c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c84c-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c84c-117">See also</span></span>

- [<span data-ttu-id="2c84c-118">Funções estáticas globais de metadados</span><span class="sxs-lookup"><span data-stu-id="2c84c-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
