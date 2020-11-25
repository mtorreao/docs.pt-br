---
title: Método ICorDebugFunction2::EnumerateNativeCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
ms.openlocfilehash: 2cac4a3120e842bde9ad708a251682421fd4ca93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696070"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a>Método ICorDebugFunction2::EnumerateNativeCode

Obtém um ponteiro de interface para um objeto ICorDebugCodeEnum que contém as instruções de código nativo na função referenciada por este objeto ICorDebugFunction2.  
  
> [!NOTE]
> `EnumerateNativeCode` Não está implementado na versão atual do .NET Framework.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorDebug.idl, CorDebug.h
