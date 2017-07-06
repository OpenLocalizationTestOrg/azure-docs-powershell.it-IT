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
ms.openlocfilehash: 97a23180a1fc65d96fdc9dbdffcbe3501a4c4c2a
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2017
---
# <a name="release-notes"></a>Note sulla versione

Questo è un elenco delle modifiche apportate ad Azure PowerShell in questa versione.

## <a name="version-400"></a>Versione 4.0.0

* Questa versione contiene modifiche di rilievo. Vedere la [Guida alla migrazione](https://aka.ms/azps-migration-guide) per dettagli sulle modifiche e sull'impatto sugli script esistenti.
* Gestione API
  - Aggiunta del supporto per la configurazione di gruppi esterni in New-AzureRmApiManagementGroup.
* Fatturazione
  - Nuovo cmdlet Get-AzureRmBillingPeriod
    + cmdlet per recuperare i periodi di fatturazione Azure della sottoscrizione.
  - Aggiornamento del cmdlet Get-AzureRmBillingInvoice
  - nuova proprietà BillingPeriodNames
  - output nella visualizzazione elenco
* Calcolo
  - Aggiornamento dei cmdlet Set-AzureRmVMAEMExtension e Test-AzureRmVMAEMExtension per il supporto di Managed Disks Premium
  - Backup delle impostazioni di crittografia per le macchine virtuali IaaS e ripristino in caso di errore
  - L'opzione ChefServiceInterval è stata rinominata ChefDaemonInterval. Quella precedente continuerà comunque a funzionare.
  - Rimozione delle proprietà DataDiskNames e NetworkInterfaceIDs duplicate dall'oggetto PS VM.
  - Rendere i parametri DataDiskNames e NetworkInterfaceIDs facoltativi, rispettivamente in Remove-AzureRmVMDataDisk e Remove-AzureRmVMNetworkInterface.
  - Correzione del problema dei pipe dei cmdlet Get nel caso in cui restituiscano un oggetto elenco.
  - Ridenominazione dei cmdlet che erano in conflitto con i cmdlet RDFE. Per altre informazioni, vedere il problema https://github.com/Azure/azure-powershell/issues/2917
    + `New-AzureVMSqlServerAutoBackupConfig` è stata rinominata `New-AzureRmVMSqlServerAutoBackupConfig`
    + `New-AzureVMSqlServerAutoPatchingConfig` è stata rinominata `New-AzureRmVMSqlServerAutoPatchingConfig`
    + `New-AzureVMSqlServerKeyVaultCredentialConfig` è stata rinominata `New-AzureRmVMSqlServerKeyVaultCredentialConfig`
* Consumo
  - Nuovo cmdlet Get-AzureRmConsumptionUsageDetail
    + cmdlet per recuperare i dettagli d'uso della sottoscrizione.
* ContainerRegistry
  - Aggiunta di cmdlet PowerShell per il Registro contenitori di Azure
    + New-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistry
    + Update-AzureRmContainerRegistry
    + Remove-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistryCredential
    + Update-AzureRmContainerRegistryCredential
    + Test-AzureRmContainerRegistryNameAvailability
* DataLakeAnalytics
  - Aggiunta del supporto per l'acquisizione e la presentazione del pacchetto catalogo
  - Aggiunta del supporto per la presentazione dei seguenti elementi del catalogo dai predecessori più approfonditi:
    + Tabella
    + Funzione con valori di tabella
    + Visualizza
    + Statistiche
* DataLakeStore
  - Per impostazione predefinita, la registrazione traccia per `Import-AzureRMDataLakeStoreItem` e `Export-AzureRMDataLakeStoreItem` è stata disabilitata per migliorare le prestazioni. Se si desidera la registrazione traccia, usare i parametri `-DiagnosticLogLevel` e `-DiagnosticLogPath`
  - Correzione di un bug che causava talvolta l'arresto anomalo di PowerShell durante il caricamento di molti file di piccole dimensioni in ADLS.
* Hub eventi
  - Correzione di bug:
    + Correzione dell'errore 'Tier' cannot be null, where it should be 'SkuName' ("Tier" non può essere Null quando dovrebbe essere "Skuname") per il cmdlet Set-AzureRmEventHubNamespace
    + Set-AzureRmEventHub - Correzione dell'errore "Riferimento a un oggetto non impostato su un'istanza di oggetto." durante l'aggiornamento di EventHub
* Informazioni dettagliate
  - Add-AzureRm*AlertRule
    + Restituisce un singolo oggetto: newResource, statusCode, requestId
  - Get-AzureRmAlertRule
    + L'output è ora enumerato anziché essere considerato un singolo oggetto. Il tipo non è stato modificato ed è sempre un elenco.
  - Remove-AzureRmAlertRule
    + statusCode segue il codice di stato restituito dalla richiesta mentre prima era sempre Ok.
  - Add-AzureRmAutoscaleSetting
    + Ora restituisce un oggetto singolo (e non un elenco come prima) contenente statusCode, requestId e la risorsa appena creata/aggiornata.
    + Il codice di stato segue lo stato restituito dalla richiesta mentre prima era sempre Ok.
  - New-AzureRmAutoscaleRule
    + Il parametro ScaleActionType è stato esteso ed accetta ora i seguenti valori: ChangeCount, PercentChangeCount, ExactCount.
  - Remove-AzureRmAutoscaleSetting
    + statusCode nell'output segue lo statusCode restituito dalla richiesta. Prima, era sempre Ok.
  - Get-AzureRMLogProfile
    + L'output è ora enumerato. Prima era considerato un singolo oggetto. Il tipo di output continua a essere un elenco, come prima.
  - Remove-AzureRmLogProfile
    + Il parametro PassThru è stato implementato.
  - Metriche API
    + SDK recupera ora le metriche da MDM.
  - Get-AzureRmMetricDefinition
    + L'output è ancora un elenco, ma la struttura dell'elenco è stata modificata.
  - Get-AzureRmMetric
    + La chiamata è stata modificata. Questa è la nuova sintassi: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailedOutput]
    + L'output è un elenco e la struttura dei suoi elementi è stata modificata.
* Insieme di credenziali delle chiavi
  - Aggiunta del supporto per il backup/ripristino dei segreti KeyVault
    + È possibile eseguire il backup e il ripristino dei segreti come con la funzionalità attualmente supportata per Chiavi

  - I cmdlet di backup per Chiavi e Segreti accettano ora un oggetto corrispondente come parametro di input
    + Il chiamante può concatenare le operazioni di recupero e backup: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey

  - I cmdlet di backup supportano ora un'opzione -Force per la sovrascrittura di un file esistente
    + Si noti che il tentativo di sovrascrivere un file esistente non genera più un'istruzione Throw ma richiede invece all'utente di scegliere come procedere.
* LogicApp
  - Nuovi parametri per i cmdlet di ripristino di emergenza del numero di controllo interscambio:
    + Parametro -AgreementType facoltativo ("X12" o "Edifact") per specificare i numeri di controllo pertinenti
* MachineLearning
  - Uso della nuova versione di Azure Machine Learning .Net SDK ed aggiunta di un nuovo cmdlet
    + Add-AzureRmMlWebServiceRegionalProperty
  - Lievi correzioni al testo della Guida.
* Rete
  - Aggiunta del cmdlet Test-AzureRmNetworkWatcherConnectivity
    + Restituisce informazioni sulla connessione per una macchina virtuale di origine specificata e una destinazione
    + Se non è possibile stabilire una connessione tra l'origine e la destinazione, il cmdlet restituisce dettagli sul problema
* Profilo
  - Aggiunta del cmdlet `Send-Feedback': consente all'utente di iniziare un set di prompt che inviano commenti al team di Azure PowerShell.
  - Sono stati rimossi i seguenti alias perché erano in conflitto con i nomi dei cmdlet esistenti nel modulo Azure:
    + `Enable-AzureDataCollection` (supportato da `Enable-AzureRmDataCollection`)
    + `Disable-AzureDataCollection` (supportato da `Disable-AzureRmDataCollection`)
* Relay
  - Aggiunge cmdlet per Inoltro di Azure che consente agli utenti di creare e gestire tutte le risorse di Inoltro di Azure.
    + `New-AzureRmRelayNamespace`
    + `Get-AzureRmRelayNamespace`
    + `Set-AzureRmRelayNamespace`
    + `Remove-AzureRmRelayNamespace`
    + `New-AzureRmWcfRelay`
    + `Get-AzureRmWcfRelay`
    + `Set-AzureRmWcfRelay`
    + `Remove-AzureRmWcfRelay`
    + `New-AzureRmRelayHybridConnection`
    + `Get-AzureRmRelayHybridConnection`
    + `Set-AzureRmRelayHybridConnection`
    + `Remove-AzureRmRelayHybridConnection`
    + `Test-AzureRmRelayName`
    + `Get-AzureRmRelayOperation`
    + `New-AzureRmRelayKey`
    + `Get-AzureRmRelayKey`
    + `New-AzureRmRelayAuthorizationRule`
    + `Get-AzureRmRelayAuthorizationRule`
    + `Set-AzureRmRelayAuthorizationRule`
    + `Remove-AzureRmRelayAuthorizationRule`
* Risorse
  - Supporto per le distribuzioni cross-resource-group per New-AzureRmResourceGroupDeployment
    + Gli utenti possono ora usare le distribuzioni nidificate per distribuire gruppi di risorse diversi.
* ServiceBus

  - Correzione di bug: i valori della proprietà oggetto ServiceBus Queue erano impostati su Null. L'oggetto è usato come parametro di input nel cmdlet Set-AzureRmServiceBusQueue cmdlet per aggiornare Queue.
   - Le proprietà interessate sono LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount e MessageCount
* ServiceFabric

  - Aggiunta di cmdlet per Service Fabric
    + Add-AzureRmServiceFabricApplicationCertificate       Aggiunge un certificato che verrà usato come certificato applicazione
    + Add-AzureRmServiceFabricClientCertificate       Aggiunge un nome comune o un'identificazione personale alle impostazioni cluster per l'autenticazione client
    + Add-AzureRmServiceFabricClusterCertificate       Aggiunge un certificato cluster secondario al cluster per la sostituzione del certificato esistente
    + Add-AzureRmServiceFabricNodes       Aggiunge nodi/macchine virtuali di un tipo di nodo specifico a un cluster
    + Add-AzureRmServiceFabricNodeType       Aggiunge un tipo di nodo/macchina virtuale a un cluster esistente
    + Get-AzureRmServiceFabricCluster       Ottiene i dettagli della risorsa cluster
    + New-AzureRmServiceFabricCluster Crea un nuovo cluster ServiceFabric. Questo comando ha molti overload per coprire vari scenari
    + Remove-AzureRmServiceFabricClientCertificate       Rimuove un certificato client perché non venga usato per accedere a un cluster
    + Remove-AzureRmServiceFabricClusterCertificate       Rimuove un certificato cluster perché non possa essere usato per la protezione del cluster
    + Remove-AzureRmServiceFabricNodes       Rimuove i nodi di un tipo di nodo specifico da un cluster
    + Remove-AzureRmServiceFabricNodeType       Rimuove un tipo di nodo da un cluster
    + Remove-AzureRmServiceFabricSettings       Rimuove una o più impostazioni ServiceFabric da un cluster
    + Set-AzureRmServiceFabricSettings       Aggiunge o aggiorna una o più impostazioni ServiceFabric di un cluster
    + Set-AzureRmServiceFabricUpgradeType       Modifica il tipo di aggiornamento ServiceFabric di un cluster
    + Update-AzureRmServiceFabricDurability       Modifica il livello di durabilità di un cluster
    + Update-AzureRmServiceFabricReliability       Modifica il livello di affidabilità di un cluster
* Sql
  - Aggiunta del parametro -SampleName a New-AzureRmSqlDatabase
  - Aggiornamenti ai cmdlet di Gruppo di failover
  - Rimozione dei parametri "Tag"
  - Rimozione dei parametri "PartnerResourceGroupName" e "PartnerServerName" dal cmdlet Remove-AzureRmSqlDatabaseFailoverGroup
  - Aggiunta del parametro "GracePeriodWithDataLossHours" ai cmdlet New- e Set-, che sostituiranno comunque "GracePeriodWithDataLossHour"
  - Approfondimento e aggiornamento della documentazione
  - Modifica della formattazione degli oggetti restituiti e correzione di alcuni bug quando i campi non erano sempre popolati
  - Aggiunta delle proprietà "DatabaseNames" e "PartnerLocation" all'oggetto Gruppo di failover
  - Correzione di un bug che causava la restituzione immediata del cmdlet Switch- anziché al termine dell'operazione
  - Correzione del bug di overflow di numero intero per l'uso di valori alti per il periodo di tolleranza
  - Rettifica del periodo di tolleranza su un minimo di 1 ora se quello specificato è minore
  - Rimozione di "Usage_Anomaly" dai valori accettati per il parametro "ExcludedDetectionType" dei cmdlet Set-AzureRmSqlDatabaseThreatDetectionPolicy e Set-AzureRmSqlServerThreatDetectionPolicy.
* Archiviazione
  - Aggiornamento di SRP SDK alla versione 6.3.0
  - New/Set-AzureRmStorageAccount: aggiunta di un nuovo parametro per supportare EnableHttpsTrafficOnly
  - New/Set/Get-AzureRmStorageAccount: l'account di archiviazione restituito contiene un nuovo attributo EnableHttpsTrafficOnly
* Azure.Storage
  - Aggiornamento ad Azure Storage Client Library 8.1.1 e Azure Storage DataMovement Library 0.5.1
  - Aggiunta di un nuovo cmdlet per supportare la funzionalità blob Incremental Copy (Copia incrementale)
