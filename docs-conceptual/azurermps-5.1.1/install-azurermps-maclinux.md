---
title: Installare e configurare Azure PowerShell in macOS e Linux | Microsoft Docs
description: Come installare e configurare Azure PowerShell per il primo uso in macOS e Linux.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.openlocfilehash: 94b39c18acaca7a4b17b5207feed025442665acc
ms.sourcegitcommit: c42c7176276ec4e1cc3360a93e6b15d32083bf9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2017
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a><span data-ttu-id="b8e2d-103">Installare e configurare Azure PowerShell in macOS e Linux</span><span class="sxs-lookup"><span data-stu-id="b8e2d-103">Install and configure Azure PowerShell on macOS and Linux</span></span>

<span data-ttu-id="b8e2d-104">È ora possibile installare PowerShell 6 (beta) e Azure PowerShell in piattaforme non Windows.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-104">It is now possible to install PowerShell 6 (beta) and Azure PowerShell on non-Windows platforms.</span></span>
<span data-ttu-id="b8e2d-105">Il processo di installazione di Azure PowerShell in macOS e Linux non è così tanto diverso da quello per Windows, tuttavia, è prima necessario installare PowerShell 6 (beta).</span><span class="sxs-lookup"><span data-stu-id="b8e2d-105">The process of installing Azure PowerShell on macOS and Linux is not that different from Windows, however, you must first install PowerShell 6 (beta).</span></span>

> [!NOTE]

> <span data-ttu-id="b8e2d-106">Al momento, sia PowerShell 6 (beta) che Azure PowerShell per .NET Core sono ancora in versione beta.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-106">At this time, both PowerShell 6 (beta) and Azure PowerShell for .NET Core are still in beta.</span></span>
> <span data-ttu-id="b8e2d-107">Il supporto per questi prodotti è limitato.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-107">Support for these products is limited.</span></span> <span data-ttu-id="b8e2d-108">Se si verificano problemi o si trovano bug, registrare i problemi in GitHub.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-108">If you have problems or discover bugs, please file Issues in GitHub.</span></span>
>
> * [<span data-ttu-id="b8e2d-109">Problemi per PowerShell 6 (beta)</span><span class="sxs-lookup"><span data-stu-id="b8e2d-109">Issues for PowerShell 6 (beta)</span></span>](https://github.com/PowerShell/PowerShell/issues)
> * [<span data-ttu-id="b8e2d-110">Problemi per Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8e2d-110">Issues for Azure PowerShell</span></span>](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a><span data-ttu-id="b8e2d-111">Passaggio 1: installare PowerShell 6 (beta)</span><span class="sxs-lookup"><span data-stu-id="b8e2d-111">Step 1: Install PowerShell 6 (beta)</span></span>

<span data-ttu-id="b8e2d-112">Il processo di installazione di PowerShell 6 (beta) varia a seconda del sistema operativo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-112">The process of installing PowerShell 6 (beta) on varies depending on the target operating system.</span></span>
<span data-ttu-id="b8e2d-113">Sebbene sia possibile installare PowerShell 6 (beta) in Windows, questo articolo è incentrato su macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-113">While it is possible to install PowerShell 6 (beta) on Windows, this article focuses on macOS and Linux.</span></span> <span data-ttu-id="b8e2d-114">Se si intende usare Azure PowerShell in Windows, vedere l'articolo dedicato all'[installazione](./install-azurerm-ps.md) per Windows.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-114">If you want to use Azure PowerShell on Windows, see the [install](./install-azurerm-ps.md) article for Windows.</span></span>

<span data-ttu-id="b8e2d-115">Per installare **PowerShell 6** (beta) in ambiente Linux o macOS, è necessario:</span><span class="sxs-lookup"><span data-stu-id="b8e2d-115">To install **PowerShell 6** (beta) on Linux or macOS, you need to:</span></span>

1. <span data-ttu-id="b8e2d-116">Ottenere PowerShell per il sistema operativo e la versione specifici da [GitHub](https://github.com/powershell/powershell#get-powershell)</span><span class="sxs-lookup"><span data-stu-id="b8e2d-116">Get PowerShell for the specific OS and version, from [GitHub](https://github.com/powershell/powershell#get-powershell)</span></span>
2. <span data-ttu-id="b8e2d-117">Seguire le istruzioni di installazione</span><span class="sxs-lookup"><span data-stu-id="b8e2d-117">Follow the installation instructions</span></span>
   - [<span data-ttu-id="b8e2d-118">Linux</span><span class="sxs-lookup"><span data-stu-id="b8e2d-118">Linux</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [<span data-ttu-id="b8e2d-119">macOS</span><span class="sxs-lookup"><span data-stu-id="b8e2d-119">macOS</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a><span data-ttu-id="b8e2d-120">Passaggio 2: installare Azure PowerShell per .NET Core</span><span class="sxs-lookup"><span data-stu-id="b8e2d-120">Step 2: Install Azure PowerShell for .NET Core</span></span>

<span data-ttu-id="b8e2d-121">PowerShell 6 (beta) viene fornito con il modulo PowerShellGet già installato.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-121">PowerShell 6 (beta) comes with the PowerShellGet module already installed.</span></span> <span data-ttu-id="b8e2d-122">Ciò semplifica l'installazione di qualsiasi modulo pubblicato in PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-122">This makes it easy to install any module that is published to the PowerShell Gallery.</span></span> <span data-ttu-id="b8e2d-123">Per installare Azure PowerShell, aprire una nuova sessione di PowerShell ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b8e2d-123">To install Azure PowerShell, open a new PowerShell session and run the following command:</span></span>

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a><span data-ttu-id="b8e2d-124">Passaggio 3: caricare il modulo AzureRM.Netcore</span><span class="sxs-lookup"><span data-stu-id="b8e2d-124">Step 3: Load the AzureRM.Netcore module</span></span>

<span data-ttu-id="b8e2d-125">Dopo aver installato il modulo, è necessario caricarlo nella sessione di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-125">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="b8e2d-126">I moduli vengono caricati usando il cmdlet `Import-Module`, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b8e2d-126">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM.Netcore
```

<span data-ttu-id="b8e2d-127">Al termine dell'importazione, è possibile testare il modulo appena installato eseguendo un tentativo di accesso ad Azure con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b8e2d-127">After the import completes, you can test your newly installed and module by attempting to sign into Azure using the following command:</span></span>

```powershell
Login-AzureRMAccount
```

<span data-ttu-id="b8e2d-128">Il comando riportato sopra richiede di passare a `https://aka.ms/devicelogin` e immettere il codice fornito.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-128">The above command should prompt you to go to `https://aka.ms/devicelogin` and enter the provided code.</span></span>

## <a name="available-cmdlets"></a><span data-ttu-id="b8e2d-129">Cmdlet disponibili</span><span class="sxs-lookup"><span data-stu-id="b8e2d-129">Available cmdlets</span></span>

<span data-ttu-id="b8e2d-130">I moduli di Azure PowerShell per .NET Standard sono ancora in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-130">The Azure PowerShell modules for .NET Standard are still in development.</span></span> <span data-ttu-id="b8e2d-131">Questi moduli non offrono il set completo di cmdlet disponibili per la versione Windows dei moduli.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-131">These modules do not provide the full set of cmdlets that are available for the Windows version of the modules.</span></span> <span data-ttu-id="b8e2d-132">Le funzioni seguenti sono implementate nei moduli AzureRM.Netcore:</span><span class="sxs-lookup"><span data-stu-id="b8e2d-132">The following functions are implemented in AzureRM.Netcore modules:</span></span>

* <span data-ttu-id="b8e2d-133">Account Management</span><span class="sxs-lookup"><span data-stu-id="b8e2d-133">Account management</span></span>
  - <span data-ttu-id="b8e2d-134">Accesso con account Microsoft, account dell'organizzazione o entità servizio tramite Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b8e2d-134">Login with Microsoft account, Organizational account, or Service Principal through Microsoft Azure Active Directory</span></span>
  - <span data-ttu-id="b8e2d-135">Salvataggio delle credenziali su disco con Save-AzureRmContext e caricamento delle credenziali salvate con Import-AzureRmContext</span><span class="sxs-lookup"><span data-stu-id="b8e2d-135">Save Credentials to disk with Save-AzureRmContext and load saved credentials using Import-AzureRmContext</span></span>
* <span data-ttu-id="b8e2d-136">Environment</span><span class="sxs-lookup"><span data-stu-id="b8e2d-136">Environment</span></span>
  - <span data-ttu-id="b8e2d-137">Recupero di ambienti predefiniti di Microsoft Azure diversi</span><span class="sxs-lookup"><span data-stu-id="b8e2d-137">Get the different out-of-box Microsoft Azure environments</span></span>
  - <span data-ttu-id="b8e2d-138">Aggiunta/impostazione/rimozione di ambienti personalizzati, come gli ambienti Azure Stack o Windows Azure Pack</span><span class="sxs-lookup"><span data-stu-id="b8e2d-138">Add/Set/Remove customized environments (like your Azure Stack or Windows Azure Pack environments)</span></span>
* <span data-ttu-id="b8e2d-139">Cmdlet del piano di gestione per i servizi di Azure tramite le interfacce di Resource Manager e di gestione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="b8e2d-139">Management plane cmdlets for Azure services using Resource Manager and Service Management interfaces.</span></span>
  - <span data-ttu-id="b8e2d-140">Macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="b8e2d-140">Virtual Machine</span></span>
  - <span data-ttu-id="b8e2d-141">Servizio app (siti Web)</span><span class="sxs-lookup"><span data-stu-id="b8e2d-141">App Service (Websites)</span></span>
  - <span data-ttu-id="b8e2d-142">Database SQL</span><span class="sxs-lookup"><span data-stu-id="b8e2d-142">SQL Database</span></span>
  - <span data-ttu-id="b8e2d-143">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="b8e2d-143">Storage</span></span>
  - <span data-ttu-id="b8e2d-144">Rete</span><span class="sxs-lookup"><span data-stu-id="b8e2d-144">Network</span></span>

## <a name="next-steps"></a><span data-ttu-id="b8e2d-145">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b8e2d-145">Next Steps</span></span>

<span data-ttu-id="b8e2d-146">Per altre informazioni sull'uso di Azure PowerShell, vedere l'articolo [Introduzione ad Azure PowerShell](get-started-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="b8e2d-146">For more information about using Azure PowerShell, see the [Get started with Azure PowerShell](get-started-azureps.md) article.</span></span>
