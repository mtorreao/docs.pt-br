---
title: Funções auxiliares Tlbexp (referência de API não gerenciada)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
ms.openlocfilehash: 9386918f3574720d90bda7e8da592fa0c91160e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708238"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Funções auxiliares Tlbexp (referência de API não gerenciada)

A [ferramenta Exportador da biblioteca de tipos](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carrega uma biblioteca de vínculo dinâmico chamada TlbRef.dll. Essa DLL contém duas funções auxiliares e uma interface que a ferramenta de exportação usa durante o processo de conversão de assembly para biblioteca de tipos.  
  
## <a name="in-this-section"></a>Nesta seção  

 [Função GetTypeLibInfo](gettypelibinfo-function.md)  
 Fornece informações de localização e do sistema operacional para uma biblioteca de tipos.  
  
 [Função LoadTypeLibWithResolver](loadtypelibwithresolver-function.md)  
 Carrega uma biblioteca de tipos por meio de uma implementação da [interface ITypeLibResolver](itypelibresolver-interface.md) para resolver quaisquer bibliotecas de tipos referenciadas.  
  
 [Interface ITypeLibResolver](itypelibresolver-interface.md)  
 Fornece o [método ResolveTypeLib](resolvetypelib-method.md), que retorna o caminho totalmente qualificado de uma biblioteca de tipos.
