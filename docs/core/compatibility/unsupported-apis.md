---
title: APIs sem suporte no .NET Core e no .NET 5 +
titleSuffix: ''
description: Saiba quais APIs do .NET sempre geram uma exceção no .NET Core e no .NET 5,0 e versões posteriores.
ms.date: 10/13/2020
ms.openlocfilehash: 1bd41192d0d6752d2b659da9fb6387dac321b2c3
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593260"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="ba1f8-103">APIs que sempre lançam exceções no .NET Core e no .NET 5 +</span><span class="sxs-lookup"><span data-stu-id="ba1f8-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="ba1f8-104">As APIs a seguir sempre lançarão um <xref:System.PlatformNotSupportedException> no .net 5,0 e em versões posteriores (incluindo todas as versões do .NET Core) em todos os ou em um subconjunto de plataformas.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="ba1f8-105">Este artigo organiza as APIs afetadas por namespace.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ba1f8-106">Este artigo é um trabalho em andamento.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-106">This article is a work-in-progress.</span></span> <span data-ttu-id="ba1f8-107">Não é uma lista completa de APIs que lançam exceções no .NET 5 +.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="ba1f8-108">Este artigo não inclui as implementações de interface explícitas para serialização binária que lançam no .NET 5 +.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="ba1f8-109">Para obter mais informações, consulte [serialização binária no .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="ba1f8-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="ba1f8-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="ba1f8-110">System</span></span>

| <span data-ttu-id="ba1f8-111">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-111">Member</span></span> | <span data-ttu-id="ba1f8-112">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-113">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-114">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-115">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-116">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-117">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-118">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-119">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-120">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-121">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-122">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="ba1f8-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="ba1f8-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="ba1f8-124">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-124">Member</span></span> | <span data-ttu-id="ba1f8-125">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-126">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-127">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-128">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="ba1f8-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="ba1f8-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="ba1f8-130">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-130">Member</span></span> | <span data-ttu-id="ba1f8-131">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-132">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-133">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-134">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="ba1f8-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="ba1f8-135">System.Configuration</span></span>

| <span data-ttu-id="ba1f8-136">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-136">Member</span></span> | <span data-ttu-id="ba1f8-137">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="ba1f8-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (todos os membros)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="ba1f8-139">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="ba1f8-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="ba1f8-140">System.Console</span></span>

| <span data-ttu-id="ba1f8-141">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-141">Member</span></span> | <span data-ttu-id="ba1f8-142">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-143">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-143">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-145">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-145">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-147">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-147">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-149">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-149">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (somente Get)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="ba1f8-151">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-152">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-153">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-154">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-154">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-155"><xref:System.Console.Title?displayProperty=nameWithType> (somente Get)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="ba1f8-156">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-156">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-158">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-158">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-160">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-160">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-162">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-162">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-164">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="ba1f8-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="ba1f8-165">System.Data.Common</span></span>

| <span data-ttu-id="ba1f8-166">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-166">Member</span></span> | <span data-ttu-id="ba1f8-167">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="ba1f8-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (gera <xref:System.NotSupportedException> )</span><span class="sxs-lookup"><span data-stu-id="ba1f8-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="ba1f8-169">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="ba1f8-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="ba1f8-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="ba1f8-171">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-171">Member</span></span> | <span data-ttu-id="ba1f8-172">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="ba1f8-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-174">Linux</span><span class="sxs-lookup"><span data-stu-id="ba1f8-174">Linux</span></span> |
| <span data-ttu-id="ba1f8-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-176">Linux</span><span class="sxs-lookup"><span data-stu-id="ba1f8-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-177">macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-178">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-179">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-180">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-181">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-182">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-183">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-183">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-184">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-184">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-185"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-185"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-186">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-186">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-187"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (somente Get)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-187"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="ba1f8-188">macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-188">macOS</span></span> |
| <span data-ttu-id="ba1f8-189"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-189"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-190">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-190">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="ba1f8-191">System.IO</span><span class="sxs-lookup"><span data-stu-id="ba1f8-191">System.IO</span></span>

| <span data-ttu-id="ba1f8-192">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-192">Member</span></span> | <span data-ttu-id="ba1f8-193">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-193">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-194">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-194">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-195">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-195">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="ba1f8-196">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="ba1f8-196">System.IO.Pipes</span></span>

| <span data-ttu-id="ba1f8-197">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-197">Member</span></span> | <span data-ttu-id="ba1f8-198">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-198">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-199">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-200">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-201">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-201">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-202">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-202">Linux and macOS</span></span> |
| <span data-ttu-id="ba1f8-203"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-203"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-204">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-204">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-205">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-205">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="ba1f8-206">System. Media</span><span class="sxs-lookup"><span data-stu-id="ba1f8-206">System.Media</span></span>

| <span data-ttu-id="ba1f8-207">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-207">Member</span></span> | <span data-ttu-id="ba1f8-208">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-208">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-209">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-209">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="ba1f8-210">System.Net</span><span class="sxs-lookup"><span data-stu-id="ba1f8-210">System.Net</span></span>

| <span data-ttu-id="ba1f8-211">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-211">Member</span></span> | <span data-ttu-id="ba1f8-212">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-212">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-213">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-213">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-214">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-214">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-215">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-215">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-216">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-216">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-217">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-217">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-218">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-219">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-219">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-220">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-221">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-221">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-222">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-222">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-223">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-223">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-224">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-224">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-225">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-225">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-226">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-226">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-227">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-227">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-228">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-228">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-229">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-229">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="ba1f8-230">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="ba1f8-230">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="ba1f8-231">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-231">Member</span></span> | <span data-ttu-id="ba1f8-232">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-232">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-233">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-233">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="ba1f8-234">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="ba1f8-234">System.Net.Sockets</span></span>

| <span data-ttu-id="ba1f8-235">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-235">Member</span></span> | <span data-ttu-id="ba1f8-236">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-236">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="ba1f8-237">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-237">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-238">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-238">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="ba1f8-239">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="ba1f8-239">System.Net.WebSockets</span></span>

| <span data-ttu-id="ba1f8-240">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-240">Member</span></span> | <span data-ttu-id="ba1f8-241">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-241">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-242">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-242">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="ba1f8-243">{1&gt;System.Reflection&lt;1}</span><span class="sxs-lookup"><span data-stu-id="ba1f8-243">System.Reflection</span></span>

| <span data-ttu-id="ba1f8-244">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-244">Member</span></span> | <span data-ttu-id="ba1f8-245">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-245">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-246">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-246">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-247">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-248">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-248">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-249">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="ba1f8-250">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-251">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-251">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-252">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-252">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="ba1f8-253">{1&gt;{2&gt;System.Runtime.CompilerServices&lt;2}&lt;1}</span><span class="sxs-lookup"><span data-stu-id="ba1f8-253">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="ba1f8-254">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-254">Member</span></span> | <span data-ttu-id="ba1f8-255">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-255">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-256">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-256">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="ba1f8-257">{1&gt;{2&gt;System.Runtime.InteropServices&lt;2}&lt;1}</span><span class="sxs-lookup"><span data-stu-id="ba1f8-257">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="ba1f8-258">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-258">Member</span></span> | <span data-ttu-id="ba1f8-259">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-259">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-260">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-261">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-262">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-262">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-263">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-263">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-264">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-265">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-265">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-266">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-266">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="ba1f8-267">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="ba1f8-267">System.Runtime.Serialization</span></span>

| <span data-ttu-id="ba1f8-268">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-268">Member</span></span> | <span data-ttu-id="ba1f8-269">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-269">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-270">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-270">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="ba1f8-271">System.Security</span><span class="sxs-lookup"><span data-stu-id="ba1f8-271">System.Security</span></span>

| <span data-ttu-id="ba1f8-272">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-272">Member</span></span> | <span data-ttu-id="ba1f8-273">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-273">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-274">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-274">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-275">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-275">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-276">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-276">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-277">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-277">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-278">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-278">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-279">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-279">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-280">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-280">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-281">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-282">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-282">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-283">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-283">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-284">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-284">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-285">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-286">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-286">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-287">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-287">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="ba1f8-288">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="ba1f8-288">System.Security.Claims</span></span>

| <span data-ttu-id="ba1f8-289">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-289">Member</span></span> | <span data-ttu-id="ba1f8-290">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-290">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-291">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-292">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="ba1f8-293">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-294">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-294">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-295">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-295">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="ba1f8-296">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="ba1f8-296">System.Security.Cryptography</span></span>

| <span data-ttu-id="ba1f8-297">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-297">Member</span></span> | <span data-ttu-id="ba1f8-298">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-298">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-299">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-299">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="ba1f8-300">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-301">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-302">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-303">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-304">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-305">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-306">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-307">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-308">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-309">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-310">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-311">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-312">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-312">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-313">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-314">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-315">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-316">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-317">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-317">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-318">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-319">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-319">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-320">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-320">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-321">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-322">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="ba1f8-322">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-323">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-323">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-324">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-325">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-325">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-326">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-326">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="ba1f8-327">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="ba1f8-327">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="ba1f8-328">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-328">Member</span></span> | <span data-ttu-id="ba1f8-329">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-329">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="ba1f8-330">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-331">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="ba1f8-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="ba1f8-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="ba1f8-333">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-333">Member</span></span> | <span data-ttu-id="ba1f8-334">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-335">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-336">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-337">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-337">All</span></span> |
| <span data-ttu-id="ba1f8-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (definir somente)</span><span class="sxs-lookup"><span data-stu-id="ba1f8-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="ba1f8-339">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="ba1f8-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="ba1f8-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="ba1f8-341">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-341">Member</span></span> | <span data-ttu-id="ba1f8-342">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-343">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="ba1f8-344">System. Security. Policy</span><span class="sxs-lookup"><span data-stu-id="ba1f8-344">System.Security.Policy</span></span>

| <span data-ttu-id="ba1f8-345">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-345">Member</span></span> | <span data-ttu-id="ba1f8-346">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-347">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="ba1f8-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="ba1f8-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="ba1f8-349">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-349">Member</span></span> | <span data-ttu-id="ba1f8-350">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="ba1f8-351">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="ba1f8-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="ba1f8-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="ba1f8-353">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-353">Member</span></span> | <span data-ttu-id="ba1f8-354">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-355">Tudo</span><span class="sxs-lookup"><span data-stu-id="ba1f8-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="ba1f8-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="ba1f8-356">System.Threading</span></span>

| <span data-ttu-id="ba1f8-357">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-357">Member</span></span> | <span data-ttu-id="ba1f8-358">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-359">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-360">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-361">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-362">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-363">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-364">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="ba1f8-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="ba1f8-365">System.Xml</span></span>

| <span data-ttu-id="ba1f8-366">Membro</span><span class="sxs-lookup"><span data-stu-id="ba1f8-366">Member</span></span> | <span data-ttu-id="ba1f8-367">Plataformas que lançam</span><span class="sxs-lookup"><span data-stu-id="ba1f8-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-368">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-369">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="ba1f8-370">Todos</span><span class="sxs-lookup"><span data-stu-id="ba1f8-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="ba1f8-371">Confira também</span><span class="sxs-lookup"><span data-stu-id="ba1f8-371">See also</span></span>

- [<span data-ttu-id="ba1f8-372">Alterações recentes de migração do .NET Framework para o .NET Core</span><span class="sxs-lookup"><span data-stu-id="ba1f8-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="ba1f8-373">Serialização binária no .NET Core</span><span class="sxs-lookup"><span data-stu-id="ba1f8-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="ba1f8-374">Analisador de portabilidade .NET</span><span class="sxs-lookup"><span data-stu-id="ba1f8-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
