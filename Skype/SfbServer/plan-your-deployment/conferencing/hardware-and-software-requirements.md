---
title: Requisiti hardware e software per i servizi di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Riepilogo: leggere questo argomento per informazioni sui requisiti hardware e software per i servizi di conferenza in Skype for Business Server.'
ms.openlocfilehash: c4efb85c7ae1674cab7ee123833df779a835e14c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187826"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Requisiti hardware e software per i servizi di conferenza in Skype for Business Server

**Riepilogo:** Leggere questo argomento per informazioni sui requisiti hardware e software per i servizi di conferenza in Skype for Business Server.

In questa sezione vengono descritti i requisiti hardware e software per le conferenze Web, le conferenze telefoniche con accesso esterno, i servizi di conferenza telefonica e la messaggistica istantanea. Tutte le funzionalità di conferenza vengono eseguite nei server front-end; Esistono requisiti aggiuntivi per i diversi tipi di conferenza, come illustrato nel diagramma seguente.

Ad esempio, se si vuole consentire i servizi di conferenza telefonica con accesso esterno, è necessario distribuire un Mediation Server e un gateway per la connessione alla rete PSTN (Public Switched Telephone Network). Se si vuole consentire la conferenza Web, è necessario assicurarsi che Skype for Business Server possa connettersi a un server di Office Web Apps. Se si vuole consentire agli utenti esterni di partecipare a conferenze, è necessario distribuire un server perimetrale.

**Funzionalità e requisiti per i servizi di conferenza**

![Componenti di conferenza](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Per altre informazioni sulle considerazioni sulla topologia, vedere [pianificare la topologia di conferenza per Skype for Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Requisiti hardware e software per i server front-end

Poiché i servizi di conferenza Web, i servizi di conferenza A/V, i servizi di conferenza telefonica con accesso esterno e i servizi di conferenza di messaggistica istantanea sono tutti collocati con il front end server, i requisiti hardware e software del server sono gli stessi per i server front-end. Per informazioni dettagliate su questi requisiti, vedere requisiti del [Server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e requisiti [ambientali per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisiti del server per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Requisiti per le conferenze Web

Se si è scelto di abilitare i servizi di conferenza Web, è necessario pianificare le operazioni seguenti:

- Accedere all'archivio file, che viene usato per archiviare il contenuto delle conferenze Web.

- Integrazione con Office Web Apps Server, che è necessario per condividere i file di PowerPoint durante una conferenza.

### <a name="file-store"></a>Archivio file

Il servizio Web Conferencing di Skype for Business Server archivia i contenuti condivisi durante le riunioni in archivio file. Come parte della distribuzione, devi specificare una condivisione di file da usare come archivio file per il pool di front-end Standard Edition Server o Enterprise Edition. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisione file. Per altre informazioni, vedere [creare una condivisione di file in Skype for Business Server](../../deploy/install/create-a-file-share.md). Il servizio Web Conferencing crittografa il contenuto prima di archiviare il contenuto nell'archivio file.

Skype for Business Server supporta l'uso di condivisioni file in un ambiente di archiviazione Direct Attached (DAS) o in una rete di archiviazione (SAN), incluso il file System distribuito (DFS) e in una matrice ridondante di dischi indipendenti (RAID) per archivi di file. Dopo che la distribuzione guidata di Skype for Business Server ha definito la posizione della condivisione file, Skype for Business Server crea una struttura di cartelle all'interno della condivisione file simile alla seguente:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - Dataconf

Il servizio Web Conferencing consente quindi di archiviare contenuti come diapositive di PowerPoint, lavagne, sondaggi e allegati nelle cartelle CollabContent e CollabMetadata, che si trovano nella cartella WebServices.

### <a name="office-web-apps-server"></a>Server Office Web Apps

Per usare le funzionalità di conferenza Web, è necessario installare Office Web Apps Server e configurare Skype for Business Server per comunicare con Office Web Apps Server.

Il server Office Web Apps deve essere installato in un computer autonomo che non è in grado di eseguire Skype for Business Server, SQL Server o qualsiasi altra applicazione server. Non è necessario che nel computer sia installata una versione di Office. Qualsiasi computer usato per eseguire Office Web Apps Server deve avere anche un set di software specifico installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0). Questi requisiti, oltre a informazioni sulla configurazione di certificati e Internet Information Services (IIS), vengono descritti in dettaglio nel [sito Web Microsoft Office Web Apps Deployment](https://go.microsoft.com/fwlink/p/?linkid=257525).

Per informazioni su come configurare Skype for Business Server per l'utilizzo con Office Web Apps Server, vedere [configurare l'integrazione con Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Requisiti per le conferenze audio e video

Per pianificare i servizi di conferenza A/V, è necessario comprendere la larghezza di banda della rete necessaria per il tipo di supporto per i servizi di conferenza richiesto dall'organizzazione. Questo potrebbe includere l'audio, il video e il video panoramico. Senza una sufficiente larghezza di banda della rete, l'esperienza utente potrebbe essere gravemente degradata.

Per informazioni sulla pianificazione della capacità audio e video per le conferenze, vedere [pianificare i requisiti di rete per Skype for business](../../plan-your-deployment/network-requirements/network-requirements.md).

Puoi usare il controllo di ammissione chiamata (CAC) per gestire la larghezza di banda della rete usata da servizi di conferenza A/V. Questa operazione è importante per le reti con restrizioni, ad esempio i collegamenti a larghezza di banda limitati tra siti centrali e succursali. Per informazioni dettagliate, vedere [pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Se si distribuiscono i servizi di audioconferenza nella rete, gli utenti avranno bisogno di dispositivi audio come auricolari per partecipare a una conferenza audio. Se si distribuiscono videoconferenze, è necessario distribuire dispositivi video, ad esempio webcam per gli utenti. Per i dispositivi audio e video, la distribuzione di dispositivi e la formazione degli utenti sono passaggi importanti da prendere in considerazione. Per altre informazioni, vedere [pianificare i client e i dispositivi](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft consiglia di usare i dispositivi Unified Communications (UC) certificati da Microsoft per tutti i tipi di dispositivi, per garantire un'esperienza utente ottimale. Per informazioni dettagliate sui dispositivi certificati UC, vedere [telefoni e dispositivi per Skype for business](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Requisiti per i servizi di conferenza telefonica con accesso esterno

I servizi di conferenza telefonica con accesso esterno sono una caratteristica facoltativa del carico di lavoro delle conferenze di Skype for Business Server che include una vasta gamma di componenti. Alcuni componenti sono specifici per i servizi di conferenza telefonica con accesso esterno e alcuni sono componenti di VoIP aziendale. Questa sezione descrive i requisiti per i componenti necessari per i servizi di conferenza telefonica con accesso esterno. Per informazioni dettagliate sui requisiti del gateway di Mediation Server e PSTN (Public Switched Telephone Network), vedere [Componente Mediation Server in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) e [distribuire un Mediation Server in Generatore di topologie in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Componenti necessari

Per poter configurare i servizi di conferenza telefonica con accesso esterno, è necessario installare i componenti di Skype for Business Server seguenti:

- Unified Communications Application Service (UCAS) (denominato servizio applicazione)

- Applicazione Supervisore conferenza

- Applicazione per l'annuncio di conferenza

- Pagina Web delle impostazioni di conferenza telefonica con accesso esterno

- Almeno un Mediation Server e almeno un gateway PSTN

Per i servizi di conferenza telefonica con accesso esterno, il servizio applicazione, l'applicazione di conferenza e l'applicazione di annunci di conferenza hanno gli stessi requisiti di sistema operativo di front end server. Per informazioni dettagliate, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

L'applicazione per i servizi di conferenza e l'applicazione per le conferenze richiede che Windows Media Format Runtime sia installato nei server front-end. Windows Media Format Runtime è necessario per riprodurre file di Windows Media Audio (WMA) usati per la musica in attesa, i nomi registrati e le istruzioni. Se si sta eseguendo l'installazione in Windows Server 2012 o Windows Server 2012 R2 (consigliato), è necessario installare Microsoft Media Foundation per ottenere Windows Media Format Runtime. Se si sta eseguendo l'installazione in qualsiasi versione di Windows Server precedente a Windows 2012, è necessario verificare che l'esperienza desktop di Windows sia installata per ottenere Windows Media Format Runtime.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisiti per i file audio per i servizi di conferenza telefonica con accesso esterno

Skype for Business Server non supporta la personalizzazione delle richieste vocali e della musica per i servizi di conferenza telefonica con accesso esterno. Tuttavia, se si ha bisogno di cambiare i file audio predefiniti, vedere l'articolo 961177 della Microsoft Knowledge base [su come personalizzare le richieste vocali o i file musicali per i servizi di conferenza telefonica con accesso esterno](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177).

È anche possibile usare l'utilità per la gestione delle [richieste vocali personalizzate di Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=396880) Conferencing, che consente agli amministratori di sostituire le richieste vocali predefinite usate quando un chiamante di telefono si unisce a una riunione Skype for business con istruzioni personalizzate per creare un'esperienza di partecipazione a una riunione diversa. Le istruzioni vocali personalizzate possono essere installate in un server Enterprise o Standard Edition.

Applicazione per i servizi di conferenza e l'applicazione di annuncio di conferenza sono i requisiti seguenti per la musica in attesa, il nome registrato e i file di prompt audio:

- Formato di file di Windows Media Audio (WMA)

- 16 bit mono

- CBR a due passaggi di 48 kbps (velocità in bit costante)

- Livello di riconoscimento vocale at-24DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Requisiti degli utenti per i servizi di conferenza telefonica con accesso esterno

Gli utenti dei servizi di conferenza telefonica con accesso esterno devono avere un numero o un'estensione di telefono univoco assegnati al proprio account. Questo requisito supporta l'autenticazione durante i servizi di conferenza telefonica con accesso esterno. Gli utenti aziendali (ovvero gli utenti con credenziali di servizi di dominio Active Directory e gli account di Skype for Business Server all'interno dell'organizzazione) immettono il loro numero di telefono (o estensione) e un PIN per accedere alle conferenze come un utente autenticato.

## <a name="port-requirements-for-conferencing"></a>Requisiti della porta per i servizi di conferenza

Per usare le funzionalità di conferenza, Skype for Business Server richiede che alcune porte siano aperte. La tabella seguente elenca i requisiti di porta per i servizi di conferenza. Per informazioni dettagliate su tutti i requisiti della porta, vedere [requisiti per la porta e il protocollo per i server](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Porte del server obbligatorie**


|**Ruolo del server**|**Nome servizio**|**Porta**|**Protocollo**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|Server front-end  <br/> |Servizio di conferenza di messaggistica istantanea di Skype for Business Server  <br/> |5062  <br/> |TCP  <br/> |Usato per le richieste SIP in arrivo per le conferenze di messaggistica istantanea.  <br/> |
|Server front-end  <br/> |Servizio di conferenza Web di Skype for Business Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Usato per ascoltare le connessioni PSOM (Persistent Shared Object Model) dal client.  <br/> |
|Server front-end  <br/> |Servizio compatibilità con Skype for Business Server Web Conferencing  <br/> |8058  <br/> |TCP (TLS)  <br/> |Usato per ascoltare le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e dalle versioni precedenti di Skype for Business Server.  <br/> |
|Server front-end  <br/> |Servizio di conferenza audio/video di Skype for Business Server  <br/> |5063  <br/> |TCP  <br/> |Usato per le richieste SIP in arrivo per le conferenze audio/video (A/V).  <br/> |
|Server front-end  <br/> |Servizio di conferenza audio/video di Skype for Business Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervallo di porte multimediali usato per i servizi di conferenza video.  <br/> |
|Server front-end  <br/> |Servizio di conferenza telefonica di Skype for Business Server (servizi di conferenza telefonica con accesso esterno)  <br/> |5064  <br/> |TCP  <br/> |Usato per le richieste SIP in arrivo per i servizi di conferenza telefonica con accesso esterno.  <br/> |
|Server front-end  <br/> |Servizio di conferenza telefonica di Skype for Business Server (servizi di conferenza telefonica con accesso esterno)  <br/> |5072  <br/> |TCP  <br/> |Usato per le richieste SIP in arrivo per l'operatore (servizi di conferenza telefonica con accesso esterno).  <br/> |
|Server front-end  <br/> |Servizio di condivisione applicazioni di Skype for Business Server  <br/> |5065  <br/> |TCP  <br/> |Usato per le richieste di ascolto SIP in arrivo per la condivisione delle applicazioni.  <br/> |
|Server front-end  <br/> |Servizio di condivisione applicazioni di Skype for Business Server  <br/> |49152-65535  <br/> |TCP  <br/> |Intervallo di porte multimediali usato per la condivisione delle applicazioni.  <br/> |
|Server front-end  <br/> |Servizio di annuncio per conferenze di Skype for Business Server  <br/> |5073  <br/> |TCP  <br/> |Usato per le richieste SIP in arrivo per il servizio di annunci conferenza di Skype for Business Server (ovvero per i servizi di conferenza telefonica con accesso esterno).  <br/> |
|Tutti i server interni  <br/> |Vari  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Intervallo di porte multimediali usato per i servizi di audioconferenza in tutti i server interni. Usato da tutti i server che interrompono l'audio: Front End Servers (per il servizio di conferenza telefonica di Skype for Business Server, servizio di annuncio per conferenze di Skype for Business Server e servizio di conferenza audio/video di Skype for Business Server) e Mediation Server.  <br/> |
|Server di Office Web Apps  <br/> ||443  <br/> ||Usato da Skype for Business Server per connettersi al server di Office Web Apps.  <br/> |

**Porte client richieste**


|**Porta**|**Protocollo**|**Note**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Usato per l'accesso degli utenti esterni alle sessioni di conferenza Web.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Usato per l'accesso degli utenti esterni alle sessioni A/V e agli elementi multimediali (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Usato per l'accesso degli utenti esterni alle sessioni A/V e agli elementi multimediali (UDP)  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervallo di porte audio (minimo 20 porte necessarie)  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervallo di porte video (è necessario un minimo di 20 porte).  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |Condivisione applicazioni.  <br/> |


