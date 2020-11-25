---
title: 'Alteração significativa: MVC: ObjectModelValidator chama uma nova sobrecarga de ValidationVisitor. Validate'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 intitulado MVC: ObjectModelValidator chama uma nova sobrecarga de ValidationVisitor. Validate'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b28c357f51291a4f73889d5d413a983f79e09daf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760526"
---
# <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a><span data-ttu-id="1ace8-103">MVC: ObjectModelValidator chama uma nova sobrecarga de ValidationVisitor. Validate</span><span class="sxs-lookup"><span data-stu-id="1ace8-103">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>

<span data-ttu-id="1ace8-104">No ASP.NET Core 5,0, uma sobrecarga do <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="1ace8-104">In ASP.NET Core 5.0, an overload of the <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> was added.</span></span> <span data-ttu-id="1ace8-105">A nova sobrecarga aceita a instância de modelo de nível superior que contém propriedades:</span><span class="sxs-lookup"><span data-stu-id="1ace8-105">The new overload accepts the top-level model instance that contains properties:</span></span>

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<span data-ttu-id="1ace8-106"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invoca essa nova sobrecarga de `ValidationVisitor` para executar a validação.</span><span class="sxs-lookup"><span data-stu-id="1ace8-106"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invokes this new overload of `ValidationVisitor` to perform validation.</span></span> <span data-ttu-id="1ace8-107">Essa nova sobrecarga será pertinente se a sua biblioteca de validação se integrar com o sistema de validação de modelo do MVC ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1ace8-107">This new overload is pertinent if your validation library integrates with ASP.NET Core MVC's model validation system.</span></span>

<span data-ttu-id="1ace8-108">Para obter uma discussão, consulte o problema do GitHub [dotnet/aspnetcore # 26020](https://github.com/dotnet/aspnetcore/issues/26020).</span><span class="sxs-lookup"><span data-stu-id="1ace8-108">For discussion, see GitHub issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="1ace8-109">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="1ace8-109">Version introduced</span></span>

<span data-ttu-id="1ace8-110">5.0</span><span class="sxs-lookup"><span data-stu-id="1ace8-110">5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="1ace8-111">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="1ace8-111">Old behavior</span></span>

<span data-ttu-id="1ace8-112">`ObjectModelValidator` Invoca a seguinte sobrecarga durante a validação do modelo:</span><span class="sxs-lookup"><span data-stu-id="1ace8-112">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

## <a name="new-behavior"></a><span data-ttu-id="1ace8-113">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="1ace8-113">New behavior</span></span>

<span data-ttu-id="1ace8-114">`ObjectModelValidator` Invoca a seguinte sobrecarga durante a validação do modelo:</span><span class="sxs-lookup"><span data-stu-id="1ace8-114">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

## <a name="reason-for-change"></a><span data-ttu-id="1ace8-115">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="1ace8-115">Reason for change</span></span>

<span data-ttu-id="1ace8-116">Essa alteração foi introduzida para dar suporte a validadores, como <xref:System.ComponentModel.DataAnnotations.CompareAttribute> , que dependem da inspeção de outras propriedades.</span><span class="sxs-lookup"><span data-stu-id="1ace8-116">This change was introduced to support validators, such as <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, that rely on inspection of other properties.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="1ace8-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="1ace8-117">Recommended action</span></span>

<span data-ttu-id="1ace8-118">As estruturas de validação que dependem de `ObjectModelValidator` para invocar a sobrecarga existente do `ValidationVisitor` devem substituir o novo método ao direcionar o .NET 5,0 ou posterior:</span><span class="sxs-lookup"><span data-stu-id="1ace8-118">Validation frameworks that rely on `ObjectModelValidator` to invoke the existing overload of `ValidationVisitor` must override the new method when targeting .NET 5.0 or later:</span></span>

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

## <a name="affected-apis"></a><span data-ttu-id="1ace8-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="1ace8-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
