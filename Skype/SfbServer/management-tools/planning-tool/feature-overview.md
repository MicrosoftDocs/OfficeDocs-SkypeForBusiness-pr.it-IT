---
title: Strumento di pianificazione della panoramica delle funzionalità
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Descripbes the Skype for Business Server 2015 planning tool.
ms.openlocfilehash: 7351ef19480f4153ee98db58ab2ba70b34e3df06
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850939"
---
# <a name="feature-overview-planning-tool"></a>Strumento di pianificazione della panoramica delle funzionalità
 
Skype for Business Server 2015 Planning Tool
  
È possibile utilizzare la **pagina Siti centrali** dello Strumento di pianificazione per progettare la Skype for Business Server distribuzione. È possibile creare due distribuzioni centralizzate o distribuite. Una distribuzione centralizzata dispone di un solo sito centrale, che include tutti Skype for Business utenti dell'organizzazione. Una distribuzione distribuita include più di un sito centrale. Se si distribuiscono Skype for Business Server in più siti centrali, sarà necessario immettere il numero di utenti in ogni sito centrale nello Strumento di pianificazione.
  
Per completare la definizione del sito centrale, è innanzitutto necessario fornire le informazioni seguenti:
  
- **Nome sito** Immettere il nome del sito centrale.
    
- **Numero di utenti** Immettere il numero di utenti, inclusi gli utenti dei siti di succursale ospitati nel sito centrale.
    
- **Utenti ospitati nel cloud** Immettere il numero di utenti ospitati nel sito centrale da Skype for Business Online.
    
> [!NOTE]
> Questo strumento non verrà aggiornato per Skype for Business Server 2019.

## <a name="ui-elements"></a>Elementi dell'interfaccia utente

Gli elementi rimanenti sono stati popolati con le risposte fornite alle domande presentate nella procedura guidata **di Informazioni di base** oppure, se la procedura guidata è stata ignorata, vengono popolate automaticamente dallo strumento di pianificazione.
  
### <a name="online-collaboration"></a>Collaborazione online

 **La collaborazione** online contiene le opzioni seguenti:
  
- **Messaggistica istantanea e presenza**
    
    La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale sui propri computer utilizzando messaggi di testo. Sono supportate le sessioni di messaggistica istantanea sia tra due che tra più parti. La presenza fornisce agli utenti informazioni sullo stato di altri utenti nella rete. Lo stato di presenza di un utente fornisce informazioni per aiutare gli altri a determinare se l'utente è online e come contattare al meglio l'utente. Ad esempio, un utente che si trova in una riunione viene contattato tramite posta elettronica.
    
- **Conferenze audio e video**
    
    Le conferenze audio/video (A/V) consentono conferenze audio e video in tempo reale.
    
- **Chiamate in conferenza**
    
    Le conferenze telefoniche con accesso esterno consentono agli utenti di partecipare a un A/V da un telefono sulla rete PSTN. Per le conferenze telefoniche con accesso esterno è necessario distribuire le applicazioni Operatore conferenza e Annuncio conferenza Service.
    
- **Conferenze Web**
    
    Le conferenze Web consentono agli utenti aziendali all'interno e all'esterno del firewall di creare e partecipare a conferenze in tempo reale ospitate nei server interni.
    
- **Chat persistente**
    
    Persistent Chat consente a più utenti di partecipare a conversazioni in cui pubblicano e accedono a contenuto su argomenti specifici, tra cui testo, collegamenti e file. Nonostante gli utenti possano comunicare in tempo reale durante una sessione, il contenuto di ogni sessione può essere salvato in modo permanente e quindi restare disponibile anche al termine di una sessione.
    
### <a name="users"></a>Utenti

 **Gli** utenti contengono le opzioni seguenti:
  
- **Organizzazione interna**
    
- **Federazione con altre organizzazioni**
    
- **Federazione con versioni precedenti**
    
- **Federazione con provider di servizi di messaggistica istantanea pubblici** Consente agli utenti dell'organizzazione di stabilire comunicazioni con provider di servizi di messaggistica istantanea pubblici come MSN, Yahoo!e AOL. È necessaria una licenza separata per stabilire la federazione con reti di messaggistica istantanea pubbliche.
    
- **Federazione con provider di servizi basati su XMPP**
    
    Skype for Business Server 2015 introduce un proxy XMPP completamente integrato (distribuito nei server perimetrali) e un gateway XMPP distribuito nei Front End Server. È possibile distribuire L'aggiunta e la configurazione del proxy XMPP e del gateway XMPP consentiranno agli utenti di Skype for Business Server 2015 di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.

> [!NOTE]
> I gateway XMPP e i proxy sono disponibili Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per [ulteriori informazioni, vedere Migrating XMPP federation.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)
    
- **Mobilità**
    
    Quando distribuisci il servizio per dispositivi mobili di Skype for Business Server 2015, gli utenti possono usare i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia supportati per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.
    
- **Cassetta postale Exchange W15**
    
    Skype for Business Server 2015 consente di archiviare i messaggi della segreteria telefonica Exchange messaggistica unificata; tali messaggi della segreteria telefonica verranno quindi visualizzati come messaggi di posta elettronica nelle cartelle Posta in arrivo degli utenti.
    
### <a name="voice"></a>Voce

 **Voice** contiene le opzioni seguenti:
  
- **VoIP aziendale**
    
    Enterprise voice è la soluzione VoIP basata su software di Microsft. Enterprise vocale consente agli utenti di Skype for Business di eseguire una chiamata telefonica dal computer.
    
- **Messaggistica unificata di Exchange**
    
    Exchange La messaggistica unificata combina la posta vocale e la posta elettronica in un'unica infrastruttura di messaggistica. Skype for Business Server 2015 utilizza la Exchange per fornire servizi di risposta alle chiamate, accesso sottoscrittore, notifica delle chiamate e operatore automatico. Se si utilizzano questi servizi, sarà necessario integrare Exchange messaggistica unificata e Skype for Business Server in una topologia di Active Directory condivisa.
    
### <a name="additional-deployment-options"></a>Opzioni di distribuzione aggiuntive

 **Opzioni di distribuzione aggiuntive** contiene le opzioni seguenti:
  
- **Disponibilità elevata**
    
    La disponibilità elevata abilita i server di standby per il supporto del failover.
    
- **Ripristino d'emergenza**
    
    Le misure di ripristino di emergenza consentono di associare pool Front End situati in due datacenter.
    
- **Monitoraggio**
    
    Il monitoraggio acquisisce i record dettagli chiamata correlati alle sessioni di comunicazione. Raccoglie anche le metriche dalle sessioni audio e video agli endpoint dei partecipanti. Monitoring Server fornisce statistiche di utilizzo, tendenze e statistiche sulla qualità multimediale.
    
- **Archiviazione**
    
    L'archiviazione archivia conversazioni e conferenze di messaggistica istantanea.
    
- **Exchange Integrazione dell'archiviazione**
    
    Se si dispone di utenti ospitati in Exchange 2013 e le relative cassette postali sono state messe In-Place blocco, è possibile selezionare l'opzione per integrare l'archiviazione di Skype for Business Server 2015 con Exchange archiviazione.
    
- **IPv4**
    
    Gli indirizzi IPv4 sono indirizzi a 32 bit che consentono a un computer di comunicare tramite Internet. A causa del numero crescente di dispositivi in tutto il mondo, gli indirizzi IPv4 disponibili si sono eseguiti. Per questo, molti nuovi dispositivi stanno passando all'uso di indirizzi IPv6.
    
- **IPv6**
    
    Gli indirizzi IPv6 eseguono la stessa funzione degli indirizzi IPv4 (con alcune funzionalità aggiuntive), ma invece di utilizzare solo 32 bit, gli indirizzi IPv6 utilizzano 128 bit. In questo modo non solo viene fornito un nuovo set di indirizzi, ma anche un numero molto maggiore di indirizzi.
    
- **Servizio Web di aggiornamento del dispositivo**
    
    Il servizio Web Aggiornamento dispositivi consente di aggiornare automaticamente tutti i dispositivi, ad esempio Skype for Business per Windows Phone, distribuiti all'esterno dell'organizzazione.
    
### <a name="server-applications"></a>Applicazioni server

 **Le applicazioni server** contengono le opzioni seguenti:
  
- **Response Group**
    
    L'applicazione Response Group risponde automaticamente e distribuisce le chiamate a un agente dell'helpdesk disponibile.
    
- **Annuncio**
    
    Se si prevede di distribuire VoIP aziendale, è possibile configurare la modalità di gestione delle chiamate telefoniche se il numero composto è valido ma non assegnato a un'area comune dell'utente. Gli amministratori possono configurare il servizio annunci in modo che queste chiamate si trasferiscono a una destinazione predeterminata (numero di telefono o URI SIP) o riproducino un annuncio audio o entrambi. L'utilizzo del servizio Annuncio evita la situazione in cui un chiamante fa un'errata diagnosi e sente un segnale di occupato o il client SIP riceve un messaggio di errore. La funzionalità del servizio Annuncio è una tipica funzionalità PBX. 
    
- **Parcheggio di chiamata**
    
    L'applicazione Parcheggio di chiamata consente a un utente VoIP aziendale di mettere in attesa una chiamata da un telefono e quindi di ricevere la chiamata da un altro telefono senza creare un collegamento tra le risorse del telefono che ha ricevuto la chiamata. L'applicazione Parcheggio di chiamata è utile quando un utente deve trasferire una chiamata, ma il destinatario specifico è sconosciuto. 
    
- **Operatore conferenza**
    
    applicazione Operatore conferenza offre funzionalità di audioconferenza agli utenti di telefonia senza il servizio di un provider di servizi di audioconferenza di terze parti.
    
- **Annuncio conferenza**
    
    applicazione Annuncio conferenza produce toni che segnalano quando gli utenti entrano o abbandonano una conferenza, nonché notifiche agli utenti di telefonia quando vengono disattivati o disattivati.
    
- **Servizio Controllo di ammissione di chiamata**
    
    Il servizio Controllo di ammissione di chiamata ( CAC), noto anche come gestione della larghezza di banda WAN, consente di evitare una scarsa qualità dell'esperienza per gli utenti su reti congestionate determinando, in base alla larghezza di banda disponibile, se consentire o meno la creazione di nuove sessioni di comunicazione in tempo reale. 
    
    > [!NOTE]
    > Il controllo di ammissione di chiamata controlla solo il traffico in tempo reale e non influisce sul traffico dati. 
  
    Se una nuova sessione vocale o video supera i limiti di larghezza di banda allocati su una rete WAN, la sessione viene bloccata o (solo per le chiamate telefoniche) reindirizzata alla rete PSTN.
    

