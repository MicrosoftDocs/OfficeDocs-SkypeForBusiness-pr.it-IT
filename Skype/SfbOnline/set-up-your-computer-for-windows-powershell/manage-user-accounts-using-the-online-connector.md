---
title: Gestione degli account utente utilizzando il connettore in linea
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Utilizzare il cmdlet Get-CsOnlineUser in Windows PowerShell per ottenere informazioni su Skype dell'organizzazione per gli utenti aziendali Online.
ms.openlocfilehash: 4c2e7e581146c179f3171f38e82eff219871a90a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893534"
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="81955-103">Gestione degli account utente utilizzando il connettore in linea</span><span class="sxs-lookup"><span data-stu-id="81955-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="81955-104">Gestione degli account utente</span><span class="sxs-lookup"><span data-stu-id="81955-104">Manage user accounts</span></span>

<span data-ttu-id="81955-105">In questo argomento contiene le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="81955-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="81955-106">Ottenere informazioni su tutti gli utenti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="81955-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [<span data-ttu-id="81955-107">Restituire informazioni per un utente specifico Skype Business online</span><span class="sxs-lookup"><span data-stu-id="81955-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [<span data-ttu-id="81955-108">Restituire informazioni specifiche per utenti specifici in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="81955-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [<span data-ttu-id="81955-109">Restituire un elenco filtrato degli utenti in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="81955-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> <span data-ttu-id="81955-110">Il cmdlet **Set-CsUser** è anche incluso nel set di cmdlet disponibili per Skype per gli amministratori aziendali in linea.</span><span class="sxs-lookup"><span data-stu-id="81955-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="81955-111">Tuttavia, **Set-CsUser** attualmente non può essere utilizzato per gestire Skype Business online, fatta eccezione per l'impostazione del parametro _AudioVideoDisabled_ .</span><span class="sxs-lookup"><span data-stu-id="81955-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="81955-112">Se si tenta di eseguire il cmdlet con un altro parametro avrà esito negativo con un messaggio di errore simile al seguente: non è possibile impostare "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="81955-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="81955-113">Questo parametro è con restrizioni all'interno di Remote PowerShell Tenant.</span><span class="sxs-lookup"><span data-stu-id="81955-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="81955-114">Ottenere informazioni su tutti gli utenti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="81955-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="81955-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="81955-115"></span></span>

<span data-ttu-id="81955-116">Per restituire informazioni su tutti gli utenti che sono stati abilitati per Skype Business online, chiamare il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) senza alcun parametro aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="81955-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```
Get-CsOnlineUser
```

<span data-ttu-id="81955-117">Per restituire informazioni per un singolo utente selezionato in modo casuale (ad esempio, per utilizzare questo account per i test), chiamare il cmdlet **Get-CsOnlineUser** e impostare il parametro _ResultSize_ su 1.</span><span class="sxs-lookup"><span data-stu-id="81955-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="81955-118">Che fa sì che il cmdlet **Get-CsOnlineUser** restituisca informazioni per un singolo utente, indipendentemente dal numero di utenti nell'organizzazione sono presenti.</span><span class="sxs-lookup"><span data-stu-id="81955-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="81955-119">Per restituire informazioni relative a cinque utenti, impostare il valore del parametro _ResultSize_ su 5.</span><span class="sxs-lookup"><span data-stu-id="81955-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="81955-120">Restituire informazioni per un utente specifico Skype Business online</span><span class="sxs-lookup"><span data-stu-id="81955-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="81955-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="81955-121"></span></span>

<span data-ttu-id="81955-122">Esistono diversi modi per fare riferimento a un account utente specifico quando si chiama il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="81955-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="81955-123">È possibile utilizzare i servizi di dominio Active Directory (AD DS) nome visualizzato dell'utente.</span><span class="sxs-lookup"><span data-stu-id="81955-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="81955-124">È possibile utilizzare l'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="81955-124">You can use the user's SIP address.</span></span>

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="81955-125">È possibile utilizzare nome entità utente dell'utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="81955-125">You can use the user's user principal name (UPN).</span></span>

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="81955-126">Restituire informazioni specifiche per utenti specifici in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="81955-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="81955-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="81955-127"></span></span>

<span data-ttu-id="81955-128">Per impostazione predefinita, il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) restituisce una grande quantità di informazioni per ogni Skype per account utente in linea aziendale.</span><span class="sxs-lookup"><span data-stu-id="81955-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="81955-129">Se si è interessati solo un sottoinsieme di tali informazioni, eseguire il piping i dati restituiti al cmdlet **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="81955-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="81955-130">Ad esempio, questo comando restituisce tutti i dati per l'utente Ken Myer e quindi viene utilizzato il cmdlet **Select-Object** per limitare le informazioni visualizzato sullo schermo al nome visualizzato di Active Directory di Ken e dial plan.</span><span class="sxs-lookup"><span data-stu-id="81955-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="81955-131">Il comando seguente restituisce il nome visualizzato e un dial plan per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="81955-131">The following command returns the display name and dial plan for all your users.</span></span>

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="81955-132">Per trovare le proprietà di un Skype per l'account utente in linea di Business, utilizzare il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="81955-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="81955-133">Restituire un elenco filtrato degli utenti in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="81955-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="81955-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="81955-134"></span></span>

<span data-ttu-id="81955-135">Utilizzando il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e i parametri _Filter_ o _LdapFilter_ , è possibile ottenere facilmente informazioni su un insieme specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="81955-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="81955-136">Ad esempio, questo comando restituisce tutti gli utenti che lavorano nel reparto Finance.</span><span class="sxs-lookup"><span data-stu-id="81955-136">For example, this command returns all the users who work in the Finance department.</span></span>

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="81955-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="81955-137">Related topics</span></span>
[<span data-ttu-id="81955-138">Configurare il computer per Skype per la gestione in linea aziendale tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="81955-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


