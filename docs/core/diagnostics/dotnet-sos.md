---
title: dotnet – ferramenta de diagnóstico do SOS-CLI do .NET
description: Saiba como instalar e usar a ferramenta dotnet-SOS CLI para gerenciar a extensão do depurador SOS, que é usada com depuradores nativos no Windows e no Linux.
ms.date: 11/17/2020
ms.openlocfilehash: 59512c42a778f68bb3cd092dc854dcc727fd2881
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825436"
---
# <a name="sos-installer-dotnet-sos"></a>Instalador do SOS (dotNet-SOS)

**Este artigo aplica-se a:** ✔️ SDK do .net Core 2,1 e versões posteriores

## <a name="install"></a>Instalar

Há duas maneiras de baixar e instalar `dotnet-sos` :

- **ferramenta global dotnet:**

  Para instalar a versão de lançamento mais recente do `dotnet-sos` [pacote NuGet](https://www.nuget.org/packages/dotnet-sos), use o comando de [instalação da ferramenta dotnet](../tools/dotnet-tool-install.md) :

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- **Download direto:**

  Baixe o executável da ferramenta que corresponde à sua plataforma:

  | SO  | Plataforma |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [ARM](https://aka.ms/dotnet-sos/win-arm) \| [ARM-x64](https://aka.ms/dotnet-sos/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-sos/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-sos/linux-x64) \| [ARM](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [MUSL-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [MUSL-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64) |

## <a name="synopsis"></a>Sinopse

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a>Descrição

A `dotnet-sos` ferramenta global instala a [extensão do depurador SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) , permitindo a [inspeção do estado do .NET Core gerenciado](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) por meio de depuradores nativos como WinDbg/CDB no Windows e Lldb no Linux e no MacOS. As versões recentes do depurador do Windows (>= versão 10.0.18317.1001 do WinDbg ou do CDB) carregarão o SOS automaticamente da Galeria de extensões da Microsoft, portanto, instalar o SOS por meio da `dotnet-sos` ferramenta só será necessário no Linux e no MacOS ou no Windows se estiver usando ferramentas de depuração mais antigas.

## <a name="options"></a>Opções

- **`--version`**

  Exibe informações de versão.

- **`-h|--help`**

  Mostra a ajuda da linha de comando.

## <a name="dotnet-sos-install"></a>dotnet – instalação do SOS

Instala a [extensão SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) localmente para depurar processos do .NET Core. No macOS e Linux, o arquivo. lldbinit será atualizado para que a extensão seja carregada automaticamente na inicialização do lldb. Se estiver instalando o SOS no Windows com as ferramentas de depuração mais antigas (< versão 10.0.18317.1001), será necessário carregar manualmente a extensão no WinDbg ou no CDB executando `.load %USERPROFILE%\.dotnet\sos\sos.dll` no depurador.

### <a name="synopsis"></a>Sinopse

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a>dotnet – desinstalação do SOS

Desinstala a [extensão SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) e, se estiver no Linux ou no MacOS, o removerá da configuração do lldb.

### <a name="synopsis"></a>Sinopse

```console
dotnet-sos uninstall
```
