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
# <a name="other-installation-methods"></a>Altri metodi di installazione

Per Azure PowerShell sono disponibili più metodi di installazione. L'uso di PowerShellGet con PowerShell Gallery è il metodo preferito. Azure PowerShell può essere installato usando l'Installazione guidata piattaforma Web (WebPI) o il file MSI disponibile su [GitHub](https://github.com/Azure/azure-powershell/releases/latest).

## <a name="docker"></a>Docker

È disponibile un'immagine Docker preconfigurata con Azure PowerShell.

Eseguire il contenitore con `docker run`.

```powershell
docker run azuresdk/azure-powershell
```

È inoltre disponibile un subset di cmdlet come contenitore di PowerShell Core.

Per Mac/Linux, usare l'immagine `latest`.

```bash
docker run azuresdk/azure-powershell-core:latest
```

Per Windows, usare l'immagine `nanoserver`.

```powershell
docker run azuresdk/azure-powershell-core:nanoserver
```

Azure PowerShell è installato nell'immagine tramite `Install-Module` da [PowerShell Gallery](https://www.powershellgallery.com/).

## <a name="install-using-the-web-platform-installer"></a>Installazione tramite l'Installazione guidata piattaforma Web

L'installazione della versione più recente di Azure PowerShell dall'Installazione guidata piattaforma Web è uguale a quella per le versioni precedenti.
Scaricare il [pacchetto per l'Installazione guidata piattaforma Web di Azure PowerShell](http://aka.ms/webpi-azps) e avviare l'installazione.

> [!NOTE]
> Se sono stati installati precedentemente moduli Azure da PowerShell Gallery, il programma di installazione li rimuoverà automaticamente. Ciò semplifica l'ambiente, garantendo l'installazione di una sola versione di Azure PowerShell. Tuttavia, esistono scenari in cui sono necessarie più versioni installate nello stesso momento.
>
> I moduli di PowerShell Gallery consentono di installare i moduli in `$env:ProgramFiles\WindowsPowerShell\Modules`. Al contrario, il programma di Installazione guidata piattaforma Web installerà i moduli di Azure in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.
>
> Se si verifica un errore durante l'installazione, è possibile rimuovere manualmente le cartelle di Azure* nella cartella `$env:ProgramFiles\WindowsPowerShell\Modules` e ripetere l'installazione.

Al termine dell'installazione, l'impostazione `$env:PSModulePath` includerà le directory contenenti i cmdlet di Azure PowerShell. È possibile usare il comando seguente per verificare che Azure PowerShell sia installato correttamente.

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> Durante l'uso dell'Installazione guidata piattaforma Web è possibile che si verifichi un problema noto. Se il computer richiede il riavvio a causa di aggiornamenti di sistema o di altre installazioni, gli aggiornamenti di `$env:PSModulePath` potrebbero non includere il percorso in cui è installato Azure PowerShell.

Quando si tenta di caricare o eseguire i cmdlet dopo l'installazione, è possibile ricevere il messaggio di errore seguente:

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

Questo errore può essere corretto riavviando il computer o importando il modulo usando il percorso completo. ad esempio:

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <a name="install-using-the-msi-package"></a>Installazione tramite il pacchetto MSI

Azure PowerShell può essere installato usando il file MSI disponibile su [GitHub](https://github.com/Azure/azure-powershell/releases/latest). Se sono state installate versioni precedenti dei moduli di Azure, il programma di installazione le rimuove automaticamente. Il pacchetto MSI consente di installare i moduli in `$env:ProgramFiles\WindowsPowerShell\Modules`, ma non crea cartelle specifiche per la versione.
