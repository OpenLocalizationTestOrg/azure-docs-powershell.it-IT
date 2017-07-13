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
ms.openlocfilehash: 368404bcb5218814b4965bb1bcda1e2876441d2a
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="93c52-103">Altri metodi di installazione</span><span class="sxs-lookup"><span data-stu-id="93c52-103">Other installation methods</span></span>
<a id="other-installation-methods" class="xliff"></a>

<span data-ttu-id="93c52-104">Per Azure PowerShell sono disponibili più metodi di installazione.</span><span class="sxs-lookup"><span data-stu-id="93c52-104">Azure PowerShell has multiple installation methods.</span></span> <span data-ttu-id="93c52-105">L'uso di PowerShellGet con PowerShell Gallery è il metodo preferito.</span><span class="sxs-lookup"><span data-stu-id="93c52-105">Using PowerShellGet with the PowerShell Gallery is the preferred method.</span></span> <span data-ttu-id="93c52-106">Azure PowerShell può essere installato usando l'Installazione guidata piattaforma Web (WebPI) o il file MSI disponibile su [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="93c52-106">Azure PowerShell can be installed using the Web Platform Installer (WebPI) or by using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span>

## <span data-ttu-id="93c52-107">Installazione tramite l'Installazione guidata piattaforma Web</span><span class="sxs-lookup"><span data-stu-id="93c52-107">Install using the Web Platform Installer</span></span>
<a id="install-using-the-web-platform-installer" class="xliff"></a>

<span data-ttu-id="93c52-108">L'installazione della versione più recente di Azure PowerShell dall'Installazione guidata piattaforma Web è uguale a quella per le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="93c52-108">Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.</span></span>
<span data-ttu-id="93c52-109">Scaricare il [pacchetto per l'Installazione guidata piattaforma Web di Azure PowerShell](http://aka.ms/webpi-azps) e avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="93c52-109">Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install.</span></span>

> [!NOTE]
> <span data-ttu-id="93c52-110">Se sono stati installati precedentemente moduli Azure da PowerShell Gallery, il programma di installazione li rimuoverà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="93c52-110">If you have previously installed Azure modules from the PowerShell Gallery, the installer automatically removes them.</span></span> <span data-ttu-id="93c52-111">Ciò semplifica l'ambiente, garantendo l'installazione di una sola versione di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93c52-111">This simplifies your environment by ensuring that only one version of Azure PowerShell is installed.</span></span> <span data-ttu-id="93c52-112">Tuttavia, esistono scenari in cui sono necessarie più versioni installate nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="93c52-112">However, there are scenarios where you may need multiple versions installed at the same time.</span></span>
>
> <span data-ttu-id="93c52-113">I moduli di PowerShell Gallery consentono di installare i moduli in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="93c52-113">PowerShell Gallery modules install modules in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="93c52-114">Al contrario, il programma di Installazione guidata piattaforma Web installerà i moduli di Azure in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span><span class="sxs-lookup"><span data-stu-id="93c52-114">In contrast, the WebPI installer installs the Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span></span>
>
> <span data-ttu-id="93c52-115">Se si verifica un errore durante l'installazione, è possibile rimuovere manualmente le cartelle di Azure* nella cartella `$env:ProgramFiles\WindowsPowerShell\Modules` e ripetere l'installazione.</span><span class="sxs-lookup"><span data-stu-id="93c52-115">If an error occurs during install, you can manually remove the Azure* folders in your `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.</span></span>

<span data-ttu-id="93c52-116">Al termine dell'installazione, l'impostazione `$env:PSModulePath` includerà le directory contenenti i cmdlet di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93c52-116">Once the installation completes, your `$env:PSModulePath` setting should include the directories containing the Azure PowerShell cmdlets.</span></span> <span data-ttu-id="93c52-117">È possibile usare il comando seguente per verificare che Azure PowerShell sia installato correttamente.</span><span class="sxs-lookup"><span data-stu-id="93c52-117">The following command can be used to verify that the Azure PowerShell is installed properly.</span></span>

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> <span data-ttu-id="93c52-118">Durante l'uso dell'Installazione guidata piattaforma Web è possibile che si verifichi un problema noto.</span><span class="sxs-lookup"><span data-stu-id="93c52-118">There is a known issue that can occur when installing from WebPI.</span></span> <span data-ttu-id="93c52-119">Se il computer richiede il riavvio a causa di aggiornamenti di sistema o di altre installazioni, gli aggiornamenti di `$env:PSModulePath` potrebbero non includere il percorso in cui è installato Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93c52-119">If your computer requires a restart due to system updates or other installations, it may cause updates to `$env:PSModulePath` to fail to include the path where Azure PowerShell is installed.</span></span>

<span data-ttu-id="93c52-120">Quando si tenta di caricare o eseguire i cmdlet dopo l'installazione, è possibile ricevere il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="93c52-120">When attempting to load or execute cmdlets after installation, you can receive the following error message:</span></span>

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

<span data-ttu-id="93c52-121">Questo errore può essere corretto riavviando il computer o importando il modulo usando il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="93c52-121">This error can be corrected by restarting the machine or importing the module using the fully qualified path.</span></span> <span data-ttu-id="93c52-122">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="93c52-122">For example:</span></span>

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <span data-ttu-id="93c52-123">Installazione tramite il pacchetto MSI</span><span class="sxs-lookup"><span data-stu-id="93c52-123">Install using the MSI Package</span></span>
<a id="install-using-the-msi-package" class="xliff"></a>

<span data-ttu-id="93c52-124">Azure PowerShell può essere installato usando il file MSI disponibile su [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="93c52-124">Azure PowerShell can be installed using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span> <span data-ttu-id="93c52-125">Se sono state installate versioni precedenti dei moduli di Azure, il programma di installazione le rimuove automaticamente.</span><span class="sxs-lookup"><span data-stu-id="93c52-125">If you have installed previous versions of Azure modules, the installer automatically removes them.</span></span> <span data-ttu-id="93c52-126">Il pacchetto MSI consente di installare i moduli in `$env:ProgramFiles\WindowsPowerShell\Modules`, ma non crea cartelle specifiche per la versione.</span><span class="sxs-lookup"><span data-stu-id="93c52-126">The MSI package installs modules in `$env:ProgramFiles\WindowsPowerShell\Modules` but does not create version-specific folders.</span></span>
