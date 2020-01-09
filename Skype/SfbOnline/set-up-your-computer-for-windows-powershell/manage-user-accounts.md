---
title: Gestione degli account utente
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Usa il cmdlet Get-CsOnlineUser in Windows PowerShell per ottenere informazioni sugli utenti Skype for business online dell'organizzazione.
ms.openlocfilehash: a61d698b5218c37c786bdba9ab7f7711e9ab47b4
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989241"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="294f2-103">Gestione degli account utente</span><span class="sxs-lookup"><span data-stu-id="294f2-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="294f2-104">Gestione degli account utente</span><span class="sxs-lookup"><span data-stu-id="294f2-104">Manage user accounts</span></span>

<span data-ttu-id="294f2-105">Questo argomento contiene le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294f2-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="294f2-106">Ottenere informazioni su tutti gli utenti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="294f2-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="294f2-107">Restituire informazioni per un utente specifico in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="294f2-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="294f2-108">Restituire informazioni specifiche per utenti specifici in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="294f2-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="294f2-109">Restituire un elenco filtrato degli utenti in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="294f2-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="294f2-110">Il cmdlet **Set-CsUser** è incluso anche nel set di cmdlet disponibili per gli amministratori di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="294f2-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="294f2-111">Tuttavia, **Set-CsUser** non può attualmente essere usato per gestire Skype for business online, tranne che per l'impostazione del parametro _AudioVideoDisabled_ .</span><span class="sxs-lookup"><span data-stu-id="294f2-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="294f2-112">Se si tenta di eseguire il cmdlet con qualsiasi altro parametro, non verrà visualizzato un messaggio di errore simile al seguente: non è possibile impostare "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="294f2-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="294f2-113">Questo parametro è limitato all'interno di PowerShell del tenant remoto.</span><span class="sxs-lookup"><span data-stu-id="294f2-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="294f2-114">Ottenere informazioni su tutti gli utenti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="294f2-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="294f2-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="294f2-115"></span></span>

<span data-ttu-id="294f2-116">Per restituire informazioni su tutti gli utenti abilitati per Skype for business online, chiama il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) senza parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="294f2-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="294f2-117">Per restituire informazioni per un singolo utente selezionato in modo casuale, ad esempio per usare questo account per scopi di test, chiama il cmdlet **Get-CsOnlineUser** e imposta il parametro _ResultSize_ su 1.</span><span class="sxs-lookup"><span data-stu-id="294f2-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="294f2-118">Questo fa sì che il cmdlet **Get-CsOnlineUser** restituisca le informazioni relative a un solo utente, indipendentemente dal numero di utenti presenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="294f2-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="294f2-119">Per restituire informazioni per cinque utenti, imposta il valore del parametro _ResultSize_ su 5.</span><span class="sxs-lookup"><span data-stu-id="294f2-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="294f2-120">Restituire informazioni per un utente specifico in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="294f2-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="294f2-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="294f2-121"></span></span>

<span data-ttu-id="294f2-122">Esistono diversi modi per fare riferimento a un account utente specifico quando si chiama il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="294f2-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="294f2-123">È possibile usare il nome visualizzato di servizi di dominio Active Directory (AD DS) dell'utente.</span><span class="sxs-lookup"><span data-stu-id="294f2-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="294f2-124">Puoi usare l'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="294f2-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="294f2-125">È possibile usare il nome dell'entità utente (UPN) dell'utente.</span><span class="sxs-lookup"><span data-stu-id="294f2-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="294f2-126">Restituire informazioni specifiche per utenti specifici in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="294f2-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="294f2-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="294f2-127"></span></span>

<span data-ttu-id="294f2-128">Per impostazione predefinita, il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) restituisce una grande quantità di informazioni per ogni account utente di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="294f2-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="294f2-129">Se si è interessati solo a un sottoinsieme di queste informazioni, eseguire il piping dei dati restituiti al cmdlet **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="294f2-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="294f2-130">Ad esempio, questo comando restituisce tutti i dati per l'utente Ken e quindi usa il cmdlet **Select-Object** per limitare le informazioni visualizzate sullo schermo al nome visualizzato e al dial plan di Ken ad DS.</span><span class="sxs-lookup"><span data-stu-id="294f2-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="294f2-131">Il comando seguente restituisce il nome visualizzato e il dial plan per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="294f2-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="294f2-132">Per trovare le proprietà di un account utente di Skype for business online, usare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="294f2-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="294f2-133">Restituire un elenco filtrato degli utenti in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="294f2-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="294f2-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="294f2-134"></span></span>

<span data-ttu-id="294f2-135">Usando il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e i parametri _LdapFilter_ o _Filter_ puoi restituire facilmente informazioni su un set di utenti mirato.</span><span class="sxs-lookup"><span data-stu-id="294f2-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="294f2-136">Ad esempio, questo comando restituisce tutti gli utenti che lavorano nel reparto Finanza.</span><span class="sxs-lookup"><span data-stu-id="294f2-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="294f2-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="294f2-137">Related topics</span></span>
[<span data-ttu-id="294f2-138">Configurare il computer per la gestione di Skype for business online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="294f2-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


