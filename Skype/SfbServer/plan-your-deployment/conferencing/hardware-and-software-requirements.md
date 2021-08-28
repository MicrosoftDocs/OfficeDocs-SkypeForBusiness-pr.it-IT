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
ms.localizationpriority: medium
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Riepilogo: leggere questo argomento per informazioni sui requisiti hardware e software per le conferenze in Skype for Business Server.'
ms.openlocfilehash: 4f3eff319165a50aa52108903c5f091415a1018d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603855"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Requisiti hardware e software per le conferenze in Skype for Business Server

**Riepilogo:** Leggere questo argomento per informazioni sui requisiti hardware e software per le conferenze in Skype for Business Server.

In questa sezione vengono descritti i requisiti hardware e software per le conferenze Web, le conferenze audio e video (A/V), le conferenze telefoniche con accesso esterno e le conferenze di messaggistica istantanea. Tutte le funzionalità di conferenza vengono eseguite nei Front End Server. esistono requisiti aggiuntivi per diversi tipi di conferenze, come illustrato nel diagramma seguente.

Ad esempio, se si desidera consentire le conferenze telefoniche con accesso esterno, è necessario distribuire un Mediation Server e un gateway per la connessione alla rete PSTN (Public Switched Telephone Network). Se si desidera consentire le conferenze Web, è necessario assicurarsi Skype for Business Server connettersi a un Office Web Apps Server. Se si desidera consentire agli utenti esterni di partecipare alle conferenze, è necessario distribuire un server perimetrale.

**Requisiti e funzionalità di conferenza**

![Componenti per conferenze](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Per ulteriori informazioni sulle considerazioni relative alla topologia, vedere [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Requisiti hardware e software per Front End Server

Poiché le conferenze Web, le conferenze audio/video, le conferenze telefoniche con accesso esterno e la messaggistica istantanea sono tutte collocate nel Front End Server, i requisiti hardware e software del server sono gli stessi dei Front End Server. Per informazioni dettagliate su questi requisiti, vedere [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e Environmental requirements for Skype for Business Server [2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Requisiti per le conferenze Web

Se si decide di abilitare le conferenze Web, è necessario pianificare quanto segue:

- Accesso all'archivio file utilizzato per l'archiviazione del contenuto delle conferenze Web.

- Integrazione con Office Web Apps Server, necessaria per condividere PowerPoint file durante una conferenza.

### <a name="file-store"></a>Archivio file

Il Skype for Business Server Web Conferencing archivia il contenuto condiviso durante le riunioni nell'archivio file. Come parte della distribuzione, è necessario specificare una condivisione file da utilizzare come archivio file per il server edizione Standard o edizione Enterprise pool Front End. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisione file. Per ulteriori informazioni, vedere [Create a file share in Skype for Business Server](../../deploy/install/create-a-file-share.md). Il servizio per conferenze Web crittografa il contenuto prima di archiviarlo nell'archivio file.

Skype for Business Server supporta l'utilizzo di condivisioni file in uno spazio di archiviazione collegato diretto (DAS) o in una rete san (Storage Area Network), incluso DFS (Distributed File System), e su un array ridondante di dischi indipendenti (RAID) per gli archivi file. Dopo che Skype for Business Server distribuzione guidata ha definito il percorso della condivisione file, Skype for Business Server una struttura di cartelle all'interno della condivisione file simile alla seguente:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

Il servizio di conferenza Web archivia quindi il contenuto, ad esempio diapositive di PowerPoint, lavagne, sondaggi e allegati, nelle cartelle CollabContent e CollabMetadata che si trovano nella cartella WebServices.

### <a name="office-web-apps-server"></a>server Office Web Apps

Per utilizzare le funzionalità di conferenza Web, è necessario installare Office Web Apps Server e configurare Skype for Business Server per comunicare con Office Web Apps Server.

Office Il server Web Apps deve essere installato in un computer autonomo che non esegue Skype for Business Server, SQL Server o qualsiasi altra applicazione server. Non è necessario che nel computer sia installata alcuna Office di installazione. In qualsiasi computer utilizzato per eseguire Office Web Apps Server deve essere installato anche un set specifico di software (inclusi .NET Framework 4.5 e Windows PowerShell 3.0). Questi requisiti, insieme alle informazioni sulla configurazione di certificati e Internet Information Services (IIS), sono descritti in dettaglio nel sito Web Microsoft Office [distribuzione di](/webappsserver/deploy-the-infrastructure-office-web-apps-server)app Web .

Per informazioni su come configurare Skype for Business Server per l'utilizzo con Office Web Apps Server, vedere [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Requisiti per le conferenze audio e video

Per la pianificazione delle conferenze audio/video è necessario conoscere i requisiti di larghezza di banda di rete dei vari tipi di supporti per le conferenze richiesti dall'organizzazione. Ciò può includere audio, video e video panoramici. Senza larghezza di banda di rete sufficiente, l'esperienza utente potrebbe essere gravemente danneggiata.

Per informazioni sulla pianificazione della capacità audio e video per le conferenze, vedere [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md).

È possibile utilizzare il servizio Controllo di ammissione di chiamata per gestire la larghezza di banda di rete utilizzata dalle conferenze audio/video. Ciò è importante per le reti con restrizioni, ad esempio collegamenti a larghezza di banda limitata tra siti centrali e siti di succursale. Per informazioni dettagliate, vedere [Plan for call admission control in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)

Se si distribuiscono audioconferenze nella rete, gli utenti dovranno utilizzare dispositivi audio, ad esempio cuffie, per partecipare a una conferenza audio. Se si distribuiscono videoconferenze, è necessario distribuire dispositivi video, ad esempio webcam per gli utenti. Per i dispositivi audio e video, la distribuzione dei dispositivi e la formazione degli utenti sono passaggi importanti da prendere in considerazione. Per ulteriori informazioni, vedere [Plan for clients and devices](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft consiglia di utilizzare dispositivi per comunicazioni unificate certificati da Microsoft per tutti i tipi di dispositivi, per garantire un'esperienza utente ottimale. Per informazioni dettagliate sui dispositivi certificati uc, vedere [Telefoni e dispositivi per Skype for Business](../../../SfbPartnerCertification/certification/devices-ip-phones.md).

## <a name="requirements-for-dial-in-conferencing"></a>Requisiti per le conferenze telefoniche con accesso esterno

Le conferenze telefoniche con accesso esterno sono una funzionalità facoltativa del carico Skype for Business Server di conferenza telefonica che include un'ampia gamma di componenti. Alcuni dei componenti sono specifici delle conferenze telefoniche con accesso esterno, mentre altri sono componenti di VoIP aziendale. In questa sezione vengono descritti i requisiti per i componenti necessari per le conferenze telefoniche con accesso esterno. Per informazioni dettagliate sui requisiti del mediation server e del gateway PSTN [(Public](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) Switched Telephone Network), vedere Mediation Server component in Skype for Business Server e Deploy [a Mediation Server in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Componenti necessari

Prima di configurare le conferenze telefoniche con Skype for Business Server, è necessario installare i componenti seguenti:

- Servizio applicazione comunicazioni unificate (UCAS, Unified Communications Application Service) (denominato servizio applicazione)

- Applicazione Operatore Conferenza

- Applicazione Annuncio conferenza

- Pagina Web conferenze telefoniche Impostazioni accesso esterno

- Almeno un Mediation Server e almeno un gateway PSTN

Per le conferenze telefoniche con accesso esterno, il servizio applicazioni, applicazione Operatore conferenza e applicazione Annuncio conferenza hanno gli stessi requisiti del sistema operativo dei Front End Server. Per informazioni dettagliate, vedere [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

applicazione Operatore conferenza e applicazione Annuncio conferenza è necessario che Windows Runtime formato multimediale sia installato nei Front End Server. Windows Runtime formato multimediale è necessario per riprodurre Windows file WMA (Media Audio) utilizzati per la musica in attesa, i nomi registrati e i prompt. Se si esegue l'installazione in Windows Server 2012 o Windows Server 2012 R2 (scelta consigliata), è necessario installare Microsoft Media Foundation per ottenere Windows Media Format Runtime. Se si esegue l'installazione in qualsiasi versione di Windows Server prima di Windows 2012, è necessario verificare che l'esperienza desktop di Windows sia installata per ottenere Windows Media Format Runtime.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisiti dei file audio per le conferenze telefoniche con accesso esterno

Skype for Business Server non supporta la personalizzazione dei prompt vocali e della musica per le conferenze telefoniche con accesso esterno. Tuttavia, se si ha una forte necessità aziendale che richiede la modifica dei file audio predefiniti, vedere l'articolo della Microsoft Knowledge Base 961177 Come personalizzare i [prompt](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)vocali o i file musicali per le audioconferenze con accesso esterno.

È inoltre possibile utilizzare l'utilità di gestione dei prompt vocali personalizzati di [Microsoft Lync Server Operatore conferenza](https://go.microsoft.com/fwlink/p/?LinkId=396880) che consente agli amministratori di sostituire i prompt vocali predefiniti utilizzati quando un chiamante del telefono partecipa a una riunione di Skype for Business con prompt personalizzati per offrire un'esperienza di immissione di riunione diversa. I prompt vocali personalizzati possono essere installati in un server Enterprise o edizione Standard server.

applicazione Operatore conferenza e applicazione Annuncio conferenza hanno i requisiti seguenti per la musica in attesa, il nome registrato e i file di prompt audio:

- Formato file WMA (Windows Media Audio)

- Mono a 16 bit

- CBR (Constant Bit Rate) a due passaggi 48 kbps

- Livello parlato a -24 DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Requisiti utente per le conferenze telefoniche con accesso esterno

Gli utenti delle conferenze telefoniche con accesso esterno devono avere un numero di telefono univoco o un interno assegnato al loro account. Questo requisito supporta l'autenticazione durante l'accesso esterno. Enterprise utenti (ovvero gli utenti che dispongono di credenziali di Servizi di dominio Active Directory e account Skype for Business Server all'interno dell'organizzazione) immettere il proprio numero di telefono (o interno) e un PIN (Personal Identification Number) per accedere alle conferenze come utente autenticato.

## <a name="port-requirements-for-conferencing"></a>Requisiti delle porte per le conferenze

Per utilizzare le funzionalità di conferenza, è Skype for Business Server che alcune porte siano aperte. Nella tabella seguente sono elencati i requisiti delle porte per le conferenze. Per informazioni dettagliate su tutti i requisiti delle porte, vedere [Port and protocol requirements for servers](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Porte server necessarie**


|**Ruolo del server**|**Nome del servizio**|**Porta**|**Protocollo**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|Front End Server  <br/> |Skype for Business Server Servizio di conferenza di messaggistica istantanea  <br/> |5062  <br/> |TCP  <br/> |Utilizzata per le richieste SIP in arrivo per le conferenze di messaggistica istantanea (IM).  <br/> |
|Front End Server  <br/> |Skype for Business Server Servizio Web Conferencing  <br/> |8057  <br/> |TCP (TLS)  <br/> |Utilizzata per attendere le connessioni PSOM (Persistent Shared Object Model) dal client.  <br/> |
|Front End Server  <br/> |Skype for Business Server Servizio Compatibilità conferenze Web  <br/> |8058  <br/> |TCP (TLS)  <br/> |Utilizzato per ascoltare le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e dalle versioni precedenti di Skype for Business Server.  <br/> |
|Front End Server  <br/> |Skype for Business Server Servizio audio/videoconferenza  <br/> |5063  <br/> |TCP  <br/> |Utilizzata per le richieste SIP in arrivo per Audio/Video (A/V) Conferencing.  <br/> |
|Front End Server  <br/> |Skype for Business Server Servizio audio/videoconferenza  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervallo di porte di attesa multimediali utilizzato per le conferenze video.  <br/> |
|Front End Server  <br/> |Skype for Business Server Operatore conferenza (conferenza telefonica con accesso esterno)  <br/> |5064  <br/> |TCP  <br/> |Utilizzata per le richieste SIP in arrivo per le conferenze telefoniche con accesso esterno.  <br/> |
|Front End Server  <br/> |Skype for Business Server Operatore conferenza (conferenza telefonica con accesso esterno)  <br/> |5072  <br/> |TCP  <br/> |Utilizzato per le richieste SIP in arrivo per l'operatore (conferenza telefonica con accesso esterno).  <br/> |
|Front End Server  <br/> |Skype for Business Server Servizio condivisione applicazioni  <br/> |5065  <br/> |TCP  <br/> |Utilizzata per le richieste di attesa SIP in arrivo per la condivisione delle applicazioni.  <br/> |
|Front End Server  <br/> |Skype for Business Server Servizio condivisione applicazioni  <br/> |49152-65535  <br/> |TCP  <br/> |Intervallo di porte di attesa multimediali per la condivisione delle applicazioni.  <br/> |
|Front End Server  <br/> |Skype for Business Server Annuncio conferenza servizio  <br/> |5073  <br/> |TCP  <br/> |Utilizzato per le richieste SIP in arrivo per il servizio Skype for Business Server Annuncio conferenza ,ovvero per le conferenze telefoniche con accesso esterno.  <br/> |
|Tutti i server interni  <br/> |Vari  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Intervallo di porte multimediali utilizzato per le conferenze audio su tutti i server interni. Utilizzato da tutti i server che terminano l'audio: Front End Server (per il servizio Skype for Business Server Operatore conferenza, il servizio Skype for Business Server Annuncio conferenza e il servizio di audioconferenza Skype for Business Server) e Mediation Server.  <br/> |
|Office Server Web Apps  <br/> ||443  <br/> ||Utilizzato da Skype for Business Server per connettersi Office server Web Apps.  <br/> |

**Porte client necessarie**


|**Porta**|**Protocollo**|**Note**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Utilizzata per l'accesso utente esterno alle sessioni di Web Conferencing.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Utilizzata per l'accesso utente esterno alle sessioni A/V e ai supporti multimediali (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Utilizzato per l'accesso degli utenti esterni alle sessioni A/V e ai supporti (UDP)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Intervallo di porte audio (almeno 20 porte richieste)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Intervallo di porte video (almeno 20 porte richieste).  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |Condivisione applicazioni.  <br/> |