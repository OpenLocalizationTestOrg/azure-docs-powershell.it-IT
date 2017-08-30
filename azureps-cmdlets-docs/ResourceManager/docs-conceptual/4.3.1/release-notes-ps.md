Programma di installazione di Azure PowerShell 4.3.1: [collegamento](https://github.com/Azure/azure-powershell/releases/download/v4.3.1-August2017/azure-powershell.4.3.1.msi)

Modulo della Gallery per i cmdlet ARM: [collegamento](https://www.powershellgallery.com/packages/AzureRM/4.3.1)

Modulo della Gallery per i cmdlet legacy per la gestione dei servizi (RDFE): [collegamento](https://www.powershellgallery.com/packages/Azure/4.3.1)

## <a name="changes-in-431"></a>Modifiche nella versione 4.3.1

- Risoluzione del problema a causa del quale determinati assembly non vengono firmati, con conseguente errore `could not load file or assembly` al momento dell'importazione dei moduli

## <a name="changes-in-430"></a>Modifiche nella versione 4.3.0

* AnalysisServices
    * Correzione del bug in Set-AzureRmAnalysisServicesServer
        - Quando l'amministratore non viene specificato, l'amministratore viene rimosso.
    * Aggiunta di Added BackupBlobContainerUri in New-AzureRmAnalysisServicesServer e Set-AzureRmAnalysisServicesServer
        - Possibilità di impostare o disabilitare il contenitore BLOB di backup per backup e ripristino del server di Azure Analysis Services
    * Aggiornamento della ricerca di SKU in New-AzureRmAnalysisServicesServer e Set-AzureRmAnalysisServicesServer
        - Modifica degli SKU hardcoded nella ricerca dinamica.
    * Add-AzureAnalysisServicesAccount per supportare l'accesso con entità servizio
* Automazione
    * Modifiche apportate ai cmdlet AutomationDSC* per eseguire il pull di più di 100 record
    * Risoluzione del problema a causa del quale i flussi dettagliati smettono di funzionare dopo la chiamata di alcuni cmdlet di Automazione, ad esempio Get-AzureRmAutomationVariable e Get-AzureRmAutomationJob.
    * Aggiunta del supporto del controllo delle versioni delle compilazioni di NodeConfiguration in StartAzureAutomationDscCompilationJob e ImportAzureAutomationDscNodeConfiguration.
    * Correzioni di bug per problemi esistenti - Correzioni del problema di alias n. 3775 e dell'alias runOn e il supporto per HybridWorkers.
* Calcolo
    * Set-AzureRmVMAEMExtension: aggiunta del supporto per nuove dimensioni dei dischi Premium
    * Set-AzureRmVMAEMExtension: aggiunta del supporto per la serie M
    * Aggiunta del parametro ForceUpdateTag ad Add-AzureRmVmssExtension
    * Aggiunta del parametro Primary a New-AzureRmVmssIpConfig
    * Aggiunta del parametro EnableAcceleratedNetworking ad Add-AzureRmVmssNetworkInterfaceConfig
    * Aggiunta di InstanceId a Set-AzureRmVmss
    * Esposizione di MaintenanceRedeployStatus nell'output -Status di Get-AzureRmVM
    * Esposizione di restrizioni e funzionalità per il formato di tabella di Get-AzureRmComputeResourceSku
* DataLakeStore
    * Correzione del problema: https://github.com/Azure/azure-powershell/issues/4323
* Hub eventi
    * Aggiunta della proprietà ResourceGroup a NamespaceAttributes
        - 'ResourceGroup' ottiene il nome del gruppo di risorse in cui si trova lo spazio dei nomi
    * Aggiornamento di cmdlet con nuovo parametro e alias di parametro
        - I cmdlet seguenti sono stati aggiornati con set di parametri per spazio dei nomi e hub eventi per il funzionamento della regola di autorizzazione
        - New-AzureRmEventHubAuthorizationRule
            + Aggiunge una nuova regola di autorizzazione allo spazio dei nomi o all'hub eventi esistente.
        - Get-AzureRmEventHubAuthorizationRule
            + Ottiene la regola di autorizzazione o un elenco delle regole di autorizzazione per lo spazio dei nomi o l'hub eventi esistente.
        - Set-AzureRmEventHubAuthorizationRule
            + Aggiorna le proprietà della regola di autorizzazione esistente per l'hub eventi o lo spazio dei nomi.
        - Remove-AzureRmEventHubAuthorizationRule
            + Elimina la regola di autorizzazione esistente dello spazio dei nomi o dell'hub eventi esistente.
        - New-AzureRmEventHubKey
            + Genera una nuova chiave primaria/secondaria per la regola di autorizzazione dello spazio dei nomi o dell'hub eventi esistente.
        - Get-AzureRmEventHubKey
            + Ottiene la chiave primaria/secondaria per la regola di autorizzazione dello spazio dei nomi o dell'hub eventi esistente.
* Rete
    * New-AzureRmExpressRouteCircuitPeeringConfig: aggiunta del supporto per IPv6. Aggiunta di un nuovo parametro facoltativo
        - PeerAddressType
    * Set-AzureRmExpressRouteCircuitPeeringConfig: aggiunta del supporto per IPv6. Aggiunta di un nuovo parametro facoltativo
        - PeerAddressType
    * Remove-AzureRmExpressRouteCircuitPeeringConfig: aggiunta del supporto per IPv6. Aggiunta di un nuovo parametro facoltativo
        - PeerAddressType
    * Parametro contrassegnato come obsoleto - ProbeEnabled
        - Add-AzureRmApplicationGatewayBackendHttpSettings
        - New-AzureRmApplicationGatewayBackendHttpSettings
        - Set-AzureRmApplicationGatewayBackendHttpSettings
* Profilo
    * La raccolta dei dati è abilitata per impostazione predefinita. Microsoft raccoglie dati di utilizzo allo scopo di migliorare l'esperienza utente. I dati sono anonimi e non includono i valori degli argomenti della riga di comando.
        - Usare il cmdlet Disable-AzureRmDataCollection per disattivare la funzionalità
        - Usare il cmdlet Enable-AzureRmDataCollection per attivare questa funzionalità
* Risorse
    * Aggiunta del supporto per la convalida degli ambiti per i cmdlet RoleDefinition e RoleAssignment seguenti prima di inviare la richiesta ad ARM
        - Get-AzureRMRoleAssignment
        - New-AzureRMRoleAssignment
        - Remove-AzureRMRoleAssignment
        - Get-AzureRMRoleDefinition
        - New-AzureRMRoleDefinition
        - Remove-AzureRMRoleDefinition
        - Set-AzureRMRoleDefinition
* ServiceBus
    * Aggiunta dei nuovi cmdlet seguenti per le regole di autorizzazione per spazio dei nomi, coda e argomento. Le operazioni relative alle regole di autorizzazione vengono eseguite in base al set di parametri.
     - New-AzureRmServiceBusAuthorizationRule
       - Aggiunge una nuova regola di autorizzazione a spazio dei nomi/coda/argomento del bus di servizio esistente.
     - Get-AzureRmServiceBusAuthorizationRule
       - Ottiene la regola di autorizzazione o un elenco delle regole di autorizzazione per spazio dei nomi/coda/argomento del bus di servizio esistente.
     - Set-AzureRmServiceBusAuthorizationRule
       - Aggiorna le proprietà della regola di autorizzazione esistente di spazio dei nomi/coda/argomento del bus di servizio.
     - New-AzureRmServiceBusKey
       - Genera una nuova chiave primaria/secondaria per la regola di autorizzazione di spazio dei nomi/coda/argomento del bus di servizio esistente.
     - Get-AzureRmServiceBusKey
       - Ottiene la chiave primaria/secondaria per la regola di autorizzazione di spazio dei nomi/coda/argomento del bus di servizio esistente.
     - Remove-AzureRmServiceBusNamespaceAuthorizationRule
       - Elimina la regola di autorizzazione esistente di spazio dei nomi/coda/argomento del bus di servizio.
    * Aggiunta della proprietà ResourceGroup a NamespaceAttributes
* Sql
    * Aggiornamento di Set-AzureRmSqlServerTransparentDataEncryptionProtector per visualizzare un avviso e richiedere conferma se il tipo di protezione della crittografia viene impostato su AzureKeyVault
    * Aggiunta di nuovi cmdlet aggiornati per le impostazioni di controllo
        - Aggiunta del cmdlet Get-AzureRmSqlDatabaseAuditing che ottiene le impostazioni di controllo di un database SQL di Azure.
        - Aggiunta del cmdlet Get-AzureRmSqlServerAuditing che ottiene le impostazioni di controllo di un server di Azure SQL.
        - Aggiunta del cmdlet Set-AzureRmSqlDatabaseAuditing che modifica le impostazioni di controllo per un database SQL di Azure.
        - Aggiunta del cmdlet Set-AzureRmSqlServerAuditing che modifica le impostazioni di controllo di un server di Azure SQL.
    * Deprecazione di cmdlet per i criteri di controllo esistenti
        - Deprecazione di Get-AzureRmSqlDatabaseAuditingPolicy
        - Deprecazione di Get-AzureRmSqlServerAuditingPolicy
        - Deprecazione di Set-AzureRmSqlDatabaseAuditingPolicy
        - Deprecazione di Set-AzureRmSqlServerAuditingPolicy
        - Deprecazione di Use-AzureRmSqlServerAuditingPolicy
        - Deprecazione di Remove-AzureRmSqlDatabaseAuditing
        - Deprecazione di Remove-AzureRmSqlServerAuditing
    * L'analisi del file di schema per Update-AzureRmSqlSyncGroup ora fa distinzione tra maiuscole e minuscole.
* Archiviazione
    * Aggiunta del supporto di NetworkRule ai cmdlet per l'account di archiviazione in modalità risorsa
        - New-AzureRmStorageAccount
        - Set-AzureRmStorageAccount
        - Get-AzureRmStorageAccountNetworkRuleSet
        - Update-AzureRmStorageAccountNetworkRuleSet
        - Add-AzureRmStorageAccountNetworkRule
        - Remove-AzureRmStorageAccountNetworkRule

Visualizzare le [modifiche apportate dall'ultima versione](https://github.com/Azure/azure-powershell/compare/v4.2.1-July2017...v4.3.1-August2017)
