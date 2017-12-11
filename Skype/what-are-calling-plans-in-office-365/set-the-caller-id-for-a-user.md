---
title: "Impostare l'ID chiamante per un utente"
ms.author: tonysmit
author: tonysmit
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
description: "Il sistema telefonico in Office 365 fornisce un ID chiamante predefinito che rappresenta il numero di telefono assegnati dell'utente. È possibile modificare o bloccare l'ID chiamante (denominato anche un ID di riga chiamare) per un utente. Sono disponibili ulteriori informazioni sull'utilizzo di ID chiamante nell'organizzazione facendo clic Come usare l'ID chiamante nella tua organizzazione."
---

# Impostare l'ID chiamante per un utente

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](c7323490-d9b7-421a-aa76-5bd485f80583.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/c7323490-d9b7-421a-aa76-5bd485f80583). 
  
Il sistema telefonico in Office 365 fornisce un ID chiamante predefinito che rappresenta il numero di telefono assegnati dell'utente. È possibile modificare o bloccare l'ID chiamante (denominato anche un ID di riga chiamare) per un utente. Sono disponibili ulteriori informazioni sull'utilizzo di ID chiamante nell'organizzazione facendo clic [Come usare l'ID chiamante nella tua organizzazione](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Non è possibile bloccare le chiamate in arrivo in Skype for Business Online. 
  
Ci sono impostazioni che possono essere modificate:
  
> [!NOTE]
> Questa funzione **non** deve essere usata per le organizzazioni in sede con Lync o Skype for Business Server.
  
- **Cambiare l'ID chiamante in uscita** È possibile sostituire l'ID chiamante di un utente, che per impostazione predefinita è il suo numero di telefono, con un altro numero di telefono. Per esempio, è possibile cambiare l'ID chiamante dell'utente dal suo numero di telefono a un numero principale usato dall'azienda o cambiare l'ID linea chiamante dal suo numero di telefono al numero principale dell'ufficio legale. È possibile cambiare l'ID chiamante in qualsiasi numero di **servizio** online o in sede (a tariffa o numero verde).
    
    > [!NOTE]
    > Se vuoi utilizzare il parametro  _Service_, devi specificare un numero di servizio valido. 
  
- **Blocco il loro ID chiamante in uscita** È possibile bloccare l'ID chiamante in uscita non verrà inviato alle chiamate PSTN in uscita dell'utente. Questa operazione blocca il numero di telefono vengano visualizzati al telefono della persona da chiamare.
    
- **Blocco il loro ID chiamante in ingresso** È possibile bloccare un utente riceva ID chiamante in qualsiasi PSTN le chiamate in arrivo.
    
> [!IMPORTANT]
> Le chiamate d'emergenza vedranno sempre il numero di telefono dell'utente (ID chiamante). 
  
Per impostazione predefinita, tutte queste impostazioni dell'ID chiamante sono **disattivate**. Questo significa che il numero di telefono di un utente Skype for Business online è visibile quando un utente effettua una chiamata a un telefono PSTN.
  
Per ulteriori informazioni su queste impostazioni e su come usarle, visita [Come usare l'ID chiamante nella tua organizzazione](how-can-caller-id-be-used-in-your-organization.md).
  
## Impostare il criterio ID chiamante

> [!NOTE]
> Per tutte le impostazioni del proprio ID chiamante in Skype for Business online, è necessario utilizzare Windows PowerShell ed è **possibile utilizzare** **Skype per Business admin center**. 
  
### Verificare e avviare Windows PowerShell

- **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
    
1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
    Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Avviare una sessione di Windows PowerShell**
    
1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
    > [!NOTE]
    > Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

    Per altre informazioni sull'avvio di Windows PowerShell, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o[Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
    
### Consultare tutte le impostazioni dei criteri ID chiamante nella propria organizzazione

- Per visualizzare tutte le impostazioni di criteri di ID chiamante nell'organizzazione, eseguire:
    
  - 
  ```
  Get-CsCallingLineIdentity |fl
  ```

    Per [Ottenere CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx), vedere altri esempi e dettagli.
    
### Creare un nuovo criterio ID chiamante per la propria organizzazione

- Per creare un nuovo criterio ID chiamante che imposta l'ID chiamante su anonimo, eseguire:
    
  - 
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```

    Vedere altri esempi e informazioni dettagliate per [Nuovo CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).
    
- Per applicare il nuovo criterio creato a Marmo Amos, eseguire:
    
  - 
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```

    Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet[Grant CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) per applicare impostazioni per gli utenti.
  
### Impostare in modo che l'ID chiamante in entrata venga bloccato

- Per bloccare la posta in arrivo ID chiamante, eseguire:
    
  - 
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```

    Per [Impostare CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx), vedere altri esempi e dettagli.
    
- Per applicare l'impostazione del criterio che è stato creato per un utente all'interno dell'organizzazione, eseguire:
    
  - 
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```

    Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
### Rimuovere un criterio ID chiamante

Per rimuovere un criterio dalla tua organizzazione, esegui:
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```

Per rimuovere un criterio da un utente, esegui:
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```

## Per saperne di più su Windows PowerShell

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## Argomenti correlati

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)
  
[Periodo di chiamata in uscita di conferenze audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

