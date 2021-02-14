---
title: Panoramica delle funzionalità (Strumento di pianificazione)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Strumento di pianificazione di Skype for Business Server
ms.openlocfilehash: f317b2963e6db83e733a3f0b259a6d0bfe466c9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819826"
---
# <a name="feature-overview-planning-tool"></a>Panoramica delle funzionalità (Strumento di pianificazione)
 
Strumento di pianificazione di Skype for Business Server
  
È possibile utilizzare la **pagina Siti** centrali dello Strumento di pianificazione per progettare la distribuzione di Skype for Business Server. È possibile creare due distribuzioni centralizzate o distribuite. Una distribuzione centralizzata ha un solo sito centrale, che contiene tutti gli utenti di Skype for Business nell'organizzazione. Una distribuzione distribuita include più di un sito centrale. Se si distribuisce Skype for Business Server in più siti centrali, si immetterà il numero di utenti in ogni sito centrale nello strumento di pianificazione.
  
Per completare la definizione del sito centrale, è innanzitutto necessario fornire le informazioni seguenti:
  
- **Nome sito** Immettere il nome del sito centrale.
    
- **Numero di utenti** Immettere il numero di utenti, inclusi gli utenti dei siti di succursale ospitati nel sito centrale.
    
- **Utenti ospitati nel cloud** Immettere il numero di utenti ospitati nel sito centrale da Skype for Business online.
    
## <a name="ui-elements"></a>Elementi dell'interfaccia utente

Gli elementi rimanenti sono stati popolati con le  risposte fornite alle domande presentate nella procedura guidata Per iniziare oppure, se la procedura guidata è stata ignorata, vengono popolate automaticamente dallo strumento di pianificazione.
  
### <a name="online-collaboration"></a>Collaborazione online

 **La collaborazione** online contiene le opzioni seguenti:
  
- **Messaggistica istantanea e presenza**
    
    La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale sui propri computer utilizzando messaggi di testo. Sono supportate le sessioni di messaggistica istantanea sia tra due che tra più parti. La presenza fornisce agli utenti informazioni sullo stato di altri utenti della rete. Lo stato di presenza di un utente fornisce informazioni che consentono ad altri di determinare se l'utente è online e come contattare al meglio l'utente. Ad esempio, un utente che si trova in una riunione viene contattato tramite posta elettronica.
    
- **Conferenze audio e video**
    
    Le conferenze audio/video (A/V) consentono conferenze audio e video in tempo reale.
    
- **Chiamate in conferenza**
    
    Le conferenze telefoniche con accesso esterno consentono agli utenti di partecipare a un A/V da un telefono della rete PSTN. Per le conferenze telefoniche con accesso esterno è necessario distribuire le applicazioni Operatore Conferenza e Servizio annuncio conferenza.
    
- **Conferenze Web**
    
    Le conferenze Web consentono agli utenti aziendali all'interno e all'esterno del firewall di creare e partecipare a conferenze in tempo reale ospitate nei server interni.
    
- **Chat persistente**
    
    Persistent Chat consente a più utenti di partecipare a conversazioni in cui pubblicano e accedono a contenuto su argomenti specifici, tra cui testo, collegamenti e file. Nonostante gli utenti possano comunicare in tempo reale durante una sessione, il contenuto di ogni sessione può essere salvato in modo permanente e quindi restare disponibile anche al termine di una sessione.

    > [!NOTE] 
    > La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. Le stesse funzionalità sono disponibili in Teams. Per altre informazioni, vedere [Aggiornamento da Skype for Business a Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here) Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.
    
### <a name="users"></a>Utenti

 **Gli** utenti contengono le opzioni seguenti:
  
- **Organizzazione interna**
    
- **Federazione con altre organizzazioni**
    
- **Federazione con versioni precedenti**
    
- **Federazione con provider di servizi di messaggistica istantanea pubblici** Consente agli utenti dell'organizzazione di stabilire comunicazioni con provider di servizi di messaggistica istantanea pubblici come MSN, Yahoo! e AOL. È necessaria una licenza separata per stabilire la federazione con reti di messaggistica istantanea pubbliche.
    
- **Federazione con provider di servizi basato su XMPP**
    
    Skype for Business Server 2015 ha introdotto un proxy XMPP completamente integrato (distribuito nei server perimetrali) e un gateway XMPP distribuito nei Front End Server. È possibile distribuire l'aggiunta e la configurazione del proxy XMPP e del gateway XMPP consentirà agli utenti di Skype for Business Server di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.
    
- **Mobilità**
    
    Quando si distribuisce il servizio per dispositivi mobili Skype for Business Server, gli utenti possono utilizzare i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia supportati per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.
    
- **Cassetta postale di Exchange W15**
    
    Skype for Business Server consente di archiviare i messaggi della segreteria telefonica nella messaggistica unificata di Exchange. Tali messaggi della segreteria telefonica verranno quindi visualizzati come messaggi di posta elettronica nelle cartelle Posta in arrivo degli utenti.

    > [!NOTE]
    > La messaggistica unificata di Exchange come precedentemente noto non è più disponibile in Exchange 2019, ma è comunque possibile utilizzare Sistema telefonico per registrare i messaggi vocali e quindi lasciare la registrazione nella cassetta postale di Exchange di un utente. Per [ulteriori informazioni, vedere Plan Cloud Voicemail service.](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)
    
### <a name="voice"></a>Voce

 **Voice** contiene le opzioni seguenti:
  
- **VoIP aziendale**
    
    VoIP aziendale è la soluzione VoIP basata su software di Microsft. VoIP aziendale consente agli utenti di usare Skype for Business per eseguire una chiamata telefonica dal proprio computer.
    
- **Messaggistica unificata di Exchange**
    
    La messaggistica unificata di Exchange combina la posta vocale e la posta elettronica in un'unica infrastruttura di messaggistica. Skype for Business Server 2015 utilizza la messaggistica unificata di Exchange per fornire servizi di risposta alle chiamate, accesso sottoscrittore, notifica di chiamata e operatore automatico. Se si utilizzano questi servizi, sarà necessario integrare la messaggistica unificata di Exchange e Skype for Business Server in una topologia di Active Directory condivisa.

    > [!NOTE]
    > La messaggistica unificata di Exchange come precedentemente noto non è più disponibile in Exchange 2019, ma è comunque possibile utilizzare Sistema telefonico per registrare i messaggi vocali e quindi lasciare la registrazione nella cassetta postale di Exchange di un utente. Per [ulteriori informazioni, vedere Plan Cloud Voicemail service.](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)
    
### <a name="additional-deployment-options"></a>Opzioni di distribuzione aggiuntive

 **Opzioni di distribuzione aggiuntive** contiene le opzioni seguenti:
  
- **Disponibilità elevata**
    
    La disponibilità elevata abilita i server di standby per il supporto del failover.
    
- **Ripristino d'emergenza**
    
    Le misure di ripristino di emergenza consentono di associare pool Front End situati in due datacenter.
    
- **Monitoraggio**
    
    Il monitoraggio acquisisce i record dettagli chiamata correlati alle sessioni di comunicazione. Raccoglie inoltre le metriche dalle sessioni audio e video agli endpoint dei partecipanti. Monitoring Server fornisce statistiche di utilizzo, tendenze e statistiche sulla qualità multimediale.
    
- **Archiviazione**
    
    L'archiviazione archivia conversazioni e conferenze di messaggistica istantanea.
    
- **Integrazione di Archiviazione Exchange**
    
    Se si dispone di utenti ospitati in Exchange e le relative cassette postali sono state messe In-Place hold, è possibile selezionare l'opzione per integrare l'archiviazione di Skype for Business Server con l'archiviazione di Exchange.
    
- **IPv4**
    
    Gli indirizzi IPv4 sono indirizzi a 32 bit che consentono a un computer di comunicare tramite Internet. A causa del numero crescente di dispositivi in tutto il mondo, gli indirizzi IPv4 disponibili si sono eseguiti. Per questo, molti nuovi dispositivi stanno passando all'utilizzo di indirizzi IPv6.
    
- **IPv6**
    
    Gli indirizzi IPv6 eseguono la stessa funzione degli indirizzi IPv4 (con alcune funzionalità aggiuntive), ma invece di utilizzare solo i 32 bit, gli indirizzi IPv6 utilizzano i 128 bit. In questo modo non solo viene fornito un nuovo set di indirizzi, ma anche un numero molto maggiore di indirizzi.
    
- **Servizio Web di aggiornamento del dispositivo**
    
    Il servizio Web Aggiornamento dispositivi offre un modo automatico per aggiornare tutti i dispositivi, ad esempio Skype for Business per Windows Phone, distribuiti all'esterno dell'organizzazione.
    
### <a name="server-applications"></a>Applicazioni server

 **Le applicazioni server** contengono le opzioni seguenti:
  
- **Response Group**
    
    L'applicazione Response Group risponde e distribuisce automaticamente le chiamate a un agente dell'helpdesk disponibile.
    
- **Annuncio**
    
    Se si prevede di distribuire VoIP aziendale, è possibile configurare la modalità di gestione delle chiamate telefoniche se il numero composto è valido ma non assegnato a un'area comune dell'utente. Gli amministratori possono configurare il servizio Annunci in modo che queste chiamate possano essere trasferite a una destinazione predeterminata (numero di telefono o URI SIP) oppure riprodurre un annuncio audio o entrambi. L'utilizzo del servizio Annuncio evita la situazione in cui un chiamante fa un'errata esecuzione delle chiamate e sente un segnale di occupato o il client SIP riceve un messaggio di errore. La funzionalità Servizio annunci è una tipica funzionalità PBX. 
    
- **Parcheggio di chiamata**
    
    L'applicazione Parcheggio di chiamata consente a un utente VoIP aziendale di mettere in attesa una chiamata da un telefono e quindi di ricevere la chiamata da un altro telefono senza che le risorse del telefono che ha ricevuto la chiamata. L'applicazione Parcheggio di chiamata è utile quando un utente deve trasferire una chiamata, ma il destinatario specifico è sconosciuto. 
    
- **Operatore conferenza**
    
    L'applicazione Operatore Conferenza offre funzionalità di audioconferenza agli utenti di telefonia senza il servizio di un provider di servizi di audioconferenza di terze parti.
    
- **Annuncio conferenza**
    
    L'applicazione Annuncio conferenza produce toni che segnalano quando gli utenti entrano o abbandonano una conferenza, nonché notifiche agli utenti di telefonia quando vengono disattivati o riattivati.
    
- **Servizio Controllo di ammissione di chiamata**
    
    Il servizio Controllo di ammissione di chiamata, noto anche come gestione della larghezza di banda WAN, consente di evitare la scarsa qualità dell'esperienza per gli utenti su reti congestionate determinando, in base alla larghezza di banda disponibile, se consentire e stabilire nuove sessioni di comunicazione in tempo reale. 
    
    > [!NOTE]
    > Il servizio Controllo di ammissione di chiamata controlla solo il traffico in tempo reale e non influisce sul traffico dati. 
  
    Se una nuova sessione vocale o video supera i limiti di larghezza di banda allocati su una rete WAN, la sessione viene bloccata o (solo per le chiamate telefoniche) reindirizzata alla rete PSTN.
    

