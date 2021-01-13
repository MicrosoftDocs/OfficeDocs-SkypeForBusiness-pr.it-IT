---
title: Confronto delle funzionalità dei client per dispositivi mobili per Skype for business
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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Riepilogo: esaminare il supporto delle funzionalità per il client per dispositivi mobili durante la pianificazione di Skype for Business Server.'
ms.openlocfilehash: cdd6e5d5afc95fe6488ee89ed96739963b5f5ac0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825996"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Confronto delle funzionalità dei client per dispositivi mobili per Skype for business
 
**Riepilogo:** Esaminare il supporto delle funzionalità per il client per dispositivi mobili durante la pianificazione di Skype for Business Server.
  
Questo articolo confronta le caratteristiche e le funzionalità dei client mobili di Skype for business e il client desktop Skype for business nelle categorie seguenti:
  
- Accesso, notifiche push e caratteristiche generali
    
- Presenza avanzata
    
- Contatti e gruppi di contatti
    
- Messaggistica istantanea
    
- Skype for business per audio e video in Skype for business
    
- Conferenze
    
- Telefonia
    
- Utenti esterni
    
- Archiviazione e conformità
    
-  Autenticazione moderna
    
Nelle tabelle seguenti sono elencate le caratteristiche disponibili per gli utenti di Skype for business in una distribuzione locale di Skype for Business Server. Le stesse caratteristiche sono disponibili anche per gli utenti di Skype for business online e Microsoft 365 o Office 365, se non diversamente indicato nelle note a piè di pagina.
  
> [!NOTE]
> Per informazioni sulla guida online e sulle risorse per gli utenti finali, vedere [Discover Skype for business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Per confrontare le funzionalità disponibili in altri client Skype for business, vedere confronto delle caratteristiche dei [client desktop per Skype for business](desktop-feature-comparison.md). 

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Accesso, notifiche push e caratteristiche generali

 
 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|La sessione di Skype for business resta connessa  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Supporto per le notifiche Push  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|È possibile memorizzare nella cache sullo stesso dispositivo le informazioni di account di più utenti  <br/> |&#x2714;||||
|Screen reader/Voice over  <br/> |&#x2714;|Solo in inglese &#x2714; &#x2777;             <br/> |&#x2714;|&#x2714;|
|Utilizzo di una tastiera esterna per l'accessibilità  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Supporto del programma Analisi utilizzo software Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; su Windows Phone, Skype for business si disconnette automaticamente dopo un periodo di inattività, come indicato di seguito:
  
- Se l'utente ha abilitato le notifiche push, Skype for business si disconnette dopo 10 giorni di inattività.
    
- Se l'utente non ha abilitato le notifiche push, Skype for business si disconnette non appena l'utente lascia l'app.
    
Nei dispositivi iOS, Skype for business si disconnette automaticamente dopo che il client per dispositivi mobili non ha contattato il server per 10 giorni a causa della perdita della connettività di rete o di altri problemi.
  
 &#x2777; solo in app.
  
 &#x2778; le notifiche sono disponibili quando l'app è in esecuzione in background.
 
 &#x2779; sia Google/Android/GCNS che Apple/APNS mobile Notification Services utilizzano la crittografia HTTPS/TLS per il recapito delle notifiche. Il payload di notifica viene gestito in testo normale durante l'elaborazione da parte del provider di notifiche.
 
-   Skype for business per Android riceve notifiche semplici (recapitate tramite GCNS) senza dati dei clienti.
-   Skype for business per iOS riceve notifiche (recapitate tramite APNS) che possono includere i dati dei clienti per la chiamata o il messaggio.
 
  
## <a name="enhanced-presence-support"></a>Supporto per la presenza avanzata


 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Pubblicare e visualizzare lo stato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare lo stato in base alle informazioni sulla disponibilità del calendario  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare note sullo stato e messaggi Fuori sede  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aggiungere una posizione personalizzata  <br/> |&#x2714;||||
|Aggiungere una nota personalizzata  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario  <br/> |&#x2714; &#x2776; ||||
|Impostare lo stato di presenza manuale, ad esempio occupato, non disturbare e così via.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; i client per dispositivi mobili Skype for business non aggiornano la presenza di un utente in base alle informazioni sulla disponibilità del calendario dell'utente. Se un utente di un client per dispositivi mobili è anche connesso al client desktop Skype for business, il client Desktop aggiorna la presenza dell'utente in base alle informazioni sulla disponibilità del calendario dell'utente. Se l'utente ha eseguito l'accesso solo a un client per dispositivi mobili, la presenza dell'utente non viene aggiornata in base alle informazioni sulla disponibilità del calendario.
  
## <a name="contacts-and-contact-groups-support"></a>Supporto per contatti e gruppi di contatti


 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
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
   
 &#x2776; non disponibile per Skype for business online e/o Microsoft 365 o per gli utenti di Office 365.
  
## <a name="instant-messaging-support"></a>Supporto per la messaggistica istantanea


 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
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
   
 &#x2776; questo dispositivo vibra ogni volta che viene ricevuta una messaggistica istantanea anche se viene visualizzato il messaggio corrente nella conversazione di messaggistica istantanea
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for business per audio e video in Skype for business


 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for business-to-Skype for Business Voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Video su Skype for business-to-Skype for business  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Il video su un dispositivo mobile richiede una connessione WiFi per impostazione predefinita. 
  
## <a name="conferencing-support"></a>Supporto per le conferenze


 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Fare clic su un collegamento nel promemoria riunioni per partecipare a una riunione video o VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a conversazioni istantanee tra più utenti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utilizzare la funzionalità di conferenza con chiamata in uscita (il server chiama il dispositivo mobile)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Utilizzare l'audioconferenza con accesso esterno  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare le videoconferenze  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzazione del video in più parti (visualizzazione raccolta)  <br/> |&#x2714;||||
|Attendere nella sala d'attesa riunione  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utilizzare controlli di relatore nell'ambito delle riunioni  <br/> |&#x2714;||||
|Accedere all'elenco dettagliato dei partecipanti alle audioconferenze  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accedere all'elenco dettagliato dei partecipanti alle conferenze di messaggistica istantanea  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condividere il desktop o un programma  <br/> |&#x2714;||||
|Visualizzazione di un desktop o di un programma condiviso (VbSS o RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Visualizzare i file di PowerPoint condivisi  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Caricare e presentare file di PowerPoint  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Utilizzare gli strumenti di riunione (utilizzare lavagna, eseguire sondaggi, condividere file)  <br/> |&#x2714;||||
|Esplorare un elenco delle proprie riunioni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a una riunione anche se non si dispone di un account Skype for business  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare altre informazioni sui partecipanti alla riunione  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Avviare una conversazione di gruppo non pianificata con più partecipanti direttamente dal client o dal dispositivo  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; per gli utenti di Microsoft 365 o Office 365, questa funzionalità richiede VoIP aziendale, che fa parte della licenza E5.
  
 Per impostazione predefinita, &#x2777; richiede una connessione WiFi.
 
 &#x2778; la visualizzazione di video incorporati nelle presentazioni di PowerPoint non è supportata.
  
## <a name="telephony-support"></a>Supporto telefonico


 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|In Skype for business, toccare l'icona di chiamata per chiamare un contatto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Trasferire una chiamata  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Trasferimento consultivo  <br/> |&#x2714; &#x2778; ||||
|Gestire l'inoltro di chiamata  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Gestire le impostazioni di intercettazione team  <br/> |&#x2714; &#x2776; ||||
|Gestire i delegati  <br/> |&#x2714; &#x2776; ||||
|Avviare una chiamata a un Response Group  <br/> |&#x2714; &#x2776; ||||
|Supportare servizi di emergenza  <br/> |&#x2714; &#x2777; ||||
|Eseguire chiamate per conto di un altro contatto (scenario manager/delegato)  <br/> |&#x2714; &#x2776; ||||
|Gestire le chiamate di un altro contatto, se configurate come delegati  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Utilizzare la chiamata tramite lavoro  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Accedere al sistema di caselle vocali  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Usare la tastiera in Skype for business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; disponibile per gli utenti di Skype for business online e/o Office 365 E5 e per gli utenti ospitati su Skype for Business Server o Lync Server 2013 con VoIP aziendale abilitato.
  
 &#x2777; per gli utenti di Skype for business online e/o Microsoft 365 o Office 365, questa funzionalità è supportata dai partner Microsoft.
  
 &#x2778; solo client desktop di Windows.
  
## <a name="external-user-support"></a>Supporto per gli utenti esterni


 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Avviare conversazioni istantanee con un contatto pubblico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Avviare conversazioni istantanee con un contatto federato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condurre chiamate con due utenti esterni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condurre chiamate con più utenti esterni.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utilizzare la chiamata tramite lavoro per raggiungere un contatto federato sul proprio telefono cellulare chiamando il numero di lavoro pubblicato &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; per impostazione predefinita, agli utenti federati viene assegnata la relazione di privacy dei contatti esterni. Per essere in grado di raggiungere un contatto federato sul proprio telefono cellulare chiamando il numero di lavoro pubblicato, il contatto federato deve assegnare manualmente la relazione di privacy ai colleghi.
  
## <a name="address-book-integration"></a>Integrazione della Rubrica


 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Contatti della rubrica del dispositivo di chiamata  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Effettuare chiamate Skype for business ai contatti direttamente dalla rubrica del dispositivo  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Supporto per l'archiviazione e la conformità


 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Fornire l'archiviazione sul lato client  <br/> |&#x2714;||||
|Fornire la registrazione sul lato client  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; non disponibile per Skype for business online e/o Microsoft 365 o per gli utenti di Office 365.
  
## <a name="modern-authentication"></a>Autenticazione moderna

In questa tabella vengono illustrate le funzionalità che richiedono il supporto per l'autenticazione moderna.
  
L'autenticazione moderna richiede anche una topologia descritta nelle [topologie Skype for business supportate con l'autenticazione moderna](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Caratteristica/funzionalità  | Client desktop Skype for business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticazione moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticazione a più fattori  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticazione basata su cert  <br/> |&#x2714; (solo dispositivo collegato al dominio)  <br/> ||&#x2714;|&#x2714;|
|Gestione delle applicazioni mobili (tramite Intune)  <br/> |||&#x2714;|&#x2714;|
   

