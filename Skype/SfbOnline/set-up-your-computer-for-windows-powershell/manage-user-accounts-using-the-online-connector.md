---
title: Gestire gli account utente con Online Connector
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
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Utilizzare il cmdlet Get-CsOnlineUser cmdlet di Windows PowerShell per ottenere informazioni sugli utenti Skype for Business online dell'organizzazione.
ms.openlocfilehash: 370150de08493507d7b401d7907c90f343802d88
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692651"
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="382a2-103">Gestire gli account utente con Online Connector</span><span class="sxs-lookup"><span data-stu-id="382a2-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="382a2-104">Gestione degli account utente</span><span class="sxs-lookup"><span data-stu-id="382a2-104">Manage user accounts</span></span>

<span data-ttu-id="382a2-105">Questo argomento contiene le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="382a2-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="382a2-106">Ottenere informazioni su tutti gli utenti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="382a2-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [<span data-ttu-id="382a2-107">Restituire informazioni per un utente specifico in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="382a2-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [<span data-ttu-id="382a2-108">Ottenere informazioni specifiche per utenti specifici in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="382a2-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [<span data-ttu-id="382a2-109">Restituire un elenco filtrato di utenti in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="382a2-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> <span data-ttu-id="382a2-110">Il cmdlet **Set-CsUser** è incluso anche nel set di cmdlet disponibili per gli amministratori di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="382a2-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="382a2-111">Tuttavia, **Set-CsUser** attualmente non può essere utilizzato per gestire Skype for Business online, ad eccezione dell'impostazione del parametro _AudioVideoDisabled._</span><span class="sxs-lookup"><span data-stu-id="382a2-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="382a2-112">Se si prova a eseguire il cmdlet con qualsiasi altro parametro, l'operazione non riesce e viene visualizzato un messaggio di errore simile al seguente: Impossibile impostare "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="382a2-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="382a2-113">Questo parametro è limitato in PowerShell per il tenant remoto.</span><span class="sxs-lookup"><span data-stu-id="382a2-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="382a2-114">Ottenere informazioni su tutti gli utenti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="382a2-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="382a2-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="382a2-115"><a name="BKAllUsers"> </a></span></span>

<span data-ttu-id="382a2-116">Per ottenere informazioni su tutti gli utenti abilitati per Skype for Business online, chiama il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) senza parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="382a2-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="382a2-117">Per restituire informazioni per un singolo utente selezionato casualmente (ad esempio, per usare questo account a scopo di test), chiama il cmdlet **Get-CsOnlineUser** e imposta il parametro _ResultSize_ su 1.</span><span class="sxs-lookup"><span data-stu-id="382a2-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="382a2-118">In questo modo il cmdlet **Get-CsOnlineUser** restituirà informazioni per un solo utente, indipendentemente dal numero di utenti presenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="382a2-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="382a2-119">Per restituire informazioni per cinque utenti, impostare il valore del parametro _ResultSize_ su 5.</span><span class="sxs-lookup"><span data-stu-id="382a2-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="382a2-120">Restituire informazioni per un utente specifico in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="382a2-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="382a2-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="382a2-121"><a name="BKSpecificUser"> </a></span></span>

<span data-ttu-id="382a2-122">Esistono diversi modi per fare riferimento a un account utente specifico quando chiami il cmdlet [Get-CsOnlineUser.](https://go.microsoft.com/fwlink/p/?linkid=849603)</span><span class="sxs-lookup"><span data-stu-id="382a2-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="382a2-123">È possibile usare il nome visualizzato di Servizi di dominio Active Directory dell'utente.</span><span class="sxs-lookup"><span data-stu-id="382a2-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="382a2-124">Puoi utilizzare l'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="382a2-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="382a2-125">È possibile usare il nome dell'entità utente (UPN) dell'utente.</span><span class="sxs-lookup"><span data-stu-id="382a2-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="382a2-126">Ottenere informazioni specifiche per utenti specifici in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="382a2-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="382a2-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="382a2-127"><a name="BKSpecificUsers"> </a></span></span>

<span data-ttu-id="382a2-128">Per impostazione predefinita, il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) restituisce un'enorme quantità di informazioni per ogni account utente di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="382a2-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="382a2-129">Se si è interessati solo a un sottoinsieme di queste informazioni, determinare il pipe dei dati restituiti al cmdlet **Select-Object.**</span><span class="sxs-lookup"><span data-stu-id="382a2-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="382a2-130">Ad esempio, questo comando restituisce tutti i dati relativi all'utente Ken Myer e quindi usa il cmdlet **Select-Object** per limitare le informazioni visualizzate sullo schermo al nome visualizzato e al dial plan di Servizi di dominio Active Directory di Ken.</span><span class="sxs-lookup"><span data-stu-id="382a2-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="382a2-131">Il comando seguente restituisce il nome visualizzato e il piano di chiamata per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="382a2-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="382a2-132">Per trovare le proprietà di un account utente di Skype for Business online, utilizza il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="382a2-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="382a2-133">Restituire un elenco filtrato di utenti in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="382a2-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="382a2-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="382a2-134"><a name="BKListofUsers"> </a></span></span>

<span data-ttu-id="382a2-135">Usando il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e i parametri _LdapFilter_ o _Filter,_ puoi recuperare facilmente informazioni su un set di utenti mirato.</span><span class="sxs-lookup"><span data-stu-id="382a2-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="382a2-136">Ad esempio, questo comando restituisce tutti gli utenti che lavorano nel reparto Finance.</span><span class="sxs-lookup"><span data-stu-id="382a2-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="382a2-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="382a2-137">Related topics</span></span>
[<span data-ttu-id="382a2-138">Configurare il computer per la gestione di Skype for Business online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="382a2-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


