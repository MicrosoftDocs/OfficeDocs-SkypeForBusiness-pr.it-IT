---
title: Procedure di raccolta dati
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: Microsoft raccoglie dati censimento, dati di utilizzo e di errore per comprendere l'utilizzo Skype per le aziende e dove gli utenti riscontrano problemi. I dati vengono utilizzati per pianificare miglioramenti del prodotto.
ms.openlocfilehash: 8ea357aefe96505285d9c7bb870ef852ea2649a4
ms.sourcegitcommit: f76ac33ae47eafa2ae853cc031b6ac53c2d4fbbd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Skype per procedure di raccolta dati Business e Teams Microsoft

Skype per Business Server 2015, Skype Business online, e Skype per le applicazioni aziendali e Teams Microsoft raccolga dati per consentire a Microsoft informazioni su come vengono utilizzati questi prodotti e i tipi di errori, ad esempio errori di accesso, si sono verificati. Queste informazioni consentono di acquisire familiarità con modelli di utilizzo, pianificare nuove funzionalità e risolvere i problemi e correggere i problemi.
  
Mentre alcuni dati di utilizzo viene raccolti automaticamente, altri dati possono essere raccolti solo quando l'amministratore e/o l'utente sceglie che consentono la. La raccolta dei dati può essere suddiviso in tre categorie:
  
- Dati
    
- Dati di utilizzo
    
- Dati della segnalazione errori
    
## <a name="census-data"></a>Dati

Dati viene acquisiti unicamente per fornire, supporto e migliorare Skype per le aziende. Team di Microsoft e Skype for Business in linea. Sono incluse informazioni ambientali quali versioni di dispositivi e del sistema operativo e le impostazioni internazionali e della lingua. Include inoltre contatori per i tentativi di accesso e gli errori. Di seguito sono riportati alcuni esempi specifici dei dati raccolti:

|**Tipo di dati**|**Esempio**|**Note**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|ID utente  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |L'ID di hashing due volte: una volta sul client e di nuovo il servizio di telemetria. L'hashing garantisce che l'ID non è collegato a un utente specifico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |L'ID del dispositivo è un GUID che ha generato una volta sul dispositivo e inviate al servizio di telemetria in modo casuale.  <br/> |
   
Dati non contengono alcuna informazione che identifica la propria organizzazione o gli utenti. [Skype per Business informativa sulla privacy](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) per ulteriori informazioni, vedere.
  
Dati sono attivata per impostazione predefinita e non possono essere disattivati da domain admins o gli utenti finali.
  
## <a name="usage-data"></a>Dati di utilizzo

Dati di utilizzo includono informazioni quali numero di chiamate effettuate, numero di messaggi immediati inviati o ricevuti, numero di riunioni che si è unito, frequenza delle caratteristiche utilizzate e problemi di stabilità.
  
Dati di utilizzo possono contenere informazioni che identifica l'organizzazione, ad esempio contoso.com. Di seguito sono riportati alcuni esempi specifici dei dati di utilizzo raccolti:
  
|**Tipo di dati**|**Esempio**|**Note**|
|:-----|:-----|:-----|
|Messaggi immediati inviati  <br/> |12  <br/> ||
|Messaggi immediati ricevuti  <br/> |5  <br/> ||
|Partecipare a una riunione (tentativi)  <br/> |5  <br/> ||
|Partecipare a una riunione (esito positivo)  <br/> |4  <br/> ||
|Minuti chiamata/riunione  <br/> |30 minuti  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Questo è il nome dell'organizzazione registrato in Office 365 e viene trasmessa in testo non crittografato, il che significa che non è offuscato.  <br/> |
   
Dati di utilizzo viene non contengono alcuna informazione che identifica gli utenti.
  
Raccolta dati di utilizzo è attivata per impostazione predefinita ma locale gli amministratori possono disattivarlo utilizzando l'impostazione di criteri di gruppo DisableAutomaticSendTracing su Skype per Business Server 2015. Disattivare questa impostazione riguarda tutti gli utenti nell'organizzazione. Per ulteriori informazioni, vedere [Configure criteri di avvio automatico client in Skype per Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
  
Gli utenti finali non possono attivare raccolta dati di utilizzo attivato o disattivato.
  
Per le pagine web di join launcher e Skype riunioni App, la modalità di controllo del telemetria è a questo criterio:
 
`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True` 

  
Questo criterio viene impostato automaticamente su false, in modo che insieme telemetria è disattivata per impostazione predefinita. Questa impostazione è per ogni pool e controlla tutti gli utenti che si connettono a Skype riunioni App a una riunione ospitata nel server.
  
## <a name="error-reporting-data"></a>Dati della segnalazione errori

Dati dei report di errore possono includere informazioni sulle prestazioni e affidabilità, configurazione del dispositivo, qualità della connessione di rete, codici di errore, i log degli errori ed eccezioni. Di seguito sono riportati alcuni esempi specifici di dati raccolti della segnalazione errori:

|**Tipo di dati**|**Esempio**|**Note**|
|:-----|:-----|:-----|
|Direzione messaggio  <br/> |In ingresso  <br/> ||
|Stato della conversazione  <br/> |Inattivo  <br/> ||
|ID del thread di conversazione  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|ID utente  <br/> |amosmarble <br/> |L'ID viene inviata in testo non crittografato, prima di archiviarli hash per il servizio di telemetria  <br/> |
   
Dati dei report di errore possono contenere anche informazioni personali, ad esempio l'indirizzo IP e Session Initiation Protocol Uniform Resource Identifier (URI SIP) dell'utente. Vedere [Skype per Business informativa sulla privacy](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) per una descrizione dettagliata delle quali raccolti.
  
Segnalazione errori richiede due operazioni:
  
- L'impostazione di criteri di gruppo DisableAutomaticSendTracing essere impostata su False, nel server o nell'interfaccia di amministrazione tenant (è lo stato predefinito). Per ulteriori informazioni, vedere [Configure criteri di avvio automatico client in Skype per Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
    
- Gli utenti finali consenso esplicito singolarmente nella scheda Generale (fare clic sull'icona dell'ingranaggio ![icona ingranaggio](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) e quindi verrà visualizzata la finestra di dialogo **Opzioni** con la visualizzazione della scheda **Generale** ) in Skype per client di Business.
    
 
  
![Skype per checkbox di raccolta dati Business nelle opzioni > finestra di dialogo generale](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Per App riunioni Skype, il MeetingUxEnableTelemetry controlla inoltre segnalazione errori, sebbene per si blocca in Windows, le impostazioni di criteri Watson controllano caricamento info arresto anomalo del sistema. Non esiste alcuna impostazione utente per App riunioni Skype come viene visualizzato nella finestra di dialogo client desktop.
  
Per ulteriori informazioni, vedere [Generale impostare le opzioni di Skype per le aziende](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) .
  
È possibile visualizzare [la configurazione della rete per Skype Business online](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) per la configurazione della rete.
  
Se si utilizza Office 365 gestito dal 21Vianet in Cina, vedere [configurazione di rete per Skype Business online gestito dal 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).
  
## <a name="related-topics"></a>See also
[Programma Analisi utilizzo software](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
