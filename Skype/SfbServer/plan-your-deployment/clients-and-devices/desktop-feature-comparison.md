---
title: Confronto delle funzionalità del client desktop per Skype for Business Server
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Riepilogo: gli amministratori di Skype for Business Server 2015 o Skype for Business online possono usare queste tabelle per comprendere quali funzionalità sono supportate su quali client.'
ms.openlocfilehash: 5ee4546e62593ca61e9833bbdf1c09efeef4ce13
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832186"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Confronto delle funzionalità del client desktop per Skype for Business Server

**Riepilogo:** Gli amministratori di Skype for Business Server 2015 o Skype for Business online possono usare queste tabelle per comprendere quali funzionalità sono supportate su quali client.
  
 Prima di distribuire o eseguire l'aggiornamento a Skype for Business, controllare quali client sono già in uso nell'organizzazione. Utilizzare le tabelle seguenti per comprendere l'impatto del supporto delle funzionalità su tali client. In questo modo è possibile comunicare modifiche agli utenti, implementare il processo di implementazione e comprendere appieno i vantaggi dell'aggiornamento al client più recente.
  
Alcune funzionalità disponibili con Skype for Business Server 2015 non sono disponibili in Skype for Business online, vedere Limitazioni degli account utente [online](desktop-feature-comparison.md#Online-Hybrid) o ibridi per specifiche. Gli amministratori di Skype for Business online possono fare riferimento alla descrizione del servizio [Skype for Business online](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) per informazioni sui diversi piani disponibili.

Consulta il confronto delle funzionalità del client desktop [per Skype for Business 2019](../../../SfBServer2019/plan/feature-comparison.md) per il supporto client in Skype for Business Server 2019.
  
Le tabelle seguenti mostrano le funzionalità disponibili con ogni client che funziona con Skype for Business Server 2015 o Skype for Business online. È anche possibile fare riferimento al confronto delle funzionalità del client per dispositivi mobili [per Skype for Business](mobile-feature-comparison.md) per i confronti delle funzionalità client per smartphone e tablet. Anche la licenza di accesso client o la licenza di sottoscrizione utente acquistata dall'organizzazione avranno un impatto sulle funzionalità disponibili per gli utenti. La distribuzione del client completo o di base agli utenti dipende dalla licenza o dal piano scelto dall'organizzazione per l'acquisto. Per altri [dettagli, vedi la](https://products.office.com/skype-for-business/it-pros) Guida alle licenze.
  
> [!IMPORTANT]
> Skype for Business Server 2015 e Skype for Business Online supportano i seguenti client rilasciati in precedenza: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Phone Edition e Lync 2010 Attendant. Per informazioni su questi client se utilizzati con altri server, vedere le tabelle di confronto dei client per [Lync Server 2013](https://technet.microsoft.com/library/gg425836%28v=ocs.15%29.aspx) e le tabelle di confronto dei [client per Lync Server 2010.](https://technet.microsoft.com/library/gg425836%28v=ocs.14%29.aspx)

> [!NOTE]
> Il **client Lync 2010 Attendant** non è supportato in Skype for Business online.

> [!NOTE]
> Il client del browser Skype for Business Web App e l'app Skype Meetings App di Windows 10 forniscono solo il supporto [per le riunioni.](desktop-feature-comparison.md#BKMK_Conferencing) Per ulteriori informazioni su questi client, vedere Plan [for Meetings clients (Web App and Meetings App).](meetings-clients.md)
  
## <a name="enhanced-presence-support"></a>Supporto della presenza avanzata

<a name="BKMK_EnhancedPresence"> </a>

Questa tabella illustra le funzionalità di presenza avanzata che si estendono oltre una semplice indicazione del fatto che un utente sia online, offline, occupato e così via.
  
|Funzionalità/funzionalità|Client Skype for Business 2015 o 2016|Skype for Business nel Mac|Client Lync 2013|App Lync di Windows Store|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator per Mac 2011|Lync per Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Stato pubblicazione |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Visualizzare lo stato   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare note sullo stato e messaggi Fuori sede |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aggiungere una posizione personalizzata |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Aggiungere una nota personalizzata |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Usare una foto da qualsiasi sito pubblico per La mia immagine (non disponibile in Skype for Business online) |&#x2714;||&#x2714;|||||||

 &#x2776; non supporta lo stato di pubblicazione in base alle informazioni sulla disponibilità del calendario.
  
## <a name="contacts-and-contact-groups-support"></a>Supporto per contatti e gruppi di contatti

<a name="BKMK_Contacts"> </a>

In questa tabella vengono illustrate le funzionalità relative alla gestione dei contatti di messaggistica istantanea e presenza.

|Funzionalità/funzionalità|Client Skype for Business 2015 o 2016|Skype for Business nel Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Elenco contatti precompilato |&#x2714;|||||||||
|Visualizzazione e modifica dell'elenco contatti |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Contrassegnare i contatti per avvisi di modifica dello stato |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Controllare le relazioni di privacy |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Eseguire ricerche nella rubrica della società |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Eseguire ricerche nei contatti di Microsoft Outlook |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gestire gruppi di contatti |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Espandere i gruppi di distribuzione e i gruppi di Microsoft 365 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Cercare Response Group  <br/> (non disponibile in Skype for Business online) |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Visualizzare gruppi di contatti recenti |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Visualizzare il gruppo Conversazioni correnti |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Visualizzare viste contatti alternative (ad esempio affiancate) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Ordinare i contatti per gruppo, relazione o nuovo (persone che hanno aggiunto l'utente al proprio elenco contatti) |&#x2714;||&#x2714;|Ordina per gruppo |&#x2714;|&#x2714;||||
|Ordinare i contatti in base allo stato (disponibilità) |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Ricerca e aggiunta di contatti di Exchange |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>Supporto per la messaggistica istantanea

<a name="BKMK_IMSupport"> </a>

Questa tabella illustra le funzionalità relative al supporto della messaggistica istantanea.

|Funzionalità/funzionalità | Client Skype for Business 2015 o 2016 | Skype for Business nel Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Avviare la messaggistica istantanea con o inviare un messaggio di posta elettronica a un contatto |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Spostarsi tra più conversazioni di messaggistica istantanea/tenere traccia di più conversazioni in un'unica finestra a schede |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Registrare conversazioni istantanee in Outlook |&#x2714;|&#x2714;se la cronologia conversazioni sul lato server è attivata  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Mantenuta in Communicator per Mac |Mantenuta in Lync per Mac |
|Utilizzare modelli di conversazioni preparati |||||&#x2714;|&#x2714;||||
|Controllo ortografico |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Ricerca per competenza (con l'integrazione di SharePoint Server)  <br/> Skype for Business Server locale e SharePoint 2013 locale sono necessari per la ricerca di competenze. |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Integrazione di Chat persistente (Group Chat)  <br/> (non disponibile per Skype for Business online) |&#x2714;||&#x2714;|||||||
|Inoltrare una chat room di Persistent Chat a una riunione Skype for Business con un solo clic  <br/> (non disponibile per Skype for Business online) |&#x2714;||&#x2714;|||||||
|Immagini inline di mittente e destinatario nella finestra di messaggistica istantanea |&#x2714;||&#x2714;|&#x2714;||||||
|Inviare messaggi di input penna ||||&#x2714;||||||
|Ricevere messaggi di input penna |&#x2714;||&#x2714;|&#x2714;||||||
|Impostare i messaggi di messaggistica istantanea come priorità alta |&#x2714;||&#x2714;|||||||
|Trasferire file in conversazioni di messaggistica istantanea peer-to-peer |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>Supporto per le riunioni

<a name="BKMK_Conferencing"> </a>

Questa tabella illustra le funzionalità correlate al supporto per le riunioni.
  
> [!NOTE]
> Le funzionalità delle riunioni di Skype for Business non sono disponibili in Skype for Business Online piano autonomo 1.  Il piano 1 verrà [ritirato.](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement)

Nelle sessioni Skype-to-Skype, un utente skype for business online piano 1 può partecipare alla condivisione desktop e alle applicazioni se viene invitato da un utente che ha accesso alle funzionalità di condivisione.
Per informazioni dettagliate, vedere la descrizione del servizio [Skype for Business online.](https://technet.microsoft.com/library/jj822172.aspx)
  
|Funzionalità/funzionalità | Client Skype for Business 2016 | Skype for Business nel Mac | Skype for Business Web App | Client Skype for Business 2015 | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Aggiungere la funzionalità audio al computer |&#x2714;|&#x2714;|&#x2714;(richiede plug-in) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aggiungere la funzionalità video |&#x2714;|&#x2714;|&#x2714;(richiede plug-in) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Visualizzare video con più parti (visualizzazione Raccolta) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Condivisione dello schermo basato su video |&#x2714;|&#x2714;|&#x2714;sola visualizzazione |||||||||
|Utilizzare controlli di relatore nell'ambito delle riunioni |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Accedere all'elenco dettagliato delle riunioni |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Partecipare a conversazioni istantanee tra più utenti |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Condividere il desktop (se consentito) |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (richiede plug-in) |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Condividere un programma (se consentito) |&#x2714;|Sola visualizzazione   |&#x2714;(richiede plug-in) |&#x2714;|&#x2714;||&#x2714;||||Sola visualizzazione |
|Aggiungere partecipanti anonimi (se consentito) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Usare riunioni audio con accesso remoto |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Avviare una riunione riunione |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Aggiungere e presentare file di Microsoft PowerPoint |&#x2714;| &#x2778; annotazioni non disponibili |&#x2714;|&#x2714;|&#x2714;|Solo presente |&#x2714;|||| &#x2778; solo visualizzazione, annotazioni non disponibili |
|Esplorare i file di Microsoft PowerPoint |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Aggiungere e modificare le note delle riunioni di OneNote |&#x2714;||Solo modifica (non aggiunta) |&#x2714;|&#x2714;|||||||
|Utilizzare una lavagna |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Effettuare sondaggi |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Caricare file da condividere con altri utenti |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Pianificare una riunione o una conferenza |Outlook o Skype for Business Web Scheduler |Outlook o Skype for Business Web Scheduler |Skype for Business Web Scheduler |Outlook o Skype for Business Web Scheduler |Outlook o Lync Web Scheduler |Outlook o Lync Web Scheduler |Outlook ||||Outlook |
|D &amp; A Manager |&#x2714;|||||||||||
|Disabilitare il video dei partecipanti|&#x2714;||&#x2714;|||||||||
 | |Disabilitare la messaggistica istantanea riunione  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Disattiva gruppo di destinatari   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Impostare tutti come partecipanti |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Produrre Skype Meeting Broadcast  |&#x2714;|||||||||||
|Il delegato può pianificare una riunione per conto del delegante  |&#x2714;|&#x2714;|&#x2714;|||||||||
|Sincronizzare i delegati tra Skype for Business e Outlook |&#x2714;||&#x2714;|||||||||
|Impostare Contenuti in evidenza video (blocca video) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Assegnare/assumere il controllo della condivisione dello schermo |&#x2714;||&#x2714;|||||||||

 &#x2776; i partecipanti non possono controllare i desktop condivisi dagli utenti di Skype for Business su Mac, Lync per Mac 2011 o Communicator per Mac 2011. Gli utenti di Skype for Business su Mac, Lync per Mac 2011 e Communicator per Mac 2011 non possono controllare i desktop condivisi dagli utenti di Windows. Questo non funzionerà anche per Skype for Business Web App su Max OSX.
  
 &#x2777; Per Skype for Business online, questa funzionalità richiede Servizi di conferenza PSTN Microsoft, Messaggistica unificata di Exchange o un provider di servizi di audioconferenza di terze parti.
  
 &#x2778; Il client Lync per Mac 2011 non è in grado di visualizzare le presentazioni di PowerPoint Microsoft Office 2013 quando sono state condivise in una conferenza da Skype for Business Web App.
  
## <a name="voice-telephony-support"></a>Supporto vocale (telefonia)

<a name="BKMK_Telephony"> </a>

Questa tabella illustra le funzionalità correlate al supporto dei servizi vocali.
  
> [!NOTE]
> Le funzionalità di Skype for Business Voice (Telefonia) sono limitate a determinati piani di sottoscrizione di Skype for Business Online. Per informazioni dettagliate, vedere la descrizione del servizio [Skype for Business online.](https://technet.microsoft.com/library/jj822172.aspx)
  
| Funzionalità/funzionalità | Client Skype for Business 2015 o 2016 | Skype for Business nel Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Avviare una chiamata |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Fare clic per chiamare un contatto  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Trasferire una chiamata |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gestire l'inoltro di chiamata |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gestire le impostazioni di intercettazione team |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Gestire i delegati |&#x2714;|&#x2714;Richiede Skype for Business Server 2015 CU4 o versione successiva |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Avviare una chiamata a un Response Group |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Supportare i servizi di emergenza (E-911)  |&#x2714;|&#x2714;Richiede Skype for Business Server 2015 CU6 o versione successiva |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notifica di messaggistica istantanea agli URI SIP per le chiamate E-911 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notifica di messaggistica istantanea alla lista di distribuzione per la chiamata E-911 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Connettersi al sistema di caselle vocali, configurare o modificare il messaggio di saluto |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Notifica di chiamata senza chiamata |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Eseguire chiamate per conto di un altro contatto (scenario manager/delegato) |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Gestire le chiamate di un altro contatto se configurato come delegato |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Gestire un elevato volume di chiamate |||||&#x2714;|&#x2714;||||
|Parcheggio di chiamata  |&#x2714;||&#x2714; &#x2776; |||||||
|Prelievo chiamata di gruppo  |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Routing basato su posizione  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gestire Response Group/Gruppo di chiamate del team |&#x2714;||&#x2714;|||||||
|Rispondi chiamata operatore automatico |&#x2714;||&#x2714;|||||||

&#x2776; Questa funzionalità non è disponibile in Skype for Business online.
  
## <a name="external-users-support"></a>Supporto per gli utenti esterni

<a name="BKMK_ExternalUsers"> </a>

Questa tabella illustra le funzionalità relative al supporto per gli utenti esterni ospitati nella rete PSTN.

|Funzionalità/funzionalità | Client Skype for Business 2015 o 2016 | Skype for Business nel Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Avviare conversazioni istantanee con un contatto pubblico  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Avviare conversazioni istantanee con un contatto federato |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Effettuare chiamate con due o più utenti esterni  <br/> (non disponibile in Skype for Business online) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>Supporto per la registrazione

<a name="BKMK_Recording"> </a>

Questa tabella illustra le funzionalità correlate al supporto per la registrazione delle riunioni.
  
| Futuro/funzionalità** | Client Skype for Business 2015 o 2016 | Skype for Business nel Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Registrazione sul lato client di audio, video, condivisione applicazioni, condivisione desktop e contenuto caricato |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Registrazione lato client di trasferimenti di file, pagine di OneNote condivise e annotazioni di PowerPoint |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Selezionare la risoluzione di registrazione preferita |&#x2714;||&#x2714;|||||||

 &#x2776; registrazione non è disponibile in alcuni piani autonomi di Skype for Business Online. La registrazione richiede diritti client Skype for Business completi.
  
 &#x2777; la registrazione dei trasferimenti di file, delle pagine condivise di OneNote e delle annotazioni di PowerPoint non è disponibile in Skype for Business online.
  
## <a name="modern-authentication"></a>Autenticazione moderna

<a name="BKMK_Recording"> </a>

Questa tabella illustra le funzionalità che richiedono il supporto per l'autenticazione moderna.
  
L'autenticazione moderna richiede anche una topologia descritta nelle [topologie di Skype for Business supportate con l'autenticazione moderna.](../../plan-your-deployment/modern-authentication/topologies-supported.md)

| Funzionalità/funzionalità | Client Skype for Business 2015 o 2016 | Skype for Business nel Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticazione moderna |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticazione a più fattori  |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticazione basata su certificato  |&#x2714;(solo dispositivo aggiunto a un dominio)| &#x2714;|&#x2714;(solo dispositivo aggiunto a un dominio)  |||||||
|Autenticazione Kerberos |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>Supporto per archiviazione, conformità e registrazione

<a name="BKMK_Archiving"> </a>

In questa tabella vengono illustrate le funzionalità relative al supporto per le funzioni di archiviazione e registrazione.

| Funzionalità/funzionalità | Client Skype for Business 2015 o 2016 | Skype for Business nel Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator per Mac 2011** | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Archiviazione delle conversazioni di messaggistica istantanea nella cronologia conversazioni di Outlook |&#x2714; &#x2776; |&#x2714;se la cronologia conversazioni sul lato server è abilitata |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Mantenuta in Communicator per Mac |Mantenuta in Lync per Mac |
|Archiviazione sul lato client di audio, video, condivisione applicazioni, condivisione desktop e contenuto caricato |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Archiviazione sul lato client di trasferimenti di file, pagine di OneNote condivise e annotazioni di PowerPoint  <br/> (non disponibile in Skype for Business online)|&#x2714;||&#x2714;||&#x2714;|||||
|Accedere ai log di accesso dall'icona di Skype for Business nella barra delle applicazioni |&#x2714;||&#x2714;|||||||

 &#x2776; per gli utenti di Skype for Business online, questa funzionalità richiede Exchange Online ed è controllata dall'attributo di blocco della cassetta postale di Exchange In-Place dell'utente.
  
## <a name="client-limitations"></a>Limitazioni client

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitazioni client di base

<a name="Full-Basic"> </a>

Le funzionalità seguenti sono disponibili con il client Completo e non sono disponibili con il client di base:

- Gestire le impostazioni di intercettazione team
- Gestire i delegati
- Gestire le chiamate di un altro contatto se configurato come delegato
- Gestire un elevato volume di chiamate
- Avviare una chiamata a un Response Group
- Parcheggio di chiamata
- Cambia messaggio di saluto
- Prelievo chiamata di gruppo
- I messaggi di posta elettronica di notifica di chiamata senza risposta non vengono generati quando lo stato di un utente è disabilitato e utilizza un client Outlook legacy (2013 o versioni precedenti)

### <a name="online-or-hybrid-user-account-limitations"></a>Limitazioni degli account utente online o ibridi

<a name="Online-Hybrid"> </a>

Gli account utente possono esistere online o locali e ciò influirà sulle funzionalità disponibili per tale utente. Gli utenti con account su Skype for Business online non avranno accesso alle seguenti funzionalità, anche con il client completo:
  
- Presenza avanzata: usare una foto da qualsiasi sito pubblico per l'immagine personale
- Contatti: cercare Response Group
- Supporto per la messaggistica istantanea: integrazione di Chat persistente (Group Chat)
- Supporto per la messaggistica istantanea: inoltrare una chat room di Persistent Chat a una riunione Skype for Business con un solo clic
- Utenti esterni: eseguire chiamate tra due o più parti con utenti esterni

## <a name="see-also"></a>Vedere anche

<a name="Types"> </a>

[Pianificare client e dispositivi](clients-and-devices.md)

[Aggiornamenti più recenti per le versioni di Skype for Business che usano Windows Installer (MSI)](../../sfb-client-updates.md)
