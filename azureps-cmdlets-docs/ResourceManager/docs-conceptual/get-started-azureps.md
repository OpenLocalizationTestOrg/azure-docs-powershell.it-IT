---
title: Introduzione ad Azure PowerShell | Microsoft Docs
description: 
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: get-started-article
ms.date: 03/30/2017
ms.openlocfilehash: 4bfa14f4f139fa8c35d4bb51ae81baea819188ce
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2017
---
# <a name="getting-started-with-azure-powershell"></a><span data-ttu-id="46094-102">Introduzione ad Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="46094-102">Getting started with Azure PowerShell</span></span>

<span data-ttu-id="46094-103">Azure PowerShell è progettato per la gestione e l'amministrazione delle risorse di Azure dalla riga di comando e per la creazione di script di automazione che funzionano con Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="46094-103">Azure PowerShell is designed for managing and administering Azure resources from the command line, and for building automation scripts that work against the Azure Resource Manager.</span></span> <span data-ttu-id="46094-104">Questo articolo consente di iniziare a usarlo e illustra i concetti di base.</span><span class="sxs-lookup"><span data-stu-id="46094-104">This article helps get you started using it, and teaches you the core concepts behind it.</span></span>


## <a name="install-azure-powershell"></a><span data-ttu-id="46094-105">Installare Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="46094-105">Install Azure PowerShell</span></span>
<span data-ttu-id="46094-106">Verificare di aver installato l'ultima versione di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46094-106">The first step is to make sure you have the latest version of the Azure PowerShell installed.</span></span>  <span data-ttu-id="46094-107">La versione più recente è la 4.1.0.</span><span class="sxs-lookup"><span data-stu-id="46094-107">The latest version is 4.1.0.</span></span>

1. <span data-ttu-id="46094-108">[Installare Azure PowerShell](install-azurerm-ps.md).</span><span class="sxs-lookup"><span data-stu-id="46094-108">[Install Azure PowerShell](install-azurerm-ps.md).</span></span>

2. <span data-ttu-id="46094-109">Per verificare che l'installazione sia riuscita, eseguire `Get-Module AzureRM` dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="46094-109">To verify the installation was successful, run `Get-Module AzureRM` from your command line.</span></span>


## <a name="log-in-to-azure"></a><span data-ttu-id="46094-110">Accedere ad Azure</span><span class="sxs-lookup"><span data-stu-id="46094-110">Log in to Azure</span></span>

<span data-ttu-id="46094-111">Accedere in modo interattivo:</span><span class="sxs-lookup"><span data-stu-id="46094-111">Sign on interactively:</span></span>

1. <span data-ttu-id="46094-112">Digitare `Login-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="46094-112">Type `Login-AzureRmAccount`.</span></span>  <span data-ttu-id="46094-113">Apparirà una finestra di dialogo che richiede le credenziali di Azure.</span><span class="sxs-lookup"><span data-stu-id="46094-113">You will get dialog box asking for your Azure credentials.</span></span> <span data-ttu-id="46094-114">L'opzione '-EnvironmentName' consente di accedere ad Azure per la Cina o Azure per la Germania.</span><span class="sxs-lookup"><span data-stu-id="46094-114">Option '-EnvironmentName' can let you login in Azure China or Azure Germany.</span></span>
   <span data-ttu-id="46094-115">Ad esempio: Login-AzureRmAccount -EnvironmentName AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="46094-115">e.g. Login-AzureRmAccount -EnvironmentName AzureChinaCloud</span></span>

2. <span data-ttu-id="46094-116">Digitare l'indirizzo di posta elettronica e la password associati all'account.</span><span class="sxs-lookup"><span data-stu-id="46094-116">Type the email address and password associated with your account.</span></span> <span data-ttu-id="46094-117">Le informazioni delle credenziali vengono autenticate e salvate in Azure, quindi la finestra viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="46094-117">Azure authenticates and saves the credential information, and then closes the window.</span></span>

<span data-ttu-id="46094-118">Dopo aver effettuato l'accesso a un account Azure, è possibile usare i cmdlet di Azure PowerShell per l'accesso e la gestione delle risorse nella sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="46094-118">Once you have signed in to an Azure account, you can use the Azure PowerShell cmdlets to access and manager the resources in your subscription.</span></span>

## <a name="create-a-resource-group"></a><span data-ttu-id="46094-119">Creare un gruppo di risorse</span><span class="sxs-lookup"><span data-stu-id="46094-119">Create a resource group</span></span>

<span data-ttu-id="46094-120">Quando è tutto pronto, si usa Azure PowerShell per creare risorse in Azure.</span><span class="sxs-lookup"><span data-stu-id="46094-120">Now that we've got everything set up, let's use Azure PowerShell to create resources within Azure.</span></span>

<span data-ttu-id="46094-121">Si crea prima un gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="46094-121">First, create a Resource Group.</span></span> <span data-ttu-id="46094-122">I gruppi di risorse di Azure consentono di gestire più risorse che si desidera raggruppare insieme in modo logico.</span><span class="sxs-lookup"><span data-stu-id="46094-122">Resource Groups in Azure provide a way to manage multiple resources that you want to logically group together.</span></span> <span data-ttu-id="46094-123">Ad esempio, è possibile creare un gruppo di risorse per un'applicazione o un progetto e aggiungere una macchina virtuale, un database e un servizio rete CDN al suo interno.</span><span class="sxs-lookup"><span data-stu-id="46094-123">For example, you might create a Resource Group for an application or project and add a virtual machine, a database and a CDN service within it.</span></span>

<span data-ttu-id="46094-124">Creare un gruppo di risorse denominato "MyResourceGroup" nell'area westeurope di Azure.</span><span class="sxs-lookup"><span data-stu-id="46094-124">Let's create a resource group named "MyResourceGroup" in the westeurope region of Azure.</span></span> <span data-ttu-id="46094-125">A tale scopo, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="46094-125">To do so type the following command:</span></span>

```powershell
New-AzureRmResourceGroup -Name 'myResourceGroup' -Location 'westeurope'
```

```
ResourceGroupName : myResourceGroup
Location          : westeurope
ProvisioningState : Succeeded
Tags              :
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myResourceGroup
```

## <a name="create-a-windows-virtual-machine"></a><span data-ttu-id="46094-126">Creare una macchina virtuale Windows</span><span class="sxs-lookup"><span data-stu-id="46094-126">Create a Windows Virtual Machine</span></span>

<span data-ttu-id="46094-127">Dopo aver creato il gruppo di risorse, si crea una macchina virtuale Windows al suo interno.</span><span class="sxs-lookup"><span data-stu-id="46094-127">Now that we have our resource group, let's create a Windows VM within it.</span></span> <span data-ttu-id="46094-128">Per creare una nuova macchina virtuale occorre prima creare le altre risorse necessarie e assegnarle a una configurazione.</span><span class="sxs-lookup"><span data-stu-id="46094-128">To create a new VM we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="46094-129">Sarà quindi possibile usare tale configurazione per creare la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-129">Then we can use that configuration to create the VM.</span></span>

### <a name="create-the-required-network-resources"></a><span data-ttu-id="46094-130">Creare le risorse di rete necessarie</span><span class="sxs-lookup"><span data-stu-id="46094-130">Create the required network resources</span></span>

<span data-ttu-id="46094-131">È prima necessario creare una configurazione di subnet da usare con il processo di creazione della rete virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-131">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="46094-132">Si crea anche un indirizzo IP pubblico in modo che sia possibile connettersi a questa macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-132">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="46094-133">Si crea quindi un gruppo di sicurezza di rete per proteggere l'accesso all'indirizzo pubblico.</span><span class="sxs-lookup"><span data-stu-id="46094-133">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="46094-134">Infine si crea la scheda di interfaccia di rete virtuale usando tutte le risorse precedenti.</span><span class="sxs-lookup"><span data-stu-id="46094-134">Finally we create the virtual NIC using all of the previous resources.</span></span>

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myWindowsVM"

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet1 -AddressPrefix 192.168.1.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET1 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 3389
$nsgRuleRDP = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleRDP  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 3389 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup1 -SecurityRules $nsgRuleRDP

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic1 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <a name="create-the-virtual-machine"></a><span data-ttu-id="46094-135">Creare la macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="46094-135">Create the virtual machine</span></span>

<span data-ttu-id="46094-136">Innanzitutto è necessario un insieme di credenziali per il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="46094-136">First we need a set of credentials for the OS.</span></span>

```powershell
# Create user object
$cred = Get-Credential -Message "Enter a username and password for the virtual machine."
```

<span data-ttu-id="46094-137">Ora che si dispone delle risorse necessarie, è possibile creare la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-137">Now that we have the required resources we can create the VM.</span></span> <span data-ttu-id="46094-138">Per questo passaggio, si crea un oggetto di configurazione della macchina virtuale, quindi si usa la configurazione per creare la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-138">For this step, we create a VM configuration object, then we use the configuration to create the VM.</span></span>

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Windows -ComputerName $vmName -Credential $cred |
  Set-AzureRmVMSourceImage -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="46094-139">Il comando `New-AzureRmVM` genera i risultati dopo che la macchina virtuale è stata creata completamente ed è pronta per essere usata.</span><span class="sxs-lookup"><span data-stu-id="46094-139">The `New-AzureRmVM` command outputs results once the VM has been fully created and is ready to be used.</span></span>

```
RequestId IsSuccessStatusCode StatusCode ReasonPhrase
--------- ------------------- ---------- ------------
                         True         OK OK
```

<span data-ttu-id="46094-140">Accedere ora alla macchina virtuale Windows Server appena creata usando Desktop remoto e l'indirizzo IP pubblico della macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-140">Now log on to your newly created Windows Server VM using Remote Desktop and the public IP address of the VM.</span></span> <span data-ttu-id="46094-141">Il comando seguente consente di visualizzare l'indirizzo IP pubblico creato nello script precedente.</span><span class="sxs-lookup"><span data-stu-id="46094-141">The following command displays the public IP address created in the previous script.</span></span>

```powershell
$publicIp | Select-Object Name,IpAddress
```

```
Name                  IpAddress
----                  ---------
mypublicdns1400512543 xx.xx.xx.xx
```

<span data-ttu-id="46094-142">Se si usa un sistema basato su Windows, è possibile eseguire questa operazione dalla riga di comando usando il comando mstsc:</span><span class="sxs-lookup"><span data-stu-id="46094-142">If you are on a Windows-based system, you can do this from the command line using the mstsc command:</span></span>

```
mstsc /v:xx.xxx.xx.xxx
```

<span data-ttu-id="46094-143">Fornire la stessa combinazione di nome utente/password usata quando si crea la macchina virtuale per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="46094-143">Supply the same username/password combination you used when creating the VM to log in.</span></span>


## <a name="create-a-linux-virtual-machine"></a><span data-ttu-id="46094-144">Creare una macchina virtuale Linux</span><span class="sxs-lookup"><span data-stu-id="46094-144">Create a Linux Virtual Machine</span></span>

<span data-ttu-id="46094-145">Per creare una nuova macchina virtuale occorre prima creare le altre risorse necessarie e assegnarle a una configurazione.</span><span class="sxs-lookup"><span data-stu-id="46094-145">To create a new Linux VM we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="46094-146">Sarà quindi possibile usare tale configurazione per creare la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-146">Then we can use that configuration to create the VM.</span></span> <span data-ttu-id="46094-147">Ciò presuppone che il gruppo di risorse sia già stato creato come indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46094-147">This assumes that you have already created the resource group as previously shown.</span></span> <span data-ttu-id="46094-148">Sarà inoltre necessario disporre di una chiave pubblica SSH denominata `id_rsa.pub` nella directory .ssh del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="46094-148">Also, you will need to have an SSH public key named `id_rsa.pub` in the .ssh directory of your user profile.</span></span>

### <a name="create-the-required-network-resources"></a><span data-ttu-id="46094-149">Creare le risorse di rete necessarie</span><span class="sxs-lookup"><span data-stu-id="46094-149">Create the required network resources</span></span>

<span data-ttu-id="46094-150">È prima necessario creare una configurazione di subnet da usare con il processo di creazione della rete virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-150">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="46094-151">Si crea anche un indirizzo IP pubblico in modo che sia possibile connettersi a questa macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-151">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="46094-152">Si crea quindi un gruppo di sicurezza di rete per proteggere l'accesso all'indirizzo pubblico.</span><span class="sxs-lookup"><span data-stu-id="46094-152">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="46094-153">Infine si crea la scheda di interfaccia di rete virtuale usando tutte le risorse precedenti.</span><span class="sxs-lookup"><span data-stu-id="46094-153">Finally we create the virtual NIC using all of the previous resources.</span></span>

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myLinuxVM"

# Definer user name and blank password
$securePassword = ConvertTo-SecureString ' ' -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential ("azureuser", $securePassword)

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 192.168.2.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET2 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 22
$nsgRuleSSH = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleSSH  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 22 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup2 -SecurityRules $nsgRuleSSH

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic2 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <a name="create-the-virtual-machine"></a><span data-ttu-id="46094-154">Creare la macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="46094-154">Create the virtual machine</span></span>

<span data-ttu-id="46094-155">Ora che si dispone delle risorse necessarie, è possibile creare la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-155">Now that we have the required resources we can create the VM.</span></span> <span data-ttu-id="46094-156">Per questo passaggio, si crea un oggetto di configurazione della macchina virtuale, quindi si usa la configurazione per creare la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="46094-156">For this step, we create a VM configuration object, then we use the configuration to create the VM.</span></span>

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Linux -ComputerName $vmName -Credential $cred -DisablePasswordAuthentication |
  Set-AzureRmVMSourceImage -PublisherName Canonical -Offer UbuntuServer -Skus 14.04.2-LTS -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Configure SSH Keys
$sshPublicKey = Get-Content "$env:USERPROFILE\.ssh\id_rsa.pub"
Add-AzureRmVMSshPublicKey -VM $vmConfig -KeyData $sshPublicKey -Path "/home/azureuser/.ssh/authorized_keys"

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="46094-157">Ora che la macchina virtuale è stata creata, è possibile accedere alla nuova macchina virtuale Linux tramite SSH con l'indirizzo IP pubblico della macchina virtuale creata:</span><span class="sxs-lookup"><span data-stu-id="46094-157">Now that the VM has been created, you can log on to your new Linux VM using SSH with the public IP address of the VM you created:</span></span>

```bash
ssh xx.xxx.xxx.xxx
```

```
Welcome to Ubuntu 14.04.4 LTS (GNU/Linux 3.19.0-65-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Sun Feb 19 00:32:28 UTC 2017

  System load: 0.31              Memory usage: 3%   Processes:       89
  Usage of /:  39.6% of 1.94GB   Swap usage:   0%   Users logged in: 0

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

my-login@MyLinuxVM:~$
```

## <a name="creating-other-resources-in-azure"></a><span data-ttu-id="46094-158">Creazione di altre risorse in Azure</span><span class="sxs-lookup"><span data-stu-id="46094-158">Creating other resources in Azure</span></span>

<span data-ttu-id="46094-159">È stato descritto come creare un gruppo di risorse, una macchina virtuale Linux e una macchina virtuale di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="46094-159">We've now walked through how to create a Resource Group, a Linux VM, and a Windows Server VM.</span></span> <span data-ttu-id="46094-160">È possibile creare molti altri tipi di risorse di Azure.</span><span class="sxs-lookup"><span data-stu-id="46094-160">You can create many other types of Azure resources as well.</span></span>

<span data-ttu-id="46094-161">Ad esempio, per creare un bilanciamento del carico di rete di Azure da associare alle macchine virtuali appena create, si può usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="46094-161">For example, to create an Azure Network Load Balancer that we could then associate with our newly created VMs, we can use the following create command:</span></span>

```powershell
New-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName myResourceGroup -Location westeurope
```

<span data-ttu-id="46094-162">È anche possibile creare una nuova rete virtuale privata (nota come "VNet" all'interno di Azure) per l'infrastruttura usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="46094-162">We could also create a new private Virtual Network (commonly referred to as a "VNet" within Azure) for our infrastructure using the following command:</span></span>

```powershell
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 10.0.0.0/16
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName myResourceGroup -Location westeurope `
  -Name MYvNET3 -AddressPrefix 10.0.0.0/16 -Subnet $subnetConfig
```

<span data-ttu-id="46094-163">Ciò che rende potenti Azure e Azure PowerShell è la possibilità di usarli non solo per ottenere un'infrastruttura basata su cloud, ma anche per creare servizi di piattaforma gestiti.</span><span class="sxs-lookup"><span data-stu-id="46094-163">What makes Azure and the Azure PowerShell powerful is that we can use it not just to get cloud-based infrastructure but also to create managed platform services.</span></span> <span data-ttu-id="46094-164">I servizi di piattaforma gestiti possono anche essere combinati con l'infrastruttura per creare soluzioni ancora più potenti.</span><span class="sxs-lookup"><span data-stu-id="46094-164">The managed platform services can also be combined with infrastructure to build even more powerful solutions.</span></span>

<span data-ttu-id="46094-165">Ad esempio, è possibile usare Azure Powershell per creare un servizio app di Azure.</span><span class="sxs-lookup"><span data-stu-id="46094-165">For example, you can use the Azure PowerShell to create an Azure AppService.</span></span> <span data-ttu-id="46094-166">Il servizio app di Azure è un servizio di piattaforma gestito che consente di eseguire l'hosting di app Web senza doversi preoccupare dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="46094-166">Azure AppService is a managed platform service that provides a great way to host web apps without having to worry about infrastructure.</span></span> <span data-ttu-id="46094-167">Dopo aver creato il servizio app di Azure, è possibile creare due nuove app Web di Azure all'interno del servizio app usando i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="46094-167">After creating the Azure AppService, you can create two new Azure Web Apps within the AppService using the following commands:</span></span>

```powershell
# Create an Azure AppService that we can host any number of web apps within
New-AzureRmAppServicePlan -Name MyAppServicePlan -Tier Basic -NumberofWorkers 2 -WorkerSize Small -ResourceGroupName myResourceGroup -Location westeurope

# Create Two Web Apps within the AppService (note: name param must be a unique DNS entry)
New-AzureRmWebApp -Name MyWebApp43432 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
New-AzureRmWebApp -Name MyWebApp43433 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
```

## <a name="listing-deployed-resources"></a><span data-ttu-id="46094-168">Elenco delle risorse distribuite</span><span class="sxs-lookup"><span data-stu-id="46094-168">Listing deployed resources</span></span>

<span data-ttu-id="46094-169">È possibile usare il cmdlet `Get-AzureRmResource` per elencare le risorse in esecuzione in Azure.</span><span class="sxs-lookup"><span data-stu-id="46094-169">You can use the `Get-AzureRmResource` cmdlet to list the resources running in Azure.</span></span> <span data-ttu-id="46094-170">L'esempio seguente illustra le risorse appena create nel nuovo gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="46094-170">The following example shows the resources we just created in the new resource group.</span></span>

```powershell
Get-AzureRmResource |
  Where-Object ResourceGroupName -eq myResourceGroup |
    Select-Object Name,Location,ResourceType
```

```
Name                                                  Location   ResourceType
----                                                  --------   ------------
myLinuxVM_OsDisk_1_36ca038791f642ba91270879088c249a   westeurope Microsoft.Compute/disks
myWindowsVM_OsDisk_1_f627e6e2bb454c72897d72e9632adf9a westeurope Microsoft.Compute/disks
myLinuxVM                                             westeurope Microsoft.Compute/virtualMachines
myWindowsVM                                           westeurope Microsoft.Compute/virtualMachines
myWindowsVM/BGInfo                                    westeurope Microsoft.Compute/virtualMachines/extensions
myNic1                                                westeurope Microsoft.Network/networkInterfaces
myNic2                                                westeurope Microsoft.Network/networkInterfaces
myNetworkSecurityGroup1                               westeurope Microsoft.Network/networkSecurityGroups
myNetworkSecurityGroup2                               westeurope Microsoft.Network/networkSecurityGroups
mypublicdns245369171                                  westeurope Microsoft.Network/publicIPAddresses
mypublicdns779537141                                  westeurope Microsoft.Network/publicIPAddresses
MYvNET1                                               westeurope Microsoft.Network/virtualNetworks
MYvNET2                                               westeurope Microsoft.Network/virtualNetworks
micromyresomywi032907510                              westeurope Microsoft.Storage/storageAccounts
```

## <a name="deleting-resources"></a><span data-ttu-id="46094-171">Eliminazione di risorse</span><span class="sxs-lookup"><span data-stu-id="46094-171">Deleting resources</span></span>

<span data-ttu-id="46094-172">Per eseguire la pulizia dell'account Azure, si dovranno rimuovere le risorse create in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="46094-172">To clean up your Azure account, you want to remove the resources we created in this example.</span></span> <span data-ttu-id="46094-173">Per eliminare le risorse non più necessarie, si può usare il cmdlet `Remove-AzureRm*`.</span><span class="sxs-lookup"><span data-stu-id="46094-173">You can use the `Remove-AzureRm*` cmdlets to delete the resources you no longer need.</span></span> <span data-ttu-id="46094-174">Per rimuovere la macchina virtuale Windows creata, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="46094-174">To remove the Windows VM we created, using the following command:</span></span>

```powershell
Remove-AzureRmVM -Name myWindowsVM -ResourceGroupName myResourceGroup
```

<span data-ttu-id="46094-175">Verrà richiesto di confermare l'eliminazione delle risorse specificate.</span><span class="sxs-lookup"><span data-stu-id="46094-175">You will be prompted to confirm that you want to remove the resource.</span></span>

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="46094-176">È anche possibile eliminare più risorse contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="46094-176">You can also use the delete many resources at one time.</span></span> <span data-ttu-id="46094-177">Ad esempio, il comando seguente elimina l'intero gruppo di risorse "MyResourceGroup" che abbiamo usato per tutti gli esempi di questa esercitazione introduttiva.</span><span class="sxs-lookup"><span data-stu-id="46094-177">For example, the following command deletes all the resource group "MyResourceGroup" that we've used for all the samples in this Get Started tutorial.</span></span> <span data-ttu-id="46094-178">Il comando elimina il gruppo di risorse e tutte le altre risorse in esso contenute.</span><span class="sxs-lookup"><span data-stu-id="46094-178">This removes the resource group and all of the resources in it.</span></span>

```powershell
Remove-AzureRmResourceGroup -Name myResourceGroup
```

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="46094-179">Questa operazione può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="46094-179">This can take several minutes to complete.</span></span>

## <a name="get-samples"></a><span data-ttu-id="46094-180">Ottenere gli esempi</span><span class="sxs-lookup"><span data-stu-id="46094-180">Get samples</span></span>

<span data-ttu-id="46094-181">Per altre informazioni sull'uso di Azure PowerShell, vedere i nostri script più comuni per le [macchine virtuali Linux](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), le [macchine virtuali di Windows](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), le [app Web](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json) e i [database SQL](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="46094-181">To learn more about ways to use the Azure PowerShell, check out our most common scripts for [Linux VMs](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Windows VMs](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Web Apps](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), and [SQL Databases](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span></span>

## <a name="next-steps"></a><span data-ttu-id="46094-182">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="46094-182">Next steps</span></span>

* [<span data-ttu-id="46094-183">Accedere ad Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="46094-183">Login with Azure PowerShell</span></span>](authenticate-azureps.md)
* [<span data-ttu-id="46094-184">Gestire le sottoscrizioni di Azure con Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="46094-184">Manage Azure subscriptions with Azure PowerShell</span></span>](manage-subscriptions-azureps.md)
* [<span data-ttu-id="46094-185">Creare entità servizio in Azure usando Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="46094-185">Create service principals in Azure using Azure PowerShell</span></span>](create-azure-service-principal-azureps.md)
* <span data-ttu-id="46094-186">Leggere le note sulla migrazione da una versione precedente: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span><span class="sxs-lookup"><span data-stu-id="46094-186">Read the Release notes about migrating from an older release: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span></span>
* <span data-ttu-id="46094-187">Ottenere informazioni dalla community:</span><span class="sxs-lookup"><span data-stu-id="46094-187">Get help from the community:</span></span>
  + [<span data-ttu-id="46094-188">Forum Azure su MSDN</span><span class="sxs-lookup"><span data-stu-id="46094-188">Azure forum on MSDN</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=320212)
  + [<span data-ttu-id="46094-189">stackoverflow</span><span class="sxs-lookup"><span data-stu-id="46094-189">stackoverflow</span></span>](http://go.microsoft.com/fwlink/?LinkId=320213)
