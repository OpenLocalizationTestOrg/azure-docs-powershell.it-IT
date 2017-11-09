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
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2017
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a>Installare e configurare Azure PowerShell in macOS e Linux

È ora possibile installare PowerShell 6 (beta) e Azure PowerShell in piattaforme non Windows.
Il processo di installazione di Azure PowerShell in macOS e Linux non è così tanto diverso da quello per Windows, tuttavia, è prima necessario installare PowerShell 6 (beta).

> [!NOTE]

> Al momento, sia PowerShell 6 (beta) che Azure PowerShell per .NET Core sono ancora in versione beta.
> Il supporto per questi prodotti è limitato. Se si verificano problemi o si trovano bug, registrare i problemi in GitHub.
>
> * [Problemi per PowerShell 6 (beta)](https://github.com/PowerShell/PowerShell/issues)
> * [Problemi per Azure PowerShell](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a>Passaggio 1: installare PowerShell 6 (beta)

Il processo di installazione di PowerShell 6 (beta) varia a seconda del sistema operativo di destinazione.
Sebbene sia possibile installare PowerShell 6 (beta) in Windows, questo articolo è incentrato su macOS e Linux. Se si intende usare Azure PowerShell in Windows, vedere l'articolo dedicato all'[installazione](./install-azurerm-ps.md) per Windows.

Per installare **PowerShell 6** (beta) in ambiente Linux o macOS, è necessario:

1. Ottenere PowerShell per il sistema operativo e la versione specifici da [GitHub](https://github.com/powershell/powershell#get-powershell)
2. Seguire le istruzioni di installazione
   - [Linux](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [macOS](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a>Passaggio 2: installare Azure PowerShell per .NET Core

PowerShell 6 (beta) viene fornito con il modulo PowerShellGet già installato. Ciò semplifica l'installazione di qualsiasi modulo pubblicato in PowerShell Gallery. Per installare Azure PowerShell, aprire una nuova sessione di PowerShell ed eseguire il comando seguente:

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a>Passaggio 3: caricare il modulo AzureRM.Netcore

Dopo aver installato il modulo, è necessario caricarlo nella sessione di PowerShell. I moduli vengono caricati usando il cmdlet `Import-Module`, come indicato di seguito:

```powershell
Import-Module AzureRM.Netcore
```

Al termine dell'importazione, è possibile testare il modulo appena installato eseguendo un tentativo di accesso ad Azure con il comando seguente:

```powershell
Login-AzureRMAccount
```

Il comando riportato sopra richiede di passare a `https://aka.ms/devicelogin` e immettere il codice fornito.

## <a name="available-cmdlets"></a>Cmdlet disponibili

I moduli di Azure PowerShell per .NET Standard sono ancora in fase di sviluppo. Questi moduli non offrono il set completo di cmdlet disponibili per la versione Windows dei moduli. Le funzioni seguenti sono implementate nei moduli AzureRM.Netcore:

* Account Management
  - Accesso con account Microsoft, account dell'organizzazione o entità servizio tramite Microsoft Azure Active Directory
  - Salvataggio delle credenziali su disco con Save-AzureRmContext e caricamento delle credenziali salvate con Import-AzureRmContext
* Environment
  - Recupero di ambienti predefiniti di Microsoft Azure diversi
  - Aggiunta/impostazione/rimozione di ambienti personalizzati, come gli ambienti Azure Stack o Windows Azure Pack
* Cmdlet del piano di gestione per i servizi di Azure tramite le interfacce di Resource Manager e di gestione dei servizi.
  - Macchina virtuale
  - Servizio app (siti Web)
  - Database SQL
  - Archiviazione
  - Rete

## <a name="next-steps"></a>Passaggi successivi

Per altre informazioni sull'uso di Azure PowerShell, vedere l'articolo [Introduzione ad Azure PowerShell](get-started-azureps.md).
