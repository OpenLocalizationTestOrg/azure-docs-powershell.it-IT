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
ms.openlocfilehash: 04f89e8d47d0825d46cb1b8817efbcc0cafa0acd
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="b4108-103">Note sulla versione</span><span class="sxs-lookup"><span data-stu-id="b4108-103">Release notes</span></span>
<a id="release-notes" class="xliff"></a>

<span data-ttu-id="b4108-104">Questo è un elenco delle modifiche apportate ad Azure PowerShell in questa versione.</span><span class="sxs-lookup"><span data-stu-id="b4108-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <span data-ttu-id="b4108-105">Versione 3.8.0</span><span class="sxs-lookup"><span data-stu-id="b4108-105">Version 3.8.0</span></span>
<a id="version-380" class="xliff"></a>
* <span data-ttu-id="b4108-106">Calcolo</span><span class="sxs-lookup"><span data-stu-id="b4108-106">Compute</span></span>
  - <span data-ttu-id="b4108-107">Correzione di un bug nei cmdlet Get-*, per permettere il recupero di più pagine di dati (oltre 120 elementi)</span><span class="sxs-lookup"><span data-stu-id="b4108-107">Fix bug in Get-* cmdlets, to allow retrieving multiple pages of data (more than 120 items)</span></span>
* <span data-ttu-id="b4108-108">DataLakeAnalytics</span><span class="sxs-lookup"><span data-stu-id="b4108-108">DataLakeAnalytics</span></span>
  - <span data-ttu-id="b4108-109">Correzione della Guida per alcuni comandi in modo da includere il testo e gli esempi appropriati.</span><span class="sxs-lookup"><span data-stu-id="b4108-109">Fix help for some commands to have the proper verbage and examples.</span></span>
* <span data-ttu-id="b4108-110">DataLakeStore</span><span class="sxs-lookup"><span data-stu-id="b4108-110">DataLakeStore</span></span>
  - <span data-ttu-id="b4108-111">Aggiunta del supporto per le parti iniziale e finale al cmdlet `Get-AzureRMDataLakeStoreItemContent`.</span><span class="sxs-lookup"><span data-stu-id="b4108-111">Add support for head and tail to the `Get-AzureRMDataLakeStoreItemContent` cmdlet.</span></span> <span data-ttu-id="b4108-112">In questo modo, è possibile restituire le prime e ultime N nuove righe delimitate da riga da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="b4108-112">This enables returning the top N or last N new line delimited rows to be displayed.</span></span>
* <span data-ttu-id="b4108-113">HDInsight</span><span class="sxs-lookup"><span data-stu-id="b4108-113">HDInsight</span></span>
  - <span data-ttu-id="b4108-114">Aggiunta del supporto per il tipo di cluster RServer</span><span class="sxs-lookup"><span data-stu-id="b4108-114">Added support for RServer cluster type</span></span>
    + <span data-ttu-id="b4108-115">È possibile specificare le dimensioni delle VM Edgenode per un cluster RServer in New-AzureRmHDInsightCluster o New-AzureRmHDInsightClusterConfig</span><span class="sxs-lookup"><span data-stu-id="b4108-115">Edgenode VM size can be specified for RServer cluster in New-AzureRmHDInsightCluster or New-AzureRmHDInsightClusterConfig</span></span>
    + <span data-ttu-id="b4108-116">RServer è ora un'opzione di configurazione in Add-AzureRmHDInsightConfigValues.</span><span class="sxs-lookup"><span data-stu-id="b4108-116">RServer is now a configuration option in Add-AzureRmHDInsightConfigValues.</span></span> <span data-ttu-id="b4108-117">Permette l'impostazione del flag RStudio per indicare che è necessario eseguire l'installazione di R Studio.</span><span class="sxs-lookup"><span data-stu-id="b4108-117">It allows for RStudio flag to be set to indicate that R Studio installation should be done.</span></span>
* <span data-ttu-id="b4108-118">LogicApp</span><span class="sxs-lookup"><span data-stu-id="b4108-118">LogicApp</span></span>
  - <span data-ttu-id="b4108-119">I cmdlet Set-AzureRmIntegrationAccountSchema e Set-AzureRmIntegrationAccountMap sono stati corretti per quanto riguarda il problema relativo a contentLink (impostazione simultanea di content e contentLink, che produce un errore di aggiornamento).</span><span class="sxs-lookup"><span data-stu-id="b4108-119">Set-AzureRmIntegrationAccountSchema and Set-AzureRmIntegrationAccountMap cmdlets are fixed for the contentlink issue(Both content and contentlink were set resulting in update failure).</span></span>
* <span data-ttu-id="b4108-120">Network</span><span class="sxs-lookup"><span data-stu-id="b4108-120">Network</span></span>
  - <span data-ttu-id="b4108-121">Aggiunta del supporto per nuove funzionalità del firewall applicazione Web ai gateway applicazione</span><span class="sxs-lookup"><span data-stu-id="b4108-121">Added support for new web application firewall features to Application Gateways</span></span>
    + <span data-ttu-id="b4108-122">Aggiunta di New-AzureRmApplicationGatewayFirewallDisabledRuleGroupConfig</span><span class="sxs-lookup"><span data-stu-id="b4108-122">Added New-AzureRmApplicationGatewayFirewallDisabledRuleGroupConfig</span></span>
    + <span data-ttu-id="b4108-123">Aggiunta di Get-AzureRmApplicationGatewayAvailableWafRuleSets (alias: List-AzureRmApplicationGatewayAvailableWafRuleSets)</span><span class="sxs-lookup"><span data-stu-id="b4108-123">Added Get-AzureRmApplicationGatewayAvailableWafRuleSets (Alias: List-AzureRmApplicationGatewayAvailableWafRuleSets)</span></span>
    + <span data-ttu-id="b4108-124">Aggiornamento di New-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: aggiunta dei parametri -RuleSetType -RuleSetVersion e -DisabledRuleGroups</span><span class="sxs-lookup"><span data-stu-id="b4108-124">Updated New-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: Added parameter -RuleSetType -RuleSetVersion and -DisabledRuleGroups</span></span>
    + <span data-ttu-id="b4108-125">Aggiornamento di Set-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: aggiunta dei parametri -RuleSetType -RuleSetVersion e -DisabledRuleGroups</span><span class="sxs-lookup"><span data-stu-id="b4108-125">Updated Set-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: Added parameter -RuleSetType -RuleSetVersion and -DisabledRuleGroups</span></span>
  - <span data-ttu-id="b4108-126">Aggiunta del supporto per criteri IPSec a connessioni del gateway di rete virtuale</span><span class="sxs-lookup"><span data-stu-id="b4108-126">Added support for IPSec policies to Virtual Network Gateway Connections</span></span>
  - <span data-ttu-id="b4108-127">Aggiunta di New-AzureRmIpsecPolicy</span><span class="sxs-lookup"><span data-stu-id="b4108-127">Added New-AzureRmIpsecPolicy</span></span>
  - <span data-ttu-id="b4108-128">Aggiornamento di New-AzureRmVirtualNetworkGatewayConnection: aggiunta dei parametri -IpsecPolicies e -UsePolicyBasedTrafficSelectors</span><span class="sxs-lookup"><span data-stu-id="b4108-128">Updated New-AzureRmVirtualNetworkGatewayConnection: Added parameter -IpsecPolicies and -UsePolicyBasedTrafficSelectors</span></span>
* <span data-ttu-id="b4108-129">Profilo</span><span class="sxs-lookup"><span data-stu-id="b4108-129">Profile</span></span>
  - <span data-ttu-id="b4108-130">*Obsoleto*: Save-AzureRmProfile è stato rinominato in Save-AzureRmContext. È disponibile un alias per il nome precedente del cmdlet, che verrà rimosso nella prossima versione.</span><span class="sxs-lookup"><span data-stu-id="b4108-130">*Obsolete*: Save-AzureRmProfile is renamed to Save-AzureRmContext, there is an alias to the old cmdlet name, the alias will be removed in the next release.</span></span>
  - <span data-ttu-id="b4108-131">*Obsoleto*: Select-AzureRmProfile è stato rinominato in Import-AzureRmContext. È disponibile un alias per il nome precedente del cmdlet, che verrà rimosso nella prossima versione.</span><span class="sxs-lookup"><span data-stu-id="b4108-131">*Obsolete*: Select-AzureRmProfile is renamed to Import-AzureRmContext, there is an alias to the old cmdlet name, the alias will be removed in the next release.</span></span>
  - <span data-ttu-id="b4108-132">I tipi di output PSAzureContext e PSAzureProfile dei cmdlet dei profili verranno modificati nella prossima versione.</span><span class="sxs-lookup"><span data-stu-id="b4108-132">The PSAzureContext and PSAzureProfile output types of profile cmdlets will be changed in the next release.</span></span>
  - <span data-ttu-id="b4108-133">Il cmdlet Save-AzureRmContext non includerà OutputType nella prossima versione.</span><span class="sxs-lookup"><span data-stu-id="b4108-133">The Save-AzureRmContext cmdlet will have no OutputType in the next release.</span></span>
  - <span data-ttu-id="b4108-134">Correzione di un bug nel codice comune dei cmdlet per usare l'algoritmo conforme a FIPS per hash di dati: https://github.com/Azure/azure-powershell/issues/3651</span><span class="sxs-lookup"><span data-stu-id="b4108-134">Fix bug in cmdlet common code to use FIPS-compliant algorithm for data hashes: https://github.com/Azure/azure-powershell/issues/3651</span></span>
* <span data-ttu-id="b4108-135">Sql</span><span class="sxs-lookup"><span data-stu-id="b4108-135">Sql</span></span>
  - <span data-ttu-id="b4108-136">Correzione di bug nei cmdlet del gruppo di failover di Azure</span><span class="sxs-lookup"><span data-stu-id="b4108-136">Bug fixes on Azure Failover Group Cmdlets</span></span>
  - <span data-ttu-id="b4108-137">Correzione per il polling di operazioni</span><span class="sxs-lookup"><span data-stu-id="b4108-137">Fix for operation polling</span></span>
  - <span data-ttu-id="b4108-138">Correzione del valore GracePeriodWithDataLossHour quando si imposta FailoverPolicy su Manual</span><span class="sxs-lookup"><span data-stu-id="b4108-138">Fix GracePeriodWithDataLossHour value when setting FailoverPolicy to Manual</span></span>
* <span data-ttu-id="b4108-139">TrafficManager</span><span class="sxs-lookup"><span data-stu-id="b4108-139">TrafficManager</span></span>
  - <span data-ttu-id="b4108-140">Supporto per il metodo di routing del traffico Geographic</span><span class="sxs-lookup"><span data-stu-id="b4108-140">Support for the Geographic traffic routing method</span></span>
    + <span data-ttu-id="b4108-141">Nuovo valore "Geographic" per il parametro TrafficRoutingMethod di New-AzureRmTrafficManagerProfile</span><span class="sxs-lookup"><span data-stu-id="b4108-141">New value 'Geographic' for the TrafficRoutingMethod parameter of New-AzureRmTrafficManagerProfile</span></span>
    + <span data-ttu-id="b4108-142">Nuovo parametro "GeoMapping" per New-AzureRmTrafficManagerEndpoint e Add-AzureRmTrafficManagerEndpointConfig</span><span class="sxs-lookup"><span data-stu-id="b4108-142">New parameter 'GeoMapping' for the New-AzureRmTrafficManagerEndpoint and Add-AzureRmTrafficManagerEndpointConfig</span></span>
    + <span data-ttu-id="b4108-143">Correzione dell'invio tramite pipe per Get-AzureRmTrafficManagerProfile quando restituisce una raccolta di profili</span><span class="sxs-lookup"><span data-stu-id="b4108-143">Fix piping for Get-AzureRmTrafficManagerProfile when it returns a collection of profiles</span></span>
* <span data-ttu-id="b4108-144">ServiceManagement</span><span class="sxs-lookup"><span data-stu-id="b4108-144">ServiceManagement</span></span>
  - <span data-ttu-id="b4108-145">Restart-AzureVM: aggiunta del parametro InitiateMaintenance per l'esecuzione di attività di manutenzione durante il riavvio della VM.</span><span class="sxs-lookup"><span data-stu-id="b4108-145">Restart-AzureVM: Added InitiateMaintenance parameter for performing maintenance during VM restart.</span></span>
  - <span data-ttu-id="b4108-146">Get-AzureVM: aggiunta del campo per lo stato di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="b4108-146">Get-AzureVM: Added Maintenance Status field.</span></span>
  - <span data-ttu-id="b4108-147">Aggiunta di nuovi cmdlet per supportare l'aggiornamento dell'insieme di credenziali di Servizi di ripristino</span><span class="sxs-lookup"><span data-stu-id="b4108-147">Added new cmdlets to support Recovery Services vault upgrade</span></span>
    + <span data-ttu-id="b4108-148">Test-AzureRecoveryServicesVaultUpgrade</span><span class="sxs-lookup"><span data-stu-id="b4108-148">Test-AzureRecoveryServicesVaultUpgrade</span></span>
    + <span data-ttu-id="b4108-149">Invoke-AzureRecoveryServicesVaultUpgrade</span><span class="sxs-lookup"><span data-stu-id="b4108-149">Invoke-AzureRecoveryServicesVaultUpgrade</span></span>