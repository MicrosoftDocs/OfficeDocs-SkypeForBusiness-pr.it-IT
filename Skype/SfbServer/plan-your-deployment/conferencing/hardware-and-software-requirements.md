---
title: Requisiti hardware e software per le conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Riepilogo: leggere questo argomento per informazioni sui requisiti hardware e software per le conferenze in Skype for Business Server.'
ms.openlocfilehash: 59ad84cd0f4445709b236baecafeeab240e6ea65
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814016"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Requisiti hardware e software per le conferenze in Skype for Business Server

**Riepilogo:** Leggere questo argomento per informazioni sui requisiti hardware e software per le conferenze in Skype for Business Server.

In questa sezione vengono descritti i requisiti hardware e software per le conferenze telefoniche, audio e video (A/V), le conferenze telefoniche con accesso esterno e le conferenze di messaggistica istantanea. Tutte le funzionalità di conferenza vengono eseguite nei Front End Server; sono previsti ulteriori requisiti per i diversi tipi di conferenza, come illustrato nel diagramma seguente.

Ad esempio, se si desidera consentire le conferenze telefoniche con accesso esterno, è necessario distribuire un Mediation Server e un gateway per la connessione alla rete PSTN (Public Switched Telephone Network). Se si desidera consentire la Web Conferencing, è necessario assicurarsi che Skype for Business Server sia in grado di connettersi a un server Office Web Apps. Se si desidera consentire agli utenti esterni di partecipare alle conferenze, è necessario distribuire un server perimetrale.

**Funzionalità e requisiti per i servizi di conferenza**

![Componenti per conferenze](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Per ulteriori informazioni sulle considerazioni relative alla topologia, vedere [plan your Conferencing topologie for Skype for Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Requisiti hardware e software per Front End Server

Poiché le conferenze Web, A/V Conferencing, le conferenze telefoniche con accesso esterno e le conferenze di messaggistica istantanea sono tutte collocate con il front end server, i requisiti hardware e software del server sono gli stessi dei Front End Server. Per informazioni dettagliate su questi requisiti, vedere requisiti del [Server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e requisiti [ambientali per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisiti del server per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Requisiti per le conferenze Web

Se si decide di abilitare le conferenze Web, è necessario pianificare quanto segue:

- Accesso all'archivio file utilizzato per l'archiviazione del contenuto delle conferenze Web.

- Integrazione con il server Office Web Apps, che è necessario per condividere i file di PowerPoint durante una conferenza.

### <a name="file-store"></a>Archivio file

Il servizio Web Conferencing di Skype for Business Server archivia il contenuto condiviso durante le riunioni nell'archivio file. Nell'ambito della distribuzione, è necessario specificare una condivisione file da utilizzare come archivio file per il server Standard Edition o per il pool Enterprise Edition front end. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisione file. Per ulteriori informazioni, vedere [creare una condivisione file in Skype for Business Server](../../deploy/install/create-a-file-share.md). Il servizio per conferenze Web crittografa il contenuto prima di archiviarlo nell'archivio file.

Skype for Business Server supporta l'utilizzo di condivisioni file su una rete di archiviazione diretta (DAS, Direct Attached Storage) o su un sistema di archiviazione (SAN), incluso il file System distribuito (DFS), e su una matrice ridondante di dischi indipendenti (RAID) per gli archivi di file. Dopo che la distribuzione guidata di Skype for Business Server ha definito il percorso della condivisione file, Skype for Business Server crea una struttura di cartelle all'interno della condivisione file simile alla seguente:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - Dataconf

Il servizio di conferenza Web archivia quindi il contenuto, ad esempio diapositive di PowerPoint, lavagne, sondaggi e allegati, nelle cartelle CollabContent e CollabMetadata che si trovano nella cartella WebServices.

### <a name="office-web-apps-server"></a>server Office Web Apps

Per poter utilizzare le funzionalità di Web Conferencing, è necessario installare il server Office Web Apps e configurare Skype for Business Server per comunicare con il server Office Web Apps.

Il server Office Web Apps deve essere installato in un computer autonomo che non esegue Skype for Business Server, SQL Server o qualsiasi altra applicazione server. Non è necessario disporre di una versione di Office installata nel computer in questione. Qualsiasi computer utilizzato per eseguire il server Office Web Apps deve disporre anche di un insieme specifico di software installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0). Tali requisiti, oltre alle informazioni sulla configurazione dei certificati e di Internet Information Services (IIS), vengono illustrati in dettaglio nel [sito Web di distribuzione di Microsoft Office Web Apps](https://go.microsoft.com/fwlink/p/?linkid=257525).

Per informazioni su come configurare Skype for Business Server per l'utilizzo con il server Office Web Apps, vedere [configurare l'integrazione con il server Office Web Apps in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Requisiti per le conferenze audio e video

Per la pianificazione delle conferenze audio/video è necessario conoscere i requisiti di larghezza di banda di rete dei vari tipi di supporti per le conferenze richiesti dall'organizzazione. Questo potrebbe includere audio, video e video panoramici. Senza larghezza di banda di rete sufficiente, l'esperienza utente può essere gravemente degradata.

Per informazioni sulla pianificazione della capacità audio e video per le conferenze, vedere [pianificare i requisiti di rete per Skype for business](../../plan-your-deployment/network-requirements/network-requirements.md).

È possibile utilizzare il controllo di ammissione di chiamata per gestire la larghezza di banda di rete utilizzata da A/V Conferencing. Questo è importante per le reti limitate, ad esempio collegamenti a larghezza di banda limitate tra i siti centrali e di succursale. Per ulteriori informazioni, vedere [Plan for Call Admission Control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Se si distribuiscono audioconferenza in rete, gli utenti avranno bisogno di dispositivi audio come gli auricolari per partecipare a una conferenza audio. Se si distribuiscono video Conferencing, è necessario distribuire dispositivi video, ad esempio webcams per gli utenti. Per i dispositivi audio e video, la distribuzione dei dispositivi e la formazione degli utenti sono passaggi importanti da prendere in considerazione. Per ulteriori informazioni, vedere [Plan for clients and Devices](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft consiglia di utilizzare i dispositivi Unified Communications (UC) certificati da Microsoft per tutti i tipi di dispositivi, per garantire un'esperienza utente ottimale. Per informazioni dettagliate sui dispositivi certificati per le comunicazioni unificate, vedere [telefoni e dispositivi per Skype for business](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Requisiti per le conferenze telefoniche con accesso esterno

Le conferenze telefoniche con accesso esterno sono una funzionalità facoltativa del carico di lavoro per le conferenze di Skype for Business Server che include una vasta gamma di componenti. Alcuni dei componenti sono specifici delle conferenze telefoniche con accesso esterno, mentre altri sono componenti di VoIP aziendale. In questa sezione vengono descritti i requisiti per i componenti necessari per le conferenze telefoniche con accesso esterno. Per informazioni dettagliate su Mediation Server e sui requisiti del gateway PSTN (Public Switched Telephone Network), vedere [Mediation Server Component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) e [distribuire un Mediation Server in Generatore di topologie in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Componenti necessari

Prima di poter configurare le conferenze telefoniche con accesso esterno, è necessario installare i componenti di Skype for Business Server seguenti:

- Unified Communications Application Service (unificate) (denominato servizio applicazione)

- Applicazione Operatore Conferenza

- Applicazione Annuncio conferenza

- Pagina Web delle impostazioni per le conferenze telefoniche con accesso esterno

- Almeno un Mediation Server e almeno un gateway PSTN

Per le conferenze telefoniche con accesso esterno, il servizio applicazione, l'applicazione Operatore Conferenza e l'applicazione Annuncio conferenza dispongono degli stessi requisiti del sistema operativo dei Front End Server. Per ulteriori informazioni, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

Applicazione Operatore Conferenza e l'applicazione Annuncio conferenza richiedono l'installazione di Windows Media Format Runtime nei Front End Server. Windows Media Format Runtime è necessario per riprodurre file di Windows Media Audio (WMA) che vengono utilizzati per la musica di attesa, per i nomi registrati e per le istruzioni vocali. Se si esegue l'installazione in Windows Server 2012 o Windows Server 2012 R2 (consigliato), è necessario installare Microsoft Media Foundation per ottenere il runtime del formato Windows Media. Se si esegue l'installazione in qualsiasi versione di Windows Server precedente a Windows 2012, è necessario verificare che l'esperienza desktop di Windows sia installata per ottenere il runtime del formato Windows Media.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisiti dei file audio per le conferenze telefoniche con accesso esterno

Skype for Business Server non supporta la personalizzazione di istruzioni vocali e musica per le conferenze telefoniche con accesso esterno. Tuttavia, se si dispone di un'esigenza aziendale complessa che richiede la modifica dei file audio predefiniti, vedere l'articolo 961177 della Microsoft Knowledge base, [come personalizzare i messaggi vocali o i file musicali per le conferenze telefoniche con accesso esterno](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177).

È inoltre possibile utilizzare [Microsoft Lync Server Conferencing Attendant Custom voice prompts](https://go.microsoft.com/fwlink/p/?LinkId=396880) Management Utility, che consente agli amministratori di sostituire le istruzioni vocali predefinite utilizzate quando un chiamante del telefono si unisce a una riunione di Skype for business con prompt personalizzati per fornire un'esperienza di partecipazione alle riunioni diversa. Le istruzioni vocali personalizzate possono essere installate su un server Enterprise o Standard Edition.

Applicazione per i servizi di conferenza e applicazione di annuncio di conferenza sono necessari i seguenti requisiti per la musica di attesa, il nome registrato e i file delle istruzioni audio:

- Formato file WMA (Windows Media Audio)

- Mono a 16 bit

- CBR (Constant Bit Rate) a due passaggi 48 kbps

- Livello parlato a -24 DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Requisiti degli utenti per le conferenze telefoniche con accesso esterno

Gli utenti delle conferenze telefoniche con accesso esterno devono avere un numero di telefono univoco o un interno assegnato al loro account. Questo requisito supporta l'autenticazione durante l'accesso esterno. Gli utenti aziendali (ovvero gli utenti che dispongono di credenziali di servizi di dominio Active Directory e gli account di Skype for Business Server all'interno dell'organizzazione) immettere il proprio numero di telefono (o estensione) e un PIN per accedere alle conferenze come utente autenticato.

## <a name="port-requirements-for-conferencing"></a>Requisiti delle porte per le conferenze

Per poter utilizzare le funzionalità di conferenza, Skype for Business Server richiede che alcune porte siano aperte. Nella tabella seguente sono elencati i requisiti di porta per le conferenze. Per informazioni dettagliate su tutti i requisiti di porta, vedere [porte e protocolli per i server](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Porte server obbligatorie**


|**Ruolo del server**|**Nome del servizio**|**Porta**|**Protocollo**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|Front End Server  <br/> |Servizio di messaggistica istantanea di Skype for Business Server  <br/> |5062  <br/> |TCP  <br/> |Utilizzata per le richieste SIP in arrivo per le conferenze di messaggistica istantanea (IM).  <br/> |
|Front End Server  <br/> |Servizio Web Conferencing di Skype for Business Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Utilizzata per attendere le connessioni PSOM (Persistent Shared Object Model) dal client.  <br/> |
|Front End Server  <br/> |Servizio compatibilità Web Conferencing di Skype for Business Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Utilizzato per l'attesa per le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e le versioni precedenti di Skype for Business Server.  <br/> |
|Front End Server  <br/> |Servizio audio/video Conferencing di Skype for Business Server  <br/> |5063  <br/> |TCP  <br/> |Utilizzata per le richieste SIP in arrivo per Audio/Video (A/V) Conferencing.  <br/> |
|Front End Server  <br/> |Servizio audio/video Conferencing di Skype for Business Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervallo di porte di attesa multimediali utilizzato per le conferenze video.  <br/> |
|Front End Server  <br/> |Skype for Business Server Conferencing Attendant (servizi di conferenza telefonica con accesso esterno)  <br/> |5064  <br/> |TCP  <br/> |Utilizzata per le richieste SIP in arrivo per le conferenze telefoniche con accesso esterno.  <br/> |
|Front End Server  <br/> |Skype for Business Server Conferencing Attendant (servizi di conferenza telefonica con accesso esterno)  <br/> |5072  <br/> |TCP  <br/> |Utilizzato per le richieste SIP in arrivo per Attendant (servizi di conferenza telefonica con accesso esterno).  <br/> |
|Front End Server  <br/> |Servizio di condivisione applicazioni di Skype for Business Server  <br/> |5065  <br/> |TCP  <br/> |Utilizzata per le richieste di attesa SIP in arrivo per la condivisione delle applicazioni.  <br/> |
|Front End Server  <br/> |Servizio di condivisione applicazioni di Skype for Business Server  <br/> |49152-65535  <br/> |TCP  <br/> |Intervallo di porte di attesa multimediali per la condivisione delle applicazioni.  <br/> |
|Front End Server  <br/> |Servizio annuncio di Skype for Business Server  <br/> |5073  <br/> |TCP  <br/> |Utilizzato per le richieste SIP in arrivo per il servizio Annuncio conferenza di Skype for Business Server (ovvero per le conferenze telefoniche con accesso esterno).  <br/> |
|Tutti i server interni  <br/> |Vari  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Intervallo di porte multimediali utilizzato per le conferenze audio su tutti i server interni. Utilizzato da tutti i server che terminano audio: Front End Server (per il servizio Operatore Conferenza di Skype for Business Server, servizio annuncio per conferenze di Skype for Business Server e servizio di conferenza audio/video per Skype for Business Server) e Mediation Server.  <br/> |
|Server Office Web Apps  <br/> ||443  <br/> ||Utilizzato da Skype for Business Server per la connessione al server Office Web Apps.  <br/> |

**Porte client richieste**


|**Porta**|**Protocollo**|**Note**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Utilizzata per l'accesso utente esterno alle sessioni di Web Conferencing.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Utilizzata per l'accesso utente esterno alle sessioni A/V e ai supporti multimediali (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Utilizzato per l'accesso degli utenti esterni alle sessioni A/V e ai supporti (UDP)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Intervallo di porte audio (almeno 20 porte richieste)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Intervallo di porte video (almeno 20 porte richieste).  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |Condivisione applicazioni.  <br/> |


