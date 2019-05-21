---
title: Gestire gli account utente con il connettore online
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
ms.openlocfilehash: 5be51ac39f4a5bd07788a3341114d72a8556cc1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284681"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Gestire gli account utente con il connettore online

## <a name="manage-user-accounts"></a>Gestione degli account utente

Questo argomento contiene le sezioni seguenti:

- [Ottenere informazioni su tutti gli utenti di Lync Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Restituire informazioni per un utente specifico in Skype for business online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Restituire informazioni specifiche per utenti specifici in Skype for business online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Restituire un elenco filtrato degli utenti in Skype for business online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> Il cmdlet **Set-CsUser** è incluso anche nel set di cmdlet disponibili per gli amministratori di Skype for business online. Tuttavia, **Set-CsUser** non può attualmente essere usato per gestire Skype for business online, tranne che per l'impostazione del parametro _AudioVideoDisabled_ . Se si tenta di eseguire il cmdlet con qualsiasi altro parametro, non verrà visualizzato un messaggio di errore simile al seguente: non è possibile impostare "SipAddress". Questo parametro è limitato all'interno di PowerShell del tenant remoto.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Ottenere informazioni su tutti gli utenti di Lync Online
<a name="BKAllUsers"> </a>

Per restituire informazioni su tutti gli utenti abilitati per Skype for business online, chiama il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) senza parametri aggiuntivi.

```
Get-CsOnlineUser
```

Per restituire informazioni per un singolo utente selezionato in modo casuale, ad esempio per usare questo account per scopi di test, chiama il cmdlet **Get-CsOnlineUser** e imposta il parametro _ResultSize_ su 1.

```
Get-CsOnlineUser -ResultSize 1
```

Questo fa sì che il cmdlet **Get-CsOnlineUser** restituisca le informazioni relative a un solo utente, indipendentemente dal numero di utenti presenti nell'organizzazione. Per restituire informazioni per cinque utenti, imposta il valore del parametro _ResultSize_ su 5.

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Restituire informazioni per un utente specifico in Skype for business online
<a name="BKSpecificUser"> </a>

Esistono diversi modi per fare riferimento a un account utente specifico quando si chiama il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . È possibile usare il nome visualizzato di servizi di dominio Active Directory (AD DS) dell'utente.

```
Get-CsOnlineUser -Identity "Ken Myer"
```

Puoi usare l'indirizzo SIP dell'utente.

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

È possibile usare il nome dell'entità utente (UPN) dell'utente.

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Restituire informazioni specifiche per utenti specifici in Skype for business online
<a name="BKSpecificUsers"> </a>

Per impostazione predefinita, il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) restituisce una grande quantità di informazioni per ogni account utente di Skype for business online. Se si è interessati solo a un sottoinsieme di queste informazioni, eseguire il piping dei dati restituiti al cmdlet **Select-Object** . Ad esempio, questo comando restituisce tutti i dati per l'utente Ken e quindi usa il cmdlet **Select-Object** per limitare le informazioni visualizzate sullo schermo al nome visualizzato e al dial plan di Ken ad DS.

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Il comando seguente restituisce il nome visualizzato e il dial plan per tutti gli utenti.

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Per trovare le proprietà di un account utente di Skype for business online, usare il comando seguente.

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Restituire un elenco filtrato degli utenti in Skype for business online
<a name="BKListofUsers"> </a>

Usando il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e i parametri _LdapFilter_ o _Filter_ puoi restituire facilmente informazioni su un set di utenti mirato. Ad esempio, questo comando restituisce tutti gli utenti che lavorano nel reparto Finanza.

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione di Skype for business online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


