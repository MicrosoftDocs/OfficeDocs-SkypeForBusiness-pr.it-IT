---
title: Confronto tra funzionalità client desktop per Skype for Business Server 2015
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Riepilogo: gli amministratori di Skype for Business Server 2015 o Skype for business online possono usare queste tabelle per comprendere quali funzionalità sono supportate dai client.'
ms.openlocfilehash: a1df39ed3a426c7e01e753222526b0f18f260f19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187886"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Confronto tra funzionalità client desktop per Skype for Business Server 2015

**Riepilogo:** Gli amministratori di Skype for Business Server 2015 o Skype for business online possono usare queste tabelle per comprendere quali funzionalità sono supportate dai client.
  
 Prima di distribuire o eseguire l'aggiornamento a Skype for business, controlla quali clienti sono già in uso nell'organizzazione. Usare le tabelle seguenti per comprendere l'impatto del supporto delle caratteristiche su tali client. Questo può aiutare a comunicare le modifiche agli utenti, a gestire il processo di implementazione e a comprendere pienamente i vantaggi dell'aggiornamento al client più recente.
  
Alcune caratteristiche disponibili con Skype for Business Server 2015 non sono disponibili in Skype for business online, vedere [limitazioni degli account utente online o ibride](desktop-feature-comparison.md#Online-Hybrid) per specifiche. Gli amministratori di Skype for business online potrebbero voler fare riferimento alla [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) per informazioni sui diversi piani a loro disposizione.

Vedere [confronto delle caratteristiche client desktop per Skype for business 2019](../../../SfBServer2019/plan/feature-comparison.md) per il supporto client in Skype for business server 2019.
  
Le tabelle seguenti mostrano le caratteristiche disponibili per ogni client che funziona con Skype for Business Server 2015 o Skype for business online. Puoi anche fare riferimento al [confronto delle caratteristiche client per dispositivi mobili](mobile-feature-comparison.md) per i confronti delle caratteristiche dei client Skype for business per Smart Phone e tablet. La licenza per l'accesso client o la licenza per l'abbonamento agli acquisti dell'organizzazione avranno anche un impatto sulle caratteristiche disponibili per gli utenti. Se si distribuisce il client completo o di base agli utenti dipende dalla licenza o dal piano scelto dall'organizzazione per l'acquisto. Per altre informazioni, vedere la [Guida alla gestione delle licenze](https://products.office.com/en-us/skype-for-business/it-pros) .
  
> [!IMPORTANT]
> Skype for Business Server 2015 e Skype for business online supportano i seguenti client rilasciati in precedenza: Lync 2013, Lync 2010, Lync 2010 mobile, Lync Phone Edition e Lync 2010 Attendant. Per informazioni su questi client quando vengono usati con altri server, vedere le [tabelle di confronto dei client per Lync server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) e le [tabelle di confronto dei client per Lync Server 2010](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.14%29.aspx).

> [!NOTE]
> Il client di supervisore di **Lync 2010** non è supportato in Skype for business online.

> [!NOTE]
> L'app client browser Skype for Business Web App e riunioni Skype app Windows 10 offre solo [supporto](desktop-feature-comparison.md#BKMK_Conferencing)per le riunioni. Vedere [piano per i client di riunioni (app Web e riunioni)](meetings-clients.md) per altre informazioni su questi client.
  
## <a name="enhanced-presence-support"></a>Supporto per la presenza avanzata

<a name="BKMK_EnhancedPresence"> </a>

Questa tabella illustra le caratteristiche di presenza avanzate che si estendono oltre una semplice indicazione del fatto che un utente sia online, offline, occupato e così via.
  
|Funzionalità/funzionalità|Client Skype for business 2015 o 2016| Skype for Business su Mac|Client Lync 2013|App Lync di Windows Store|Lync 2010 | Assistente di Lync 2010|Lync Phone Edition|Communicator per Mac 2011|Lync per Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Stato pubblicazione |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Stato visualizzazione   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualizzare le note sullo stato e i messaggi fuori sede |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aggiungere un percorso personalizzato |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Aggiungere una nota personalizzata |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Usare una foto da qualsiasi sito pubblico per l'immagine personale (non disponibile in Skype for business online) |&#x2714;||&#x2714;|||||||

 &#x2776; non supporta lo stato di pubblicazione in base alle informazioni sulla disponibilità del calendario.
  
## <a name="contacts-and-contact-groups-support"></a>Supporto per contatti e gruppi di contatti

<a name="BKMK_Contacts"> </a>

Questa tabella illustra le caratteristiche relative alla gestione dei contatti di messaggistica istantanea e presenza.

|Funzionalità/funzionalità|Client Skype for business 2015 o 2016| Skype for Business su Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Assistente di Lync 2010 | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Elenco contatti prepopolato |&#x2714;|||||||||
|Visualizzare e modificare l'elenco contatti |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Contrassegnare i contatti per gli avvisi di modifica dello stato |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Controllare le relazioni di privacy |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Eseguire ricerche nella rubrica aziendale |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Cercare i contatti di Microsoft Outlook |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gestire i gruppi di contatti |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Espandere i gruppi di distribuzione e i gruppi di Office 365 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Cercare gruppi di risposte  <br/> (non disponibile in Skype for business online) |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Visualizzare il gruppo contatti recenti |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Visualizzare il gruppo conversazioni correnti |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Visualizzare visualizzazioni di contatto alternate (ad esempio, riquadro) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Ordinare i contatti per gruppo, relazione o nuovo (persone che hanno aggiunto l'elenco contatti) |&#x2714;||&#x2714;|Ordinare in base al gruppo |&#x2714;|&#x2714;||||
|Ordinare i contatti in base allo stato (disponibilità) |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Cercare e aggiungere contatti di Exchange |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>Supporto di messaggistica istantanea

<a name="BKMK_IMSupport"> </a>

Questa tabella illustra le caratteristiche relative al supporto di messaggistica istantanea.

|Funzionalità/funzionalità | Client Skype for business 2015 o 2016 |  Skype for Business su Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Assistente di Lync 2010 | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Avviare messaggi istantanei o inviare messaggi di posta elettronica a un contatto |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Spostarsi tra più conversazioni ISTANTANEe/tenere traccia di più conversazioni in una singola finestra a schede |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Registrare conversazioni ISTANTANEe in Outlook |&#x2714;|&#x2714;se la cronologia delle conversazioni sul lato server è attivata  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Salvato in Communicator per Mac |Salvato in Lync per Mac |
|Usare i modelli di conversazione preparati |||||&#x2714;|&#x2714;||||
|Controllare l'ortografia |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Ricerca competenze (con integrazione di SharePoint Server)  <br/> (In locale Skype for Business Server e SharePoint 2013 locale sono necessari per la ricerca di competenze). |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Integrazione chat persistente (chat di gruppo)  <br/> (non disponibile per Skype for business online) |&#x2714;||&#x2714;|||||||
|Escalation di una chat room persistente in una riunione Skype for business con un solo clic  <br/> (non disponibile per Skype for business online) |&#x2714;||&#x2714;|||||||
|Immagini in linea del mittente e del destinatario nella finestra di messaggistica istantanea |&#x2714;||&#x2714;|&#x2714;||||||
|Inviare messaggi input penna ||||&#x2714;||||||
|Ricevere messaggi input penna |&#x2714;||&#x2714;|&#x2714;||||||
|Impostare messaggi di messaggistica istantanea come priorità alta |&#x2714;||&#x2714;|||||||
|Trasferire file in conversazioni di messaggistica istantanea peer-to-peer |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>Supporto per le riunioni

<a name="BKMK_Conferencing"> </a>

Questa tabella illustra le caratteristiche relative al supporto delle riunioni.
  
> [!NOTE]
> Le caratteristiche delle riunioni Skype for business non sono disponibili in Skype for business online standalone Plan 1.  Il piano 1 viene [ritirato](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement).

Nelle sessioni Skype-to-Skype, un utente di Skype for business online Plan 1 può partecipare alla condivisione desktop e alla condivisione delle applicazioni se è invitato da un utente che ha accesso alle funzionalità di condivisione.
Per informazioni dettagliate, vedere la [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/jj822172.aspx).
  
|Funzionalità/funzionalità | Client di 2016 per Skype for business |  Skype for Business su Mac | App web Skype for business | Client di 2015 per Skype for business | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Assistente di Lync 2010 | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Aggiungere l'audio del computer |&#x2714;|&#x2714;|&#x2714; (richiede il plug-in) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aggiungere un video |&#x2714;|&#x2714;|&#x2714; (richiede il plug-in) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Visualizzare il video in più parti (visualizzazione raccolta) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Condivisione dello schermo basata su video |&#x2714;|&#x2714;|&#x2714;solo visualizzazione |||||||||
|Usare i controlli relatore in-meeting |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Accedere a un elenco dettagliato delle riunioni |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Partecipare a un messaggio istantaneo a più parti |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Condividere il desktop (se abilitato) |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776;  (richiede il plug-in) |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Condividere un programma (se abilitato) |&#x2714;|Solo visualizzazione   |&#x2714; (richiede il plug-in) |&#x2714;|&#x2714;||&#x2714;||||Solo visualizzazione |
|Aggiungere partecipanti anonimi (se abilitati) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Usare le riunioni audio con accesso esterno |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Avviare una riunione meeting Now |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Aggiungere e presentare file di Microsoft PowerPoint |&#x2714;| &#x2778; annotazioni non disponibili |&#x2714;|&#x2714;|&#x2714;|Presenta solo |&#x2714;|||| &#x2778; solo visualizzazione, annotazioni non disponibili |
|Spostarsi tra i file di Microsoft PowerPoint |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Aggiungere e modificare le note della riunione di OneNote |&#x2714;||Modifica solo (non aggiungere) |&#x2714;|&#x2714;|||||||
|Usare una lavagna |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Eseguire sondaggi |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Caricare file da condividere con altri |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Pianificare una riunione o una conferenza |Outlook o Skype for Business Web Scheduler |Outlook o Skype for Business Web Scheduler |Programmatore web Skype for business |Outlook o Skype for Business Web Scheduler |Outlook o Lync Web Scheduler |Outlook o Lync Web Scheduler |Outlook ||||Outlook |
|Responsabile&amp;di Q A |&#x2714;|||||||||||
|Disabilitare il video dei partecipanti|&#x2714;||&#x2714;|||||||||
 | |Disabilitare la messaggistica istantanea della riunione  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Disattivare l'audio del pubblico   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Rendere tutti partecipanti un partecipante |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Produrre Skype meeting broadcast  |&#x2714;|||||||||||
|Il delegato può pianificare una riunione per conto del delegante  |&#x2714;|&#x2714;|&#x2714;|||||||||
|Sincronizzare i delegati tra Skype for business e Outlook |&#x2714;||&#x2714;|||||||||
|Impostare il video in evidenza (blocco video) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Assegnare/assumere il controllo della condivisione dello schermo |&#x2714;||&#x2714;|||||||||

 &#x2776; i partecipanti non possono controllare i desktop condivisi da Skype for business su Mac, Lync per Mac 2011 o Communicator per Mac 2011 utenti. Skype for business su Mac, Lync per Mac 2011 e Communicator per Mac 2011 gli utenti non possono controllare i desktop condivisi dagli utenti di Windows. Questo non funzionerà anche per Skype for Business Web App su Max OSX.
  
 &#x2777; per Skype for business online, questa funzionalità richiede conferenze PSTN Microsoft, messaggistica unificata di Exchange o un provider di servizi di audioconferenza di terze parti.
  
 &#x2778; il client Lync per Mac 2011 non può visualizzare le presentazioni di PowerPoint di Microsoft Office 2013 quando è stato condiviso in una conferenza da Skype for Business Web App.
  
## <a name="voice-telephony-support"></a>Supporto vocale (telefonia)

<a name="BKMK_Telephony"> </a>

Questa tabella illustra le caratteristiche relative al supporto dei servizi vocali.
  
> [!NOTE]
> Le caratteristiche di Skype for Business Voice (telefonia) sono limitate a determinati piani di abbonamento a Skype for business online. > per informazioni dettagliate, vedere la [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/jj822172.aspx).
  
| Funzionalità/funzionalità | Client Skype for business 2015 o 2016 |  Skype for Business su Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Assistente di Lync 2010 | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Avviare una chiamata |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Fare clic per chiamare un contatto  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Trasferire una chiamata |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gestire l'inoltro di chiamata |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gestire le impostazioni delle chiamate di Team |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Gestire i delegati |&#x2714;|&#x2714;richiede Skype for Business Server 2015 CU4 o versione successiva |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Avviare una chiamata a un gruppo di risposte |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Supportare i servizi di emergenza (E-911)  |&#x2714;|&#x2714;richiede Skype for Business Server 2015 CU6 o versione successiva |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notifica di messaggistica istantanea agli URI SIP per la chiamata E-911 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notifica di messaggistica istantanea alla lista di distribuzione per la chiamata E-911 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Connettersi alla segreteria telefonica, configurare o modificare il messaggio di saluto |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Notifica di chiamata senza risposta |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Effettuare chiamate per conto di un altro contatto (scenario manager/delegato) |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Gestire le chiamate di un altro se configurato come delegato |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Gestire un elevato volume di chiamate |||||&#x2714;|&#x2714;||||
|Parcheggio delle chiamate  |&#x2714;||&#x2714; &#x2776; |||||||
|Raccolta chiamate di gruppo  |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Routing basato sulla posizione  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gestisci gruppo risposta/gruppi di chiamate team |&#x2714;||&#x2714;|||||||

 &#x2776; questa funzionalità non è disponibile in Skype for business online.
  
## <a name="external-users-support"></a>Supporto per utenti esterni

<a name="BKMK_ExternalUsers"> </a>

Questa tabella include le caratteristiche relative al supporto per gli utenti esterni ospitati nella rete PSTN.

|Funzionalità/funzionalità | Client Skype for business 2015 o 2016 |  Skype for Business su Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Assistente di Lync 2010 | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Avviare un messaggio istantaneo con un contatto pubblico  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Avviare un messaggio istantaneo con un contatto federato |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Eseguire chiamate a due o più partecipanti con utenti esterni  <br/> (non disponibile in Skype for business online) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>Supporto per la registrazione

<a name="BKMK_Recording"> </a>

Questa tabella illustra le caratteristiche relative al supporto per le riunioni di registrazione.
  
| Futuro/funzionalità * * | Client Skype for business 2015 o 2016 |  Skype for Business su Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Assistente di Lync 2010 | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Registrazione lato client di audio, video, condivisione applicazioni, condivisione desktop e contenuto caricato |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Registrazione sul lato client di trasferimenti di file, pagine condivise di OneNote e annotazioni di PowerPoint |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Selezionare la risoluzione di registrazione preferita |&#x2714;||&#x2714;|||||||

 &#x2776; registrazione non è disponibile in determinati piani autonomi di Skype for business online. La registrazione richiede i diritti client Skype for business completo.
  
 &#x2777; la registrazione di trasferimenti di file, pagine di OneNote condivise e annotazioni di PowerPoint non è disponibile in Skype for business online.
  
## <a name="modern-authentication"></a>Autenticazione moderna

<a name="BKMK_Recording"> </a>

Questa tabella include le caratteristiche che richiedono il supporto per l'autenticazione moderna.
  
L'autenticazione moderna richiede anche una topologia descritta nelle [topologie Skype for business supportate con l'autenticazione moderna](../../plan-your-deployment/modern-authentication/topologies-supported.md).

| Funzionalità/funzionalità | Client Skype for business 2015 o 2016 |  Skype for Business su Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Assistente di Lync 2010 | Lync Phone Edition | Communicator per Mac 2011 | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticazione moderna |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticazione a più fattori  |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticazione basata su cert  |&#x2714; (solo per il dispositivo collegato al dominio)| &#x2714;|&#x2714; (solo per il dispositivo collegato al dominio)  |||||||
|Autenticazione Kerberos |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>Supporto per l'archiviazione, la conformità e la registrazione

<a name="BKMK_Archiving"> </a>

Questa tabella illustra le caratteristiche relative al supporto per le funzioni di archiviazione e registrazione.

| Funzionalità/funzionalità | Client Skype for business 2015 o 2016 |  Skype for Business su Mac | Client Lync 2013 | App Lync di Windows Store | Lync 2010 | Assistente di Lync 2010 | Lync Phone Edition | **Communicator per Mac 2011** | Lync per Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Archiviazione delle conversazioni di messaggistica istantanea nella cronologia delle conversazioni di Outlook |&#x2714; &#x2776; |&#x2714;se è abilitata la cronologia delle conversazioni sul lato server |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Salvato in Communicator per Mac |Salvato in Lync per Mac |
|Archiviazione lato client di audio, video, condivisione applicazioni, condivisione desktop e contenuto caricato |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Archiviazione lato client di trasferimenti di file, pagine condivise di OneNote e annotazioni di PowerPoint  <br/> (non disponibile in Skype for business online)|&#x2714;||&#x2714;||&#x2714;|||||
|Accedere ai log di accesso dall'icona di Skype for business nella barra delle applicazioni |&#x2714;||&#x2714;|||||||

 &#x2776; per gli utenti di Skype for business online, questa funzionalità richiede Exchange Online ed è controllata dall'attributo di blocco sul posto della cassetta postale di Exchange dell'utente.
  
## <a name="client-limitations"></a>Limitazioni del client

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitazioni del client di base

<a name="Full-Basic"> </a>

Le caratteristiche seguenti sono disponibili usando il client completo e non sono disponibili con il client di base:

- Gestire le impostazioni delle chiamate di Team
- Gestire i delegati
- Gestire le chiamate di un altro se configurato come delegato
- Gestire un volume elevato di chiamate
- Avviare una chiamata a un gruppo di risposte
- Parcheggio delle chiamate
- Modificare il messaggio di saluto
- Raccolta chiamate di gruppo
- I messaggi di notifica delle chiamate senza risposta non vengono generati quando un utente è abilitato alla messaggistica unificata e usa un client Outlook legacy (2013 o versioni precedenti)

### <a name="online-or-hybrid-user-account-limitations"></a>Limitazioni degli account utente online o ibride

<a name="Online-Hybrid"> </a>

Gli account utente possono esistere online o locale e questo influirà sulle funzionalità disponibili per l'utente. Gli utenti con account in Skype for business online non avranno accesso alle caratteristiche seguenti, anche con il client completo:
  
- Presenza avanzata: usare una foto da qualsiasi sito pubblico per l'immagine personale
- Contatti: cercare gruppi di risposte
- Supporto per la messaggistica istantanea: integrazione della chat persistente (chat di gruppo)
- Supporto per i messaggi istantanei: aumentare una chat room persistente in una riunione Skype for business con un solo clic
- Utenti esterni: effettuare chiamate a due o più partecipanti con utenti esterni

## <a name="see-also"></a>Vedere anche

<a name="Types"> </a>

[Pianificare client e dispositivi](clients-and-devices.md)

[Aggiornamenti più recenti per le versioni di Skype for business che usano Windows Installer (MSI)](../../sfb-client-updates.md)
