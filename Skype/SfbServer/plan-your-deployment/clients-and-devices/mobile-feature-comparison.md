---
title: Confronto delle funzionalità dei client mobili per Skype for Business
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Riepilogo: esaminare il supporto delle funzionalità per il client mobile durante la pianificazione Skype for Business Server.'
ms.openlocfilehash: 576947499c506052c5204d4826489ae9a2a60037
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614126"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Confronto delle funzionalità dei client mobili per Skype for Business
 
**Riepilogo:** Esaminare il supporto delle funzionalità per il client mobile durante la pianificazione di Skype for Business Server.
  
In questo articolo vengono confrontate le funzionalità Skype for Business client mobili e il client desktop Skype for Business nelle categorie seguenti:
  
- Accesso, notifiche push e funzionalità generali
    
- Presenza avanzata
    
- Contatti e gruppi di contatti
    
- Messaggistica istantanea
    
- Skype for Business per Skype for Business audio e video
    
- Conferenze
    
- Telefonia
    
- Utenti esterni
    
- Archiviazione e conformità
    
-  Autenticazione moderna
    
Nelle tabelle seguenti sono elencate le funzionalità disponibili per Skype for Business utenti in una distribuzione locale di Skype for Business Server. Le stesse funzionalità sono disponibili anche per gli utenti Skype for Business Online e Microsoft 365 o Office 365, se non diversamente indicato nelle note a piè di pagina della tabella.
  
> [!NOTE]
> Per informazioni e risorse online per gli utenti finali, vedere [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Per confrontare le funzionalità disponibili in altri client Skype for Business desktop, vedere [Desktop client feature comparison for Skype for Business](desktop-feature-comparison.md). 

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Accesso, notifiche push e funzionalità generali

 
 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business sessione rimane connesso  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Supporto per le notifiche Push  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|È possibile memorizzare nella cache sullo stesso dispositivo le informazioni di account di più utenti  <br/> |&#x2714;||||
|Screen reader/voice over  <br/> |&#x2714;|&#x2714; &#x2777;           solo inglese  <br/> |&#x2714;|&#x2714;|
|Usare una tastiera esterna per l'accessibilità  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Supporto del programma Analisi utilizzo software Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; In Windows Phone, Skype for Business automaticamente dopo un periodo di inattività, come indicato di seguito:
  
- Se l'utente ha abilitato le notifiche push, Skype for Business dopo 10 giorni di inattività.
    
- Se l'utente non ha abilitato le notifiche push, Skype for Business si esce non appena l'utente lascia l'app.
    
Nei dispositivi iOS, Skype for Business si esce automaticamente dopo che il client mobile non ha contattato il server per 10 giorni a causa della perdita della connettività di rete o di altri problemi.
  
 &#x2777; solo nell'app.
  
 &#x2778; le notifiche sono disponibili quando l'app è in esecuzione in background.
 
 &#x2779; entrambi i servizi di notifica mobile Google/Android/GCNS e Apple/APNS usano la crittografia HTTPS/TLS per il recapito delle notifiche. Il payload della notifica viene gestito in testo normale durante l'elaborazione da parte del provider di notifiche.
 
-   Skype for Business per Android riceve notifiche semplici (recapitate tramite GCNS) senza dati del cliente.
-   Skype for Business per iOS riceve notifiche (recapitate tramite APNS) che possono includere i dati del cliente per la chiamata o il messaggio.
 
  
## <a name="enhanced-presence-support"></a>Supporto della presenza avanzata


 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Pubblicare e visualizzare lo stato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare lo stato in base alle informazioni sulla disponibilità del calendario  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare note sullo stato e messaggi Fuori sede  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aggiungere una posizione personalizzata  <br/> |&#x2714;||||
|Aggiungere una nota personalizzata  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario  <br/> |&#x2714; &#x2776; ||||
|Impostare lo stato di presenza manuale (ad esempio Occupato, Non disturbare e così via)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Skype for Business i client mobili non aggiornano la presenza di un utente in base alle informazioni del calendario sulla disponibilità dell'utente. Se un utente del client per dispositivi mobili è anche connesso al client desktop Skype for Business, il client desktop aggiorna la presenza dell'utente in base alle informazioni del calendario sulla disponibilità dell'utente. Se l'utente ha eseguito l'accesso solo a un client per dispositivi mobili, la presenza dell'utente non viene aggiornato in base alle informazioni del calendario sulla disponibilità.
  
## <a name="contacts-and-contact-groups-support"></a>Supporto per contatti e gruppi di contatti


 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Visualizzare l'elenco contatti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare i gruppi di contatti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare il gruppo Contatti frequenti  <br/> |&#x2714;||||
|Modificare l'elenco contatti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Contrassegnare i contatti per avvisi di modifica dello stato  <br/> |&#x2714;||||
|Controllare le relazioni di privacy  <br/> |&#x2714;||||
|Eseguire ricerche nella rubrica della società  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Eseguire una ricerca nell'elenco contatti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Gestire gruppi di contatti  <br/> |&#x2714;|||&#x2714;|
|Espandere i gruppi di distribuzione  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Cercare Response Group  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Visualizzare o nascondere le foto dei contatti  <br/> |&#x2714;|&#x2714;|||
|Aggiungere un contatto alla schermata iniziale  <br/> ||&#x2714;|||
   
 &#x2776; non disponibile per Skype for Business online e/o Microsoft 365 o Office 365 utenti.
  
## <a name="instant-messaging-support"></a>Supporto per la messaggistica istantanea


 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Avviare la messaggistica istantanea con un contatto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a conversazioni istantanee tra più utenti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitare altri utente dalla finestra di conversazione  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare le conversazioni correnti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Spostarsi tra più conversazioni istantanee  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accedere automaticamente a conversazioni di messaggistica istantanea in Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviare una conversazione di messaggistica istantanea come messaggio di posta elettronica  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Avviare un messaggio di posta elettronica per un contatto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare gli inviti di messaggistica istantanea persi  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Impostare la vibrazione per i messaggi istantanei in arrivo  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; Questo dispositivo vibra ogni volta che viene ricevuta una messaggistica istantanea anche se viene visualizzato il messaggio corrente nella conversazione di messaggistica istantanea
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business per Skype for Business audio e video


 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business da a Skype for Business vocale  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business da Skype for Business video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Il video su un dispositivo mobile richiede una connessione WiFi per impostazione predefinita. 
  
## <a name="conferencing-support"></a>Supporto per conferenze


 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Fare clic su un collegamento nel promemoria della riunione per partecipare a un video o a una riunione VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a conversazioni istantanee tra più utenti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utilizzare la funzionalità di conferenza con chiamata in uscita (il server chiama il dispositivo mobile)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Utilizzare l'audioconferenza con accesso esterno  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare le videoconferenze  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare video con più parti (visualizzazione Raccolta)  <br/> |&#x2714;||||
|Attendere nella sala d'attesa riunione  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utilizzare controlli di relatore nell'ambito delle riunioni  <br/> |&#x2714;||||
|Accedere all'elenco dettagliato dei partecipanti alle audioconferenze  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accedere all'elenco dettagliato dei partecipanti alle conferenze di messaggistica istantanea  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condividere il desktop o un programma  <br/> |&#x2714;||||
|Visualizzare il desktop o il programma condiviso (VbSS o RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Visualizzare file PowerPoint condivisi  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Upload e presentare PowerPoint file  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Usare gli strumenti per le riunioni (usare lavagna, condurre sondaggi, condividere file)  <br/> |&#x2714;||||
|Esplorare un elenco delle proprie riunioni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a una riunione anche se non si dispone di un Skype for Business account  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare ulteriori informazioni sui partecipanti alla riunione  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Avviare una conversazione di gruppo non pianificata con più partecipanti direttamente dal client o dal dispositivo  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; Per Microsoft 365 utenti Office 365, questa funzionalità richiede VoIP aziendale, che fa parte della licenza E5.
  
 &#x2777; richiede una connessione WiFi per impostazione predefinita.
 
 &#x2778; La visualizzazione di video incorporati in PowerPoint presentazioni non è supportata.
  
## <a name="telephony-support"></a>Supporto per telefonia


 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|In Skype for Business toccare l'icona chiamata per chiamare un contatto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Trasferire una chiamata  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Trasferimento consultivo  <br/> |&#x2714; &#x2778; ||||
|Gestire l'inoltro di chiamata  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Gestire le impostazioni di intercettazione team  <br/> |&#x2714; &#x2776; ||||
|Gestire i delegati  <br/> |&#x2714; &#x2776; ||||
|Avviare una chiamata a un Response Group  <br/> |&#x2714; &#x2776; ||||
|Supportare servizi di emergenza  <br/> |&#x2714; &#x2777; ||||
|Eseguire chiamate per conto di un altro contatto (scenario manager/delegato)  <br/> |&#x2714; &#x2776; ||||
|Gestire le chiamate di un altro contatto, se configurato come delegato  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usare Chiamata tramite lavoro  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Accedere al sistema di caselle vocali  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Usare la tastiera in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; Disponibile per gli utenti di Skype for Business Online e/o Office 365 E5 e gli utenti ospitati in Skype for Business Server o Lync Server 2013 con VoIP aziendale abilitata.
  
 &#x2777; Per Skype for Business online e/o Microsoft 365 o Office 365 utenti, questa funzionalità è supportata dai partner Microsoft.
  
 &#x2778; Windows solo client Desktop.
  
## <a name="external-user-support"></a>Supporto per utenti esterni


 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Avviare conversazioni istantanee con un contatto pubblico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Avviare conversazioni istantanee con un contatto federato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condurre chiamate con due utenti esterni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condurre chiamate con più utenti esterni.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usare Chiama tramite ufficio per raggiungere un contatto federato sul proprio telefono cellulare chiamando il numero di ufficio pubblicato &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; per impostazione predefinita, agli utenti federati viene assegnata la relazione di privacy Contatti esterni. Per poter raggiungere un contatto federato sul proprio cellulare chiamando il numero di ufficio pubblicato, il contatto federato deve assegnare manualmente la relazione di privacy Colleghi.
  
## <a name="address-book-integration"></a>Integrazione della rubrica


 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Contatti rubrica del dispositivo di chiamata  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Effettuare Skype for Business chiamate ai contatti direttamente dalla rubrica del dispositivo  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Supporto per archiviazione e conformità


 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Fornire l'archiviazione sul lato client  <br/> |&#x2714;||||
|Fornire la registrazione sul lato client  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; non disponibile per Skype for Business online e/o Microsoft 365 o Office 365 utenti.
  
## <a name="modern-authentication"></a>Autenticazione moderna

Questa tabella illustra le funzionalità che richiedono il supporto per l'autenticazione moderna.
  
L'autenticazione moderna richiede anche una topologia descritta in [Skype for Business topologie supportate con l'autenticazione moderna.](../../plan-your-deployment/modern-authentication/topologies-supported.md)
  

 | Funzionalità/funzionalità  | Skype for Business client desktop  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticazione moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticazione a più fattori  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticazione basata su certificato  <br/> |&#x2714;(solo dispositivo aggiunto a un dominio)  <br/> ||&#x2714;|&#x2714;|
|Gestione applicazioni mobili (tramite Intune)  <br/> |||&#x2714;|&#x2714;|
   

