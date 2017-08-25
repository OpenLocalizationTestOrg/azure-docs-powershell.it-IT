---
title: Panoramica di PowerShell per Azure Stack | Microsoft Docs
description: Panoramica dell'installazione e della configurazione di PowerShell per Azure Stack.
author: SnehaGunda
manager: Byronr
ms.product: azure-stack
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.author: sngun
ms.manager: byronr
ms.openlocfilehash: 2a03697e0f3e80d63c48f2dc5615f6c99b9ef716
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2017
---
# <a name="azure-stack-powershell"></a>PowerShell per Azure Stack 

Azure Stack richiede i due moduli PowerShell seguenti:  

1. Il modulo **AzureRM** compatibile con Azure Stack, disponibile installando il profilo di versione API **2017-03-09-profile**. I cmdlet installati con questo profilo possono essere usati dai tenant e dagli amministratori cloud di Azure Stack. Per informazioni sui cmdlet di PowerShell disponibili in questo profilo, vedere i contenuti di riferimento di PowerShell per il modulo [AzureRM versione 1.2.9](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9).  

2. Versione **1.2.9** del modulo **AzureStack**. I cmdlet installati con questo modulo possono essere usati solo dagli amministratori cloud di Azure Stack. Un amministratore può eseguire operazioni come la gestione di offerte, piani, servizi, quote e così via usando i cmdlet di PowerShell disponibili in questo modulo. Per informazioni sui cmdlet di PowerShell disponibili in questo modulo, vedere i contenuti di riferimento su [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) e [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage).

## <a name="next-steps"></a>Passaggi successivi

* [Installare PowerShell per Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [Configurare PowerShell per l'uso con Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)


