---
title: "Altre modalità di installazione e configurazione di Azure PowerShell | Microsoft Docs"
description: Come installare Azure PowerShell usando il pacchetto MSI o l'Installazione guidata piattaforma Web.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.openlocfilehash: 9cee582f74b7f3260c6ae167a8ac358d360ad8ab
ms.sourcegitcommit: 45587b5091293288e16cfae8ac412e0d42f8f450
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2017
---
# <a name="other-installation-methods"></a><span data-ttu-id="1f333-103">Altri metodi di installazione</span><span class="sxs-lookup"><span data-stu-id="1f333-103">Other installation methods</span></span>

<span data-ttu-id="1f333-104">Per Azure PowerShell sono disponibili più metodi di installazione.</span><span class="sxs-lookup"><span data-stu-id="1f333-104">Azure PowerShell has multiple installation methods.</span></span> <span data-ttu-id="1f333-105">L'uso di PowerShellGet con PowerShell Gallery è il metodo preferito.</span><span class="sxs-lookup"><span data-stu-id="1f333-105">Using PowerShellGet with the PowerShell Gallery is the preferred method.</span></span> <span data-ttu-id="1f333-106">Azure PowerShell può essere installato usando l'Installazione guidata piattaforma Web (WebPI) o il file MSI disponibile su [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="1f333-106">Azure PowerShell can be installed using the Web Platform Installer (WebPI) or by using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span>

## <a name="docker"></a><span data-ttu-id="1f333-107">Docker</span><span class="sxs-lookup"><span data-stu-id="1f333-107">Docker</span></span>

<span data-ttu-id="1f333-108">È disponibile un'immagine Docker preconfigurata con Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f333-108">We maintain a Docker image preconfigured with Azure PowerShell.</span></span>

<span data-ttu-id="1f333-109">Eseguire il contenitore con `docker run`.</span><span class="sxs-lookup"><span data-stu-id="1f333-109">Run the container with `docker run`.</span></span>

```powershell
docker run azuresdk/azure-powershell
```

<span data-ttu-id="1f333-110">È inoltre disponibile un subset di cmdlet come contenitore di PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="1f333-110">In addition, we maintain a subset of cmdlets as a PowerShell Core container.</span></span>

<span data-ttu-id="1f333-111">Per Mac/Linux, usare l'immagine `latest`.</span><span class="sxs-lookup"><span data-stu-id="1f333-111">For Mac/Linux, use the `latest` image.</span></span>

```bash
docker run azuresdk/azure-powershell-core:latest
```

<span data-ttu-id="1f333-112">Per Windows, usare l'immagine `nanoserver`.</span><span class="sxs-lookup"><span data-stu-id="1f333-112">For Windows, use the `nanoserver` image.</span></span>

```powershell
docker run azuresdk/azure-powershell-core:nanoserver
```

<span data-ttu-id="1f333-113">Azure PowerShell è installato nell'immagine tramite `Install-Module` da [PowerShell Gallery](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="1f333-113">Azure PowerShell is installed on the image via `Install-Module` from the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>

## <a name="install-using-the-web-platform-installer"></a><span data-ttu-id="1f333-114">Installazione tramite l'Installazione guidata piattaforma Web</span><span class="sxs-lookup"><span data-stu-id="1f333-114">Install using the Web Platform Installer</span></span>

<span data-ttu-id="1f333-115">L'installazione della versione più recente di Azure PowerShell dall'Installazione guidata piattaforma Web è uguale a quella per le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="1f333-115">Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.</span></span>
<span data-ttu-id="1f333-116">Scaricare il [pacchetto per l'Installazione guidata piattaforma Web di Azure PowerShell](http://aka.ms/webpi-azps) e avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1f333-116">Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install.</span></span>

> [!NOTE]
> <span data-ttu-id="1f333-117">Se sono stati installati precedentemente moduli Azure da PowerShell Gallery, il programma di installazione li rimuoverà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1f333-117">If you have previously installed Azure modules from the PowerShell Gallery, the installer automatically removes them.</span></span> <span data-ttu-id="1f333-118">Ciò semplifica l'ambiente, garantendo l'installazione di una sola versione di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f333-118">This simplifies your environment by ensuring that only one version of Azure PowerShell is installed.</span></span> <span data-ttu-id="1f333-119">Tuttavia, esistono scenari in cui sono necessarie più versioni installate nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="1f333-119">However, there are scenarios where you may need multiple versions installed at the same time.</span></span>
>
> <span data-ttu-id="1f333-120">I moduli di PowerShell Gallery consentono di installare i moduli in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="1f333-120">PowerShell Gallery modules install modules in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="1f333-121">Al contrario, il programma di Installazione guidata piattaforma Web installerà i moduli di Azure in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span><span class="sxs-lookup"><span data-stu-id="1f333-121">In contrast, the WebPI installer installs the Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span></span>
>
> <span data-ttu-id="1f333-122">Se si verifica un errore durante l'installazione, è possibile rimuovere manualmente le cartelle di Azure* nella cartella `$env:ProgramFiles\WindowsPowerShell\Modules` e ripetere l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1f333-122">If an error occurs during install, you can manually remove the Azure* folders in your `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.</span></span>

<span data-ttu-id="1f333-123">Al termine dell'installazione, l'impostazione `$env:PSModulePath` includerà le directory contenenti i cmdlet di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f333-123">Once the installation completes, your `$env:PSModulePath` setting should include the directories containing the Azure PowerShell cmdlets.</span></span> <span data-ttu-id="1f333-124">È possibile usare il comando seguente per verificare che Azure PowerShell sia installato correttamente.</span><span class="sxs-lookup"><span data-stu-id="1f333-124">The following command can be used to verify that the Azure PowerShell is installed properly.</span></span>

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> <span data-ttu-id="1f333-125">Durante l'uso dell'Installazione guidata piattaforma Web è possibile che si verifichi un problema noto.</span><span class="sxs-lookup"><span data-stu-id="1f333-125">There is a known issue that can occur when installing from WebPI.</span></span> <span data-ttu-id="1f333-126">Se il computer richiede il riavvio a causa di aggiornamenti di sistema o di altre installazioni, gli aggiornamenti di `$env:PSModulePath` potrebbero non includere il percorso in cui è installato Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f333-126">If your computer requires a restart due to system updates or other installations, it may cause updates to `$env:PSModulePath` to fail to include the path where Azure PowerShell is installed.</span></span>

<span data-ttu-id="1f333-127">Quando si tenta di caricare o eseguire i cmdlet dopo l'installazione, è possibile ricevere il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="1f333-127">When attempting to load or execute cmdlets after installation, you can receive the following error message:</span></span>

```
PS C:\> Login-AzureRmAccount
Login-AzureRmAccount : The term 'Login-AzureRmAccount' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Login-AzureRmAccount
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Login-AzureRmAccount:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="1f333-128">Questo errore può essere corretto riavviando il computer o importando il modulo usando il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="1f333-128">This error can be corrected by restarting the machine or importing the module using the fully qualified path.</span></span> <span data-ttu-id="1f333-129">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1f333-129">For example:</span></span>

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <a name="install-using-the-msi-package"></a><span data-ttu-id="1f333-130">Installazione tramite il pacchetto MSI</span><span class="sxs-lookup"><span data-stu-id="1f333-130">Install using the MSI Package</span></span>

<span data-ttu-id="1f333-131">Azure PowerShell può essere installato usando il file MSI disponibile su [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="1f333-131">Azure PowerShell can be installed using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span> <span data-ttu-id="1f333-132">Se sono state installate versioni precedenti dei moduli di Azure, il programma di installazione le rimuove automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1f333-132">If you have installed previous versions of Azure modules, the installer automatically removes them.</span></span> <span data-ttu-id="1f333-133">Il pacchetto MSI consente di installare i moduli in `$env:ProgramFiles\WindowsPowerShell\Modules`, ma non crea cartelle specifiche per la versione.</span><span class="sxs-lookup"><span data-stu-id="1f333-133">The MSI package installs modules in `$env:ProgramFiles\WindowsPowerShell\Modules` but does not create version-specific folders.</span></span>
