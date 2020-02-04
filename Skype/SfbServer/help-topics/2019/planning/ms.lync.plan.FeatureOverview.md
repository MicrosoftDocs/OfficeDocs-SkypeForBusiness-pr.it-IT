---
title: Panoramica delle caratteristiche (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Strumento di pianificazione di Skype for Business Server
ms.openlocfilehash: 6b90f29e37b64bfe2b1b808a23e11f66a8758760
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689831"
---
# <a name="feature-overview-planning-tool"></a>Panoramica delle caratteristiche (strumento di pianificazione)
 
Strumento di pianificazione di Skype for Business Server
  
È possibile usare la pagina **siti centrali** dello strumento di pianificazione per progettare la distribuzione di Skype for Business Server. È possibile creare due distribuzioni centralizzate o distribuite. Una distribuzione centralizzata ha un solo sito centrale, che ospita tutti gli utenti di Skype for business nell'organizzazione. Una distribuzione distribuita include più di un sito centrale. Se si distribuisce Skype for Business Server in più siti centrali, verrà immesso il numero di utenti in ogni sito centrale nello strumento di pianificazione.
  
Per completare la definizione del sito centrale, è prima di tutto necessario specificare le informazioni seguenti:
  
- **Nome sito** Immettere il nome del sito centrale.
    
- **Numero di utenti** Immettere il numero di utenti, inclusi gli utenti nei siti di succursale ospitati nel sito centrale.
    
- **Utenti cloud homed** Immettere il numero di utenti assegnati al sito centrale da Skype for business online.
    
## <a name="ui-elements"></a>Elementi dell'interfaccia utente

Gli elementi rimanenti sono stati popolati con le risposte fornite alle domande presentate nella procedura guidata Guida **introduttiva** oppure, se la procedura guidata è stata ignorata, popolata automaticamente dallo strumento di pianificazione.
  
### <a name="online-collaboration"></a>Collaborazione online

 La **collaborazione online** contiene le opzioni seguenti:
  
- **Messaggistica istantanea e presenza**
    
    La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale nei propri computer usando messaggi basati su testo. Sono supportate entrambe le sessioni di messaggistica istantanea a due parti e a più parti. La presenza fornisce informazioni agli utenti sullo stato degli altri nella rete. Lo stato presenza di un utente fornisce informazioni utili per consentire ad altri utenti di determinare se l'utente è online e come contattare meglio l'utente. Ad esempio, un utente che partecipa a una riunione è il più possibile contattato tramite posta elettronica.
    
- **Conferenze audio e video**
    
    I servizi di conferenza audio/video (A/V) consentono conferenze audio e video in tempo reale.
    
- **Chiamate in conferenza**
    
    I servizi di conferenza telefonica con accesso esterno consentono agli utenti di partecipare a un/V da un telefono della rete PSTN. I servizi di conferenza telefonica con accesso esterno richiedono la distribuzione delle applicazioni del servizio di conferenza e dell'annuncio.
    
- **Conferenze Web**
    
    I servizi di conferenza Web consentono agli utenti aziendali interni ed esterni al firewall di creare e partecipare a conferenze in tempo reale ospitate nei server interni.
    
- **Chat persistente**
    
    La chat persistente consente a più utenti di partecipare a conversazioni in cui pubblicano e accedono a contenuti su argomenti specifici, inclusi testo, collegamenti e file. Anche se gli utenti possono comunicare in tempo reale durante una sessione, il contenuto di ogni sessione è persistente, il che significa che continuerà a essere disponibile dopo la fine di una sessione.

    > [!NOTE] 
    > La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, Vedi [aggiornamento di Skype for business a Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.
    
### <a name="users"></a>Utenti

 **Gli utenti** contengono le opzioni seguenti:
  
- **Organizzazione interna**
    
- **Federazione con altre organizzazioni**
    
- **Federazione con versioni precedenti**
    
- **Federazione con provider di servizi di messaggistica istantanea pubblici** Consente agli utenti dell'organizzazione di stabilire comunicazioni con provider di servizi di messaggistica istantanea pubblici come MSN, Yahoo! e AOL. È necessaria una licenza separata per stabilire la Federazione con le reti di messaggistica istantanea pubblica.
    
- **Federazione con provider di servizi basato su XMPP**
    
    Skype for Business Server 2015 ha introdotto un proxy XMPP completamente integrato (distribuito sugli Edge Server) e un gateway XMPP distribuito nei server front-end. Puoi distribuire l'aggiunta e la configurazione del proxy XMPP e del gateway XMPP consentirà agli utenti di Skype for Business Server di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.
    
- **Mobilità**
    
    Quando si distribuisce il servizio di mobilità di Skype for Business Server, gli utenti possono usare dispositivi mobili Apple iOS, Android, Windows Phone o Nokia per eseguire attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.
    
- **Cassetta postale di Exchange W15**
    
    Skype for Business Server consente di archiviare i messaggi della segreteria telefonica in messaggistica unificata di Exchange. i messaggi della segreteria telefonica verranno quindi visualizzati come messaggi di posta elettronica nelle cassette postali degli utenti.

    > [!NOTE]
    > La messaggistica unificata di Exchange, come precedentemente nota, non è più disponibile in Exchange 2019, ma è comunque possibile usare il sistema telefonico per registrare i messaggi della segreteria telefonica e quindi abbandonare la registrazione nella cassetta postale di Exchange dell'utente. Per altre informazioni, vedere [pianificare il servizio di segreteria cloud](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
    
### <a name="voice"></a>Segreteria telefonica

 La **voce** contiene le opzioni seguenti:
  
- **VoIP aziendale**
    
    Enterprise Voice è la soluzione VoIP basata su software di Microsft. Enterprise Voice consente agli utenti di usare Skype for business per effettuare una telefonata dal proprio computer.
    
- **Messaggistica unificata di Exchange**
    
    La messaggistica unificata di Exchange combina la posta vocale e la posta elettronica in un'unica infrastruttura di messaggistica. Skype for Business Server 2015 usa la messaggistica unificata di Exchange per fornire risposte alle chiamate, accesso sottoscrittore, notifica delle chiamate e servizi di operatore automatico. Se si usano questi servizi, sarà necessario integrare Exchange UM e Skype for Business Server in una topologia di Active Directory condivisa.

    > [!NOTE]
    > La messaggistica unificata di Exchange, come precedentemente nota, non è più disponibile in Exchange 2019, ma è comunque possibile usare il sistema telefonico per registrare i messaggi della segreteria telefonica e quindi abbandonare la registrazione nella cassetta postale di Exchange dell'utente. Per altre informazioni, vedere [pianificare il servizio di segreteria cloud](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
    
### <a name="additional-deployment-options"></a>Opzioni di distribuzione aggiuntive

 Le **Opzioni di distribuzione aggiuntive** contengono le opzioni seguenti:
  
- **Disponibilità elevata**
    
    La disponibilità elevata consente ai server di standby di supportare il failover.
    
- **Ripristino d'emergenza**
    
    Le misure per il ripristino di emergenza consentono di associare i pool Front-end situati in due centri dati.
    
- **Monitoraggio**
    
    Il monitoraggio acquisisce i record dettagli chiamata correlati alle sessioni di comunicazione. Raccoglie anche metriche da sessioni audio e video presso gli endpoint dei partecipanti. Server di monitoraggio offre statistiche sull'utilizzo, tendenze e statistiche di qualità multimediale.
    
- **Archiviazione**
    
    Archiviazione archivia le conversazioni e le conferenze di messaggistica istantanea.
    
- **Integrazione dell'archiviazione di Exchange**
    
    Se si hanno utenti ospitati in Exchange e le cassette postali sono state inserite in blocco sul posto, è possibile selezionare l'opzione per l'integrazione dello spazio di archiviazione di Skype for Business Server con lo spazio di archiviazione di Exchange.
    
- **IPv4**
    
    Gli indirizzi IPv4 sono indirizzi a 32 bit che consentono a un computer di comunicare tramite Internet. A causa del numero crescente di dispositivi in tutto il mondo, gli indirizzi IPv4 disponibili sono esauriti. Per questo motivo, molti nuovi dispositivi si spostano nell'uso degli indirizzi IPv6.
    
- **IPv6**
    
    Gli indirizzi IPv6 eseguono la stessa funzione degli indirizzi IPv4 (con alcune funzionalità aggiuntive), ma invece di usare solo 32 bit, gli indirizzi IPv6 usano 128 bit. Questo fornisce non solo un nuovo set di indirizzi, ma anche un numero molto più grande.
    
- **Servizio Web aggiornamento dispositivi**
    
    Il servizio Web Update per dispositivi offre un modo automatizzato per aggiornare tutti i dispositivi, ad esempio Skype for business per Windows Phone, distribuiti all'esterno dell'organizzazione.
    
### <a name="server-applications"></a>Applicazioni server

 Le **applicazioni server** contengono le opzioni seguenti:
  
- **Response Group**
    
    L'applicazione Response Group risponde e distribuisce automaticamente le chiamate a un agente helpdesk disponibile.
    
- **Annuncio**
    
    Se si prevede di distribuire VoIP aziendale, è consigliabile essere in grado di configurare la modalità di gestione delle chiamate telefoniche se il numero composto è valido ma non è assegnato a un'area comune dell'utente. Gli amministratori possono configurare il servizio di annunci in modo che le chiamate vengano trasferite a una destinazione predeterminata (numero di telefono o URI SIP) oppure Riproduci un annuncio audio o entrambi. L'uso del servizio annunci evita la situazione in cui un chiamante effettua una chiamata errata e sente un tono di occupato o il client SIP riceve un messaggio di errore. La funzionalità del servizio di annuncio è una caratteristica PBX tipica. 
    
- **Parcheggio di chiamata**
    
    L'applicazione Call Park consente a un utente di VoIP aziendale di effettuare una chiamata in attesa da un telefono e quindi di ricevere la chiamata da un altro telefono senza legare le risorse al telefono che ha ricevuto la chiamata. L'applicazione Call Park è utile quando un utente deve trasferire una chiamata, ma il destinatario specifico non è noto. 
    
- **Assistente conferenza**
    
    L'applicazione per i servizi di conferenza include funzionalità di conferenza audio per gli utenti telefonici senza il servizio di un provider di servizi di audioconferenza di terze parti.
    
- **Annuncio conferenza**
    
    L'applicazione di annunci per conferenze produce toni che segnalano quando gli utenti entrano o lasciano una conferenza, nonché le notifiche agli utenti del telefono quando sono attivati o disattivati.
    
- **Servizio Controllo di ammissione di chiamata**
    
    Il controllo di ammissione di chiamata (CAC), noto anche come gestione della larghezza di banda WAN, consente di evitare una qualità scadente dell'esperienza per gli utenti sulle reti congestionate determinando, in base alla larghezza di banda disponibile, se consentire e nuove sessioni di comunicazioni in tempo reale stabilito. 
    
    > [!NOTE]
    > CAC controlla solo il traffico in tempo reale e non influisce sul traffico dei dati. 
  
    Se una nuova sessione vocale o video supera i limiti di larghezza di banda assegnati a una WAN, la sessione viene bloccata oppure (solo per le chiamate telefoniche) viene reinstradata alla rete PSTN.
    

