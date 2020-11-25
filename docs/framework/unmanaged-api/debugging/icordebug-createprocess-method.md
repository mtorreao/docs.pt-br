---
title: Método ICorDebug::CreateProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
ms.openlocfilehash: aeb39782c4c0624501a0e2a71960f5d16ab3c03e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723474"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="ad077-102">Método ICorDebug::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="ad077-102">ICorDebug::CreateProcess Method</span></span>

<span data-ttu-id="ad077-103">Inicia um processo e seu thread principal sob o controle do depurador.</span><span class="sxs-lookup"><span data-stu-id="ad077-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad077-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ad077-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad077-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ad077-105">Parameters</span></span>  

 `lpApplicationName`  
 <span data-ttu-id="ad077-106">no Ponteiro para uma cadeia de caracteres terminada em nulo que especifica o módulo a ser executado pelo processo iniciado.</span><span class="sxs-lookup"><span data-stu-id="ad077-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="ad077-107">O módulo é executado no contexto de segurança do processo de chamada.</span><span class="sxs-lookup"><span data-stu-id="ad077-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="ad077-108">no Ponteiro para uma cadeia de caracteres terminada em nulo que especifica a linha de comando a ser executada pelo processo iniciado.</span><span class="sxs-lookup"><span data-stu-id="ad077-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="ad077-109">O nome do aplicativo (por exemplo, "SomeApp.exe") deve ser o primeiro argumento.</span><span class="sxs-lookup"><span data-stu-id="ad077-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="ad077-110">no Ponteiro para uma `SECURITY_ATTRIBUTES` estrutura Win32 que especifica o descritor de segurança para o processo.</span><span class="sxs-lookup"><span data-stu-id="ad077-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="ad077-111">Se `lpProcessAttributes` for NULL, o processo obterá um descritor de segurança padrão.</span><span class="sxs-lookup"><span data-stu-id="ad077-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="ad077-112">no Ponteiro para uma `SECURITY_ATTRIBUTES` estrutura Win32 que especifica o descritor de segurança para o thread principal do processo.</span><span class="sxs-lookup"><span data-stu-id="ad077-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="ad077-113">Se `lpThreadAttributes` for NULL, o thread obterá um descritor de segurança padrão.</span><span class="sxs-lookup"><span data-stu-id="ad077-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="ad077-114">no Defina como `true` para indicar que cada identificador herdável no processo de chamada é herdado pelo processo iniciado ou `false` para indicar que os identificadores não são herdados.</span><span class="sxs-lookup"><span data-stu-id="ad077-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="ad077-115">Os identificadores herdados têm o mesmo valor e direitos de acesso que os identificadores originais.</span><span class="sxs-lookup"><span data-stu-id="ad077-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="ad077-116">no Uma combinação de bits de bit que indica os [sinalizadores de criação de processos do Win32](/windows/win32/procthread/process-creation-flags) que controlam a classe de prioridade e o comportamento do processo iniciado.</span><span class="sxs-lookup"><span data-stu-id="ad077-116">[in] A bitwise combination of the [Win32 Process Creation Flags](/windows/win32/procthread/process-creation-flags) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="ad077-117">no Ponteiro para um bloco de ambiente para o novo processo.</span><span class="sxs-lookup"><span data-stu-id="ad077-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="ad077-118">no Ponteiro para uma cadeia de caracteres terminada em nulo que especifica o caminho completo para o diretório atual para o processo.</span><span class="sxs-lookup"><span data-stu-id="ad077-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="ad077-119">Se esse parâmetro for nulo, o novo processo terá a mesma unidade e diretório atuais que o processo de chamada.</span><span class="sxs-lookup"><span data-stu-id="ad077-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="ad077-120">no Ponteiro para uma `STARTUPINFOW` estrutura Win32 que especifica a estação da janela, a área de trabalho, os identificadores padrão e a aparência da janela principal para o processo iniciado.</span><span class="sxs-lookup"><span data-stu-id="ad077-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="ad077-121">no Ponteiro para uma `PROCESS_INFORMATION` estrutura Win32 que especifica as informações de identificação sobre o processo a ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="ad077-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="ad077-122">no Um valor da Enumeração CorDebugCreateProcessFlags que especifica as opções de depuração.</span><span class="sxs-lookup"><span data-stu-id="ad077-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="ad077-123">fora Um ponteiro para o endereço de um objeto ICorDebugProcess que representa o processo.</span><span class="sxs-lookup"><span data-stu-id="ad077-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad077-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="ad077-124">Remarks</span></span>  

 <span data-ttu-id="ad077-125">Os parâmetros desse método são os mesmos que os do `CreateProcess` método Win32.</span><span class="sxs-lookup"><span data-stu-id="ad077-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="ad077-126">Para habilitar a depuração de modo misto não gerenciado, defina `dwCreationFlags` como DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="ad077-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="ad077-127">Se você quiser usar apenas a depuração gerenciada, não defina esses sinalizadores.</span><span class="sxs-lookup"><span data-stu-id="ad077-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="ad077-128">Se o depurador e o processo a serem depurados (o processo anexado) compartilharem um único console e se a depuração de interoperabilidade for usada, é possível que o processo anexado Mantenha os bloqueios do console e pare em um evento de depuração.</span><span class="sxs-lookup"><span data-stu-id="ad077-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="ad077-129">O depurador bloqueará qualquer tentativa de usar o console.</span><span class="sxs-lookup"><span data-stu-id="ad077-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="ad077-130">Para evitar esse problema, defina o sinalizador CREATE_NEW_CONSOLE no `dwCreationFlags` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="ad077-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="ad077-131">Não há suporte para depuração de interoperabilidade em plataformas Win9x e não x86, como plataformas baseadas em IA-64 e AMD64.</span><span class="sxs-lookup"><span data-stu-id="ad077-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad077-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad077-132">Requirements</span></span>  

 <span data-ttu-id="ad077-133">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad077-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad077-134">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad077-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad077-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad077-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad077-136">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad077-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad077-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="ad077-137">See also</span></span>

- [<span data-ttu-id="ad077-138">Interface ICorDebug</span><span class="sxs-lookup"><span data-stu-id="ad077-138">ICorDebug Interface</span></span>](icordebug-interface.md)
