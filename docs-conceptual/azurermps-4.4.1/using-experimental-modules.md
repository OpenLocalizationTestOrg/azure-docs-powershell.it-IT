---
title: Uso dei moduli sperimentali di Azure PowerShell
description: Informazioni sulla filosofia e sull'utilizzo dei moduli sperimentali di Azure PowerShell.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/05/2017
ms.openlocfilehash: 7a01957040be7c0498ef4f0e9b8f7297119221a5
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2017
---
# <a name="using-experimental-azure-powershell-modules"></a><span data-ttu-id="d90d5-103">Uso dei moduli sperimentali di Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90d5-103">Using experimental Azure PowerShell modules</span></span>

<span data-ttu-id="d90d5-104">In considerazione della particolare importanza attribuita agli strumenti di sviluppo e soprattutto alle interfacce della riga di comando in Azure, il team di Azure PowerShell sta sperimentando molti miglioramenti nell'esperienza di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d90d5-104">With the emphasis on developer tools (especially CLIs) in Azure, the Azure PowerShell team is experimenting with many improvements to the Azure PowerShell experience.</span></span>

## <a name="experimentation-methodology"></a><span data-ttu-id="d90d5-105">Metodologia di sperimentazione</span><span class="sxs-lookup"><span data-stu-id="d90d5-105">Experimentation methodology</span></span>

<span data-ttu-id="d90d5-106">Per facilitare la sperimentazione, vengono creati nuovi moduli di Azure PowerShell che implementano funzionalità esistenti di Azure SDK in nuovi modi più facili da usare.</span><span class="sxs-lookup"><span data-stu-id="d90d5-106">To facilitate experimentation, we are creating new Azure PowerShell modules that implement existing Azure SDK functionality in new, easier to use ways.</span></span> <span data-ttu-id="d90d5-107">Nella maggior parte dei casi, i cmdlet rispecchiano esattamente cmdlet esistenti.</span><span class="sxs-lookup"><span data-stu-id="d90d5-107">In most cases, the cmdlets exactly mirror existing cmdlets.</span></span> <span data-ttu-id="d90d5-108">I cmdlet sperimentali, tuttavia, offrono una notazione a sintassi abbreviata e valori predefiniti più intelligenti che semplificano la creazione e la gestione delle risorse di Azure.</span><span class="sxs-lookup"><span data-stu-id="d90d5-108">However, the experimental cmdlets provide a shorthand notation and smarter default values that make it easier to create and manage Azure resources.</span></span>

<span data-ttu-id="d90d5-109">Questi moduli possono essere installati side-by-side con i moduli di Azure PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="d90d5-109">These modules can be installed side-by-side with existing Azure PowerShell modules.</span></span> <span data-ttu-id="d90d5-110">I nomi dei cmdlet sono stati abbreviati per offrire nomi più corti ed evitare conflitti di nome con i cmdlet non sperimentali esistenti.</span><span class="sxs-lookup"><span data-stu-id="d90d5-110">The cmdlet names have been shortened to provide shorter names and avoid name conflicts with existing, non-experimental cmdlets.</span></span>

<span data-ttu-id="d90d5-111">I moduli sperimentali adottano la convenzione di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="d90d5-111">The experimental modules use the following naming convention:</span></span>

- <span data-ttu-id="d90d5-112">AzureRM.Compute.Experiments</span><span class="sxs-lookup"><span data-stu-id="d90d5-112">AzureRM.Compute.Experiments</span></span>
- <span data-ttu-id="d90d5-113">AzureRM.Websites.Experiments</span><span class="sxs-lookup"><span data-stu-id="d90d5-113">AzureRM.Websites.Experiments</span></span>

<span data-ttu-id="d90d5-114">Questa convenzione di denominazione è simile alla denominazione dei moduli in anteprima: `AzureRM.*.Preview`.</span><span class="sxs-lookup"><span data-stu-id="d90d5-114">This naming convention is similar to the naming of Preview modules: `AzureRM.*.Preview`.</span></span> <span data-ttu-id="d90d5-115">I moduli in anteprima differiscono da quelli sperimentali</span><span class="sxs-lookup"><span data-stu-id="d90d5-115">Preview modules differ from experimental modules.</span></span> <span data-ttu-id="d90d5-116">perché implementano nuove funzionalità dei servizi di Azure che sono disponibili solo come anteprima.</span><span class="sxs-lookup"><span data-stu-id="d90d5-116">Preview modules implement new functionality of Azure services that is only available as a Preview offering.</span></span> <span data-ttu-id="d90d5-117">I moduli in anteprima sostituiscono moduli di Azure PowerShell esistenti e usano gli stessi nomi per cmdlet e parametri.</span><span class="sxs-lookup"><span data-stu-id="d90d5-117">Preview modules replace existing Azure PowerShell modules and use the same cmdlet and parameter names.</span></span>

## <a name="how-to-install-an-experimental-module"></a><span data-ttu-id="d90d5-118">Come installare un modulo sperimentale</span><span class="sxs-lookup"><span data-stu-id="d90d5-118">How to install an experimental module</span></span>

<span data-ttu-id="d90d5-119">I moduli sperimentali vengono pubblicati in PowerShell Gallery così come i moduli di Azure PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="d90d5-119">Experimental modules are published to the PowerShell Gallery just like the existing Azure PowerShell modules.</span></span> <span data-ttu-id="d90d5-120">Per visualizzare un elenco di moduli sperimentali, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="d90d5-120">To see a list of experimental modules, run the following command:</span></span>

```powershell
Find-Module AzureRM.*.Experiments
```

```Output
Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0.0      AzureRM.Websites.Experiments        PSGallery            Create and deploy web applications using Azure Ap...
1.0.25     AzureRM.Compute.Experiments         PSGallery            Azure Compute experiments for VM creation
```

<span data-ttu-id="d90d5-121">Per installare il modulo sperimentale, usare i comandi seguenti in una sessione di PowerShell con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="d90d5-121">To install the experimental module, use the following commands from an elevated PowerShell session:</span></span>

```powershell
Install-Module AzureRM.Compute.Experiments
Install-Module AzureRM.Websites.Experiments
```

### <a name="documentation-and-support"></a><span data-ttu-id="d90d5-122">Documentazione e supporto</span><span class="sxs-lookup"><span data-stu-id="d90d5-122">Documentation and support</span></span>

<span data-ttu-id="d90d5-123">La documentazione è inclusa nel pacchetto di installazione ed è accessibile con il cmdlet `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="d90d5-123">Documentation is included in the install package and is accessed using the `Get-Help` cmdlet.</span></span> <span data-ttu-id="d90d5-124">Per i moduli sperimentali non viene pubblicata documentazione ufficiale.</span><span class="sxs-lookup"><span data-stu-id="d90d5-124">No official documentation is published for experimental modules.</span></span>

<span data-ttu-id="d90d5-125">Gli utenti sono invitati a testare questi moduli</span><span class="sxs-lookup"><span data-stu-id="d90d5-125">We encourage you to test these modules.</span></span> <span data-ttu-id="d90d5-126">e inviare commenti e suggerimenti, che consentiranno di migliorare l'usabilità e soddisfare le esigenze.</span><span class="sxs-lookup"><span data-stu-id="d90d5-126">Your feedback allows us to improve usability and respond to your needs.</span></span> <span data-ttu-id="d90d5-127">Dato che sono sperimentali, tuttavia, il supporto per questi moduli è limitato.</span><span class="sxs-lookup"><span data-stu-id="d90d5-127">However, being experimental, support for these modules is limited.</span></span> <span data-ttu-id="d90d5-128">È possibile inviare domande o segnalare problemi creando un [problema](https://github.com/Azure/azure-powershell/issues) nel repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="d90d5-128">Questions or problem reports can be submitted by creating an [issue](https://github.com/Azure/azure-powershell/issues) in the GitHub repository.</span></span>

## <a name="experiments-and-areas-of-improvement"></a><span data-ttu-id="d90d5-129">Esperimenti e aree di miglioramento</span><span class="sxs-lookup"><span data-stu-id="d90d5-129">Experiments and areas of improvement</span></span>

<span data-ttu-id="d90d5-130">Questi miglioramenti sono stati selezionati in base agli elementi di differenziazione chiave nei prodotti concorrenti.</span><span class="sxs-lookup"><span data-stu-id="d90d5-130">These improvements were selected based on key differentiators in competing products.</span></span> <span data-ttu-id="d90d5-131">Uno degli obiettivi dell'interfaccia della riga di comando di Azure 2.0, ad esempio, è stato basare i comandi su _scenari_ anziché sulla _superficie di attacco dell'API_.</span><span class="sxs-lookup"><span data-stu-id="d90d5-131">For example, Azure CLI 2.0 has made a point of basing commands on _scenarios_ rather than _API surface area_.</span></span>
<span data-ttu-id="d90d5-132">L'interfaccia della riga di comando di Azure 2.0 usa diverse impostazioni predefinite intelligenti che semplificano gli scenari "introduttivi" per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="d90d5-132">Azure CLI 2.0 use a number of smart defaults that make "getting started" scenarios easier for end users.</span></span>

### <a name="core-improvements"></a><span data-ttu-id="d90d5-133">Miglioramenti di base</span><span class="sxs-lookup"><span data-stu-id="d90d5-133">Core improvements</span></span>

<span data-ttu-id="d90d5-134">I miglioramenti di base sono considerati "buon senso" e non è necessaria molta sperimentazione per procedere all'implementazione di questi aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="d90d5-134">The core improvements are regarded as "common sense", and little experimentation is needed to move forward in implementing these updates.</span></span>

- <span data-ttu-id="d90d5-135">Cmdlet basati su scenari: i cmdlet **All*- dovranno essere progettati sulla base di scenari, non del servizio REST di Azure.</span><span class="sxs-lookup"><span data-stu-id="d90d5-135">Scenario-based Cmdlets - **All*- cmdlets should be designed around scenarios, not the Azure REST service.</span></span>

- <span data-ttu-id="d90d5-136">Nomi più brevi: include i nomi dei cmdlet (ad esempio, `New-AzureRmVM` => `New-AzVm`) e dei parametri (ad esempio, `-ResourceGroupName` => `-Rg`).</span><span class="sxs-lookup"><span data-stu-id="d90d5-136">Shorter Names - Includes the names of cmdlets (for example, `New-AzureRmVM` => `New-AzVm`) and the names of parameters (for example, `-ResourceGroupName` => `-Rg`).</span></span> <span data-ttu-id="d90d5-137">Usare alias per la compatibilità con i cmdlet "meno recenti"</span><span class="sxs-lookup"><span data-stu-id="d90d5-137">Use aliases for compatibility with "old" cmdlets.</span></span> <span data-ttu-id="d90d5-138">e specificare set di parametri _compatibili con le versioni precedenti_.</span><span class="sxs-lookup"><span data-stu-id="d90d5-138">Provide _backwards compatible_ parameter sets.</span></span>

- <span data-ttu-id="d90d5-139">Impostazioni predefinite intelligenti: creare impostazioni predefinite intelligenti per immettere le informazioni "necessarie",</span><span class="sxs-lookup"><span data-stu-id="d90d5-139">Smart Defaults - Create smart defaults to fill in "required" information.</span></span> <span data-ttu-id="d90d5-140">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d90d5-140">For example:</span></span>
  - <span data-ttu-id="d90d5-141">Gruppo di risorse</span><span class="sxs-lookup"><span data-stu-id="d90d5-141">Resource Group</span></span>
  - <span data-ttu-id="d90d5-142">Percorso</span><span class="sxs-lookup"><span data-stu-id="d90d5-142">Location</span></span>
  - <span data-ttu-id="d90d5-143">Risorse dipendenti</span><span class="sxs-lookup"><span data-stu-id="d90d5-143">Dependent resources</span></span>

### <a name="experimental-improvements"></a><span data-ttu-id="d90d5-144">Miglioramenti sperimentali</span><span class="sxs-lookup"><span data-stu-id="d90d5-144">Experimental improvements</span></span>

<span data-ttu-id="d90d5-145">I miglioramenti sperimentali presentano un cambiamento significativo che il team vuole convalidare tramite la sperimentazione.</span><span class="sxs-lookup"><span data-stu-id="d90d5-145">The experimental improvements present a significant change that the team wants to validate via experimentation.</span></span>

- <span data-ttu-id="d90d5-146">Tipi semplici: per gli scenari di creazione non dovranno più essere usati tipi complessi e oggetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d90d5-146">Simple types - Create scenarios should move away from complex types and config objects.</span></span> <span data-ttu-id="d90d5-147">Semplificare la configurazione riducendola a uno o due parametri.</span><span class="sxs-lookup"><span data-stu-id="d90d5-147">Simplify the configuration down to one or two parameters.</span></span>

- <span data-ttu-id="d90d5-148">"Creazione intelligente": tutti gli scenari di creazione che implementano la "creazione intelligente" _non_ avranno parametro obbligatori. Tutte le informazioni necessarie verranno scelte autonomamente da Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d90d5-148">"Smart Create" - All create scenarios implementing "Smart Create" would have _no_ required parameters: all necessary information would be chosen by Azure PowerShell in an opinionated fashion.</span></span>

- <span data-ttu-id="d90d5-149">Parametri "grigi": in molti casi, alcuni parametri potrebbero essere "grigi" o semifacoltativi.</span><span class="sxs-lookup"><span data-stu-id="d90d5-149">Gray Parameters - In many cases, some parameters could be "gray" or semi-optional.</span></span> <span data-ttu-id="d90d5-150">Se il parametro non viene specificato, all'utente viene richiesto se vuole che venga generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d90d5-150">If the parameter is not specified, the user is asked if they want the parameter generated for them.</span></span> <span data-ttu-id="d90d5-151">È anche opportuno che il valore per i parametri "grigi" venga dedotto in base al contesto con il consenso dell'utente,</span><span class="sxs-lookup"><span data-stu-id="d90d5-151">It also makes sense for gray parameters to infer a value based on context with the user's consent.</span></span>
  <span data-ttu-id="d90d5-152">ad esempio suggerendo il valore usato di recente.</span><span class="sxs-lookup"><span data-stu-id="d90d5-152">For example, it may make sense to have the gray parameter suggest the most recently used value.</span></span>

- <span data-ttu-id="d90d5-153">Opzione `-Auto`: l'opzione `-Auto` offrirà agli utenti la possibilità di "acconsentire esplicitamente" all'_impostazione predefinita di tutti i valori_ mantenendo al tempo stesso l'integrità dei parametri obbligatori nel percorso principale.</span><span class="sxs-lookup"><span data-stu-id="d90d5-153">`-Auto` Switch - The `-Auto` switch would provide an "opt-in" way for users to _default all the things_ while maintaining the integrity of required parameters in the mainline path.</span></span>

### <a name="feature-specific-switches"></a><span data-ttu-id="d90d5-154">Opzioni specifiche delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="d90d5-154">Feature-specific switches</span></span>

<span data-ttu-id="d90d5-155">Lo scenario di creazione di app Web, ad esempio, potrebbe avere un'opzione `-Git` o `-AddRemote` che aggiungerà automaticamente un'istanza remota di Azure a un repository Git esistente.</span><span class="sxs-lookup"><span data-stu-id="d90d5-155">For example, the "Create web app" scenario might have a `-Git` or `-AddRemote` switch that would automatically add an "azure" remote to an existing git repository.</span></span>

- <span data-ttu-id="d90d5-156">Valori predefiniti impostabili: gli utenti dovranno avere la possibilità di impostare valori predefiniti per determinati parametri comuni come `-ResourceGroupName` e `-Location`.</span><span class="sxs-lookup"><span data-stu-id="d90d5-156">Settable Defaults - Users should have the ability to default certain ubiquitous parameters like `-ResourceGroupName` and `-Location`.</span></span>

- <span data-ttu-id="d90d5-157">Impostazioni predefinite per le dimensioni: le "dimensioni" delle risorse possono confondere gli utenti perché molti provider di risorse usano nomi diversi, ad esempio "Standard\_DS1\_v2" o "S1".</span><span class="sxs-lookup"><span data-stu-id="d90d5-157">Size Defaults - Resource "sizes" can be confusing to users since many Resource Providers use different names (for example, "Standard\_DS1\_v2" or "S1").</span></span> <span data-ttu-id="d90d5-158">La maggior parte degli utenti, tuttavia presta molta attenzione al costo.</span><span class="sxs-lookup"><span data-stu-id="d90d5-158">However, most users care more about cost.</span></span> <span data-ttu-id="d90d5-159">È quindi opportuno definire dimensioni "universali" in base alla pianificazione prezzi.</span><span class="sxs-lookup"><span data-stu-id="d90d5-159">Therefore, it makes sense to define "universal" sizes based on a pricing schedule.</span></span> <span data-ttu-id="d90d5-160">Gli utenti possono scegliere dimensioni specifiche o lasciare che Azure PowerShell scelga l'_opzione migliore_ in base alla risorsa e al budget.</span><span class="sxs-lookup"><span data-stu-id="d90d5-160">Users can choose a specific size or let Azure PowerShell choose the _best option_ based on the resource the budget.</span></span>

- <span data-ttu-id="d90d5-161">Formato di output: Azure PowerShell attualmente restituisce oggetti `PSObject` e l'output della console è ridotto.</span><span class="sxs-lookup"><span data-stu-id="d90d5-161">Output Format - Azure PowerShell currently returns `PSObject`s and there is little console output.</span></span> <span data-ttu-id="d90d5-162">Potrebbe essere necessario visualizzare all'utente in Azure PowerShell alcune informazioni relative alle impostazioni predefinite intelligenti usate.</span><span class="sxs-lookup"><span data-stu-id="d90d5-162">Azure PowerShell may need to display some information to the user regarding the "smart defaults" used.</span></span>

## <a name="try-using-the-experiments"></a><span data-ttu-id="d90d5-163">Provare a usare gli esperimenti</span><span class="sxs-lookup"><span data-stu-id="d90d5-163">Try using the experiments</span></span>

### <a name="install"></a><span data-ttu-id="d90d5-164">Installa</span><span class="sxs-lookup"><span data-stu-id="d90d5-164">Install</span></span>

```powershell
Install-Module AzureRM.Compute.Experiments
```

### <a name="create-a-vm"></a><span data-ttu-id="d90d5-165">Creare una macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="d90d5-165">Create a VM</span></span>

```powershell
$job = New-AzVm -Name MyVm -AsJob
Receive-Job $job
```

### <a name="send-us-feedback"></a><span data-ttu-id="d90d5-166">Inviare commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="d90d5-166">Send us feedback</span></span>

```powershell
Send-Feedback
```

### <a name="uninstall-the-experimental-modules"></a><span data-ttu-id="d90d5-167">Disinstallare i moduli sperimentali</span><span class="sxs-lookup"><span data-stu-id="d90d5-167">Uninstall the experimental modules</span></span>

```powershell
Uninstall-Module AzureRM.Compute.Experiments
```