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
ms.openlocfilehash: 143d92384fd270711378f6741ba59e88c12833d1
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="dda08-103">Note sulla versione</span><span class="sxs-lookup"><span data-stu-id="dda08-103">Release notes</span></span>
<a id="release-notes" class="xliff"></a>

<span data-ttu-id="dda08-104">Questo è un elenco delle modifiche apportate ad Azure PowerShell in questa versione.</span><span class="sxs-lookup"><span data-stu-id="dda08-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <span data-ttu-id="dda08-105">Versione 2.2.0</span><span class="sxs-lookup"><span data-stu-id="dda08-105">Version 2.2.0</span></span>
<a id="version-220" class="xliff"></a>
* <span data-ttu-id="dda08-106">Calcolo</span><span class="sxs-lookup"><span data-stu-id="dda08-106">Compute</span></span>
  - <span data-ttu-id="dda08-107">Aggiunta del supporto per l'esecuzione di query sullo stato di crittografia dall'estensione AzureDiskEncryptionForLinux</span><span class="sxs-lookup"><span data-stu-id="dda08-107">Add support for querying encryption status from the AzureDiskEncryptionForLinux extension</span></span>
* <span data-ttu-id="dda08-108">DataFactory</span><span class="sxs-lookup"><span data-stu-id="dda08-108">DataFactory</span></span>
  - <span data-ttu-id="dda08-109">Aggiunta di un nuovo cmdlet per elencare le finestre attività</span><span class="sxs-lookup"><span data-stu-id="dda08-109">Added new cmdlet for listing activity windows</span></span>
    + <span data-ttu-id="dda08-110">Get-AzureRmDataFactoryActivityWindow</span><span class="sxs-lookup"><span data-stu-id="dda08-110">Get-AzureRmDataFactoryActivityWindow</span></span>
* <span data-ttu-id="dda08-111">DataLake</span><span class="sxs-lookup"><span data-stu-id="dda08-111">DataLake</span></span>
  - <span data-ttu-id="dda08-112">Modifica del parametro `Host` in `DatabaseHost` e aggiunta dell'alias a `Host`</span><span class="sxs-lookup"><span data-stu-id="dda08-112">Changed parameter `Host` to `DatabaseHost` and added alias to `Host`</span></span>
    + <span data-ttu-id="dda08-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="dda08-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
    + <span data-ttu-id="dda08-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="dda08-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
  - <span data-ttu-id="dda08-115">Aggiunta del supporto per la rimozione di ACL e ACL predefiniti</span><span class="sxs-lookup"><span data-stu-id="dda08-115">Add support for ACL and Default ACL removal</span></span>
  - <span data-ttu-id="dda08-116">Aggiunta del supporto per ottenere e impostare autorizzazioni senza nome per file e cartelle</span><span class="sxs-lookup"><span data-stu-id="dda08-116">Add support for getting and setting unnamed permissions on files and folders</span></span>
* <span data-ttu-id="dda08-117">Insieme di credenziali delle chiavi</span><span class="sxs-lookup"><span data-stu-id="dda08-117">KeyVault</span></span>
  - <span data-ttu-id="dda08-118">Aggiunta del supporto per certificati</span><span class="sxs-lookup"><span data-stu-id="dda08-118">Add support for certificates</span></span>
    + <span data-ttu-id="dda08-119">Add-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="dda08-119">Add-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="dda08-120">Add-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="dda08-120">Add-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="dda08-121">Get-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="dda08-121">Get-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="dda08-122">Get-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="dda08-122">Get-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="dda08-123">Get-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="dda08-123">Get-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="dda08-124">Get-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="dda08-124">Get-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="dda08-125">Get-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="dda08-125">Get-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="dda08-126">Import-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="dda08-126">Import-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="dda08-127">New-AzureKeyVaultCertificateAdministratorDetails</span><span class="sxs-lookup"><span data-stu-id="dda08-127">New-AzureKeyVaultCertificateAdministratorDetails</span></span>
    + <span data-ttu-id="dda08-128">New-AzureKeyVaultCertificateOrganizationDetails</span><span class="sxs-lookup"><span data-stu-id="dda08-128">New-AzureKeyVaultCertificateOrganizationDetails</span></span>
    + <span data-ttu-id="dda08-129">New-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="dda08-129">New-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="dda08-130">Remove-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="dda08-130">Remove-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="dda08-131">Remove-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="dda08-131">Remove-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="dda08-132">Remove-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="dda08-132">Remove-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="dda08-133">Remove-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="dda08-133">Remove-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="dda08-134">Set-AzureKeyVaultCertificateAttribute</span><span class="sxs-lookup"><span data-stu-id="dda08-134">Set-AzureKeyVaultCertificateAttribute</span></span>
    + <span data-ttu-id="dda08-135">Set-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="dda08-135">Set-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="dda08-136">Set-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="dda08-136">Set-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="dda08-137">Stop-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="dda08-137">Stop-AzureKeyVaultCertificateOperation</span></span>
* <span data-ttu-id="dda08-138">Rete</span><span class="sxs-lookup"><span data-stu-id="dda08-138">Network</span></span>

  - <span data-ttu-id="dda08-139">Aggiunta di un nuovo parametro opzionale per l'interfaccia di rete per abilitare/disabilitare la rete accelerata +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span><span class="sxs-lookup"><span data-stu-id="dda08-139">New switch parameter added for network interface to enable/disable accelerated networking +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span></span>
  - <span data-ttu-id="dda08-140">Abilitazione di cmdlet di PowerShell per la funzionalità del gateway attiva-attiva</span><span class="sxs-lookup"><span data-stu-id="dda08-140">Enable Active-Active gateway feature PowerShell cmdlets</span></span>
    + <span data-ttu-id="dda08-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="dda08-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span></span>
    + <span data-ttu-id="dda08-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="dda08-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span></span>
  - <span data-ttu-id="dda08-143">Aggiunta di un nuovo cmdlet</span><span class="sxs-lookup"><span data-stu-id="dda08-143">Added new cmdlet</span></span>
    + <span data-ttu-id="dda08-144">Test-AzureRmPrivateIpAddressAvailability</span><span class="sxs-lookup"><span data-stu-id="dda08-144">Test-AzureRmPrivateIpAddressAvailability</span></span>
* <span data-ttu-id="dda08-145">Risorse</span><span class="sxs-lookup"><span data-stu-id="dda08-145">Resources</span></span>
  - <span data-ttu-id="dda08-146">Supporto delle zone nei cmdlet di provider e risorse</span><span class="sxs-lookup"><span data-stu-id="dda08-146">Support zones in provider and resource cmdlets</span></span>
    + <span data-ttu-id="dda08-147">Get-AzureRmProvider</span><span class="sxs-lookup"><span data-stu-id="dda08-147">Get-AzureRmProvider</span></span>
    + <span data-ttu-id="dda08-148">New-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="dda08-148">New-AzureRmResource</span></span>
    + <span data-ttu-id="dda08-149">Set-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="dda08-149">Set-AzureRmResource</span></span>
* <span data-ttu-id="dda08-150">Sql</span><span class="sxs-lookup"><span data-stu-id="dda08-150">Sql</span></span>
  - <span data-ttu-id="dda08-151">Aggiunta di nuovi cmdlet per la gestione dei criteri di rilevamento delle minacce di SQL di Azure a livello di server</span><span class="sxs-lookup"><span data-stu-id="dda08-151">Added new cmdlets for Azure SQL threat detection policy management at server level</span></span>
    + <span data-ttu-id="dda08-152">Get-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="dda08-152">Get-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="dda08-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="dda08-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="dda08-154">Set-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="dda08-154">Set-AzureRmSqlServerThreatDetectionPolicy</span></span>
  - <span data-ttu-id="dda08-155">Aggiunta di nuovi cmdlet per supportare l'abilitazione/disabilitazione di GeoBackupPolicy per Azure SQL Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="dda08-155">Added new cmdlets to support enabling/disabling GeoBackupPolicy for Sql Azure DataWarehouses</span></span>
    + <span data-ttu-id="dda08-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="dda08-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
    + <span data-ttu-id="dda08-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="dda08-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
  - <span data-ttu-id="dda08-158">Aggiunta di nuovi cmdlet per Advisor SQL di Azure e API per azioni consigliate</span><span class="sxs-lookup"><span data-stu-id="dda08-158">Added new cmdlets for Azure Sql Advisors and Recommended Actions APIs</span></span>
    + <span data-ttu-id="dda08-159">Get-AzureRmSqlDatabaseAdvisor</span><span class="sxs-lookup"><span data-stu-id="dda08-159">Get-AzureRmSqlDatabaseAdvisor</span></span>
    + <span data-ttu-id="dda08-160">Get-AzureRmSqlElasticPoolAdvisor</span><span class="sxs-lookup"><span data-stu-id="dda08-160">Get-AzureRmSqlElasticPoolAdvisor</span></span>
    + <span data-ttu-id="dda08-161">Get-AzureRmSqlServerAdvisor</span><span class="sxs-lookup"><span data-stu-id="dda08-161">Get-AzureRmSqlServerAdvisor</span></span>
    + <span data-ttu-id="dda08-162">Get-AzureRmSqlDatabaseRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="dda08-162">Get-AzureRmSqlDatabaseRecommendedActions</span></span>
    + <span data-ttu-id="dda08-163">Get-AzureRmSqlElasticPoolRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="dda08-163">Get-AzureRmSqlElasticPoolRecommendedActions</span></span>
    + <span data-ttu-id="dda08-164">Get-AzureRmSqlServerRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="dda08-164">Get-AzureRmSqlServerRecommendedActions</span></span>
    + <span data-ttu-id="dda08-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="dda08-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="dda08-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="dda08-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="dda08-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="dda08-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="dda08-168">Set-AzureRmSqlDatabaseRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="dda08-168">Set-AzureRmSqlDatabaseRecommendedActionState</span></span>
    + <span data-ttu-id="dda08-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="dda08-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span></span>
    + <span data-ttu-id="dda08-170">Set-AzureRmSqlServerRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="dda08-170">Set-AzureRmSqlServerRecommendedActionState</span></span>
