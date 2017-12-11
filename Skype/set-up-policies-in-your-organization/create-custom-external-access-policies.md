---
title: "Creare criteri di accesso esterno personalizzato"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
description: "Skype for Business Online consente di creare criteri di accesso esterno aggiuntive. A differenza dei criteri client o i servizi di conferenza, in cui sono combinazioni di più, sono disponibili tre criteri di accesso esterno predefiniti che possono coprire la maggior parte degli scenari. Di seguito sono:"
---

# Creare criteri di accesso esterno personalizzato

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](89cbd278-5480-473c-8cd9-04e07e5f9e0b.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/89cbd278-5480-473c-8cd9-04e07e5f9e0b). 
  
Skype for Business Online consente di creare criteri di accesso esterno aggiuntive. A differenza dei criteri client o i servizi di conferenza, in cui sono combinazioni di più, sono disponibili tre criteri di accesso esterno predefiniti che possono coprire la maggior parte degli scenari. Di seguito sono:
  
- N federato o Access Consumer di Skype ( _Tag:NoFederationAndPIC_ )
    
- Accesso federato ( _Tag:FederationOnly_ )
    
- Federato e Consumer accedere ( _FederationAndPICDefault_)
    
Criteri esterni personalizzati consentono di creare ulteriori criteri che non rientrano le impostazioni precedenti. Quando è stato creato il criterio, sarà richiesto di impostare tutti i parametri necessari e non modificare in un secondo momento. Creazione di nuovi criteri personalizzati consentono alle funzionalità di controllo, ad esempio consumer di Skype accedere o un criterio per disabilitare pubblico cloud audio/video, un'operazione che non è stato considerato con le impostazioni predefinite. Criteri di accesso esterno personalizzato seguono la stessa sintassi di criteri client, mobilità e conferenze. È possibile trovare ulteriori informazioni su queste impostazioni [qui](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Per garantire il corretto funzionamento, l'utente deve usando una versione supportata di 2016 a portata di clic Skype per Business app che lo supporta. La versione minima seguente di Skype per Business 2016 a portata di clic client è necessaria:
  
|**Tipo**|**Data di rilascio**|**Versione**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release per Current Channel  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Versione 1611 (Build 7571.2006)  <br/> |
|Current Channel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> | Versione 1611 (build 7571.2072) <br/> |
|Deferred Channel  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versione 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Utenti che utilizzano versioni precedenti di Skype per Business Windows App o i client Mac ancora saranno possibile trasferire i file. 
  
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
    
## Creazione di un criterio di accesso esterno personalizzato per un utente

A tale scopo, eseguire:
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
  

