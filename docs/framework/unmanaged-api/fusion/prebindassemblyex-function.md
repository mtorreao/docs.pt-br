---
title: Função PreBindAssemblyEx
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
ms.openlocfilehash: a729249f7b0681941a0b1a478dbe2c0d9d6cd01c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723955"
---
# <a name="prebindassemblyex-function"></a>Função PreBindAssemblyEx

Obtém o nome de exibição de pós-política para um assembly.  
  
 Essa função dá suporte à infraestrutura de .NET Framework e não se destina a ser usada diretamente do seu código.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pAppCtx`  
 no Identifica o contexto do aplicativo.  
  
 `pName`  
 no Identifica o nome do assembly.  
  
 `pAsmParent`  
 no Identifica o assembly pai. Este parâmetro é ignorado.  
  
 `pwzRuntimeVersion`  
 no Identifica a versão de tempo de execução.  
  
 `ppNamePostPolicy`  
 fora Contém o nome de exibição de pós-política.  
  
 `pvReserved`  
 no Reservado para extensibilidade futura. `pvReserved` deve ser uma referência nula.  
  
## <a name="remarks"></a>Comentários  

 O `ppNamePostPolicy` parâmetro de saída será definido somente se a função retornar HRESULT FUSION_E_REF_DEF_MISMATCH. Caso contrário, será nulo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Fusion. h  
  
 **Biblioteca:** Incluído como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Funções estáticas globais de fusão](fusion-global-static-functions.md)
