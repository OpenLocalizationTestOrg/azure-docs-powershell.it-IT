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
ms.date: 11/14/2017
ms.openlocfilehash: ab35cbc4ec1a0bd4e7ee40e1864bd7941f5bca87
ms.sourcegitcommit: 79dd3700b5cb4cb90b268778b482082052160093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2017
---
# <a name="release-notes"></a>Note sulla versione

Questo è un elenco delle modifiche apportate ad Azure PowerShell in questa versione.

## <a name="20171110-version-501"></a>10.11.2017 - Versione 5.0.1
* Correzione del problema di caricamento degli assembly che causa l'esito negativo di alcuni cmdlet quando vengono eseguiti nei moduli seguenti:
    - AzureRM.ApiManagement
    - AzureRM.Backup
    - AzureRM.Batch
    - AzureRM.Compute
    - AzureRM.DataFactories
    - AzureRM.HDInsight
    - AzureRM.KeyVault
    - AzureRM.RecoveryServices
    - AzureRM.RecoveryServices.Backup
    - AzureRM.RecoveryServices.SiteRecovery
    - AzureRM.RedisCache
    - AzureRM.SiteRecovery
    - AzureRM.Sql
    - AzureRM.Storage
    - AzureRM.StreamAnalytics

## <a name="2017118---version-500"></a>8.11.2017 - Versione 5.0.0
* NOTA: questa è una versione con modifiche di rilievo. Per un elenco competo delle modifiche di rilievo introdotte, vedere la guida alla migrazione (https://aka.ms/azps-migration-guide).
* Tutti i cmdlet in AzureRM ora supportano la Guida
    - Eseguire Get-Help con il parametro -Online per aprire la Guida nel browser Internet predefinito
* AnalysisServices
    * Correzione del comando Synchronize-AzureAsInstance per usare la nuova API REST AsAzure per la sincronizzazione
* Gestione API
    * Vedere la guida alla migrazione per le modifiche di rilievo apportate ad ApiManagement in questa versione
    * Aggiornamento del cmdlet Get-AzureRmApiManagementUser per correggere il problema segnalato all'indirizzo https://github.com/Azure/azure-powershell/issues/4510
    * Aggiornamento del cmdlet New-AzureRmApiManagementApi per creare l'API con percorso vuoto, come segnalato all'indirizzo https://github.com/Azure/azure-powershell/issues/4069
* ApplicationInsights
    * Aggiungere i comandi per ottenere/creare/rimuovere la risorsa Application Insights
        - Get-AzureRmApplicationInsights
        - New-AzureRmApplicationInsights
        - Remove-AzureRmApplicationInsights
    * Aggiungere i comandi per ottenere/aggiornare i prezzi e il limite giornaliero della risorsa Application Insights
        - Get-AzureRmApplicationInsights -IncludeDailyCap
        - Set-AzureRmApplicationInsightsPricingPlan
        - Set-AzureRmApplicationInsightsDailyCap
    * Aggiungere i comandi per ottenere/creare/aggiornare/rimuovere l'esportazione continua della risorsa Application Insights
        - Get-AzureRmApplicationInsightsContinuousExport
        - Set-AzureRmApplicationInsightsContinuousExport
        - New-AzureRmApplicationInsightsContinuousExport
        - Remove-AzureRmApplicationInsightsContinuousExport
    * Aggiungere i comandi per ottenere/creare/rimuovere le chiavi API della risorsa Application Insights
        - Get-AzureRmApplicationInsightsApiKey
        - New-AzureRmApplicationInsightsApiKey
        - Remove-AzureRmApplicationInsightsApiKey
* AzureBatch
    * Aggiunta di nuovo parametri a `New-AzureRmBatchAccount`.
        - `PoolAllocationMode`: modalità di allocazione da usare per la creazione di pool nell'account Batch. Per creare un account Batch che alloca i nodi dei pool nella sottoscrizione dell'utente, impostarla su `UserSubscription`.
        - `KeyVaultId`: ID risorsa dell'insieme di credenziali delle chiavi di Azure associato all'account Batch.
        - `KeyVaultUrl`: URL dell'insieme di credenziali delle chiavi di Azure associato all'account Batch.
    * Aggiornamento dei parametri a `New-AzureBatchTask`.
        - Rimozione dell'opzione `RunElevated`. Il parametro `UserIdentity` è stato aggiunto per sostituire `RunElevated` e il comportamento equivalente può essere ottenuto costruendo un elemento `PSUserIdentity` come illustrato di seguito:
            - $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
            - $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
        - Aggiunta del parametro `AuthenticationTokenSettings`. Questo parametro consente di richiedere al servizio Batch di fornire un token di autenticazione all'attività quando viene eseguita, evitando la necessità di passare le chiavi dell'account Batch all'attività per inviare richieste al servizio Batch.
        - Aggiunta del parametro `ContainerSettings`.
            - Questo parametro consente di richiedere al servizio Batch di eseguire l'attività in un contenitore.
        - Aggiunta del parametro `OutputFiles`.
            - Questo parametro consente di configurare l'attività per il caricamento dei file in Archiviazione di Azure al termine dell'esecuzione.
    * Aggiornamento dei parametri a `New-AzureBatchPool`.
        - Aggiunta del parametro `UserAccounts`.
            - Questo parametro definisce gli account utente creati in ogni nodo del pool.
        - Aggiunta di `TargetLowPriorityComputeNodes` e ridenominazione di `TargetDedicated` in `TargetDedicatedComputeNodes`.
            - Creazione di un alias `TargetDedicated` per il parametro `TargetDedicatedComputeNodes`.
        - Aggiunta del parametro `NetworkConfiguration`.
            - Questo parametro consente di configurare le impostazioni di rete dei pool.
    * Aggiornamento dei parametri a `New-AzureBatchCertificate`.
        - Il parametro `Password` è ora un elemento `SecureString`.
    * Aggiornamento dei parametri a `New-AzureBatchComputeNodeUser`.
        - Il parametro `Password` è ora un elemento `SecureString`.
    * Aggiornamento dei parametri a `Set-AzureBatchComputeNodeUser`.
        - Il parametro `Password` è ora un elemento `SecureString`.
    * Ridenominazione del parametro `Name` con `Path` in `Get-AzureBatchNodeFile`, `Get-AzureBatchNodeFileContent` e `Remove-AzureBatchNodeFile`.
        - Creazione di un alias `Name` per il parametro `Path`.
    * Modifiche agli oggetti
        - Per l'elenco completo, vedere il log delle modifiche di Batch
    * Aggiunta del supporto per l'autenticazione basata su Azure Active Directory.
        - Per usare l'autenticazione di Azure Active Directory, recuperare un oggetto `BatchAccountContext` usando il cmdlet `Get-AzureRmBatchAccount` e fornire questo `BatchAccountContext` al parametro `-BatchContext` di un cmdlet del servizio Batch. L'autenticazione di Azure Active Directory è obbligatoria per gli account con `PoolAllocationMode = UserSubscription`.
        - Per gli account esistenti o per i nuovi account creati con `PoolAllocationMode = BatchService`, è possibile continuare a usare l'autenticazione con chiave condivisa recuperando un oggetto `BatchAccountContext` con il cmdlet `Get-AzureRmBatchAccoutKeys`.
* Calcolo
    * Comandi per l'estensione Crittografia dischi di Azure
        - Nuovo parametro per "Set-AzureRmVmDiskEncryptionExtension": la crittografia "-EncryptFormatAll" formatta i dischi dati
        - Nuovi parametri per "Set-AzureRmVmDiskEncryptionExtension": "-ExtensionPublisherName" ed "-ExtensionType" consentono il passaggio ad altre versioni dell'estensione
        - Nuovi parametri "Disable-AzureRmVmDiskEncryption": "-ExtensionPublisherName" ed "-ExtensionType" consentono il passaggio ad altre versioni dell'estensione
        - Nuovi parametri per "Get-AzureRmVmDiskEncryptionStatus": "-ExtensionPublisherName" ed "-ExtensionType" consentono il passaggio ad altre versioni dell'estensione
* DataLakeAnalytics
    * Vedere la guida alla migrazione per le modifiche di rilievo apportate a DataLakeAnalytics in questa versione
    * Modifica di uno dei due OutputType di Get-AzureRmDataLakeAnalyticsAccount
        - Da List\<DataLakeAnalyticsAccount> a List\<PSDataLakeAnalyticsAccountBasic>
        - Le proprietà di PSDataLakeAnalyticsAccountBasic sono un subset limitato delle proprietà di DataLakeAnalyticsAccount
        - Le proprietà aggiuntive in DataLakeAnalyticsAccount non vengono restituite dal servizio.  Questa modifica è quindi stata apportata con questo preciso scopo. Queste proprietà aggiuntive sono ancora in PSDataLakeAnalyticsAccountBasic, ma sono contrassegnate come obsolete.
    * Modifica di uno dei due OutputType di Get-AzureRmDataLakeAnalyticsJob
        - Da List\<JobInformation> a List\<PSJobInformationBasic>
        - Le proprietà di PSJobInformationBasic sono un subset limitato delle proprietà di JobInformation
        - Le proprietà aggiuntive in JobInformation non vengono restituite dal servizio.  Questa modifica è quindi stata apportata con questo preciso scopo. Queste proprietà aggiuntive sono ancora in PSJobInformationBasic, ma sono contrassegnate come obsolete.
* DataLakeStore
    * Vedere la guida alla migrazione per le modifiche di rilievo apportate a DataLakeStore in questa versione
    * Modifica di uno dei due OutputType di Get-AzureRmDataLakeStoreAccount
        - Da List\<PSDataLakeStoreAccount> a List\<PSDataLakeStoreAccountBasic>
        - Le proprietà di PSDataLakeStoreAccountBasic sono un subset limitato delle proprietà di PSDataLakeStoreAccount
        - Le proprietà aggiuntive in PSDataLakeStoreAccount non vengono restituite dal servizio.  Questa modifica è quindi stata apportata con questo preciso scopo. Queste proprietà aggiuntive sono ancora in PSDataLakeStoreAccountBasic, ma sono contrassegnate come obsolete.
* DNS
    * Supporto per i tipi di record CAA in DNS di Azure
       - Supporta tutte le operazioni nei tipi di record CAA
* Hub eventi
    * Vedere la guida alla migrazione per le modifiche di rilievo apportate a EventHub in questa versione
* Informazioni dettagliate
    * Vedere la guida alla migrazione per le modifiche di rilievo apportate a Insights in questa versione
* Rete
    * Vedere la guida alla migrazione per le modifiche di rilievo apportate a Network in questa versione
    * Aggiunta del cmdlet per elencare i provider di servizi Internet disponibili per un'area di Azure specificata
        - Get-AzureRmNetworkWatcherReachabilityProvidersList
    * Aggiunta del cmdlet per ottenere il punteggio di latenza relativa per i provider di servizi Internet da una località specificata alle aree di Azure
        - Get-AzureRmNetworkWatcherReachabilityReport
* Profilo
    - Set-AzureRmDefault
        - Usare questo cmdlet per impostare un gruppo di risorse predefinito.  Il parametro -ResourceGroup risulterà così facoltativo per alcuni cmdlet e verrà usata l'impostazione predefinita quando un gruppo di risorse non viene specificato
        - ```Set-AzureRmDefault -ResourceGroupName "ExampleResourceGroup"```
        - Se il gruppo di risorse specificato esiste nella sottoscrizione, verrà impostato sul valore predefinito.  In caso contrario, il gruppo di risorse verrà creato e quindi impostato sul valore predefinito.
    - Get-AzureRmDefault
        - Usare questo cmdlet per ottenere il gruppo di risorse predefinito corrente (e altre impostazioni predefinite in futuro).
        - ```Get-AzureRmDefault -ResourceGroup```
    - Clear-AzureRmDefault
        - Usare questo cmdlet per rimuovere il gruppo di risorse predefinito corrente
        - ```Clear-AzureRmDefault -ResourceGroup```
    - Add-AzureRmEnvironment e Set-AzureRmEnvironment
        - Aggiunta del parametro BatchAudience, che consente di specificare i destinatari di Active Directory per Azure Batch da usare quando si acquisiscono i token di autenticazione per il servizio Batch.
* RecoveryServices.Backup
    * Aggiunta di cmdlet per eseguire recupero di file immediato.
        - Get-AzureRmRecoveryServicesBackupRPMountScript
        - Disable-AzureRmRecoveryServicesBackupRPMountScript
    * Aggiornamento di RecoveryServices.Backup alla versione più recente dell'SDK
    * Aggiornamento dei test per il carico di lavoro della VM di Azure in modo che tutte le configurazioni necessarie per le esecuzioni dei test vengano eseguite dai test stessi.
    * Correzione del problema segnalato in https://github.com/Azure/azure-powershell/issues/3164
* RecoveryServices.SiteRecovery
    * Modifiche per ASR VMware in Azure Site Recovery (i cmdlet supportano attualmente operazioni da Enterprise a Enterprise, da Enterprise ad Azure, da HyperV ad Azure)
        - New-AzureRmRecoveryServicesAsrPolicy
        - New-AzureRmRecoveryServicesAsrProtectedItem
        - Update-AzureRmRecoveryServicesAsrPolicy
        - Update-AzureRmRecoveryServicesAsrProtectionDirection
    * Aggiunta del supporto all'insieme di credenziali basato su AAD
    * Aggiunta dei cmdlet per gestire le risorse di VCenter
        - Get-AzureRmRecoveryServicesAsrVCenter
        - New-AzureRmRecoveryServicesAsrVCenter
        - Remove-AzureRmRecoveryServicesAsrVCenter
        - Update-AzureRmRecoveryServicesAsrVCenter
    * Aggiunta di altri cmdlet
        - Get-AzureRmRecoveryServicesAsrAlertSetting
        - Get-AzureRmRecoveryServicesAsrEvent
        - New-AzureRmRecoveryServicesAsrProtectableItem
        - Set-AzureRmRecoveryServicesAsrAlertSetting
        - Start-AzureRmRecoveryServicesAsrResynchronizeReplicationJob
        - Start-AzureRmRecoveryServicesAsrSwitchProcessServerJob
        - Start-AzureRmRecoveryServicesAsrTestFailoverCleanupJob
        - Update-AzureRmRecoveryServicesAsrMobilityService
* ServiceBus
    - Vedere la guida alla migrazione per le modifiche di rilievo apportate a ServiceBus in questa versione
* Sql
    * Aggiunta del supporto per elencare e annullare l'operazione updateslo asincrona nel database
        - Aggiornare il cmdlet Get-AzureRmSqlDatabaseActivity esistente per restituire lo stato dell'operazione DB nel database.
        - Aggiungere il nuovo cmdlet Stop-AzureRmSqlDatabaseActivity per annullare l'operazione updateslo asincrona nel database.
    * Aggiunta del supporto per la ridondanza di zona per i database e i pool elastici
        - Aggiunta del parametro opzionale ZoneRedundant a New-AzureRmSqlDatabase
        - Aggiunta del parametro opzionale ZoneRedundant a Set-AzureRmSqlDatabase
        - Aggiunta del parametro opzionale ZoneRedundant a New-AzureRmSqlElasticPool
        - Aggiunta del parametro opzionale ZoneRedundant a Set-AzureRmSqlElasticPool
    * Aggiunta del supporto per gli alias DNS del server
        - Aggiunta del cmdlet Get-AzureRmSqlServerDnsAlias che ottiene gli alias DNS del server in base al nome del server e dell'alias o un elenco di alias DNS del server per un server SQL di Azure.
        - Aggiunta del cmdlet New-AzureRmSqlServerDnsAlias che crea il nuovo alias DNS del server per un determinato server SQL di Azure
        - Aggiunta del cmdlet Set-AzurermSqlServerDnsAlias che consente di aggiornare un server SQL di Azure a cui punta l'alias DNS del server
        - Aggiunta del cmdlet Remove-AzureRmSqlServerDnsAlias che rimuove un alias DNS del server per un server SQL di Azure
* Azure.Storage
    * Eseguire l'aggiornamento ad Azure Storage Client Library 8.5.0 e Azure Storage DataMovement Library 0.6.3
    * Aggiunta della funzionalità di supporto per snapshot di condivisione file
        - Aggiunta del parametro "SnapshotTime" a Get-AzureStorageShare
        - Aggiunta del parametro "IncludeAllSnapshot" a Remove-AzureStorageShare