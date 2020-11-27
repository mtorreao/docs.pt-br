---
title: Eventos ETW de segurança
description: Entenda os eventos ETW de segurança, que são gerados durante a verificação de nome forte e a verificação de Authenticode no .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: 4402bf5690a53ce518077268a3e20a95aeb14e8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272508"
---
# <a name="security-etw-events"></a><span data-ttu-id="3774e-103">Eventos ETW de segurança</span><span class="sxs-lookup"><span data-stu-id="3774e-103">Security ETW Events</span></span>

<span data-ttu-id="3774e-104"> Eventos de segurança são gerados durante a verificação de nome forte e a verificação de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="3774e-104">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="3774e-105">Eventos StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="3774e-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  

 <span data-ttu-id="3774e-106">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="3774e-106">The following table shows the keyword and level.</span></span> <span data-ttu-id="3774e-107">(Para obter mais informações, consulte [Palavras-chaves e níveis CLR ETW](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="3774e-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="3774e-108">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3774e-108">Keyword for raising the event</span></span>|<span data-ttu-id="3774e-109">Nível</span><span class="sxs-lookup"><span data-stu-id="3774e-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="3774e-110">`SecurityKeyword`(0x400)</span><span class="sxs-lookup"><span data-stu-id="3774e-110">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="3774e-111">Informativo(4)</span><span class="sxs-lookup"><span data-stu-id="3774e-111">Informational(4)</span></span>|  
  
 <span data-ttu-id="3774e-112">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="3774e-112">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="3774e-113">Evento</span><span class="sxs-lookup"><span data-stu-id="3774e-113">Event</span></span>|<span data-ttu-id="3774e-114">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3774e-114">Event ID</span></span>|<span data-ttu-id="3774e-115">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3774e-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="3774e-116">181</span><span class="sxs-lookup"><span data-stu-id="3774e-116">181</span></span>|<span data-ttu-id="3774e-117">Início da verificação de nome forte.</span><span class="sxs-lookup"><span data-stu-id="3774e-117">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="3774e-118">182</span><span class="sxs-lookup"><span data-stu-id="3774e-118">182</span></span>|<span data-ttu-id="3774e-119">Fim da verificação de nome forte.</span><span class="sxs-lookup"><span data-stu-id="3774e-119">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="3774e-120">A tabela a seguir mostra os dados do evento.</span><span class="sxs-lookup"><span data-stu-id="3774e-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="3774e-121">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3774e-121">Field name</span></span>|<span data-ttu-id="3774e-122">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3774e-122">Data type</span></span>|<span data-ttu-id="3774e-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="3774e-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="3774e-124">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="3774e-124">VerificationFlags</span></span>|<span data-ttu-id="3774e-125">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="3774e-125">win:UInt32</span></span>|<span data-ttu-id="3774e-126">Os sinalizadores de verificação.</span><span class="sxs-lookup"><span data-stu-id="3774e-126">The verification flags.</span></span>|  
|<span data-ttu-id="3774e-127">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="3774e-127">ErrorCode</span></span>|<span data-ttu-id="3774e-128">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="3774e-128">win:UInt32</span></span>|<span data-ttu-id="3774e-129">O código de erro HResult.</span><span class="sxs-lookup"><span data-stu-id="3774e-129">The HResult error code.</span></span>|  
|<span data-ttu-id="3774e-130">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="3774e-130">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="3774e-131">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="3774e-131">win:UnicodeString</span></span>|<span data-ttu-id="3774e-132">O nome totalmente qualificado do assembly.</span><span class="sxs-lookup"><span data-stu-id="3774e-132">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="3774e-133">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="3774e-133">ClrInstanceID</span></span>|<span data-ttu-id="3774e-134">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="3774e-134">win:UInt16</span></span>|<span data-ttu-id="3774e-135">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3774e-135">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="3774e-136">Eventos AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="3774e-136">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  

 <span data-ttu-id="3774e-137">A tabela a seguir mostra a palavra-chave e o nível.</span><span class="sxs-lookup"><span data-stu-id="3774e-137">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="3774e-138">Palavra-chave para acionar o evento</span><span class="sxs-lookup"><span data-stu-id="3774e-138">Keyword for raising the event</span></span>|<span data-ttu-id="3774e-139">Nível</span><span class="sxs-lookup"><span data-stu-id="3774e-139">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="3774e-140">`SecurityKeyword`(0x400)</span><span class="sxs-lookup"><span data-stu-id="3774e-140">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="3774e-141">Informativo(4)</span><span class="sxs-lookup"><span data-stu-id="3774e-141">Informational(4)</span></span>|  
  
 <span data-ttu-id="3774e-142">A tabela a seguir mostra as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="3774e-142">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="3774e-143">Evento</span><span class="sxs-lookup"><span data-stu-id="3774e-143">Event</span></span>|<span data-ttu-id="3774e-144">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3774e-144">Event ID</span></span>|<span data-ttu-id="3774e-145">Acionado quando</span><span class="sxs-lookup"><span data-stu-id="3774e-145">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="3774e-146">183</span><span class="sxs-lookup"><span data-stu-id="3774e-146">183</span></span>|<span data-ttu-id="3774e-147">Início da verificação de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="3774e-147">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="3774e-148">184</span><span class="sxs-lookup"><span data-stu-id="3774e-148">184</span></span>|<span data-ttu-id="3774e-149">Fim da verificação de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="3774e-149">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="3774e-150">A tabela a seguir mostra os dados do evento.</span><span class="sxs-lookup"><span data-stu-id="3774e-150">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="3774e-151">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3774e-151">Field name</span></span>|<span data-ttu-id="3774e-152">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3774e-152">Data type</span></span>|<span data-ttu-id="3774e-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="3774e-153">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="3774e-154">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="3774e-154">VerificationFlags</span></span>|<span data-ttu-id="3774e-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="3774e-155">win:UInt32</span></span>|<span data-ttu-id="3774e-156">Os sinalizadores de verificação.</span><span class="sxs-lookup"><span data-stu-id="3774e-156">The verification flags.</span></span>|  
|<span data-ttu-id="3774e-157">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="3774e-157">ErrorCode</span></span>|<span data-ttu-id="3774e-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="3774e-158">win:UInt32</span></span>|<span data-ttu-id="3774e-159">O código de erro HResult.</span><span class="sxs-lookup"><span data-stu-id="3774e-159">The HResult error code.</span></span>|  
|<span data-ttu-id="3774e-160">ModulePath</span><span class="sxs-lookup"><span data-stu-id="3774e-160">ModulePath</span></span>|<span data-ttu-id="3774e-161">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="3774e-161">win:UnicodeString</span></span>|<span data-ttu-id="3774e-162">O caminho do módulo.</span><span class="sxs-lookup"><span data-stu-id="3774e-162">The module path.</span></span>|  
|<span data-ttu-id="3774e-163">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="3774e-163">ClrInstanceID</span></span>|<span data-ttu-id="3774e-164">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="3774e-164">win:UInt16</span></span>|<span data-ttu-id="3774e-165">ID exclusiva da instância do CLR ou do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3774e-165">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3774e-166">Veja também</span><span class="sxs-lookup"><span data-stu-id="3774e-166">See also</span></span>

- [<span data-ttu-id="3774e-167">Eventos ETW no CLR</span><span class="sxs-lookup"><span data-stu-id="3774e-167">CLR ETW Events</span></span>](clr-etw-events.md)
