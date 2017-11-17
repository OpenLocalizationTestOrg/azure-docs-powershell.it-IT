---
title: Log delle modifiche di Azure PowerShell | Microsoft Docs
description: "Questa è una cronologia delle modifiche apportate ad Azure PowerShell nella versione più recente."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-powershell
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 05/18/2017
ms.openlocfilehash: 5fe7591855577e083aad5923aed37b18d0b2a40c
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2017
---
# <a name="release-notes"></a><span data-ttu-id="ba59e-103">Note sulla versione</span><span class="sxs-lookup"><span data-stu-id="ba59e-103">Release notes</span></span>

<span data-ttu-id="ba59e-104">Questo è un elenco delle modifiche apportate ad Azure PowerShell in questa versione.</span><span class="sxs-lookup"><span data-stu-id="ba59e-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <a name="version-129"></a><span data-ttu-id="ba59e-105">Versione 1.2.9</span><span class="sxs-lookup"><span data-stu-id="ba59e-105">Version 1.2.9</span></span>

<span data-ttu-id="ba59e-106">Modifiche di questa versione</span><span class="sxs-lookup"><span data-stu-id="ba59e-106">Changes This Release</span></span>

* <span data-ttu-id="ba59e-107">Modulo AzureRm.AzureStackAdmin</span><span class="sxs-lookup"><span data-stu-id="ba59e-107">AzureRm.AzureStackAdmin Module</span></span>
    + <span data-ttu-id="ba59e-108">Modifiche apportate al cmdlet Add-AzureRmResourceProviderRegistration per il supporto della divisione tra Azure Resource Manager per amministratori e Azure Resource Manager per tenant.</span><span class="sxs-lookup"><span data-stu-id="ba59e-108">Changes in the Add-AzureRmResourceProviderRegistration cmdlet for the support of Admin Azure resource manager and tenant azure resource manager split.</span></span> <span data-ttu-id="ba59e-109">Aggiunta del nuovo parametro -ResourceManagerType.</span><span class="sxs-lookup"><span data-stu-id="ba59e-109">A new parameter -ResourceManagerType has been added.</span></span>
    + <span data-ttu-id="ba59e-110">Rimozione dei parametri -AdminUri, -ApiVersion, -SubscriptionId e -Token da ogni cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ba59e-110">Removal of the parameters -AdminUri, -ApiVersion, -SubscriptionId and -Token from each cmdlets.</span></span> <span data-ttu-id="ba59e-111">Dopo aver emesso avvisi relativi al fatto che questi parametri sarebbero stati deprecati, i parametri sono ora stati rimossi.</span><span class="sxs-lookup"><span data-stu-id="ba59e-111">We have been printing warnings that these parameters will be deprecated and now they got removed.</span></span>
* <span data-ttu-id="ba59e-112">Modulo AzureStackStorage</span><span class="sxs-lookup"><span data-stu-id="ba59e-112">AzureStackStorage module</span></span>
    + <span data-ttu-id="ba59e-113">Aggiunta di nuovi cmdlet per supportare scenari di migrazione dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="ba59e-113">Added new cmdlets to support container migration scenarios.</span></span>
    + <span data-ttu-id="ba59e-114">Rimozione dei cmdlet correlati a componenti interni e funzionalità sottostanti.</span><span class="sxs-lookup"><span data-stu-id="ba59e-114">Removed cmdlets referring to internal components and underlying features.</span></span>
* <span data-ttu-id="ba59e-115">AzureRM.BootStrapper</span><span class="sxs-lookup"><span data-stu-id="ba59e-115">AzureRM.BootStrapper</span></span>
    + <span data-ttu-id="ba59e-116">Creazione del nuovo modulo per gestire le versioni dei cmdlet di Azure PowerShell tramite l'uso dei profili di versione</span><span class="sxs-lookup"><span data-stu-id="ba59e-116">Created new module to manage versions of Azure PowerShell cmdlets through the use of version profiles</span></span>