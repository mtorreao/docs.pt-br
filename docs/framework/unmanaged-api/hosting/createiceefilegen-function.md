---
title: Função CreateICeeFileGen
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 454cfa2dd1b676f32649050625b1074fbd776d54
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673326"
---
# <a name="createiceefilegen-function"></a>Função CreateICeeFileGen

Cria um objeto [ICeeFileGen](iceefilegen-class.md) .  
  
 Essa função foi preterida no .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ceeFileGen`  
 fora Um ponteiro para o endereço de um novo `ICeeFileGen` objeto.  
  
## <a name="return-value"></a>Valor Retornado  

 Esse método retorna códigos de erro COM padrão.  
  
## <a name="remarks"></a>Comentários  

 O `ICeeFileGen` objeto é usado para criar Common Language Runtime (CLR) arquivos executáveis portáteis (PE).  
  
 Chame a função [DestroyICeeFileGen](destroyiceefilegen-function.md) para destruir o `ICeeFileGen` objeto quando terminar.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** ICeeFileGen. h  
  
 **Biblioteca:** MSCorPE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Funções de hospedagem CLR reprovadas](deprecated-clr-hosting-functions.md)
