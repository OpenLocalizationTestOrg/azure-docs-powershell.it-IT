---
title: <span data-ttu-id="bcc30-101">Formattazione dei risultati delle query | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="bcc30-101">Formatting query results | Microsoft Docs</span></span>
description: <span data-ttu-id="bcc30-102">Come eseguire una query delle risorse in Azure e formattare i risultati.</span><span class="sxs-lookup"><span data-stu-id="bcc30-102">How to query for resources in Azure and format the results.</span></span>
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/30/2017
ms.openlocfilehash: 2b23af1ef84b7c91abdcbe0738b29b068f82fd32
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="bcc30-103">Formattazione dei risultati delle query</span><span class="sxs-lookup"><span data-stu-id="bcc30-103">Formatting query results</span></span>
<a id="formatting-query-results" class="xliff"></a>

<span data-ttu-id="bcc30-104">Per impostazione predefinita, ogni cmdlet PowerShell genera un output con formattazione predefinita, per semplificarne la lettura.</span><span class="sxs-lookup"><span data-stu-id="bcc30-104">By default each PowerShell cmdlet has predefined formatting of output making it easy to read.</span></span>  <span data-ttu-id="bcc30-105">PowerShell offre inoltre la flessibilità necessaria per modificare l'output o convertire l'output del cmdlet in un formato diverso con i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcc30-105">PowerShell also provides the flexibility to adjust the output or convert the cmdlet output to a different format with the following cmdlets:</span></span>

| <span data-ttu-id="bcc30-106">Formattazione</span><span class="sxs-lookup"><span data-stu-id="bcc30-106">Formatting</span></span>      | <span data-ttu-id="bcc30-107">Conversione</span><span class="sxs-lookup"><span data-stu-id="bcc30-107">Conversion</span></span>       |
|-----------------|------------------|
| `Format-Custom` | `ConvertTo-Csv`  |
| `Format-List`   | `ConvertTo-Html` |
| `Format-Table`  | `ConvertTo-Json` |
| `Format-Wide`   | `ConvertTo-Xml`  |

## <span data-ttu-id="bcc30-108">Esempi di formattazione</span><span class="sxs-lookup"><span data-stu-id="bcc30-108">Formatting examples</span></span>
<a id="formatting-examples" class="xliff"></a>

<span data-ttu-id="bcc30-109">L'esempio seguente mostra un elenco di macchine virtuali di Azure nella sottoscrizione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bcc30-109">In this example we get a list of Azure VMs in our default subscription.</span></span>  <span data-ttu-id="bcc30-110">Per impostazione predefinita, il comando Get-AzureRmVM esegue l'output in formato tabella.</span><span class="sxs-lookup"><span data-stu-id="bcc30-110">The Get-AzureRmVM command defaults output into a table format.</span></span>

```powershell
Get-AzureRmVM
```

```
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

<span data-ttu-id="bcc30-111">Se si desidera limitare le colonne restituite è possibile usare il cmdlet `Format-Table`.</span><span class="sxs-lookup"><span data-stu-id="bcc30-111">If you would like to limit the columns returned you can use the `Format-Table` cmdlet.</span></span> <span data-ttu-id="bcc30-112">Nell'esempio seguente si ottiene lo stesso elenco di macchine virtuali, ma l'output è limitato al solo nome della macchina virtuale, al gruppo di risorse e al percorso della macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="bcc30-112">In the following example we get the same list of virtual machines but restrict the output to just the name of the VM, the resource group, and the location of the VM.</span></span>  <span data-ttu-id="bcc30-113">Il parametro `-Autosize` ridimensiona le colonne in base alla dimensione dei dati.</span><span class="sxs-lookup"><span data-stu-id="bcc30-113">The `-Autosize` parameter sizes the columns according to the size of the data.</span></span>

```powershell
Get-AzureRmVM | Format-Table Name,ResourceGroupName,Location -AutoSize
```

```
Name          ResourceGroupName Location
----          ----------------- --------
MyUnbuntu1610 MYWESTEURG        westeurope
MyWin2016VM   MYWESTEURG        westeurope
```

<span data-ttu-id="bcc30-114">Se lo si preferisce, è possibile visualizzare le informazioni in formato elenco.</span><span class="sxs-lookup"><span data-stu-id="bcc30-114">If you would prefer you can view information in a list format.</span></span> <span data-ttu-id="bcc30-115">L'esempio seguente illustra questa opzione, con l'uso del cmdlet `Format-List`.</span><span class="sxs-lookup"><span data-stu-id="bcc30-115">The following example shows this using the`Format-List` cmdlet.</span></span>

```powershell
Get-AzureVM | Format-List Name,VmId,Location,ResourceGroupName
```

```
Name              : MyUnbuntu1610
VmId              : 33422f9b-e339-4704-bad8-dbe094585496
Location          : westeurope
ResourceGroupName : MYWESTEURG

Name              : MyWin2016VM
VmId              : 4650c755-fc2b-4fc7-a5bc-298d5c00808f
Location          : westeurope
ResourceGroupName : MYWESTEURG
```

## <span data-ttu-id="bcc30-116">Conversione in altri tipi di dati</span><span class="sxs-lookup"><span data-stu-id="bcc30-116">Converting to other data types</span></span>
<a id="converting-to-other-data-types" class="xliff"></a>

<span data-ttu-id="bcc30-117">PowerShell offre inoltre più formati di output, da usare in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="bcc30-117">PowerShell also offers multiple output format you can use to meet your needs.</span></span>  <span data-ttu-id="bcc30-118">Nell'esempio seguente viene usato il cmdlet `Select-Object` per recuperare gli attributi delle macchine virtuali nella sottoscrizione e convertire l'output in formato CSV per importarlo facilmente in un database o un foglio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="bcc30-118">In the following example we use the `Select-Object` cmdlet to get attributes of the virtual machines in our subscription and and convert the output to CSV format for easy import into a database or spreadsheet.</span></span>

```powershell
Get-AzureRmVM | Select-Object ResourceGroupName,Id,VmId,Name,Location,ProvisioningState | ConvertTo-Csv -NoTypeInformation
```

```
"ResourceGroupName","Id","VmId","Name","Location","ProvisioningState"
"MYWESTUERG","/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTUERG/providers/Microsoft.Compute/virtualMachines/MyUnbuntu1610","33422f9b-e339-4704-bad8-dbe094585496","MyUnbuntu1610","westeurope","Succeeded"
"MYWESTUERG","/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTUERG/providers/Microsoft.Compute/virtualMachines/MyWin2016VM","4650c755-fc2b-4fc7-a5bc-298d5c00808f","MyWin2016VM","westeurope","Succeeded"
```

<span data-ttu-id="bcc30-119">È inoltre possibile convertire l'output in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="bcc30-119">You can also convert the output into JSON format.</span></span>  <span data-ttu-id="bcc30-120">Nell'esempio seguente viene creato lo stesso elenco di macchine virtuali, ma il formato di output è modificato in JSON.</span><span class="sxs-lookup"><span data-stu-id="bcc30-120">The following example creates the same list of VMs but changes the output format to JSON.</span></span>

```powershell
Get-AzureRmVM | Select-Object ResourceGroupName,Id,VmId,Name,Location,ProvisioningState | ConvertTo-Json
```

```
[
    {
        "ResourceGroupName":  "MYWESTEURG",
        "Id":  "/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTEURG/providers/Microsoft.Compute/virtualMachines/MyUnbuntu1610",
        "VmId":  "33422f9b-e339-4704-bad8-dbe094585496",
        "Name":  "MyUnbuntu1610",
        "Location":  "westeurope",
        "ProvisioningState":  "Succeeded"
    },
    {
        "ResourceGroupName":  "MYWESTEURG",
        "Id":  "/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTEURG/providers/Microsoft.Compute/virtualMachines/MyWin2016VM",
        "VmId":  "4650c755-fc2b-4fc7-a5bc-298d5c00808f",
        "Name":  "MyWin2016VM",
        "Location":  "westeurope",
        "ProvisioningState":  "Succeeded"
    }
]
```