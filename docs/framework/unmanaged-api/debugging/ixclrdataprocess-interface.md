---
title: Interface IXCLRDataProcess
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 376ec2b840bc17c79ed1f27c17a8ddd22c37a0f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245335"
---
# <a name="ixclrdataprocess-interface"></a>Interface IXCLRDataProcess

Fornece métodos para consultar informações sobre um processo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Métodos

| Método                                                                                                                                               | Descrição                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetRuntimeNameByAddress](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | Obtém um nome para o endereço fornecido.                                                               |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Obtém um `AppDomain` em um processo por sua ID exclusiva.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Fornece um identificador para enumerar os módulos de um processo.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | Enumera os módulos desse processo.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Libera os recursos usados por iteradores internos usados durante a enumeração do módulo.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Fornece um identificador para enumerar as instâncias de método de `AppDomain` Iniciar em um determinado endereço. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Enumera as instâncias de método deste processo Iniciando em um deslocamento de endereço.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Libera os recursos usados por iteradores internos usados durante a enumeração da instância.             |

## <a name="remarks"></a>Comentários

Essa interface reside dentro do tempo de execução e não é exposta por nenhum cabeçalho ou arquivo de biblioteca. No entanto, é uma interface COM que deriva de `IUnknown` com GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` que pode ser obtido por meio dos mecanismos com usuais.

## <a name="requirements"></a>Requisitos

**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).
**Cabeçalho:** None  
**Biblioteca:** None  
**.NET Framework versões:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Veja também

- [Depuração](index.md)
- [Depurando interfaces](debugging-interfaces.md)
