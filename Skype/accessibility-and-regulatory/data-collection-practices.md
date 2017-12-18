---
title: "Skype for Business e Microsoft Teams procedure di raccolta dati"
ms.author: tonysmit
author: tonysmit
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
description: "Microsoft collects census, usage, and error data to understand how Skype for Business is being used and where users encounter problems. The data is used to plan product improvements."
---

# Skype for Business e Microsoft Teams procedure di raccolta dati

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
client Skype for Business Server 2015, Skype for Business online e Skype for Business raccogliere dati per consentire a Microsoft informazioni su come vengono utilizzati questi prodotti e si sono verificati i tipi di errori, ad esempio problemi di accesso. Queste informazioni permettono di ottenere informazioni sui modelli di utilizzo, pianificare nuove caratteristiche e identificare e risolvere problemi.
  
Sebbene alcuni dati di utilizzo vengano raccolti automaticamente, altri possono essere raccolti solo quando l'amministratore e/o l'utente sceglie di consentirlo. La raccolta dati rientra in queste tre categorie: 
  
- Dati demografici
    
- Dati sull'utilizzo
    
- Dati di segnalazione degli errori
    
## Dati demografici

Dati viene acquisiti esclusivamente per fornire, supporto e migliorare Skype for Business e Skype for Business online. Include informazioni ambientale, ad esempio le versioni di dispositivo e il sistema operativo e opzioni internazionali e della lingua. Sono inoltre disponibili contatori per tentativi di accesso e gli errori. Ecco alcuni esempi specifici dei dati raccolti:
  
|
|
|****Tipo di dati****|****Esempio****|****Note****|
|:-----|:-----|:-----|
|AppName  <br/> |IPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |IPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |L'hashing dell'ID viene seguito due volte: una volta sul client e di nuovo clic sul servizio di telemetria. L'hashing garantisce che l'ID non venga collegato a un utente specifico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |L'ID del dispositivo è un GUID che ha generato una volta sul dispositivo e inviato al servizio di telemetria in modo casuale.  <br/> |
   
Dati non contengano informazioni che identificano organizzazione o utenti. [Skype per Business informativa sulla privacy](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) per ulteriori informazioni, vedere.
  
I dati demografici sono attivati per impostazione predefinita e non possono essere disattivati dagli amministratori o dagli utenti finali.
  
## Dati sull'utilizzo

I dati sull'utilizzo comprendono informazioni quali il numero di chiamate effettuate, il numero di messaggi istantanei inviati o ricevuti, il numero di riunioni a cui si partecipa, la frequenza delle funzionalità utilizzate e problemi di stabilità.
  
I dati sull'utilizzo potrebbero contenere informazioni che identificano un'organizzazione, ad esempio contoso.com. Di seguito sono illustrati alcuni esempi specifici dei dati sull'utilizzo raccolti.
  
|
|
|****Tipo di dati****|****Esempio****|****Note****|
|:-----|:-----|:-----|
|Messaggi istantanei inviati  <br/> |12  <br/> ||
|Messaggi istantanei ricevuti  <br/> |5  <br/> ||
|Partecipazione a una riunione (tentativi)  <br/> |5  <br/> ||
|Partecipazione a una riunione (esiti positivi)  <br/> |4  <br/> ||
|Minuti di chiamate/riunioni  <br/> |30 minuti  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Questo è il nome dell'organizzazione registrata in Office 365 e viene trasmesso in testo non crittografato, ovvero non offuscato.  <br/> |
   
I dati sull'utilizzo NON contengono informazioni che identificano un utente.
  
Raccolta di dati di utilizzo è attivata per impostazione predefinita ma gli amministratori possono disattivarlo mediante l'impostazione di criteri di gruppo DisableAutomaticSendTracing in Skype for Business Server 2015 in locale. Disattivare questa impostazione viene applicata a tutti gli utenti nell'organizzazione. Per ulteriori informazioni, vedere [configurare client avvio automatico i criteri in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
  
Gli utenti finali non è possibile disattivare raccolta dati di utilizzo.
  
Per App riunioni Skype e le pagine web di join pulsante di visualizzazione, il modo per controllare telemetria è tramite questo criterio:
  
Set CsWebServiceConfiguration - MeetingUxEnableTelemetry $True
  
Questo criterio predefinita è false, in modo insieme di telemetria è disattivata per impostazione predefinita. Questa impostazione per pool e i controlli di tutti gli utenti che metta App riunioni Skype a una riunione ospitata nel server.
  
## Dati di segnalazione degli errori

I dati di segnalazione degli errori possono includere informazioni sulle prestazioni e sull'affidabilità, sulla configurazione dei dispositivi, sulla qualità della connessione di rete, sui codici di errore, sui log degli errori e sulle eccezioni. Di seguito sono illustrati alcuni esempi specifici dei dati di segnalazione degli errori raccolti.
  
|
|
|****Tipo di dati****|****Esempio****||
|:-----|:-----|:-----|
|Direzione del messaggio  <br/> |In arrivo  <br/> ||
|Stato della conversazione  <br/> |Inattivo  <br/> ||
|ID del thread di conversazione  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> ||L'ID viene inviato in formato di testo non crittografato e sottoposto ad hashing da parte del servizio di telemetria prima dell'archiviazione  <br/> |
   
Dati dei report di errore possono contenere anche informazioni personali, ad esempio indirizzo IP dell'utente e sessione avvio Protocol Uniform Resource Identifier (URI SIP). Vedere [Skype per Business informativa sulla privacy](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) per una spiegazione dettagliata delle informazioni raccolte.
  
La segnalazione degli errori richiede due elementi: 
  
- L'impostazione di criteri di gruppo DisableAutomaticSendTracing impostare False sul server o nell'interfaccia di amministrazione tenant (è stato predefinito). Per ulteriori informazioni, vedere [configurare client avvio automatico i criteri in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
    
- Gli utenti finali singolarmente acconsentire esplicitamente dalla scheda Generale (fare clic sull'icona degli ingranaggi e la finestra di dialogo Opzioni verrà visualizzato con la visualizzazione della scheda Generale) nel client Skype for Business.
    
     ![Icona ingranaggio](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype for Business data collection checkbox in the Options > General dialog](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Per App riunioni Skype, il MeetingUxEnableTelemetry controlla inoltre segnalazione errori, anche se per si blocca in Windows, le impostazioni di Watson controllano caricamento informazioni arresto anomalo. Non esiste nessuna impostazione dell'utente per App riunioni di Skype come viene visualizzato nella finestra di dialogo client desktop.
  
Per ulteriori informazioni, consulta [Impostare le opzioni generali in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439).
  
È possibile consultare [Configurare la rete per Skype for Business online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) per configurare la rete.
  
Se utilizzi Office 365 gestito tramite 21Vianet in Cina, consulta [Set up your network for Lync Online](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).
  
## Argomenti correlati

[Programma Analisi utilizzo software](https://www.microsoft.com/products/ceip/en-US/default.mspx)
  
[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

