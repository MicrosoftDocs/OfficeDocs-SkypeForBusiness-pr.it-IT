---
title: Confronto delle funzionalità dei client desktop per Skype for Business Server 2019
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
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
description: 'Riepilogo: gli amministratori di Skype for Business Server 2019 o Skype for business online possono utilizzare queste tabelle per comprendere quali funzionalità sono supportate nei client.'
ms.openlocfilehash: 9fcc86f59943ef770947b8311952b03f213d268b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808716"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2019"></a>Confronto delle funzionalità dei client desktop per Skype for Business Server 2019

**Riepilogo:** Gli amministratori di Skype for Business Server 2019 o Skype for business online possono utilizzare queste tabelle per comprendere quali funzionalità sono supportate nei client.

 Prima di eseguire la distribuzione o l'aggiornamento a Skype for Business Server, controllare quali client sono già in uso nell'organizzazione. Utilizzare le tabelle riportate di seguito per comprendere l'impatto del supporto delle caratteristiche su tali client. In questo modo è possibile comunicare le modifiche apportate agli utenti, passare al processo di implementazione e comprendere appieno i vantaggi dell'aggiornamento al client più recente.

Alcune funzionalità disponibili con Skype for Business Server 2019 non sono disponibili in Skype for business online; per informazioni specifiche, vedere [online o le limitazioni dell'account utente ibrido](feature-comparison.md#Online-Hybrid) . Gli amministratori di Skype for business online possono fare riferimento alla [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) per informazioni sui diversi piani disponibili.

Nelle tabelle seguenti sono riportate le funzionalità disponibili con ogni client compatibile con Skype for Business Server 2019 o Skype for business online. È inoltre possibile fare riferimento al [confronto delle funzionalità dei client per dispositivi mobili per](../../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) i confronti delle funzionalità di Skype for business per Smart Phone e Tablet client. La licenza di accesso client o la patente di sottoscrizione dell'utente che l'organizzazione acquista avrà un impatto anche sulle caratteristiche disponibili per gli utenti. Se si distribuisce il client completo o di base per gli utenti dipende dalla licenza o dal piano che l'organizzazione sceglie di acquistare. Per ulteriori informazioni, vedere la [Guida alla gestione delle licenze](https://products.office.com/skype-for-business/it-pros) .

> [!IMPORTANT]
> Skype for Business Server 2019 e Skype for business online supportano i seguenti client rilasciati in precedenza: Lync 2013, Skype for business 2015 e Skype for business 2016, nonché il client Skype for business 2019. Per informazioni su questi client se utilizzati con altri server, vedere le [tabelle di confronto dei client per Lync Server 2013](https://technet.microsoft.com/library/gg425836%28v=ocs.15%29.aspx) e [confronto delle funzionalità client desktop per Skype for business 2015](../../SfbServer/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md). 


> [!NOTE]
> Le app di Skype for Business Web App browser client e Skype Meetings app Windows 10 offrono solo supporto per le [riunioni](feature-comparison.md#BKMK_Conferencing). Fare riferimento a [pianificare i client di riunioni (app Web App e riunioni)](../../SfbServer/plan-your-deployment/clients-and-devices/meetings-clients.md) per ulteriori informazioni su questi client.

## <a name="enhanced-presence-support"></a>Supporto per la presenza avanzata
<a name="BKMK_EnhancedPresence"> </a>

In questa tabella sono riportate le funzionalità di presenza avanzata che si estendono oltre una semplice indicazione del fatto che un utente sia online, offline, occupato e così via. 


| Caratteristica/funzionalità                                                                                  | Client Skype for business 2015, 2016 o 2019 | Skype for Business nel Mac | Client Lync 2013 |
|:----------------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Stato pubblicazione                                                                                      | &#x2714;                                      | &#x2714; &#x2776;         | &#x2714;         |
| Visualizzare lo stato                                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Visualizzare note sullo stato e messaggi Fuori sede                                                        | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Aggiungere una posizione personalizzata                                                                               | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Aggiungere una nota personalizzata                                                                                   | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Utilizzo di una foto da qualsiasi sito pubblico per la foto  <br/> (non disponibile in Skype for business online) | &#x2714;                                      |                           | &#x2714;         |

 &#x2776; non supporta lo stato di pubblicazione in base alle informazioni sulla disponibilità del calendario.

## <a name="contacts-and-contact-groups-support"></a>Supporto per contatti e gruppi di contatti
<a name="BKMK_Contacts"> </a>

In questa tabella vengono illustrate le funzionalità relative alla gestione dei contatti di messaggistica istantanea e presenza. 


| Caratteristica/funzionalità                                                                            | Client Skype for business 2015, 2016 o 2019 | Skype for Business nel Mac | Client Lync 2013 |
|:----------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Elenco contatti precompilati                                                                   | &#x2714;                                      |                           |                  |
| Visualizzare e modificare l'elenco dei contatti                                                                 | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Contrassegnare i contatti per avvisi di modifica dello stato                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Controllare le relazioni di privacy                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Eseguire ricerche nella rubrica della società                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Eseguire ricerche nei contatti di Microsoft Outlook                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Gestire gruppi di contatti                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Espandere i gruppi di distribuzione e i gruppi di Microsoft 365                                              | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Cercare Response Group  <br/> (non disponibile in Skype for business online)                | &#x2714;                                      |                           | &#x2714;         |
| Visualizzare gruppi di contatti recenti                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Visualizzare il gruppo Conversazioni correnti                                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Visualizzare viste contatti alternative (ad esempio affiancate)                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Ordinare i contatti per gruppo, relazione o nuovo (persone che hanno aggiunto l'elenco dei contatti) | &#x2714;                                      |                           | &#x2714;         |
| Ordinare i contatti in base allo stato (disponibilità)                                                        | &#x2714;                                      |                           | &#x2714;         |
| Ricercare e aggiungere contatti di Exchange                                                              | &#x2714;                                      |                           | &#x2714;         |

## <a name="im-support"></a>Supporto per la messaggistica istantanea
<a name="BKMK_IMSupport"> </a>

In questa tabella vengono illustrate le caratteristiche relative al supporto di messaggistica istantanea.

|Caratteristica/funzionalità | Client Skype for business 2015, 2016 o 2019 | Skype for Business nel Mac | Client Lync 2013 | 
|:-----|:-----|:-----|:-----|  
|Avviare la messaggistica istantanea con o la posta elettronica a un contatto  |&#x2714;|&#x2714;|&#x2714;|  
|Spostarsi tra più conversazioni di messaggistica istantanea/registrare più conversazioni in una singola finestra a schede   |&#x2714;|&#x2714;|&#x2714;| 
|Registrare conversazioni istantanee in Outlook  |&#x2714;|&#x2714; se la cronologia delle conversazioni sul fianco del server è attivata   |&#x2714;|   
|Controllo ortografico |&#x2714;|&#x2714;||   
|Ricerca di competenze (con integrazione di SharePoint Server)  <br/> (In locale Skype for Business Server e SharePoint locale 2013 sono necessari per la ricerca di competenze.)  |&#x2714;||&#x2714;|
|Integrazione di chat persistente (Group Chat)  <br/> (non disponibile per Skype for business online)|&#x2714;||&#x2714;|  
|Inoltrare una chat room persistente a una riunione Skype for business con un solo clic  <br/> (non disponibile per Skype for business online) |&#x2714;||&#x2714;| 
|Immagini in linea del mittente e del destinatario nella finestra di messaggistica istantanea |&#x2714;||&#x2714;| 
|Ricezione di messaggi di input penna |&#x2714;||&#x2714;| 
|Impostare i messaggi di messaggistica istantanea come priorità alta |&#x2714;||&#x2714;|

## <a name="meetings-support"></a>Supporto per le riunioni
<a name="BKMK_Conferencing"> </a>

In questa tabella sono riportate le funzionalità correlate al supporto delle riunioni.

> [!NOTE]
>  Le funzionalità di riunioni di Skype for business non sono disponibili in Skype for business online piano autonomo 1.  Il piano 1 è in fase di [ritirata](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement
).

Nelle sessioni Skype to Skype, un utente di Skype for business online piano 1 può partecipare alla condivisione di desktop e alla condivisione di applicazioni se sono invitati da un utente che ha accesso alle funzionalità di condivisione.
Per informazioni dettagliate, vedere la [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/jj822172.aspx). 

|Caratteristica/funzionalità | Client Skype for business 2016 | Skype for Business nel Mac | Skype for Business Web App | Client Skype for business 2015 | Client Lync 2013 | 
|:-----|:-----|:-----|:-----|:-----|:-----|  
|Aggiungere la funzionalità audio al computer  |&#x2714;|&#x2714;|&#x2714; (richiede plug-in)  |&#x2714;|&#x2714;| 
|Aggiungere la funzionalità video |&#x2714;|&#x2714;|&#x2714; (richiede plug-in) |&#x2714;|&#x2714;| 
|Visualizzazione del video in più parti (visualizzazione raccolta)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condivisione dello schermo basato su video    |&#x2714;|&#x2714;|&#x2714; di sola visualizzazione   ||| 
|Utilizzare controlli di relatore nell'ambito delle riunioni |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Accedere all'elenco dettagliato delle riunioni |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Partecipare a conversazioni istantanee tra più utenti |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Condividere il desktop (se consentito)  |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776;  (richiede plug-in) |&#x2714;| &#x2714;|
|Condividere un programma (se consentito) |&#x2714;|Sola visualizzazione   |&#x2714; (richiede plug-in)  |&#x2714;|&#x2714;|   
|Aggiungere partecipanti anonimi (se consentito) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utilizzo di riunioni audio con accesso esterno &#x2777;|&#x2714; |&#x2714;|&#x2714;  |&#x2714;|&#x2714;  |
|Avviare una riunione adesso|&#x2714;|&#x2714;||&#x2714;|&#x2714;|  
|Aggiungere e presentare file di Microsoft PowerPoint |&#x2714;| Annotazioni di &#x2778; non disponibili   |&#x2714;|&#x2714;|&#x2714;| 
|Passare ai file di Microsoft PowerPoint |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Aggiungere e modificare le note della riunione di OneNote  |&#x2714;||Modifica solo (non aggiungere)  |&#x2714;|&#x2714;|
|Utilizzare una lavagna |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Effettuare sondaggi |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Caricare file da condividere con altri utenti |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Pianificare una riunione o una conferenza |Outlook o Skype for Business Web Scheduler  |Outlook o Skype for Business Web Scheduler |Utilità di pianificazione Web di Skype for business |Outlook o Skype for Business Web Scheduler   |Outlook o utilità di pianificazione Web di Lync |  
|Q &amp; un Manager |&#x2714;|||||
|Disattiva video partecipante |&#x2714;||&#x2714;|||
|Disattiva messaggistica istantanea riunione |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Disattiva gruppo di destinatari |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Rendere tutti un partecipante |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Produrre Skype meeting broadcast |&#x2714;|||||
|Il delegato può pianificare una riunione per conto del delegante |&#x2714;|&#x2714;|&#x2714;|||
|Sincronizzare i delegati tra Skype for business e Outlook |&#x2714;||&#x2714;|&#x2714;|| 
|Impostare Spotlight video (Lock video) |&#x2714;||&#x2714;|&#x2714;|&#x2714;| 
|Fornire/assumere il controllo della condivisione dello schermo  |&#x2714;||&#x2714;|||

 &#x2776; i partecipanti non possono controllare i desktop condivisi da Skype for business su Mac, Lync per Mac 2011 o Communicator per Mac 2011. Skype for business su Mac, Lync per Mac 2011 e Communicator per Mac 2011 gli utenti non possono controllare i desktop condivisi dagli utenti di Windows. Questo non funzionerà anche per Skype for Business Web App su Max OSX.

 &#x2777; per Skype for business online, questa funzionalità richiede servizi di conferenza PSTN Microsoft, messaggistica unificata di Exchange o un provider di audioconferenza di terze parti.

 &#x2778; il client Lync per Mac 2011 non è in grado di visualizzare le presentazioni di Microsoft Office 2013 PowerPoint quando sono state condivise in una conferenza da Skype for Business Web App.

&#x2779; per le app di Skype for business 2016, è necessario utilizzare la funzione a portata di clic, creare 16.0.4227 o versione successiva.

&#x2780; per le app di Skype for business 2015, è necessario disporre dell'aggiornamento di settembre, Build 15.0.4747 o versione successiva.

## <a name="voice-telephony-support"></a>Supporto vocale (telefonia)
<a name="BKMK_Telephony"> </a>

In questa tabella vengono illustrate le funzionalità relative al supporto dei servizi vocali.

> [!NOTE]
> Le funzionalità di Skype for Business Voice (telefonia) sono limitate a determinati piani di sottoscrizione di Skype for business online. Per informazioni dettagliate, vedere la [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/jj822172.aspx). 

 | Caratteristica/funzionalità | Client Skype for business 2015, 2016 o 2019 | Skype for Business nel Mac | Client Lync 2013 |  
|:-----|:-----|:-----|:-----| 
|Avviare una chiamata |&#x2714;|&#x2714;|&#x2714;|
|Fare clic per chiamare un contatto |&#x2714;|&#x2714;|&#x2714;|
|Trasferire una chiamata |&#x2714;|&#x2714;|&#x2714;|  
|Gestire l'inoltro di chiamata |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Gestire le impostazioni di intercettazione team |&#x2714;||&#x2714; &#x2776; |
|Gestire i delegati |&#x2714;|&#x2714;   |&#x2714; &#x2776; |
|Avviare una chiamata a un Response Group|&#x2714;||&#x2714; &#x2776; |
|Supporto per i servizi di emergenza (E-911) |&#x2714;|&#x2714; |&#x2714; &#x2776; |
|Notifiche di messaggistica istantanea agli URI SIP per la chiamata E-911 |&#x2714;|&#x2714;|&#x2714;|
|Notifica di messaggistica istantanea alla lista di distribuzione per la chiamata E-911|&#x2714;|&#x2714;|&#x2714;|
|Connettersi alla segreteria telefonica, configurare o modificare il messaggio di saluto |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Notifica di chiamata senza risposta |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Eseguire chiamate per conto di un altro contatto (scenario manager/delegato) |&#x2714;|&#x2714;|&#x2714; &#x2776; |
|Gestire le chiamate di un altro contatto se configurato come delegato |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Parcheggio di chiamata |&#x2714;||&#x2714; &#x2776; |
|Prelievo chiamata di gruppo |&#x2714;||&#x2714; &#x2776; |
|Routing basato su posizione |&#x2714;|&#x2714;|&#x2714;| 
|Gestisci Response Group/gruppo di chiamate del team |&#x2714;||&#x2714;|

 &#x2776; questa funzionalità non è disponibile in Skype for business online.

## <a name="external-users-support"></a>Supporto per gli utenti esterni
<a name="BKMK_ExternalUsers"> </a>

In questa tabella sono riportate le funzionalità relative al supporto per gli utenti esterni ospitati nella rete PSTN.


|Caratteristica/funzionalità | Client Skype for business 2015, 2016 o 2019 | Skype for Business nel Mac | Client Lync 2013 |  
|:-----|:-----|:-----|:-----|  
|Avviare conversazioni istantanee con un contatto pubblico |&#x2714;|&#x2714;|&#x2714;| 
|Avviare conversazioni istantanee con un contatto federato |&#x2714;|&#x2714;|&#x2714;| 
|Effettuare chiamate con due o più utenti esterni  <br/> (non disponibile in Skype for business online)  |&#x2714;|&#x2714;|&#x2714;| 

## <a name="recording-support"></a>Supporto per la registrazione
<a name="BKMK_Recording"> </a>

In questa tabella vengono illustrate le funzionalità relative al supporto per le riunioni di registrazione.

| Caratteristica/funzionalità | Client Skype for business 2015, 2016 o 2019 | Skype for Business nel Mac | Client Lync 2013 |   
|:-----|:-----|:-----|:-----|  
|Registrazione sul fronte client di audio, video, condivisione applicazioni, condivisione del desktop e contenuto caricato |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Registrazione sul retro dei file, pagine di OneNote condivise e annotazioni di PowerPoint| &#x2714; &#x2777; ||&#x2714; &#x2777; |
|Selezionare la risoluzione di registrazione preferita  |&#x2714;||&#x2714;|

 &#x2776; la registrazione non è disponibile in alcuni piani autonomi di Skype for business online. La registrazione richiede i diritti client Skype for business completi.

 &#x2777; la registrazione dei trasferimenti di file, le pagine di OneNote condivise e le annotazioni di PowerPoint non sono disponibili in Skype for business online.

## <a name="modern-authentication"></a>Autenticazione moderna
<a name="BKMK_Recording"> </a>

In questa tabella vengono illustrate le funzionalità che richiedono il supporto per l'autenticazione moderna. 

L'autenticazione moderna richiede anche una topologia descritta nelle [topologie Skype for business supportate con l'autenticazione moderna](../../SfbServer/plan-your-deployment/modern-authentication/topologies-supported.md).


 | Caratteristica/funzionalità | Client Skype for business 2015, 2016 o 2019 | Skype for Business nel Mac | Client Lync 2013 | 
|:-----|:-----|:-----|:-----|  
|Autenticazione moderna |&#x2714;|&#x2714;|&#x2714;|
|Autenticazione a più fattori|&#x2714;|&#x2714;|&#x2714;|
|Autenticazione basata su cert |&#x2714; (solo dispositivo collegato al dominio) |&#x2714;|&#x2714; (solo dispositivo collegato al dominio)  |
|Autenticazione Kerberos |&#x2714;||&#x2714;|

## <a name="archiving-compliance-and-logging-support"></a>Supporto per l'archiviazione, la conformità e la registrazione
<a name="BKMK_Archiving"> </a>

In questa tabella sono riportate le funzionalità relative al supporto per le funzioni di archiviazione e registrazione.


 | Caratteristica/funzionalità | Client Skype for business 2015, 2016 o 2019 | Skype for Business nel Mac | Client Lync 2013 |  
|:-----|:-----|:-----|:-----|  
|Archiviazione delle conversazioni ISTANTANEe nella cronologia delle conversazioni di Outlook|&#x2714; &#x2776; |&#x2714; se la cronologia delle conversazioni sul fianco del server è attivata  |&#x2714; &#x2776; | 
|Archiviazione sul retro del client di audio, video, condivisione applicazioni, condivisione del desktop e contenuto caricato  |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Archiviazione sul fronte client di trasferimenti di file, pagine di OneNote condivise e annotazioni di PowerPoint (non disponibile in Skype for business online)  |&#x2714;||&#x2714;|
|Accedere ai log di accesso dall'icona di Skype for business nella barra delle applicazioni |&#x2714;||&#x2714;|

 &#x2776; per gli utenti di Skype for business online, questa funzionalità richiede Exchange Online ed è controllata dall'attributo cassetta postale di Exchange dell'utente In-Place blocco.

## <a name="client-limitations"></a>Limitazioni client
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitazioni client di base
<a name="Full-Basic"> </a>

Le funzionalità riportate di seguito sono disponibili utilizzando il client completo e non sono disponibili con il client di base: 

- Gestire le impostazioni di intercettazione team

- Gestire i delegati

- Eseguire chiamate per conto di un altro contatto (scenario manager/delegato)

- Gestire le chiamate di un altro contatto se configurato come delegato

- Gestire un elevato volume di chiamate

- Avviare una chiamata a un Response Group

- Parcheggio di chiamata

- Cambia messaggio di saluto

- Prelievo chiamata di gruppo

### <a name="online-or-hybrid-user-account-limitations"></a>Limitazioni dell'account utente online o ibrido
<a name="Online-Hybrid"> </a>

Gli account utente possono esistere online o in locale e che influiscono sulle caratteristiche disponibili per l'utente. Gli utenti con account su Skype for business online non avranno accesso alle funzionalità seguenti, anche con il client completo: 

- Presenza avanzata: utilizzare una foto da qualsiasi sito pubblico per l'immagine personale

- Contatti: ricerca di Response Group

- Supporto per la messaggistica istantanea: integrazione di chat persistente (Group Chat)

- Supporto per la messaggistica istantanea: inoltrare una chat room persistente a una riunione di Skype for business con un solo clic

- Utenti esterni: eseguire chiamate a due o più parti con utenti esterni

## <a name="see-also"></a>Vedere anche
<a name="Types"> </a>

[Pianificare i client e i dispositivi](../../SfbServer/plan-your-deployment/clients-and-devices/clients-and-devices.md)

[Aggiornamenti più recenti per le versioni di Skype for business che utilizzano Windows Installer (MSI)](../../SfbServer/sfb-client-updates.md)
