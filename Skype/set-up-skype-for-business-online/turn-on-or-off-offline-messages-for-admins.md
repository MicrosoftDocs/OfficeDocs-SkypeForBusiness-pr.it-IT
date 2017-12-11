---
title: "Attivare o disattivare i messaggi offline per gli amministratori"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
description: "Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell."
---

# Attivare o disattivare i messaggi offline per gli amministratori

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](8967a77f-caa2-4680-aa22-8faa32c716e4.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/8967a77f-caa2-4680-aa22-8faa32c716e4). 
  
È possibile inviare Skype per Business i messaggi istantanei ai contatti anche se non è connesso. Questa caratteristica informa i contatti che si è tentato di comunicare con loro. Non è necessario attendere fino a quando non è in linea prima dell'invio di un messaggio.
  
Per i messaggi offline, è importante sapere:
  
- I messaggi offline non verranno archiviati nella cassetta postale dell'utente.
    
- Non in linea verranno inviati alla cassetta postale dell'utente e l'utente verrà visualizzato al momento dell'accesso a Skype for Business.
    
- Se lo stato del destinatario del messaggio è impostato su **Non disturbare** o **presentazione**, riceveranno un messaggio senza risposta viene inviato dal Skype del destinatario for Business client.
    
Per ulteriori informazioni, vedere [Utilizzare messaggi offline su Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).
  
## Per iniziare

### 

 **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
  
1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
### 

 **Avviare una sessione di Windows PowerShell**
  
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
  
## Attivazione o disattivazione della messaggistica offline

> [!NOTE]
> Messaggi non in linea sono **solo** disponibili nella versione più recente di Skype a portata di clic for Business client e non sono disponibili quando viene utilizzato un Skype a portata di clic precedente per le aziende o un file MSI è stato usato per installare Skype for Business client.
  
Per attivare o disattivare i messaggi non in linea invia messaggi non in linea per gli utenti dell'organizzazione, impostare  _EnableIMAutoArchiving_ su `True` o `False`. L'impostazione predefinita, è  `True`.
  
Per disattivarli, utilizzare il cmdlet **Set-CsClientPolicy** ed eseguire:
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Per attivare o disattivare i messaggi non in linea invia messaggi fuori rete per un utente, impostare  _EnableIMAutoArchiving_ su `True` o `False`. L'impostazione predefinita, è  `True`. È possibile utilizzare un criterio esistente o creare in quello raffigurato nell'illustrazione seguente.
  
> 
  ```
  New-CsClientPolicy -Identity OfflineIM
  ```

> 
  ```
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  ```

> 
  ```
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## Per saperne di più su Windows PowerShell

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

