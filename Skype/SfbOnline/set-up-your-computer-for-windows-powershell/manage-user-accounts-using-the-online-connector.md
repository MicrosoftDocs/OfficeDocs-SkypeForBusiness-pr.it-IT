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
# <a name="manage-user-accounts-using-the-online-connector"></a>Gestione degli account utente utilizzando il connettore in linea

## <a name="manage-user-accounts"></a>Gestione degli account utente

In questo argomento contiene le sezioni seguenti:

- [Ottenere informazioni su tutti gli utenti di Lync Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Restituire informazioni per un utente specifico Skype Business online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Restituire informazioni specifiche per utenti specifici in Skype Business online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Restituire un elenco filtrato degli utenti in Skype Business online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> Il cmdlet **Set-CsUser** è anche incluso nel set di cmdlet disponibili per Skype per gli amministratori aziendali in linea. Tuttavia, **Set-CsUser** attualmente non può essere utilizzato per gestire Skype Business online, fatta eccezione per l'impostazione del parametro _AudioVideoDisabled_ . Se si tenta di eseguire il cmdlet con un altro parametro avrà esito negativo con un messaggio di errore simile al seguente: non è possibile impostare "SipAddress". Questo parametro è con restrizioni all'interno di Remote PowerShell Tenant.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Ottenere informazioni su tutti gli utenti di Lync Online
<a name="BKAllUsers"> </a>

Per restituire informazioni su tutti gli utenti che sono stati abilitati per Skype Business online, chiamare il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) senza alcun parametro aggiuntivo.

```
Get-CsOnlineUser
```

Per restituire informazioni per un singolo utente selezionato in modo casuale (ad esempio, per utilizzare questo account per i test), chiamare il cmdlet **Get-CsOnlineUser** e impostare il parametro _ResultSize_ su 1.

```
Get-CsOnlineUser -ResultSize 1
```

Che fa sì che il cmdlet **Get-CsOnlineUser** restituisca informazioni per un singolo utente, indipendentemente dal numero di utenti nell'organizzazione sono presenti. Per restituire informazioni relative a cinque utenti, impostare il valore del parametro _ResultSize_ su 5.

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Restituire informazioni per un utente specifico Skype Business online
<a name="BKSpecificUser"> </a>

Esistono diversi modi per fare riferimento a un account utente specifico quando si chiama il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . È possibile utilizzare i servizi di dominio Active Directory (AD DS) nome visualizzato dell'utente.

```
Get-CsOnlineUser -Identity "Ken Myer"
```

È possibile utilizzare l'indirizzo SIP dell'utente.

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

È possibile utilizzare nome entità utente dell'utente (UPN).

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Restituire informazioni specifiche per utenti specifici in Skype Business online
<a name="BKSpecificUsers"> </a>

Per impostazione predefinita, il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) restituisce una grande quantità di informazioni per ogni Skype per account utente in linea aziendale. Se si è interessati solo un sottoinsieme di tali informazioni, eseguire il piping i dati restituiti al cmdlet **Select-Object** . Ad esempio, questo comando restituisce tutti i dati per l'utente Ken Myer e quindi viene utilizzato il cmdlet **Select-Object** per limitare le informazioni visualizzato sullo schermo al nome visualizzato di Active Directory di Ken e dial plan.

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Il comando seguente restituisce il nome visualizzato e un dial plan per tutti gli utenti.

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Per trovare le proprietà di un Skype per l'account utente in linea di Business, utilizzare il seguente comando.

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Restituire un elenco filtrato degli utenti in Skype Business online
<a name="BKListofUsers"> </a>

Utilizzando il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e i parametri _Filter_ o _LdapFilter_ , è possibile ottenere facilmente informazioni su un insieme specifico di utenti. Ad esempio, questo comando restituisce tutti gli utenti che lavorano nel reparto Finance.

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per Skype per la gestione in linea aziendale tramite Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


