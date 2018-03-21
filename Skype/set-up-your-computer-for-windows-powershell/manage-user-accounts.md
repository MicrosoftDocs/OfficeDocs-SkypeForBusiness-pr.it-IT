---
title: Gestione degli account utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Utilizzare il cmdlet Get-CsOnlineUser in Windows PowerShell per ottenere informazioni su Skype dell'organizzazione per gli utenti aziendali Online.
ms.openlocfilehash: f51f2c1f723a26bfa3a815bfe7641b68c5d23b26
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="manage-user-accounts"></a><span data-ttu-id="0a5aa-103">Gestione degli account utente</span><span class="sxs-lookup"><span data-stu-id="0a5aa-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="0a5aa-104">Gestione degli account utente</span><span class="sxs-lookup"><span data-stu-id="0a5aa-104">Manage user accounts</span></span>

<span data-ttu-id="0a5aa-105">In questo argomento contiene le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a5aa-105">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="0a5aa-106">Restituire informazioni su tutti i Skype per gli utenti aziendali Online</span><span class="sxs-lookup"><span data-stu-id="0a5aa-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)
    
- [<span data-ttu-id="0a5aa-107">Restituire informazioni per un utente specifico Skype Business online</span><span class="sxs-lookup"><span data-stu-id="0a5aa-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)
    
- [<span data-ttu-id="0a5aa-108">Restituire informazioni specifiche per utenti specifici in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="0a5aa-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)
    
- [<span data-ttu-id="0a5aa-109">Restituire un elenco filtrato degli utenti in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="0a5aa-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)
    
> [!NOTE]
> <span data-ttu-id="0a5aa-110">Il cmdlet **Set-CsUser** è anche incluso nel set di cmdlet disponibili per Skype per gli amministratori aziendali in linea.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="0a5aa-111">Tuttavia, **Set-CsUser** attualmente non può essere utilizzato per gestire Skype Business online, fatta eccezione per l'impostazione del parametro _AudioVideoDisabled_ .</span><span class="sxs-lookup"><span data-stu-id="0a5aa-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="0a5aa-112">Se si tenta di eseguire il cmdlet con un altro parametro avrà esito negativo con un messaggio di errore simile al seguente: non è possibile impostare "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="0a5aa-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="0a5aa-113">Questo parametro è con restrizioni all'interno di Remote PowerShell Tenant.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="0a5aa-114">Ottenere informazioni su tutti gli utenti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="0a5aa-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="0a5aa-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="0a5aa-115"></span></span>

<span data-ttu-id="0a5aa-116">Per restituire informazioni su tutti gli utenti che sono stati abilitati per Skype Business online, chiamare il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) senza alcun parametro aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>
  
```
Get-CsOnlineUser
```

<span data-ttu-id="0a5aa-117">Per restituire informazioni per un singolo utente selezionato in modo casuale (ad esempio, per utilizzare questo account per i test), chiamare il cmdlet **Get-CsOnlineUser** e impostare il parametro _ResultSize_ su 1.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>
  
```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="0a5aa-118">Che fa sì che il cmdlet **Get-CsOnlineUser** restituisca informazioni per un singolo utente, indipendentemente dal numero di utenti nell'organizzazione sono presenti.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="0a5aa-119">Per restituire informazioni relative a cinque utenti, impostare il valore del parametro _ResultSize_ su 5.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="0a5aa-120">Restituire informazioni per un utente specifico Skype Business online</span><span class="sxs-lookup"><span data-stu-id="0a5aa-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="0a5aa-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="0a5aa-121"></span></span>

<span data-ttu-id="0a5aa-122">Esistono diversi modi per fare riferimento a un account utente specifico quando si chiama il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="0a5aa-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="0a5aa-123">È possibile utilizzare i servizi di dominio Active Directory (AD DS) nome visualizzato dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="0a5aa-124">È possibile utilizzare l'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-124">You can use the user's SIP address.</span></span>
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="0a5aa-125">È possibile utilizzare nome entità utente dell'utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="0a5aa-125">You can use the user's user principal name (UPN).</span></span>
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="0a5aa-126">Restituire informazioni specifiche per utenti specifici in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="0a5aa-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="0a5aa-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="0a5aa-127"></span></span>

<span data-ttu-id="0a5aa-128">Per impostazione predefinita, il cmdlet [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) restituisce una grande quantità di informazioni per ogni Skype per account utente in linea aziendale.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-128">By default, the [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="0a5aa-129">Se si è interessati solo un sottoinsieme di tali informazioni, eseguire il piping i dati restituiti al cmdlet **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="0a5aa-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="0a5aa-130">Ad esempio, questo comando restituisce tutti i dati per l'utente Ken Myer e quindi viene utilizzato il cmdlet **Select-Object** per limitare le informazioni visualizzato sullo schermo al nome visualizzato di Active Directory di Ken e dial plan.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="0a5aa-131">Il comando seguente restituisce il nome visualizzato e un dial plan per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-131">The following command returns the display name and dial plan for all your users.</span></span>
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="0a5aa-132">Per trovare le proprietà di un Skype per l'account utente in linea di Business, utilizzare il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="0a5aa-133">Restituire un elenco filtrato degli utenti in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="0a5aa-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="0a5aa-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="0a5aa-134"></span></span>

<span data-ttu-id="0a5aa-135">Utilizzando il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e i parametri _Filter_ o _LdapFilter_ , è possibile ottenere facilmente informazioni su un insieme specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="0a5aa-136">Ad esempio, questo comando restituisce tutti gli utenti che lavorano nel reparto Finance.</span><span class="sxs-lookup"><span data-stu-id="0a5aa-136">For example, this command returns all the users who work in the Finance department.</span></span>
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="0a5aa-137">See also</span><span class="sxs-lookup"><span data-stu-id="0a5aa-137">Related topics</span></span>
[<span data-ttu-id="0a5aa-138">Configurare il computer per Skype per la gestione in linea aziendale tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a5aa-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
