---
title: Método ICorProfilerInfo2::GetAppDomainStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 271f9f4fd0d85407aedf088ffb524fa6e0398e37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727205"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a>Método ICorProfilerInfo2::GetAppDomainStaticAddress

Obtém o endereço do campo de domínio estático do aplicativo especificado que está no escopo do domínio do aplicativo especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `classId`  
 no A ID de classe da classe que contém o campo de domínio de aplicativo solicitado-estático.  
  
 `fieldToken`  
 no O token de metadados para o campo de domínio estático do aplicativo solicitado.  
  
 `appDomainId`  
 no A ID do domínio do aplicativo que é o escopo do campo estático solicitado.  
  
 `ppAddress`  
 fora Um ponteiro para o endereço do campo estático que está dentro do domínio de aplicativo especificado.  
  
## <a name="remarks"></a>Comentários  

 O `GetAppDomainStaticAddress` método pode retornar um dos seguintes:  
  
- Um CORPROF_E_DATAINCOMPLETE HRESULT se o campo estático fornecido não tiver sido atribuído um endereço no contexto especificado.  
  
- Os endereços de objetos que podem estar no heap de coleta de lixo. Esses endereços podem se tornar inválidos após a coleta de lixo, portanto, após a coleta de lixo, os profileres não devem presumir que eles são válidos.  
  
 Antes que o construtor de classe de uma classe seja concluído, o `GetAppDomainStaticAddress` retornará CORPROF_E_DATAINCOMPLETE para todos os seus campos estáticos, embora alguns dos campos estáticos já possam ser inicializados e a raiz dos objetos de coleta de lixo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf. idl, CorProf. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interface ICorProfilerInfo2](icorprofilerinfo2-interface.md)
