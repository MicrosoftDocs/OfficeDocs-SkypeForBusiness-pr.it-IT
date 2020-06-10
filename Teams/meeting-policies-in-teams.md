---
title: Gestire i criteri di riunione
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Informazioni su come gestire le impostazioni dei criteri di riunione in teams e usarle per controllare le funzionalità disponibili per le riunioni dei partecipanti per i meeting pianificati dagli utenti.
ms.openlocfilehash: 726e14aef92eed8fe681d183b8e1cfd404e659ca
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665138"
---
# <a name="manage-meeting-policies-in-teams"></a>Gestire i criteri di riunione in Teams

::: zone target="docs"
I criteri riunione vengono usati per controllare le funzionalità disponibili per i partecipanti alle riunioni programmate dagli utenti nell'organizzazione. Dopo aver creato un criterio e aver apportato le modifiche necessarie, è possibile assegnare utenti al criterio. Si possono gestire i criteri di riunione nell'interfaccia di amministrazione di Microsoft Teams o tramite [PowerShell](teams-powershell-overview.md).

> [!NOTE]
> Per informazioni sull'uso dei ruoli per gestire le autorizzazioni di relatori e partecipanti alla riunione, vedere [ruoli in una riunione di teams](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

È possibile implementare i criteri nei modi descritti di seguito. La scelta influisce sull'esperienza di riunione per gli utenti prima, durante o dopo una riunione.

|Tipo di implementazione  |Descrizione  |
|---------|---------|
|Per organizzatore    |Quando si implementa un criterio per organizzatore, tutti i partecipanti alla riunione ereditano il criterio dell'organizzatore. Ad esempio, **Ammetti automaticamente le persone** è un criterio per organizzatore e controlla se gli utenti accedono direttamente alla riunione oppure attendono nella sala di attesa per le riunioni pianificate dall'utente a cui è assegnato il criterio.          |
|Per utente    |Quando si implementano criteri per utente, viene applicato solo il criterio per utente per limitare l'uso di determinate funzionalità da parte dell'organizzatore e/o dei partecipanti alla riunione. Ad esempio, **Consenti l'uso di Riunione immediata nei canali** è un criterio per utente.     |
|Per organizzatore e per utente     |Quando si implementa una combinazione di criteri per organizzatore e per utente, l'uso di alcune funzionalità da parte dei partecipanti alla riunione è limitato, in base ai criteri applicati al singolo utente e ai criteri dell'organizzatore. Ad esempio, **Consenti registrazione cloud** è un criterio per organizzazione e per utente. Attivare questa impostazione per consentire all'organizzatore della riunione e ai partecipanti di avviare o interrompere una registrazione.

Per impostazione predefinita, viene creato un criterio denominato Globale (predefinito a livello di organizzazione). Il criterio di riunione Globale viene assegnato per impostazione predefinita a tutti gli utenti dell'organizzazione. È possibile modificarlo o creare uno o più criteri personalizzati e assegnarli agli utenti. Se non si creano e assegnano criteri personalizzati, gli utenti riceveranno il criterio Globale. Quando si crea un criterio personalizzato, è possibile consentire o impedire che determinate funzionalità siano disponibili per gli utenti e quindi assegnarlo a uno o più utenti ai quali verranno applicate le impostazioni.

> [!NOTE]
> Il pulsante Dettagli riunione sarà disponibile se l'utente ha abilitato le licenze per le conferenze audio o se l'utente è autorizzato a ricevere servizi di audioconferenza, in caso contrario, i dettagli della riunione non saranno disponibili.

## <a name="change-or-create-a-meeting-policy"></a>Modificare o creare un criterio di riunione

Per modificare o creare un criterio riunione, passare all'interfaccia di amministrazione di Microsoft Teams > **Riunioni**  >  **Criteri riunione**. Selezionare un criterio dall'elenco o selezionare **Aggiungi**. Se si sta creando un nuovo criterio, aggiungere un nome e una descrizione. Il nome non può contenere caratteri speciali o più di 64 caratteri. Scegliere le impostazioni desiderate e quindi selezionare **Salva**.

Ad esempio, si supponga di avere un gruppo di utenti e di voler limitare la larghezza di banda necessaria per la riunione. È possibile creare un nuovo criterio personalizzato denominato "Larghezza di banda limitata" e disabilitare le impostazioni seguenti:

In **Audio e video**:
- Disattivare Consenti registrazione cloud.
- Disattivare Consenti video IP.

In **Condivisione di contenuti**:
- Disabilitare la modalità di condivisione dello schermo.
- Disattivare Consenti la lavagna.
- Disattivare Consenti note condivise.

Assegnare poi il criterio agli utenti.

> [!NOTE]
> A ogni utente può essere assegnato un solo criterio di riunione per volta.

## <a name="assign-a-meeting-policy-to-users"></a>Assegnare un criterio riunione agli utenti

Per assegnare un criterio riunione a un solo utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. In **Criteri riunioni** selezionare il criterio da assegnare e poi fare clic su **Applica**.

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.  

Si può anche procedere nel modo seguente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Dopo avere aggiunto gli utenti, selezionare **Salva**.

> [!NOTE]
> Non è possibile eliminare un criterio a cui sono utenti. È prima di tutto necessario assegnare un criterio diverso a tutti gli utenti interessati, quindi sarà possibile eliminare il criterio originale.

## <a name="meeting-policy-settings"></a>Impostazioni dei criteri di riunione

Quando si seleziona un criterio esistente nella pagina **Criteri riunione** o si seleziona **Aggiungi** per aggiungere un nuovo criterio, è possibile configurare le impostazioni per gli elementi seguenti.

- [Generale](#meeting-policy-settings---general)
- [Audio e video](#meeting-policy-settings---audio--video)
- [Condivisione di contenuti](#meeting-policy-settings---content-sharing)
- [Partecipanti e ospiti](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Impostazioni dei criteri di riunione - Generale

- [Consenti l'uso di Riunione immediata nei canali](#allow-meet-now-in-channels)
- [Consenti il componente aggiuntivo per Outlook](#allow-the-outlook-add-in)
- [Consenti la pianificazione delle riunioni di canale](#allow-channel-meeting-scheduling)
- [Consenti la pianificazione di riunioni private](#allow-scheduling-private-meetings)
- [Consenti l'uso di Riunione immediata nelle riunioni private](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Consenti l'uso di Riunione immediata nei canali

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se un utente può avviare una riunione ad hoc in un canale di Teams. Se si attiva, quando un utente pubblica un messaggio in un canale di Teams, può fare clic su **Riunione immediata** sotto la casella di composizione per avviare una riunione ad hoc nel canale. Il valore predefinito è True.

![Screenshot che mostra l'icona Riunione immediata sotto un messaggio](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a>Consenti il componente aggiuntivo per Outlook

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione consente di controllare se è possibile pianificare riunioni di Teams dall'interno di Outlook (Windows, Mac, Web e Mobile).

![Screenshot che mostra la possibilità di pianificare una nuova riunione](media/meeting-policies-outlook-add-in.png)

Se si disattiva questa impostazione, gli utenti non potranno pianificare riunioni di Teams durante la creazione di una nuova riunione in Outlook. In Outlook per Windows, ad esempio, l'opzione **Nuova riunione di Teams ** non comparirà sulla barra multifunzione.

### <a name="allow-channel-meeting-scheduling"></a>Consenti la pianificazione delle riunioni di canale

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se gli utenti possono pianificare una riunione in un canale di Teams.  Se si disattiva, l'opzione **Pianifica una riunione** non sarà disponibile per l'utente quando avvia una riunione in un canale di Teams e l'opzione **Aggiungi canale** sarà disabilitata per gli utenti in Teams. Il valore predefinito è True.

![Screenshot che mostra l'opzione Pianifica una riunione in Teams](media/meeting-policies-schedule-a-meeting.png)

![Screenshot che mostra l'opzione Seleziona un canale per la riunione](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>Consenti la pianificazione di riunioni private

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se gli utenti possono pianificare riunioni private in Teams. Una riunione è privata quando non viene pubblicata in un canale in un team.

Si noti che, disattivando **Consenti la pianificazione di riunioni private** e **Consenti la pianificazione delle riunioni di canale**, le opzioni **Aggiungi partecipanti obbligatori** e **Aggiungi canale** vengono disabilitate per gli utenti in Teams. Il valore predefinito è True.

### <a name="allow-meet-now-in-private-meetings"></a>Consenti l'uso di Riunione immediata nelle riunioni private

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se un utente può avviare una riunione privata ad hoc.  Il valore predefinito è True.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Impostazioni dei criteri di riunione - Audio e video

- [Consenti la trascrizione](#allow-transcription)
- [Consenti registrazione cloud](#allow-cloud-recording)
- [Consenti video IP](#allow-ip-video)
- [Velocità in bit media (KBS)](#media-bit-rate-kbs)

### <a name="allow-transcription"></a>Consenti la trascrizione

Questa è una combinazione di criterio per organizzatore e criterio per utente. Questa impostazione controlla la disponibilità di didascalie e funzionalità di trascrizione durante la riproduzione di registrazioni delle riunioni. Se si disattiva questa opzione, durante la riproduzione di una registrazione di riunione non saranno disponibili le opzioni **Cerca** e **Cc**. La persona che ha avviato la registrazione ha bisogno che questa impostazione sia attivata perché la registrazione includa anche una trascrizione. 

Si noti che la trascrizione per le riunioni registrate è attualmente supportata solo per gli utenti che hanno la lingua di Teams impostata sull'inglese e quando durante la riunione si usa l'inglese.

![Screenshot che mostra le opzioni di trascrizione in una riunione](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Consenti registrazione cloud

Questa è una combinazione di criterio per organizzatore e criterio per utente. Questa impostazione controlla se è possibile registrare le riunioni di quest'utente. La registrazione può essere avviata dall'organizzatore della riunione o da un altro partecipante alla riunione, se l'impostazione dei criteri è attivata per il partecipante e se si tratta di un utente autenticato della stessa organizzazione.

Le persone esterne all'organizzazione, ad esempio gli utenti federati e anonimi, non possono avviare la registrazione. Gli utenti guest non possono avviare o interrompere la registrazione. 

![Screenshot che mostra le opzioni di registrazione](media/meeting-policies-recording.png)

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti registrazione cloud |
|---------|---------|---------|
|Daniela | Globale   | Falso |
|Amanda | CriterioRiunionePosizione1 | Vero|
|Luca (utente esterno) | Non applicabile | Non applicabile|

Non è possibile registrare le riunioni organizzate da Daniela e Amanda che ha l'impostazione del criterio attivata, non può registrare le riunioni organizzate da Daniela. Le riunioni organizzate da Amanda possono essere registrate, tuttavia Daniela, che ha l'impostazione del criterio disabilitata, e John, che è un utente esterno, non possono registrare le riunioni organizzate da Amanda.

Per altre informazioni sulla registrazione di una riunione cloud, vedere [Registrazione delle riunioni cloud di Teams](cloud-recording.md).

### <a name="allow-ip-video"></a>Consenti video IP

Questa è una combinazione di criterio per organizzatore e criterio per utente. Il video è un componente chiave per le riunioni. In alcune organizzazioni gli amministratori potrebbero volere un maggiore controllo sulle riunioni degli utenti che hanno un video. Questa impostazione controlla se è possibile attivare il video nelle riunioni ospitate da un utente e nelle chiamate 1:1 e di gruppo avviate da un utente. Le riunioni organizzate da un utente che ha questo criterio abilitato consentono la condivisione di video nella riunione da parte dei partecipanti, se anche questi ultimi hanno il criterio abilitato. I partecipanti alla riunione a cui non sono assegnati criteri, ad esempio i partecipanti anonimi e federati, ereditano i criteri dell'organizzatore della riunione.

![Screenshot che mostra una riunione con impostazioni audio e video](media/meeting-policies-audio-video-settings.png)

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti video IP |
|---------|---------|---------|
|Daniela   | Globale   | Vero        |
|Amanda    | CriterioRiunionePosizione1        | Falso      |

Le riunioni ospitate da Daniela consentono di attivare il video. Daniela può partecipare alla riunione e attivare il video. Amanda non può attivare il video nella riunione di Daniela perché la politica di Amanda è impostata su non consentire il video. Amanda può vedere i video condivisi da altri partecipanti alla riunione.

Nelle riunioni ospitate da Amanda nessuno può attivare il video, indipendentemente dai criteri video assegnati. Questo significa che Daniela non può attivare il video nelle riunioni di Amanda.  

Se Daniela chiama Amanda con il video, Amanda può rispondere alla chiamata solo con l'audio.  Quando la chiamata è connessa, Amanda può vedere il video di Daniela, ma non può attivare il video. Se Amanda chiama Daniela, Daniela può rispondere alla chiamata con il video e l'audio. Una volta connessa la chiamata, Daniela può attivare o disattivare suo video come desidera.

### <a name="media-bit-rate-kbs"></a>Velocità in bit media (KBS)

Questo è un criterio per utente. Questa impostazione determina la velocità in bit per le trasmissioni audio, video e di condivisione di app basate su video nelle chiamate e riunioni dell'utente. Si applica ai flussi multimediali in uplink o downlink per gli utenti nella chiamata o riunione. Questa impostazione consente di controllare in modo granulare la gestione della larghezza di banda dell'organizzazione. In base agli scenari di riunione necessari per gli utenti, è necessario disporre di una larghezza di banda sufficiente per fornire un'esperienza di buona qualità. Il valore minimo è 30 Kbps e il valore massimo dipende dallo scenario della riunione. Per altre informazioni sulla larghezza di banda minima consigliata per una buona qualità di riunioni, chiamate ed eventi live in Teams, vedere [Requisiti di larghezza di banda](prepare-network.md#bandwidth-requirements).

Se non è disponibile una larghezza di banda sufficiente per una riunione, i partecipanti vedranno un messaggio che indica una qualità di rete scadente.

Per le riunioni che necessitano di un'esperienza video di qualità elevata, ad esempio le riunioni del consiglio di amministrazione e gli eventi live di Teams, è consigliabile impostare la larghezza di banda su 10 Mbps. Anche se è stata impostata la massima qualità dell'esperienza, lo stack multimediale di Teams si adatta alle condizioni di larghezza di banda ridotte quando vengono rilevate determinate condizioni di rete, a seconda dello scenario. 

## <a name="meeting-policy-settings---content-sharing"></a>Impostazioni dei criteri di riunione - Condivisione di contenuti

- [Modalità condivisione schermo](#screen-sharing-mode)
- [Consenti a un partecipante di fornire o richiedere il controllo](#allow-a-participant-to-give-or-request-control)
- [Consenti a un partecipante esterno di fornire o richiedere il controllo](#allow-an-external-participant-to-give-or-request-control)
- [Consenti la condivisione di PowerPoint](#allow-powerpoint-sharing)
- [Consenti la lavagna](#allow-whiteboard)
- [Consenti note condivise](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>Modalità di condivisione dello schermo

Questa è una combinazione di criterio per organizzatore e criterio per utente. Questa impostazione determina se la condivisione del desktop o della finestra è consentita nella riunione dell'utente. I partecipanti alla riunione a cui non sono assegnati criteri, ad esempio i partecipanti anonimi, guest, B2B e federati, ereditano i criteri dell'organizzatore della riunione.

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Schermo intero**    | È consentita la condivisione completa del desktop e delle applicazioni nella riunione |
|**Applicazione singola**   | È consentita la condivisione di applicazioni nella riunione        |
|**Disattiva**     |Condivisione dello schermo e delle applicazioni disattivata nella riunione.       |

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione |Modalità condivisione schermo |
|---------|---------|---------|
|Daniela  | Globale   | Schermo intero |
|Amanda   | CriterioRiunionePosizione1  | Disattiva |

Le riunioni ospitate da Daniela consentono ai partecipanti alla riunione di condividere l'intero schermo o una specifica applicazione. Se Amanda si unisce alla riunione di Daniela, Amanda non può condividere il suo schermo o un'applicazione specifica perché l'impostazione dei criteri è disabilitata. Nelle riunioni ospitate da Amanda nessuno può condividere lo schermo o una singola applicazione, indipendentemente dal criterio di condivisione dello schermo assegnati. Questo significa che Daniela non può condividere il suo schermo o una singola applicazione nelle riunioni di Amanda.  

Al momento, gli utenti non possono riprodurre video o condividere il proprio schermo in una riunione di Teams se usano Google Chrome.

### <a name="allow-a-participant-to-give-or-request-control"></a>Consenti a un partecipante di fornire o richiedere il controllo

Questo è un criterio per utente. Questa impostazione controlla se l'utente può assegnare il controllo del desktop o della finestra condivisa ad altri partecipanti della riunione. Per concedere il controllo, posizionare il puntatore del mouse nella parte superiore dello schermo. 

Se questa impostazione è attivata per l'utente, nella barra superiore di una sessione di condivisione compare l'opzione **Concedi controllo**. 

![Screenshot che mostra l'opzione Concedi controllo](media/meeting-policies-give-control.png)

Se l'impostazione è disattivata per l'utente, l'opzione **Concedi controllo** non è disponibile.

![Screenshot che mostra che l'opzione Concedi controllo non è disponibile](media/meeting-policies-give-control-not-available.png)

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti a un partecipante di fornire o richiedere il controllo |
|---------|---------|---------|
|Daniela   | Globale   | Vero       |
|Pio    | CriterioRiunionePosizione1        | Falso   |

Daniela può assegnare il controllo del desktop o della finestra condivisa ad altri partecipanti a una riunione organizzata da Pio, mentre Pio non può concedere il controllo ad altri partecipanti.

Per usare PowerShell per controllare gli utenti autorizzati a concedere il controllo o accettare richieste di controllo, usare il cmdlet AllowParticipantGiveRequestControl.

> [!NOTE]
> Per concedere e assumere il controllo del contenuto condiviso durante la condivisione, entrambe le parti devono usare il client desktop di Teams. Il controllo non è supportato se una delle parti esegue Teams in un browser. Ciò è dovuto a una limitazione tecnica che si prevede di risolvere. 

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Consenti a un partecipante esterno di fornire o richiedere il controllo

Questo è un criterio per utente. Questa impostazione controlla se i partecipanti esterni a una riunione possono concedere il controllo del desktop o della finestra condivisa ad altri partecipanti nella riunione. I partecipanti esterni nelle riunioni di Teams possono essere classificati come segue:  

- Utente anonimo
- Utenti guest  
- Utente B2B
- Utente federato  

La possibilità per gli utenti federati di concedere il controllo a utenti esterni durante la condivisione è controllata dall'impostazione **Consenti a un partecipante esterno di fornire o richiedere il controllo** della loro organizzazione.

Per usare PowerShell per controllare i partecipanti esterni autorizzati a concedere il controllo o accettare richieste di controllo, usare il cmdlet AllowExternalParticipantGiveRequestControl.

### <a name="allow-powerpoint-sharing"></a>Consenti la condivisione di PowerPoint

Questo è un criterio per utente. Questa impostazione controlla se l'utente può condividere le presentazioni di PowerPoint in una riunione. Gli utenti esterni, inclusi gli utenti anonimi, guest e federati, ereditano i criteri dell'organizzatore della riunione.

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti la condivisione di PowerPoint |
|---------|---------|---------|
|Daniela   | Globale   | Vero       |
|Amanda   | CriterioRiunionePosizione1        | Falso   |

Amanda non può condividere le presentazioni di PowerPoint nelle riunioni, anche se è l'organizzatrice della riunione. Daniela può condividere le presentazioni di PowerPoint anche se la riunione è organizzata da Amanda. Amanda può visualizzare le presentazioni di PowerPoint condivise da altri nella riunione, anche se non può condividere presentazioni di PowerPoint.

### <a name="allow-whiteboard"></a>Consenti la lavagna

Questo è un criterio per utente. Questa impostazione controlla se un utente può condividere la lavagna in una riunione. Gli utenti esterni, inclusi gli utenti anonimi, B2B e federati, ereditano i criteri dell'organizzatore della riunione. 

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti la lavagna|
|---------|---------|---------|
|Daniela   | Globale   | Vero       |
|Amanda   | CriterioRiunionePosizione1        | Falso   |

Amanda non può condividere la lavagna in una riunione, anche se è l'organizzatrice della riunione. Daniela può condividere la lavagna anche se una riunione è organizzata da Amanda.  

### <a name="allow-shared-notes"></a>Consenti note condivise

Questo è un criterio per utente. Questa impostazione controlla se un utente può creare e condividere note in una riunione. Gli utenti esterni, inclusi gli utenti anonimi, B2B e federati, ereditano i criteri dell'organizzatore della riunione. La scheda **Note riunione** è attualmente supportata solo nelle riunioni con meno di 20 partecipanti.

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti note condivise |
|---------|---------|---------|
|Daniela   | Globale   | Vero       |
|Amanda   | CriterioRiunionePosizione1 | Falso |

Daniela può creare note nelle riunioni di Amanda, mentre Amanda non può creare note in alcuna riunione.

## <a name="meeting-policy-settings---participants--guests"></a>Impostazioni dei criteri di riunione - Partecipanti e ospiti

Queste impostazioni controllano i partecipanti che devono aspettare nella sala di attesa prima di essere ammessi alla riunione e il livello di partecipazione consentito in una riunione.

- [Consenti alle persone anonime di avviare una riunione](#let-anonymous-people-start-a-meeting)
- [Ammetti automaticamente le persone](#automatically-admit-people)
- [Consenti agli utenti che chiamano di ignorare la sala di attesa](#allow-dial-in-users-to-bypass-the-lobby)
- [Abilita i sottotitoli in tempo reale ](#enable-live-captions)
- [Consenti l'uso della chat nelle riunioni ](#allow-chat-in-meetings)

> [!NOTE]
>Le opzioni per partecipare a una riunione variano in base alle impostazioni di ogni gruppo di Teams e al metodo di connessione. Se il gruppo dispone di servizi di audioconferenza e lo usa per la connessione [, vedere audioconferenza](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365). Se il gruppo di Teams non ha le funzionalità di audioconferenza, vedere [Partecipare a una riunione in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

### <a name="let-anonymous-people-start-a-meeting"></a>Consenti alle persone anonime di avviare una riunione

Si tratta di un criterio per organizzatore che consente la chiamata in riunioni di conferenza. Questa impostazione controlla se la chiamata in utenti può partecipare alla riunione senza un utente autenticato dall'organizzazione in presenza. Il valore predefinito è false che indica che la chiamata in utenti attenderà nella sala di attesa fino a quando un utente autenticato dell'organizzazione non partecipa alla riunione. 

**Nota** Se falso e una chiamata in un utente si unisce prima alla riunione e viene inserita nella sala di attesa, un utente dell'organizzazione deve partecipare alla riunione con un client di teams per ammettere l'utente dalla sala di attesa. Non sono disponibili controlli della sala di attesa per gli utenti con accesso esterno. 


### <a name="automatically-admit-people"></a>Ammetti automaticamente le persone

Questo è un criterio per organizzatore. Questa impostazione controlla se gli utenti si uniscono direttamente a una riunione o restano in sala di attesa finché non vengono ammessi da un utente autenticato. Questa impostazione non si applica alla chiamata in utenti. 

![Screenshot che mostra una riunione con un utente in sala di attesa](media/meeting-policies-lobby.png)

 Gli organizzatori di riunioni possono fare clic **Opzioni riunione** nell'invito alla riunione per modificare questa impostazione per ogni riunione pianificata.
 
 **Nota** Nelle opzioni della riunione l'impostazione è denominata "chi può bypassare la sala d'attesa"
  
|Valore dell'impostazione  |Comportamento di partecipazione |
|---------|---------|
|**Tutti**   |Tutti i partecipanti accedono direttamente alla riunione senza passare dalla sala di attesa. Sono inclusi utenti autenticati, utenti esterni di organizzazioni attendibili (federati), Guest e utenti anonimi.     |
|**Tutti gli utenti dell'organizzazione e delle organizzazioni federate**     |Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest e gli utenti provenienti da organizzazioni attendibili, partecipano direttamente alla riunione senza attendere nella sala di attesa.  Gli utenti anonimi attendono nella sala di attesa.   |
|**Tutti gli utenti dell'organizzazione**    |Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest, accedono direttamente alla riunione senza passare dalla sala di attesa.  Gli utenti di organizzazioni attendibili e utenti anonimi attendono nella sala di attesa. Questa è l'impostazione predefinita.           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Consenti agli utenti che chiamano di ignorare la sala di attesa

Questo è un criterio per organizzatore. Questa impostazione consente di controllare se le persone che effettuano l'accesso tramite telefono si uniscono direttamente alla riunione oppure aspettano in sala d'attesa, indipendentemente dall'impostazione **Ammetti automaticamente le persone**. Il valore predefinito è False. Quando falso, gli utenti della chiamata in ingresso aspetteranno nella sala di attesa finché un utente dell'organizzazione non partecipa alla riunione con un client di teams e li ammette. Quando true, la chiamata in utenti si unirà automaticamente alla riunione quando un utente dell'organizzazione partecipa alla riunione. 

**Nota** Se una chiamata in un utente partecipa a una riunione prima che un utente dell'organizzazione partecipi alla riunione, verrà inserita nella sala di attesa fino a quando un utente dell'organizzazione non partecipa alla riunione usando un client di teams e li ammette. 


### <a name="enable-live-captions"></a>Abilita i sottotitoli in tempo reale

Questo è un criterio per utente e si applica durante una riunione. Questa impostazione controlla se, l'opzione **Abilita i sottotitoli in tempo reale** è disponibile nelle riunioni a cui l'utente partecipa, per l'attivazione e la disattivazione dei sottotitoli in tempo reale.  

![Screenshot che mostra l'opzione Abilita i sottotitoli in tempo reale](media/meeting-policies-live-captions.png)

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Disabilitato ma l'utente può eseguire l'override**     | I sottotitoli in tempo reale non sono attivati automaticamente per l'utente durante una riunione. L'utente vede l'opzione **Abilita i sottotitoli in tempo reale** nel menu di riversamento (**...**). Questa è l'impostazione predefinita. |
|**Disattiva**     | I sottotitoli in tempo reale sono disabilitati per l'utente durante le riunioni. L'utente non ha a disposizione l'opzione per attivarli.          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>Consenti l'uso della chat nelle riunioni 

Questo è un criterio per organizzatore. Questa impostazione determina se la chat della riunione è consentita nella riunione dell'utente.

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a>Impostazioni dei criteri riunione-modalità ruolo relatore designato

Questo è un criterio per utente. Questa impostazione consente di modificare il valore predefinito dell'utente **che può presentare** l'impostazione in **Opzioni riunione** nel client teams. Questa impostazione del criterio ha effetto su tutte le riunioni, incluse le riunioni di riunione ora.

**Chi può presentarsi?** l'impostazione consente agli organizzatori della riunione di scegliere chi può essere relatore in una riunione. Per altre informazioni, vedere [modificare le impostazioni dei partecipanti per una riunione di Team](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) e [ruoli in una riunione teams](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Al momento, è possibile usare PowerShell solo per configurare questa impostazione di criteri. È possibile modificare un criterio di riunione di team esistenti usando il cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . In alternativa, crea un nuovo criterio riunione teams usando il cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e assegnalo agli utenti.

Per specificare il valore predefinito dell'utente **che può presentare** l'impostazione in teams, imposta il parametro **DesignatedPresenterRoleMode** su una delle opzioni seguenti:

- **EveryoneUserOverride**: tutti i partecipanti alla riunione possono essere relatori. Questo è il valore predefinito. Questo parametro corrisponde all'impostazione **Everyone** in teams.
- **EveryoneInCompanyUserOverride**: gli utenti autenticati dell'organizzazione, inclusi gli utenti guest, possono essere relatori. Questo parametro corrisponde all'impostazione **utenti nell'organizzazione** in teams.
- **OrganizerOnlyUserOverride**: solo l'organizzatore della riunione può essere un relatore e tutti i partecipanti alla riunione sono designati come partecipanti. Questo parametro corrisponde all'impostazione **solo me** in teams.

Tieni presente che dopo aver impostato il valore predefinito, gli organizzatori della riunione possono comunque modificare questa impostazione in teams e scegliere chi può presentare nelle riunioni che pianificano.

## <a name="meeting-policy-settings---meeting-attendance-report"></a>Impostazioni dei criteri riunione-report presenza riunione

Questo è un criterio per utente. Questa impostazione controlla se gli organizzatori della riunione possono scaricare il [report presenza riunione](teams-analytics-and-reports/meeting-attendance-report.md).

Al momento, è possibile usare PowerShell solo per configurare questa impostazione di criteri. È possibile modificare un criterio di riunione di team esistenti usando il cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . In alternativa, crea un nuovo criterio riunione teams usando il cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e assegnalo agli utenti.

Per consentire a un organizzatore di una riunione di scaricare il report presenza riunione, imposta il parametro **AllowEngagementReport** su **Enabled**. Quando è abilitata, l'opzione per scaricare il report viene visualizzata nel riquadro **partecipanti** .

Per impedire a un organizzatore di una riunione di scaricare il report, imposta il parametro su **disabled**. Per impostazione predefinita, questa impostazione è disabilitata e l'opzione per scaricare il report non è disponibile.

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a>Impostazioni dei criteri riunione-provider riunione per la modalità Isole

Questo è un criterio per utente. Questa impostazione controlla il componente aggiuntivo riunione di Outlook usato per *gli utenti che si trovano in modalità isole*. Puoi specificare se gli utenti possono usare solo il componente aggiuntivo riunione teams o sia la riunione teams che i componenti aggiuntivi per le riunioni di Skype for business per pianificare le riunioni in Outlook.

Puoi applicare questo criterio solo agli utenti che si trovano in modalità isole e avere il parametro **AllowOutlookAddIn** impostato su **true** nei criteri della riunione teams.

Al momento, è possibile usare PowerShell solo per impostare questo criterio. È possibile modificare un criterio di riunione di team esistenti usando il cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . In alternativa, crea un nuovo criterio riunione teams usando il cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e assegnalo agli utenti.

Per specificare il componente aggiuntivo per la riunione che si desidera sia disponibile per gli utenti, impostare il parametro **PreferredMeetingProviderForIslandsMode** nel modo seguente:

- Imposta il parametro su **TeamsAndSfB** per abilitare sia il componente aggiuntivo riunioni teams che Skype for business in Outlook. Questo è il valore predefinito.
- Imposta il parametro su **TeamsOnly** per abilitare solo il componente aggiuntivo riunione teams in Outlook. Questa impostazione dei criteri garantisce che tutte le riunioni future abbiano un collegamento per la riunione di teams. Non esegue la migrazione dei collegamenti alle riunioni di Skype for business esistenti in teams. Questa impostazione dei criteri non influisce sulla presenza, la chat, le chiamate PSTN o altre funzionalità di Skype for business, quindi gli utenti continueranno a usare Skype for business per queste funzionalità.

  Se si imposta il parametro su **TeamsOnly**e quindi si torna a **TeamsAndSfB**, entrambi i componenti aggiuntivi riunione sono abilitati. Tuttavia, tieni presente che i collegamenti alle riunioni di join di teams esistenti non verranno migrati in Skype for business. Solo le riunioni di Skype for business programmate dopo la modifica avranno un collegamento a una riunione Skype for business.

## <a name="meeting-policy-settings---video-filters-mode"></a>Impostazioni dei criteri riunione-modalità filtri video

Questo è un criterio per utente. Questa impostazione controlla se gli utenti possono personalizzare lo sfondo del video in una riunione.

Al momento, è possibile usare PowerShell solo per impostare questo criterio. È possibile modificare un criterio di riunione di team esistenti usando il cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . In alternativa, crea un nuovo criterio riunione teams usando il cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e quindi assegna il criterio agli utenti.

Per specificare se gli utenti possono personalizzare lo sfondo del video in una riunione, imposta il parametro **VideoFiltersMode** nel modo seguente:

|Valore di impostazione in PowerShell |Comportamento  |
|---------|---------|
|**Nofilters**     |L'utente non può personalizzare lo sfondo del video.|
|**BlurOnly**     |L'utente ha la possibilità di sfocare lo sfondo del video. |
|**BlurandDefaultBackgrounds**     |L'utente ha la possibilità di sfocare lo sfondo del video o scegliere da un set di immagini da usare come sfondo. |
|**AllFilters**     |Use ha la possibilità di sfocare lo sfondo del video, scegliere da un set di immagini o caricare immagini personalizzate da usare come sfondo. |

> [!NOTE]
> Le immagini caricate dagli utenti non vengono visualizzate dai team. Quando si usa l'impostazione **AllFilters** , è necessario disporre di criteri di organizzazione interni per impedire agli utenti di caricare immagini offensive o inappropriate o immagini che l'organizzazione non ha diritto di usare per gli sfondi delle riunioni di teams.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare criteri agli utenti in teams](assign-policies.md)
