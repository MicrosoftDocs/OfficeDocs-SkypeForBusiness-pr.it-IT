---
title: Confronto delle caratteristiche dei client per dispositivi mobili per Skype for business
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Riepilogo: rivedere il supporto delle funzionalità per il client per dispositivi mobili durante la pianificazione per Skype for Business Server.'
ms.openlocfilehash: d3d3764ee5315b4fe211b4f79ea2401b98703261
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "36195874"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Confronto delle caratteristiche dei client per dispositivi mobili per Skype for business
 
**Riepilogo:** Esaminare il supporto delle funzionalità per il client per dispositivi mobili durante la pianificazione di Skype for Business Server.
  
Questo articolo confronta le caratteristiche e le funzionalità tra i client per dispositivi mobili Skype for business e il client desktop Skype for business nelle categorie seguenti:
  
- Accesso, notifiche push e funzionalità generali
    
- Presenza avanzata
    
- Contatti e gruppi di contatti
    
- Messaggistica istantanea (IM)
    
- Skype for business per l'audio e il video di Skype for business
    
- Servizi di conferenza
    
- Telefonia
    
- Utenti esterni
    
- Archiviazione e conformità
    
-  Autenticazione moderna
    
Le tabelle seguenti elencano le caratteristiche disponibili per gli utenti di Skype for business in una distribuzione locale di Skype for Business Server. Le stesse caratteristiche sono disponibili anche per gli utenti di Skype for business online e Microsoft Office 365, se non diversamente indicato nelle note a piè di pagina.
  
> [!NOTE]
> Per informazioni sulla guida e le risorse online per gli utenti finali, vedere [individuare Skype for business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Per confrontare le funzionalità disponibili in altri client Skype for business, Vedi [confronto tra funzionalità client desktop per Skype for business](desktop-feature-comparison.md). 

> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Accesso, notifiche push e funzionalità generali

 
 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|La sessione di Skype for business rimane confirmata  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Supporto per le notifiche push  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|Le informazioni sull'account per più utenti possono essere memorizzate nella cache nello stesso dispositivo  <br/> |&#x2714;||||
|Utilità per la lettura dello schermo/Voice over  <br/> |&#x2714;|Solo &#x2714; &#x2777;  inglese  <br/> |&#x2714;|&#x2714;|
|Usare una tastiera esterna per l'accessibilità  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Supporto di Microsoft Customer Experience Improvement Program  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; in Windows Phone, Skype for business si disconnette automaticamente dopo un periodo di inattività, come indicato di seguito:
  
- Se l'utente ha abilitato le notifiche push, Skype for business si disconnette dopo 10 giorni di inattività.
    
- Se l'utente non ha abilitato le notifiche push, Skype for business si disconnette non appena l'utente esce dall'app.
    
Nei dispositivi iOS Skype for business si disconnette automaticamente dopo che il client per dispositivi mobili non ha contattato il server per 10 giorni a causa della perdita di connettività di rete o di altri problemi.
  
 &#x2777; solo in app.
  
 Le notifiche di &#x2778; sono disponibili quando l'app viene eseguita in background.
 
 &#x2779; i servizi di notifica per dispositivi mobili Google/Android/GCNS e Apple/APN usano la crittografia HTTPS/TLS per il recapito delle notifiche. Il payload della notifica viene gestito in testo normale durante l'elaborazione da parte del provider di notifiche.
 
-   Skype for business per Android riceve le notifiche semplici (fornite tramite GCNS) senza dati del cliente.
-   Skype for business per iOS riceve le notifiche (recapitate tramite APN) che possono includere i dati del cliente per la chiamata o il messaggio.
 
  
## <a name="enhanced-presence-support"></a>Supporto per la presenza avanzata


 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Pubblicare e visualizzare lo stato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare lo stato in base alle informazioni sulla disponibilità del calendario  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare le note sullo stato e i messaggi fuori sede  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aggiungere un percorso personalizzato  <br/> |&#x2714;||||
|Aggiungere una nota personalizzata  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario  <br/> |&#x2714; &#x2776; ||||
|Impostare lo stato di presenza manuale (ad esempio occupato, non disturbare e così via)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; i client di Skype for business mobile non aggiornano la presenza di un utente in base alle informazioni del calendario sulla disponibilità dell'utente. Se un utente del client mobile ha anche eseguito l'accesso al client desktop Skype for business, il client Desktop aggiorna la presenza dell'utente in base alle informazioni del calendario sulla disponibilità dell'utente. Se l'utente ha eseguito l'accesso solo a un client per dispositivi mobili, la presenza dell'utente non viene aggiornata in base alle informazioni sul calendario della disponibilità.
  
## <a name="contacts-and-contact-groups-support"></a>Supporto per contatti e gruppi di contatti


 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Visualizzare l'elenco contatti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare i gruppi di contatti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare il gruppo contatti frequenti  <br/> |&#x2714;||||
|Modificare l'elenco contatti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Contrassegnare i contatti per gli avvisi di modifica dello stato  <br/> |&#x2714;||||
|Controllare le relazioni di privacy  <br/> |&#x2714;||||
|Eseguire ricerche nella rubrica aziendale  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Cerca nell'elenco contatti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Gestire i gruppi di contatti  <br/> |&#x2714;|||&#x2714;|
|Espandere i gruppi di distribuzione  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Cercare gruppi di risposte  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Visualizzare o nascondere le foto del contatto  <br/> |&#x2714;|&#x2714;|||
|Aggiungere un contatto alla schermata iniziale  <br/> ||&#x2714;|||
   
 &#x2776; non è disponibile per gli utenti di Skype for business online e/o di Office 365.
  
## <a name="instant-messaging-support"></a>Supporto della messaggistica istantanea


 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Avviare la messaggistica istantanea con un contatto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a un messaggio istantaneo a più parti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitare altri utenti all'interno della finestra di conversazione  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare le conversazioni correnti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Spostarsi tra più conversazioni di messaggistica istantanea  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Registrare automaticamente le conversazioni ISTANTANEe in Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviare una conversazione istantanea come messaggio di posta elettronica  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Avviare un messaggio di posta elettronica a un contatto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare gli inviti di messaggistica istantanea mancanti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibrazione con messaggistica istantanea in arrivo  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; questo dispositivo vibra ogni volta che viene ricevuto un messaggio ISTANTANEo anche se viene visualizzato il testo corrente nella conversazione di messaggistica istantanea
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for business per l'audio e il video di Skype for business


 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for business-to-Skype for Business Voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Video di Skype for business-to-Skype for business  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Il video in un dispositivo mobile richiede una connessione WiFi per impostazione predefinita. 
  
## <a name="conferencing-support"></a>Supporto per le conferenze


 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Fare clic su un collegamento nel promemoria della riunione per partecipare a una riunione video o VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a un messaggio istantaneo a più parti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usare i servizi di conferenza telefonica con accesso esterno (server chiama il dispositivo mobile)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usare i servizi di conferenza telefonica con accesso esterno  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare il video della riunione  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare il video in più parti (visualizzazione raccolta)  <br/> |&#x2714;||||
|Attendere nella sala di attesa della riunione  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usare i controlli relatore in-meeting  <br/> |&#x2714;||||
|Accedere a roster delle riunioni dettagliato per le conferenze audio  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accedere a un roster dettagliato delle riunioni per le conferenze ISTANTANEe  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condividere desktop o programmi  <br/> |&#x2714;||||
|Visualizzazione di desktop o programmi condivisi (VbSS o RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Visualizzare i file di PowerPoint condivisi  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Caricare e presentare file di PowerPoint  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Usare gli strumenti riunione (usare lavagna, eseguire sondaggi, condividere file)  <br/> |&#x2714;||||
|Spostarsi in un elenco delle riunioni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a una riunione anche se non si ha un account Skype for business  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare altre informazioni sui partecipanti alla riunione  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Avviare una conversazione di gruppo non pianificata con più partecipanti direttamente dal client o dal dispositivo  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; per gli utenti di Office 365, questa funzionalità richiede VoIP aziendale, che fa parte della licenza E5.
  
 &#x2777; richiede una connessione WiFi per impostazione predefinita.
 
 &#x2778; la visualizzazione di video incorporati nelle presentazioni di PowerPoint non è supportata.
  
## <a name="telephony-support"></a>Supporto per la telefonia


 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|In Skype for business toccare l'icona chiama per chiamare un contatto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Trasferire una chiamata  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Trasferimento consultivo  <br/> |&#x2714; &#x2778; ||||
|Gestire l'inoltro di chiamata  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Gestire le impostazioni delle chiamate di Team  <br/> |&#x2714; &#x2776; ||||
|Gestire i delegati  <br/> |&#x2714; &#x2776; ||||
|Avviare una chiamata a un gruppo di risposte  <br/> |&#x2714; &#x2776; ||||
|Supportare i servizi di emergenza  <br/> |&#x2714; &#x2777; ||||
|Effettuare chiamate per conto di un altro contatto (scenario manager/delegato)  <br/> |&#x2714; &#x2776; ||||
|Gestire le chiamate di un altro contatto, se configurato come delegato  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usare la chiamata tramite lavoro  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Accedere alla segreteria telefonica  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Usare la tastiera in Skype for business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; disponibile per gli utenti di Skype for business online e/o Office 365 E5 e per gli utenti ospitati in Skype for Business Server o Lync Server 2013 con Enterprise Voice Enabled.
  
 &#x2777; per gli utenti di Skype for business online e/o Office 365, questa funzionalità è supportata da Microsoft partner.
  
 &#x2778; solo client desktop di Windows.
  
## <a name="external-user-support"></a>Supporto utenti esterni


 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Avviare un messaggio istantaneo con un contatto pubblico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Avviare un messaggio istantaneo con un contatto federato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Eseguire chiamate in due parti con utenti esterni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Eseguire chiamate in più parti con utenti esterni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usare la chiamata tramite lavoro per raggiungere un contatto federato sul proprio telefono cellulare chiamando il numero di lavoro pubblicato &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; per impostazione predefinita, agli utenti federati viene assegnata la relazione di privacy dei contatti esterni. Per poter raggiungere un contatto federativo sul proprio telefono cellulare chiamando il numero di lavoro pubblicato, il contatto federato deve assegnare manualmente la relazione di privacy dei colleghi.
  
## <a name="address-book-integration"></a>Integrazione della Rubrica


 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Chiamare i contatti della rubrica del dispositivo  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Effettuare chiamate Skype for business ai contatti direttamente da Rubrica dispositivi  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Supporto per l'archiviazione e la conformità


 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Fornisci l'archiviazione lato client  <br/> |&#x2714;||||
|Fornisci registrazione lato client  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; non è disponibile per gli utenti di Skype for business online e/o di Office 365.
  
## <a name="modern-authentication"></a>Autenticazione moderna

Questa tabella include le caratteristiche che richiedono il supporto per l'autenticazione moderna.
  
L'autenticazione moderna richiede anche una topologia descritta nelle [topologie Skype for business supportate con l'autenticazione moderna](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Funzionalità/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticazione moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticazione a più fattori  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticazione basata su cert  <br/> |&#x2714; (solo per il dispositivo collegato al dominio)  <br/> ||&#x2714;|&#x2714;|
|Gestione applicazioni per dispositivi mobili (tramite Intune)  <br/> |||&#x2714;|&#x2714;|
   

