---
title: <span data-ttu-id="70f58-101">Installare e configurare il modulo Gestione dei servizi di Azure PowerShell | Documenti di Microsoft</span><span class="sxs-lookup"><span data-stu-id="70f58-101">Install and configure the Azure PowerShell Service Management module | Microsoft Docs</span></span>
description: <span data-ttu-id="70f58-102">Come installare e configurare Azure PowerShell per il primo uso.</span><span class="sxs-lookup"><span data-stu-id="70f58-102">How to install and configure Azure PowerShell for first time use.</span></span>
services: azure
author: sdwheeler
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/06/2017
ms.openlocfilehash: c51c727c1cb022eca59f819c7f24d8e058c677da
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="70f58-103">Installare il modulo Gestione dei servizi di Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="70f58-103">Installing the Azure PowerShell Service Management module</span></span>
<a id="installing-the-azure-powershell-service-management-module" class="xliff"></a>

<span data-ttu-id="70f58-104">L'installazione di Azure PowerShell da [PowerShell Gallery](https://www.powershellgallery.com/) è il metodo preferito di installazione.</span><span class="sxs-lookup"><span data-stu-id="70f58-104">Installing Azure PowerShell from the [PowerShell Gallery](https://www.powershellgallery.com/) is the preferred method of installation.</span></span>

## <span data-ttu-id="70f58-105">Passaggio 1: installare PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="70f58-105">Step 1: Install PowerShellGet</span></span>
<a id="step-1-install-powershellget" class="xliff"></a>

<span data-ttu-id="70f58-106">L'installazione degli elementi da PowerShell Gallery richiede il modulo PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="70f58-106">Installing items from the PowerShell Gallery requires the PowerShellGet module.</span></span> <span data-ttu-id="70f58-107">Assicurarsi di avere la versione appropriata di PowerShellGet e di soddisfare gli altri requisiti di sistema.</span><span class="sxs-lookup"><span data-stu-id="70f58-107">Make sure you have the appropriate version of PowerShellGet and other system requirements.</span></span> <span data-ttu-id="70f58-108">Eseguire il comando seguente per determinare se PowerShellGet è installato nel sistema.</span><span class="sxs-lookup"><span data-stu-id="70f58-108">Run the following command to see if you have PowerShellGet installed on your system.</span></span>

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

<span data-ttu-id="70f58-109">Verrà visualizzata una schermata simile all'output seguente:</span><span class="sxs-lookup"><span data-stu-id="70f58-109">You should see something similar to the following output:</span></span>

```
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

<span data-ttu-id="70f58-110">Se PowerShellGet non è installato, vedere la sezione [Come ottenere PowerShellGet](install-azurerm-ps.md#how-to-get-powershellget).</span><span class="sxs-lookup"><span data-stu-id="70f58-110">If you do not have PowerShellGet installed, see the [How to get PowerShellGet](install-azurerm-ps.md#how-to-get-powershellget).</span></span>

## <span data-ttu-id="70f58-111">Passaggio 2: Installare Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="70f58-111">Step 2: Install Azure PowerShell</span></span>
<a id="step-2-install-azure-powershell" class="xliff"></a>

<span data-ttu-id="70f58-112">Eseguire il comando seguente dalla console di Windows PowerShell come amministratore:</span><span class="sxs-lookup"><span data-stu-id="70f58-112">Run the following command from the Windows PowerShell console running as Administrator:</span></span>

```powershell
Install-Module Azure
```

<span data-ttu-id="70f58-113">Il modulo Azure è un modulo di rollup per i cmdlet di Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="70f58-113">The Azure module is a rollup module for the Azure Resource Manager cmdlets.</span></span> <span data-ttu-id="70f58-114">Durante l'installazione del modulo AzureRM, qualsiasi modulo di Azure non installato precedentemente viene scaricato e installato da PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="70f58-114">When you install the AzureRM module, any other Azure modules that have not previously been installed will be downloaded and installed from the PowerShell Gallery.</span></span>

<span data-ttu-id="70f58-115">Il modulo di Gestione dei servizi di Azure condivide le dipendenze con i moduli di Gestione risorse di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70f58-115">The Azure Service Management module shares dependencies with the Azure PowerShell Resource Manager modules.</span></span> <span data-ttu-id="70f58-116">Se sono stati installati i moduli di Gestione risorse di Azure PowerShell, sarà necessario aggiungere il parametro `-AllowClobber` al comando di installazione.</span><span class="sxs-lookup"><span data-stu-id="70f58-116">If you have installed the Azure PowerShell Resource Manager modules, you will need to add the `-AllowClobber` parameter to the install command.</span></span> <span data-ttu-id="70f58-117">In questo modo le dipendenze condivise esistenti verranno aggiornate.</span><span class="sxs-lookup"><span data-stu-id="70f58-117">This allows this existing shared dependencies to be updated.</span></span> <span data-ttu-id="70f58-118">Senza questo parametro, si verifica un errore di installazione del modulo.</span><span class="sxs-lookup"><span data-stu-id="70f58-118">Without this parameter, installation of the module fails.</span></span>

```powershell
Install-Module Azure -AllowClobber
```

<span data-ttu-id="70f58-119">Dopo aver installato il modulo, è possibile importarlo eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="70f58-119">After you install this module, you can import the module by running the following command:</span></span>

```powershell
Import-Module Azure
```

## <span data-ttu-id="70f58-120">Usare i cmdlet</span><span class="sxs-lookup"><span data-stu-id="70f58-120">To use the cmdlets</span></span>
<a id="to-use-the-cmdlets" class="xliff"></a>

<span data-ttu-id="70f58-121">Per iniziare a lavorare con i cmdlet di Gestione dei servizi di Azure, accedere al proprio account Azure.</span><span class="sxs-lookup"><span data-stu-id="70f58-121">To start working with the Azure Service Management cmdlets, first log on to your Azure account.</span></span> <span data-ttu-id="70f58-122">Per accedere al proprio account, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="70f58-122">To log on to your account, run the following command:</span></span>

```powershell
Add-AzureAccount
```

<span data-ttu-id="70f58-123">Dopo l'accesso ad Azure, Azure PowerShell crea un contesto per la sessione specificata.</span><span class="sxs-lookup"><span data-stu-id="70f58-123">After logging into Azure, Azure PowerShell creates a context for the given session.</span></span> <span data-ttu-id="70f58-124">Tale contesto contiene l'ambiente Azure PowerShell, l'account, il tenant e la sottoscrizione che verranno usati per tutti i cmdlet della sessione.</span><span class="sxs-lookup"><span data-stu-id="70f58-124">That context contains the Azure PowerShell environment, account, tenant, and subscription that will be used for all cmdlets within that session.</span></span> <span data-ttu-id="70f58-125">È ora possibile usare i moduli seguenti.</span><span class="sxs-lookup"><span data-stu-id="70f58-125">Now you are ready to use the modules below.</span></span>

## <span data-ttu-id="70f58-126">Cmdlet di Gestione dei servizi di Azure</span><span class="sxs-lookup"><span data-stu-id="70f58-126">Azure Service Management cmdlets</span></span>
<a id="azure-service-management-cmdlets" class="xliff"></a>

<span data-ttu-id="70f58-127">I moduli di Azure PowerShell vengono aggiornati di frequente.</span><span class="sxs-lookup"><span data-stu-id="70f58-127">Azure PowerShell modules are updated frequently.</span></span> <span data-ttu-id="70f58-128">Se si nota che la guida dei cmdlet online include cmdlet o parametri non presenti nel modulo, scaricare e installare la versione più recente del modulo.</span><span class="sxs-lookup"><span data-stu-id="70f58-128">If you notice that the online cmdlet help includes cmdlets or parameters that are not in your module, download and install the latest version of the module.</span></span> <span data-ttu-id="70f58-129">Per conoscere la versione del modulo, digitare: `(Get-Module Azure).Version`.</span><span class="sxs-lookup"><span data-stu-id="70f58-129">To find the version of your module, type: `(Get-Module Azure).Version`.</span></span>

<span data-ttu-id="70f58-130">Per gli script di esempio che consentono di automatizzare alcune delle attività comuni in Azure, vedere lo [Script Center di Windows Azure](http://www.windowsazure.com/documentation/scripts/).</span><span class="sxs-lookup"><span data-stu-id="70f58-130">For sample scripts that can help you automate some of the common tasks in Azure, see the [Windows Azure Script Center](http://www.windowsazure.com/documentation/scripts/).</span></span>

<span data-ttu-id="70f58-131">Per informazioni generali sull'installazione, la formazione, l'uso e la personalizzazione di Windows PowerShell, vedere [Scripting con Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).</span><span class="sxs-lookup"><span data-stu-id="70f58-131">For general information about installing, learning, using, and customizing Windows PowerShell, see [Scripting with Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).</span></span>