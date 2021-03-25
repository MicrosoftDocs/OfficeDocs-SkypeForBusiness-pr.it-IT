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
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Usare il cmdlet Get-CsOnlineUser in Windows PowerShell per ottenere informazioni sugli utenti skype for business online dell'organizzazione.
ms.openlocfilehash: a4675bdb438dd81f9c72aa743134f9a444f0d1f9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113152"
---
# <a name="manage-user-accounts"></a>Gestione degli account utente

## <a name="manage-user-accounts"></a>Gestione degli account utente

Questo argomento contiene le sezioni seguenti:

- [Ottenere informazioni su tutti gli utenti di Lync Online](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [Restituire informazioni per un utente specifico in Skype for Business online](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [Restituire informazioni specifiche per utenti specifici in Skype for Business online](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [Restituire un elenco filtrato di utenti in Skype for Business online](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> Il cmdlet **Set-CsUser** è incluso anche nel set di cmdlet disponibili per gli amministratori di Skype for Business Online. Tuttavia, **Set-CsUser** non può attualmente essere usato per gestire Skype for Business online, ad eccezione dell'impostazione del parametro _AudioVideoDisabled._ Se si prova a eseguire il cmdlet con qualsiasi altro parametro, non riuscirà con un messaggio di errore simile al seguente: Impossibile impostare "SipAddress". Questo parametro è limitato in PowerShell tenant remoto.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Ottenere informazioni su tutti gli utenti di Lync Online
<a name="BKMKReturnInfoAboutAllUsers"> </a>

Per restituire informazioni su tutti gli utenti abilitati per Skype for Business online, chiamare il cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) senza parametri aggiuntivi.

```PowerShell
Get-CsOnlineUser
```

Per restituire informazioni per un singolo utente selezionato in modo casuale, ad esempio per usare questo account a scopo di test, chiamare il cmdlet **Get-CsOnlineUser** e impostare il parametro _ResultSize_ su 1.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

In questo modo il cmdlet **Get-CsOnlineUser** restituisce informazioni per un solo utente, indipendentemente dal numero di utenti presenti nell'organizzazione. Per restituire informazioni per cinque utenti, impostare il valore del _parametro ResultSize_ su 5.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Restituire informazioni per un utente specifico in Skype for Business online
<a name="BKMKReturnInfoSpecificUser"> </a>

Esistono diversi modi per fare riferimento a un account utente specifico quando si chiama il cmdlet [Get-CsOnlineUser.](/powershell/module/skype/Get-CsOnlineUser) È possibile usare il nome visualizzato di Servizi di dominio Active Directory dell'utente.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

È possibile usare l'indirizzo SIP dell'utente.

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

È possibile usare il nome dell'entità utente (UPN) dell'utente.

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Restituire informazioni specifiche per utenti specifici in Skype for Business online
<a name="BKMKReturninfoSpecificUsers"> </a>

Per impostazione predefinita, il cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) restituisce una quantità enorme di informazioni per ogni account utente di Skype for Business Online. Se si è interessati solo a un sottoinsieme di tali informazioni, eseguire il pipe dei dati restituiti al cmdlet **Select-Object.** Ad esempio, questo comando restituisce tutti i dati per l'utente Davide Davide, quindi usa il cmdlet **Select-Object** per limitare le informazioni visualizzate sullo schermo al nome visualizzato e al dial plan di Servizi di dominio Active Directory di Davide.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Il comando seguente restituisce il nome visualizzato e il piano di chiamata per tutti gli utenti.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Per trovare le proprietà di un account utente di Skype for Business Online, usare il comando seguente.

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Restituire un elenco filtrato di utenti in Skype for Business online
<a name="BKMKReturnFilteredListofUsers"> </a>

Usando il cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) e i parametri _LdapFilter_ o _Filter,_ è possibile restituire facilmente informazioni su un set di utenti mirato. Ad esempio, questo comando restituisce tutti gli utenti che lavorano nel reparto Finanze.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione online di Skype for Business usando Windows PowerShell](set-up-your-computer-for-windows-powershell.md)