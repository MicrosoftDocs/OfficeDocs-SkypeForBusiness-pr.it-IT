---
title: Panoramica delle funzionalità (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Strumento di pianificazione di Skype for Business Server 2015
ms.openlocfilehash: 3aa259314d8a92142cf37dcd3611773490248e02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834786"
---
# <a name="feature-overview-planning-tool"></a>Panoramica delle funzionalità (strumento di pianificazione)
 
Strumento di pianificazione di Skype for Business Server 2015
  
È possibile utilizzare la pagina **siti centrali** dello strumento di pianificazione per progettare la distribuzione di Skype for Business Server. È possibile creare due distribuzioni centralizzate o distribuite. Una distribuzione centralizzata ha un solo sito centrale, che ospita tutti gli utenti di Skype for business nell'organizzazione. Una distribuzione distribuita dispone di più di un sito centrale. Se si distribuisce Skype for Business Server in più siti centrali, immettere il numero di utenti in ogni sito centrale dello strumento di pianificazione.
  
Per completare la definizione del sito centrale, è innanzitutto necessario fornire le informazioni seguenti:
  
- **Nome sito** Immettere il nome del sito centrale.
    
- **Numero di utenti** Immettere il numero di utenti, inclusi gli utenti nei siti di succursale che sono ospitati nel sito centrale.
    
- **Utenti cloud homed** Immettere il numero di utenti che si trovano nel sito centrale da Skype for business online.
    
> [!NOTE]
> Questo strumento non verrà aggiornato per Skype for Business Server 2019.

## <a name="ui-elements"></a>Elementi dell'interfaccia utente

Gli elementi restanti sono stati popolati con le risposte fornite alle domande presentate nella procedura guidata di guida **introduttiva** oppure, se la procedura guidata è stata ignorata, viene popolata automaticamente dallo strumento di pianificazione.
  
### <a name="online-collaboration"></a>Collaborazione online

 La **collaborazione online** contiene le opzioni seguenti:
  
- **Messaggistica istantanea e presenza**
    
    La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale nei propri computer usando messaggi basati su testo. Sono supportate le sessioni di messaggistica istantanea sia tra due che tra più parti. La presenza fornisce informazioni agli utenti sullo stato di altre persone sulla rete. Lo stato di presenza di un utente fornisce informazioni utili per consentire ad altri utenti di stabilire se l'utente è online e come contattare al meglio l'utente. Ad esempio, un utente che si trova in una riunione è il più possibile contattato tramite posta elettronica.
    
- **Conferenze audio e video**
    
    I servizi di conferenza audio/video (A/V) consentono conferenze audio e video in tempo reale.
    
- **Chiamate in conferenza**
    
    Le conferenze telefoniche con accesso esterno consentono agli utenti di partecipare a un A/V da un telefono della rete PSTN. Per le conferenze telefoniche con accesso esterno è necessario distribuire l'operatore conferenza e le applicazioni di servizio per i servizi di conferenza.
    
- **Conferenze Web**
    
    Web Conferencing consente agli utenti dell'organizzazione all'interno e all'esterno del firewall di creare e partecipare a conferenze in tempo reale ospitate nei server interni.
    
- **Chat persistente**
    
    La chat persistente consente a più utenti di partecipare a conversazioni nelle quali postano e accedono a contenuti su argomenti specifici, inclusi testo, collegamenti e file. Nonostante gli utenti possano comunicare in tempo reale durante una sessione, il contenuto di ogni sessione può essere salvato in modo permanente e quindi restare disponibile anche al termine di una sessione.
    
### <a name="users"></a>Utenti

 **Gli utenti** contengono le opzioni seguenti:
  
- **Organizzazione interna**
    
- **Federazione con altre organizzazioni**
    
- **Federazione con versioni precedenti**
    
- **Federazione con provider di servizi di messaggistica istantanea pubblici** Consente agli utenti dell'organizzazione di stabilire la comunicazione con provider di servizi di messaggistica istantanea pubblici quali MSN, Yahoo! e AOL. È necessaria una licenza separata per stabilire la Federazione con le reti di messaggistica istantanea pubblica.
    
- **Federazione con provider di servizi basato su XMPP**
    
    Skype for Business Server 2015 introduce un proxy XMPP completamente integrato (distribuito sui server perimetrali) e un gateway XMPP distribuito nei server front end. È possibile distribuire l'aggiunta e la configurazione del proxy XMPP e del gateway XMPP consentirà agli utenti di Skype for Business Server 2015 di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
    
- **Mobilità**
    
    Quando si distribuisce il servizio per dispositivi mobili di Skype for Business Server 2015, gli utenti possono utilizzare i sistemi Apple iOS, Android, Windows Phone o Nokia per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.
    
- **Cassetta postale di Exchange di W15**
    
    Skype for Business Server 2015 consente di disporre di messaggi vocali archiviati nella messaggistica unificata di Exchange. i messaggi vocali verranno quindi visualizzati come messaggi di posta elettronica nelle cassette postali degli utenti.
    
### <a name="voice"></a>Voce

 **Voice** contiene le opzioni seguenti:
  
- **VoIP aziendale**
    
    Enterprise Voice è la soluzione VoIP basata su software di Microsoft. VoIP aziendale consente agli utenti di utilizzare Skype for business per effettuare una telefonata dal proprio computer.
    
- **Messaggistica unificata di Exchange**
    
    La messaggistica unificata di Exchange combina la posta vocale e la posta elettronica in un'unica infrastruttura di messaggistica. Skype for Business Server 2015 utilizza la messaggistica unificata di Exchange per fornire servizi di ricezione chiamata, accesso sottoscrittore, notifica di chiamata e operatore automatico. Se si utilizzano questi servizi, sarà necessario integrare la messaggistica unificata di Exchange e Skype for Business Server in una topologia di Active Directory condivisa.
    
### <a name="additional-deployment-options"></a>Opzioni di distribuzione aggiuntive

 **Altre opzioni di distribuzione** contengono le opzioni seguenti:
  
- **Disponibilità elevata**
    
    La disponibilità elevata consente ai server di standby di supportare il failover.
    
- **Ripristino d'emergenza**
    
    Le misure di ripristino di emergenza consentono di associare pool Front end situati in due datacenter.
    
- **Monitoraggio**
    
    Il monitoraggio acquisisce i record dettagli chiamata relativi alle sessioni di comunicazione. Raccoglie anche metriche da sessioni audio e video negli endpoint dei partecipanti. Monitoring Server fornisce statistiche sull'utilizzo, tendenze e statistiche sulla qualità multimediale.
    
- **Archiviazione**
    
    Archiviazione archivia conversazioni e conferenze di messaggistica istantanea.
    
- **Integrazione dell'archiviazione di Exchange**
    
    Se si dispone di utenti ospitati in Exchange 2013 e le relative cassette postali sono state inserite In-Place blocco, è possibile selezionare l'opzione per l'integrazione dell'archiviazione di Skype for Business Server 2015 con lo spazio di archiviazione di Exchange.
    
- **IPv4**
    
    Gli indirizzi IPv4 sono indirizzi a 32 bit che consentono a un computer di comunicare tramite Internet. A causa del numero crescente di dispositivi in tutto il mondo, gli indirizzi IPv4 disponibili sono esauriti. Per questo motivo, molti nuovi dispositivi si stanno spostando nell'utilizzo degli indirizzi IPv6.
    
- **IPv6**
    
    Gli indirizzi IPv6 eseguono la stessa funzione degli indirizzi IPv4 (con alcune funzionalità aggiuntive), ma invece di utilizzare solo 32 bit, gli indirizzi IPv6 utilizzano 128 bit. Questo fornisce non solo un nuovo set di indirizzi, ma anche un numero molto più grande.
    
- **Servizio Web di aggiornamento del dispositivo**
    
    Il servizio Web aggiornamento dispositivi consente di aggiornare tutti i dispositivi, ad esempio Skype for business per Windows Phone, distribuiti all'esterno dell'organizzazione.
    
### <a name="server-applications"></a>Applicazioni server

 Le **applicazioni server** contengono le opzioni seguenti:
  
- **Response Group**
    
    L'applicazione Response Group risponde e distribuisce automaticamente le chiamate a un agente helpdesk disponibile.
    
- **Annuncio**
    
    Se si prevede di distribuire VoIP aziendale, è consigliabile essere in grado di configurare la modalità di gestione delle chiamate telefoniche se il numero composto è valido ma non assegnato a un'area comune dell'utente. Gli amministratori possono configurare il servizio di annuncio in modo che le chiamate vengano trasferite a una destinazione predeterminata (numero di telefono o URI SIP) oppure riprodurre un annuncio audio o entrambi. L'utilizzo del servizio annuncio consente di evitare la situazione in cui un chiamante effettua una composizione errata e sente un segnale di occupato o il client SIP riceve un messaggio di errore. La funzionalità del servizio annunci è una caratteristica tipica del PBX. 
    
- **Parcheggio di chiamata**
    
    L'applicazione Parcheggio di chiamata consente a un utente di VoIP aziendale di mettere in attesa una chiamata da un telefono e quindi di ricevere la chiamata da un altro telefono senza legare le risorse sul telefono che ha ricevuto la chiamata. L'applicazione Parcheggio di chiamata è utile quando un utente deve trasferire una chiamata, ma il destinatario specifico è sconosciuto. 
    
- **Operatore Conferenza**
    
    L'applicazione Operatore Conferenza fornisce funzionalità di audioconferenza agli utenti di telefonia senza il servizio di un provider di servizi di audioconferenza di terze parti.
    
- **Annuncio per conferenze**
    
    L'applicazione annuncio per conferenze produce toni che segnalano quando gli utenti immettono o lasciano una conferenza, nonché le notifiche agli utenti di telefonia quando vengono disattivate o riattivate.
    
- **Servizio Controllo di ammissione di chiamata**
    
    Il controllo di ammissione di chiamata (CAC), noto anche come gestione della larghezza di banda WAN, consente di evitare la qualità di esperienza scadente per gli utenti nelle reti congestionate determinando, in base alla larghezza di banda disponibile, se consentire e nuove sessioni di comunicazione in tempo reale da stabilire. 
    
    > [!NOTE]
    > CAC controlla solo il traffico in tempo reale e non influisce sul traffico dei dati. 
  
    Se una nuova sessione vocale o video supera i limiti di larghezza di banda allocati in una rete WAN, la sessione viene bloccata oppure (solo per le chiamate telefoniche) reinstradata alla rete PSTN.
    

