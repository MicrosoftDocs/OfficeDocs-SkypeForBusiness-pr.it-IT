---
title: "Attivare o disattivare i report di feedback client di Skype for Business"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
description: "Questa caratteristica è attualmente in anteprima e potrebbe essere modificata al momento del rilascio o dell'aggiornamento."
---

# Attivare o disattivare i report di feedback client di Skype for Business

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](35562b48-1da1-4081-8a3a-033d0f1986b2.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/35562b48-1da1-4081-8a3a-033d0f1986b2). 
  
 **Questa caratteristica è attualmente in anteprima e potrebbe essere modificata al momento del rilascio o dell'aggiornamento.**
  
È possibile abilitare la Skype agli utenti aziendali di utilizzare Skype predefiniti per lo strumento di commenti e suggerimenti app aziendali per consentire agli utenti di segnalare problemi e fornire commenti e suggerimenti direttamente a Microsoft parlare della propria esperienza.
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
Con questo strumento, un utente possibile copiare i registri dall'app sul dispositivo di meglio individuare e risolvere i problemi che potrebbero disporre di Microsoft.
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
Puoi anche utilizzare l'impostazione  _EnableOnlineFeedbackScreenshot_ in modo che gli utenti possano includere una schermata del proprio dispositivo nel loro feedback.
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!SECURITY NOTE]
> Verranno archiviati i registri raccolti dallo strumento di commenti e suggerimenti dell'app per fino a un massimo di 90 giorni negli Stati Uniti durante il problema in corso di analisi. Per questi motivi, non abilitare questo strumento commenti e suggerimenti se questo viola i criteri di protezione dei dati dell'organizzazione. 
  
## Verificare e avviare Windows PowerShell

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
    
## Attiva i report di feedback dell'applicazione client per tutti gli utenti dell'organizzazione

Per attivare commenti e suggerimenti per gli utenti dell'organizzazione e consentire loro di inviare schermate dispositivo, eseguire:
  
> 
  ```
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true

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
  

