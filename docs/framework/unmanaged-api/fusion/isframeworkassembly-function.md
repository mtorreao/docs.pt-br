---
title: Função IsFrameworkAssembly
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
ms.openlocfilehash: 828c7660d6c006e700302d119ce4caf7d76e5d84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728557"
---
# <a name="isframeworkassembly-function"></a>Função IsFrameworkAssembly

Obtém um valor que indica se o assembly especificado é gerenciado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pwzAssemblyReference`  
 no O nome do assembly a ser verificado.  
  
 `pbIsFrameworkAssembly`  
 fora Um valor booliano que indica se o assembly é gerenciado.  
  
 `pwzFrameworkAssemblyIdentity`  
 no Uma cadeia de caracteres não canônica que contém a identidade exclusiva do assembly.  
  
 `pccSize`  
 [in] O tamanho do `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Comentários  

 O `pwzAssemblyReference` parâmetro é um ponteiro para uma cadeia de caracteres que contém o nome de um assembly.  
  
 Se esse assembly fizer parte do .NET Framework, o `pbIsFrameworkAssembly` parâmetro conterá um valor booliano de `true` .  
  
 Se o assembly nomeado não fizer parte do .NET Framework, ou se o `pwzAssemblyReference` parâmetro não nomear um assembly, `pbIsFrameworkAssembly` conterá um valor booliano de `false` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>Confira também

- [Funções estáticas globais de fusão](fusion-global-static-functions.md)
