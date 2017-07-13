---
title: <span data-ttu-id="f18b6-101">Accedere ad Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="f18b6-101">Log in with Azure PowerShell</span></span>
description: <span data-ttu-id="f18b6-102">Accedere ad Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="f18b6-102">Log in with Azure PowerShell</span></span>
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.openlocfilehash: f6d249ca5bb09c4fe8445ba5b339ffa6012815ed
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="f18b6-103">Accedere ad Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="f18b6-103">Log in with Azure PowerShell</span></span>
<a id="log-in-with-azure-powershell" class="xliff"></a>

<span data-ttu-id="f18b6-104">Azure PowerShell supporta più metodi di accesso.</span><span class="sxs-lookup"><span data-stu-id="f18b6-104">Azure PowerShell supports multiple login methods.</span></span> <span data-ttu-id="f18b6-105">Il modo più semplice per iniziare consiste nell'accedere in modo interattivo dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f18b6-105">The simplest way to get started is to log in interactively at the command line.</span></span>

## <span data-ttu-id="f18b6-106">Accesso interattivo</span><span class="sxs-lookup"><span data-stu-id="f18b6-106">Interactive log in</span></span>
<a id="interactive-log-in" class="xliff"></a>

1. <span data-ttu-id="f18b6-107">Digitare `Login-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="f18b6-107">Type `Login-AzureRmAccount`.</span></span> <span data-ttu-id="f18b6-108">Apparirà una finestra di dialogo che richiede le credenziali di Azure.</span><span class="sxs-lookup"><span data-stu-id="f18b6-108">You will get dialog box asking for your Azure credentials.</span></span>

2. <span data-ttu-id="f18b6-109">Digitare l'indirizzo di posta elettronica e la password associati all'account.</span><span class="sxs-lookup"><span data-stu-id="f18b6-109">Type the email address and password associated with your account.</span></span> <span data-ttu-id="f18b6-110">Le informazioni delle credenziali vengono autenticate e salvate in Azure, quindi la finestra viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="f18b6-110">Azure authenticates and saves the credential information, and then closes the window.</span></span>

## <span data-ttu-id="f18b6-111">Accesso con un'entità servizio</span><span class="sxs-lookup"><span data-stu-id="f18b6-111">Log in with a service principal</span></span>
<a id="log-in-with-a-service-principal" class="xliff"></a>

<span data-ttu-id="f18b6-112">Le entità servizio consentono di creare account non interattivi da usare per la modifica delle risorse.</span><span class="sxs-lookup"><span data-stu-id="f18b6-112">Service principals provide a way for you to create non-interactive accounts that you can use to manipulate resources.</span></span> <span data-ttu-id="f18b6-113">Le entità servizio sono simili ad account utente a cui è possibile applicare delle regole mediante Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f18b6-113">Service principals are like user accounts to which you can apply rules using Azure Active Directory.</span></span> <span data-ttu-id="f18b6-114">Concedendo le autorizzazioni minime necessarie a un'entità servizio, è possibile garantire una sicurezza ancora maggiore agli script di automazione.</span><span class="sxs-lookup"><span data-stu-id="f18b6-114">By granting the minimum permissions needed to a service principal, you can ensure your automation scripts are even more secure.</span></span>

1. <span data-ttu-id="f18b6-115">Se non si dispone già di un'entità servizio, [crearne una](create-azure-service-principal-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="f18b6-115">If you don't already have a service principal, [create one](create-azure-service-principal-azureps.md).</span></span>

2. <span data-ttu-id="f18b6-116">Accedere con l'entità servizio.</span><span class="sxs-lookup"><span data-stu-id="f18b6-116">Log in with the service principal.</span></span>

    ```powershell
    Login-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
    ```

    <span data-ttu-id="f18b6-117">Per ottenere il TenantId, accedere in modo interattivo e quindi recuperare il TenantId dalla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="f18b6-117">To get your TenantId, log in interactively and then get the TenantId from your subscription.</span></span>

    ```powershell
    Get-AzureRmSubscription
    ```

    ```
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Production Subscription
    CurrentStorageAccount :
    ```

## <span data-ttu-id="f18b6-118">Accedere a un altro cloud</span><span class="sxs-lookup"><span data-stu-id="f18b6-118">Log in to another Cloud</span></span>
<a id="log-in-to-another-cloud" class="xliff"></a>

<span data-ttu-id="f18b6-119">I servizi cloud di Azure offrono più ambienti conformi alle norme in materia di gestione dei dati vigenti in diversi paesi.</span><span class="sxs-lookup"><span data-stu-id="f18b6-119">Azure cloud services provide different environments that adhere to the data-handling regulations of various governments.</span></span> <span data-ttu-id="f18b6-120">Se l'account di Azure si trova in un cloud governativo è necessario specificare l'ambiente quando si accede.</span><span class="sxs-lookup"><span data-stu-id="f18b6-120">If your Azure account is in one the government clouds, you need to specify the environment when you sign in.</span></span> <span data-ttu-id="f18b6-121">Ad esempio, se l'account si trova nel cloud della Cina, accedere usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f18b6-121">For example, if you account is in the China cloud you sign on using the following command:</span></span>

```powershell
Login-AzureRmAccount -EnvironmentName AzureChinaCloud
```

<span data-ttu-id="f18b6-122">Usare il comando seguente per visualizzare un elenco degli ambienti disponibili:</span><span class="sxs-lookup"><span data-stu-id="f18b6-122">Use the following command to get a list of available environments:</span></span>

```powershell
Get-AzureRmEnvironment | Select-Object Name
```

```
Name
----
AzureCloud
AzureChinaCloud
AzureUSGovernment
AzureGermanCloud
```

## <span data-ttu-id="f18b6-123">Altre informazioni sulla gestione degli accessi in base al ruolo in Azure</span><span class="sxs-lookup"><span data-stu-id="f18b6-123">Learn more about managing Azure role-based access</span></span>
<a id="learn-more-about-managing-azure-role-based-access" class="xliff"></a>

<span data-ttu-id="f18b6-124">Per altre informazioni su autenticazione e gestione delle sottoscrizioni in Azure, vedere [Gestire account, sottoscrizioni e ruoli amministrativi](/azure/active-directory/role-based-access-control-configure).</span><span class="sxs-lookup"><span data-stu-id="f18b6-124">For more information about authentication and subscription management in Azure, see [Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure).</span></span>

<span data-ttu-id="f18b6-125">Cmdlet di Azure PowerShell per la gestione dei ruoli</span><span class="sxs-lookup"><span data-stu-id="f18b6-125">Azure PowerShell cmdlets for role management</span></span>

* [<span data-ttu-id="f18b6-126">Get-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="f18b6-126">Get-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleAssignment)
* [<span data-ttu-id="f18b6-127">Get-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="f18b6-127">Get-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleDefinition)
* [<span data-ttu-id="f18b6-128">New-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="f18b6-128">New-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleAssignment)
* [<span data-ttu-id="f18b6-129">New-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="f18b6-129">New-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleDefinition)
* [<span data-ttu-id="f18b6-130">Remove-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="f18b6-130">Remove-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleAssignment)
* [<span data-ttu-id="f18b6-131">Remove-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="f18b6-131">Remove-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleDefinition)
* [<span data-ttu-id="f18b6-132">Set-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="f18b6-132">Set-AzureRmRoleDefinition</span></span>](/powershell/moduel/AzureRM.Resources/Set-AzureRmRoleDefinition)