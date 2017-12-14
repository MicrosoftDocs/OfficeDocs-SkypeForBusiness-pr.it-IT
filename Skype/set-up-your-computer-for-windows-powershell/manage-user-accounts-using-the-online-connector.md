---
title: "Gestire gli account utente utilizzando il Skype per Business Connector Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/23/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
description: "Use the Get-CsOnlineUser cmdlet in Windows PowerShell to get information about your organization's Skype for Business Online users."
---

# Gestire gli account utente utilizzando il Skype per Business Connector Online

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/a226b0d4-6359-42b8-808d-4b8ab3736d3b). 
  
## Gestione degli account utente

Questo argomento contiene le sezioni seguenti:
  
- [Ottenere informazioni su tutti gli utenti di Skype for Business Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoAboutAllUsers)
    
- [Ottenere informazioni su un utente specifico in Skype for Business Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoSpecificUser)
    
- [Ottenere informazioni specifiche su utenti specifici in Skype for Business Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturninfoSpecificUsers)
    
- [Visualizzare un elenco utenti filtrato in Skype for Business Online ](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnFilteredListofUsers)
    
> [!NOTE]
> Il cmdlet **Set-CsUser** è incluso anche nel set di cmdlet disponibili per gli amministratori di Skype for Business online. Tuttavia, non è possibile utilizzare **Set-CsUser** per gestire Skype for Business online, tranne per l'impostazione del parametro _AudioVideoDisabled_. Se tenti di eseguire il cmdlet con qualsiasi altro parametro, l'operazione avrà esito negativo e verrà visualizzato un messaggio di errore simile al seguente: Impossibile impostare "SipAddress". Il parametro è limitato in PowerShell per il tenant remoto. 
  
### Ottenere informazioni su tutti gli utenti di Skype for Business Online
<a name="BKMK_ReturnInfoAboutAllUsers"> </a>

Per ottenere informazioni su tutti gli utenti abilitati per Skype for Business online, chiama il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) senza parametri aggiuntivi.
  
```
Get-CsOnlineUser
```

Per ottenere informazioni su un singolo utente selezionato casualmente, ad esempio per usare l'account a scopo di test, chiama il cmdlet **Get-CsOnlineUser** e imposta il parametro _ResultSize_ su 1.
  
```
Get-CsOnlineUser -ResultSize 1
```

In questo modo il cmdlet **Get-CsOnlineUser** restituirà informazioni per un solo utente, indipendentemente dal numero di utenti presenti nell'organizzazione. Per ottenere informazioni per cinque utenti, impostare il valore del parametro _ResultSize_ su 5.
  
```
Get-CsOnlineUser -ResultSize 5
```

### Ottenere informazioni su un utente specifico in Skype for Business Online
<a name="BKMK_ReturnInfoSpecificUser"> </a>

Esistono diversi modi per fare riferimento a un account utente specifico quando viene usato il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603). Puoi usare il nome visualizzato Servizi di dominio Active Directory dell'utente.
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

Puoi usare l'indirizzo SIP dell'utente.
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

In alternativa, puoi usare il nome dell'entità utente (UPN) per l'utente.
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### Ottenere informazioni specifiche su utenti specifici in Skype for Business Online
<a name="BKMK_ReturninfoSpecificUsers"> </a>

Per impostazione predefinita, il cmdlet [Get-CsOnlineUser](https://support.office.com/article/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) restituisce un'enorme quantità di informazioni per ogni account utente di Skype for Business online. Se sei interessato solo a una parte di queste informazioni, devi inviare una pipe dei dati restituiti al cmdlet **Select-Object**. Ad esempio, il comando seguente restituisce tutti i dati relativi all'utente Ken Myer, quindi usa il cmdlet **Select-Object** per limitare le informazioni visualizzate sullo schermo al dial plan e al nome visualizzato di Servizi di dominio Active Directory di Ken Myer.
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Il comando seguente restituisce il nome visualizzato e il dial plan di tutti gli utenti.
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Per trovare le proprietà di un account utente di Skype for Business online, usare questo comando.
  
```
Get-CsOnlineUser | Get-Member
```

### Visualizzare un elenco utenti filtrato in Skype for Business Online
<a name="BKMK_ReturnFilteredListofUsers"> </a>

Mediante il cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e il parametro _LdapFilter_ o _Filter_, puoi recuperare facilmente informazioni su un set di utenti specifico. Ad esempio, questo comando restituisce tutti gli utenti che lavorano nel reparto Finance.
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

