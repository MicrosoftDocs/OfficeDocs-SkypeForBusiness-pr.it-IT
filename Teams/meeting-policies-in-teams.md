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
- m365initiative-meetings
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
ms.openlocfilehash: 11f3a0f585a3fad2d2fbb653496a151bfd75160d
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030712"
---
# <a name="manage-meeting-policies-in-teams"></a>Gestire i criteri di riunione in Teams

::: zone target="docs"
I criteri riunione vengono usati per controllare le funzionalità disponibili per i partecipanti alle riunioni programmate dagli utenti nell'organizzazione. Puoi usare il criterio globale (predefinito per l'intera organizzazione) creato automaticamente o crea e assegna criteri personalizzati. Si possono gestire i criteri di riunione nell'interfaccia di amministrazione di Microsoft Teams o tramite [PowerShell](teams-powershell-overview.md).

> [!NOTE]
> Per informazioni sull'uso dei ruoli per gestire le autorizzazioni di relatori e partecipanti alla riunione, vedere [ruoli in una riunione di teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

È possibile implementare i criteri nei modi descritti di seguito. La scelta influisce sull'esperienza di riunione per gli utenti prima, durante o dopo una riunione.

|Tipo di implementazione  |Descrizione  |
|---------|---------|
|Per organizzatore    |Quando si implementa un criterio per organizzatore, tutti i partecipanti alla riunione ereditano il criterio dell'organizzatore. Ad esempio, **Ammetti automaticamente le persone** è un criterio per organizzatore e controlla se gli utenti accedono direttamente alla riunione oppure attendono nella sala di attesa per le riunioni pianificate dall'utente a cui è assegnato il criterio.          |
|Per utente    |Quando si implementano criteri per utente, viene applicato solo il criterio per utente per limitare l'uso di determinate funzionalità da parte dell'organizzatore e/o dei partecipanti alla riunione. Ad esempio, **Consenti l'uso di Riunione immediata nei canali** è un criterio per utente.     |
|Per organizzatore e per utente     |Quando si implementa una combinazione di criteri per organizzatore e per utente, l'uso di alcune funzionalità da parte dei partecipanti alla riunione è limitato, in base ai criteri applicati al singolo utente e ai criteri dell'organizzatore. Ad esempio, **Consenti registrazione cloud** è un criterio per organizzazione e per utente. Attivare questa impostazione per consentire all'organizzatore della riunione e ai partecipanti di avviare o interrompere una registrazione.

È possibile modificare le impostazioni dei criteri globali oppure creare e assegnare uno o più criteri personalizzati. Gli utenti otterranno i criteri globali a meno che non si creino e si assegnano criteri personalizzati.

> [!NOTE]
> Il pulsante Dettagli riunione sarà disponibile se l'utente ha abilitato le licenze per le conferenze audio o se l'utente è autorizzato a ricevere servizi di audioconferenza, in caso contrario, i dettagli della riunione non saranno disponibili.

## <a name="create-a-custom-meeting-policy"></a>Creare un criterio di riunione personalizzato

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio. Il nome non può contenere caratteri speciali o più di 64 caratteri.
4. Scegliere le impostazioni desiderate.
5. Fare clic su **Salva**.

Ad esempio, si supponga di avere un gruppo di utenti e di voler limitare la larghezza di banda necessaria per la riunione. È possibile creare un nuovo criterio personalizzato denominato "Larghezza di banda limitata" e disabilitare le impostazioni seguenti:

In **Audio e video** :

- Disattivare Consenti registrazione cloud.
- Disattivare Consenti video IP.

In **Condivisione di contenuti** :

- Disabilitare la modalità di condivisione dello schermo.
- Disattivare Consenti la lavagna.
- Disattivare Consenti note condivise.

Assegnare poi il criterio agli utenti.

## <a name="edit-a-meeting-policy"></a>Modificare i criteri di una riunione

È possibile modificare i criteri globali e i criteri personalizzati creati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Da qui apportare le modifiche desiderate.
4. Fare clic su **Salva**.

> [!NOTE]
> A ogni utente può essere assegnato un solo criterio di riunione per volta.

## <a name="assign-a-meeting-policy-to-users"></a>Assegnare un criterio riunione agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

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

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se un utente può avviare una riunione ad hoc in un canale di Teams. Se si attiva questa opzione, gli utenti possono fare clic sul pulsante **incontra** per avviare una riunione ad hoc o pianificare una riunione nel canale. Il valore predefinito è True.

[![Screenshot che mostra l'icona incontra ora sotto un messaggio ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

### <a name="allow-the-outlook-add-in"></a>Consenti il componente aggiuntivo per Outlook

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione consente di controllare se è possibile pianificare riunioni di Teams dall'interno di Outlook (Windows, Mac, Web e Mobile).

![Screenshot che mostra la possibilità di pianificare una nuova riunione](media/meeting-policies-outlook-add-in.png)

Se si disattiva questa impostazione, gli utenti non potranno pianificare riunioni di Teams durante la creazione di una nuova riunione in Outlook. In Outlook per Windows, ad esempio, l'opzione **Nuova riunione di Teams** non comparirà sulla barra multifunzione.

### <a name="allow-channel-meeting-scheduling"></a>Consenti la pianificazione delle riunioni di canale

Usare i criteri di AllowChannelMeetingScheduling esistenti per controllare i tipi di eventi che è possibile creare nei calendari del canale del team. Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se gli utenti possono pianificare una riunione in un canale di Teams. Per impostazione predefinita, questa impostazione è attivata. 

Se questo criterio è disattivato, gli utenti non saranno in grado di creare nuove riunioni di canale. Tuttavia, le riunioni di canale esistenti possono essere modificate dall'organizzatore dell'evento.

Pianificare una riunione verrà disabilitata.

![Screenshot che mostra l'opzione Pianifica una riunione in Teams](media/schedule-meeting-option.png)

La selezione del canale è disabilitata.

[![Screenshot che mostra l'opzione calendario per la selezione di un canale in cui si vuole pianificare una riunione. ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

Nella pagina post di canale, la seguente verrà disabilitata:

- **Pianificare un pulsante riunione** nella casella di composizione canale Rispondi.
  ![Screenshot che mostra l'opzione calendario per la selezione di un canale in cui si vuole pianificare una riunione.](media/schedule-meeting-disabled-in-chat2.png)
  
- **Pianificare un pulsante riunione** nell'intestazione del canale.
  ![Screenshot che mostra l'opzione calendario per la selezione di un canale in cui si vuole pianificare una riunione.](media/schedule-now-in-header.png)

Nel calendario del canale:

- Il pulsante **Aggiungi nuovo evento** nell'intestazione del calendario del canale verrà disabilitato.
  ![Screenshot che mostra l'opzione calendario per la selezione di un canale in cui si vuole pianificare una riunione.](media/add-new-event-disabled.png)

- Gli utenti non potranno trascinare e selezionare un blocco di tempo nel calendario del canale per creare una riunione del canale.

- Gli utenti non possono usare le scelte rapide da tastiera per creare una riunione nel calendario del canale.

Nell'interfaccia di amministrazione:

L'app calendario canali verrà visualizzata nella sezione app **Microsoft** nella pagina Criteri di autorizzazione dell'app.

![Screenshot che mostra i criteri delle autorizzazioni dell'app nell'interfaccia di amministrazione di teams.](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a>Consenti la pianificazione di riunioni private

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se gli utenti possono pianificare riunioni private in Teams. Una riunione è privata quando non viene pubblicata in un canale in un team.

Si noti che, disattivando **Consenti la pianificazione di riunioni private** e **Consenti la pianificazione delle riunioni di canale** , le opzioni **Aggiungi partecipanti obbligatori** e **Aggiungi canale** vengono disabilitate per gli utenti in Teams. Per impostazione predefinita, questa impostazione è attivata.

### <a name="allow-meet-now-in-private-meetings"></a>Consenti l'uso di Riunione immediata nelle riunioni private

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se un utente può avviare una riunione privata ad hoc.  Per impostazione predefinita, questa impostazione è attivata.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Impostazioni dei criteri di riunione - Audio e video

- [Consenti la trascrizione](#allow-transcription)
- [Consenti registrazione cloud](#allow-cloud-recording)
- [Modalità per l'audio IP](#mode-for-ip-audio) 
- [Modalità per il video IP](#mode-for-ip-video) 
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
|Daniela | Globale   | Disattivare |
|Amanda | CriterioRiunionePosizione1 | Nella|
|Luca (utente esterno) | Non applicabile | Non applicabile|

Non è possibile registrare le riunioni organizzate da Daniela e Amanda che ha l'impostazione del criterio attivata, non può registrare le riunioni organizzate da Daniela. Le riunioni organizzate da Amanda possono essere registrate, tuttavia Daniela, che ha l'impostazione del criterio disabilitata, e John, che è un utente esterno, non possono registrare le riunioni organizzate da Amanda.

Per altre informazioni sulla registrazione di una riunione cloud, vedere [Registrazione delle riunioni cloud di Teams](cloud-recording.md).

### <a name="mode-for-ip-audio"></a>Modalità per l'audio IP

Questo è un criterio per utente. Questa impostazione controlla se l'audio può essere attivato in riunioni e chiamate di gruppo. Ecco i valori per questa impostazione.

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Audio in uscita e in ingresso abilitato**    |La riunione è consentita per l'audio in uscita e in ingresso. Questa è l'impostazione predefinita. |
|**Disattiva**     |L'audio in uscita e in entrata è disattivato durante la riunione.     |

Se impostato su **disabilitato** per un utente, l'utente può comunque pianificare e organizzare le riunioni ma non può usare l'audio. Per partecipare a una riunione, è necessario effettuare l'accesso tramite la rete PSTN (Public Switched Telephone Network) o avere la chiamata di riunione e partecipare tramite telefono. I partecipanti alla riunione che non hanno un criterio assegnato, ad esempio i partecipanti anonimi, hanno questo set per l' **audio in uscita e in entrata abilitato** per impostazione predefinita. Nei client di teams mobile, se questa impostazione è disabilitata, l'utente deve connettersi alla riunione tramite la rete PSTN.

Questa impostazione non si applica alle chiamate 1:1. Per limitare le chiamate di 1:1, configurare un [criterio di chiamata](teams-calling-policy.md) per i team e disattivare l'impostazione imposta **chiamate private** . Questa impostazione non si applica anche ai dispositivi della sala riunioni, ad esempio i dispositivi Surface Hub e Microsoft teams rooms.

Questa impostazione non è ancora disponibile per gli ambienti Microsoft 365 Government community Cloud (GCC), GCC High o Department of Defense (DoD).

Per altre informazioni, vedere [gestire l'audio/video per i partecipanti alla riunione](#manage-audiovideo-for-meeting-participants).

### <a name="mode-for-ip-video"></a>Modalità per il video IP

Questo è un criterio per utente. Questa impostazione controlla se il video può essere attivato in riunioni e chiamate di gruppo. Ecco i valori per questa impostazione.

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Video in uscita e in arrivo abilitato**    | La riunione è consentita per il video in uscita e in arrivo. Questa è l'impostazione predefinita. |
|**Disattiva**     | Il video in uscita e in arrivo è disattivato durante la riunione. Nei client di teams mobile gli utenti non possono condividere video o foto nella riunione. <br><br>Tieni presente che se la **modalità per l'audio IP** è disabilitata, anche **la modalità per il video IP** rimarrà disabilitata.  |

Se impostato su **disabled** per un utente, l'utente non può attivare video o visualizzare i video condivisi da altri partecipanti alla riunione. I partecipanti alla riunione che non hanno un criterio assegnato, ad esempio i partecipanti anonimi, hanno questo set per il **video in uscita e in arrivo abilitato** per impostazione predefinita.

Questa impostazione non si applica ai dispositivi della sala riunioni, ad esempio i dispositivi Surface Hub e Microsoft teams rooms. 

Questa impostazione non è ancora disponibile per gli ambienti Microsoft 365 Government community Cloud (GCC), GCC High o Department of Defense (DoD).

> [!NOTE]
> Tieni presente che questa impostazione controlla il video in uscita e in arrivo mentre l'impostazione **Consenti video IP consente** di controllare il video in uscita. Per altre informazioni, vedere [quali impostazioni dei criteri video IP hanno la precedenza?](#which-ip-video-policy-setting-takes-precedence) e [gestire audio/video per i partecipanti alla riunione](#manage-audiovideo-for-meeting-participants).

Per altre informazioni, vedere [gestire l'audio/video per i partecipanti alla riunione](#manage-audiovideo-for-meeting-participants).

### <a name="allow-ip-video"></a>Consenti video IP

Questa è una combinazione di criterio per organizzatore e criterio per utente. Il video è un componente chiave per le riunioni. In alcune organizzazioni gli amministratori potrebbero volere un maggiore controllo sulle riunioni degli utenti che hanno un video. Questa impostazione controlla se il video può essere attivato nelle riunioni ospitate da un utente e in 1:1 e raggruppa le chiamate avviate da un utente. Nei client di teams mobile questa impostazione controlla se gli utenti possono condividere foto e video in una riunione. 

Riunioni organizzate da un utente con questa impostazione di criterio abilitata, Consenti la condivisione di video nella riunione da parte dei partecipanti alla riunione, se i partecipanti hanno anche l'impostazione del criterio abilitata. I partecipanti alla riunione a cui non sono assegnati criteri, ad esempio i partecipanti anonimi e federati, ereditano i criteri dell'organizzatore della riunione.

> [!NOTE]
> Tieni presente che questa impostazione controlla il video in uscita mentre la **modalità per** l'impostazione del video IP controlla sia il video in uscita che in arrivo. Per altre informazioni, vedere [quali impostazioni dei criteri video IP hanno la precedenza?](#which-ip-video-policy-setting-takes-precedence) e [gestire audio/video per i partecipanti alla riunione](#manage-audiovideo-for-meeting-participants).

| Client desktop e Web Teams |Client per dispositivi mobili Teams  |
|:-------:|:-------:|
|![Screenshot che mostra la partecipazione alle riunioni con le impostazioni audio/video sul desktop](media/meeting-policies-audio-video-settings.png)    |![Screenshot che mostra la partecipazione a una riunione con le impostazioni audio/video in un dispositivo mobile](media/meeting-policies-mobile-join.png)          |

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consentire video IP |
|---------|---------|---------|
|Daniela   | Globale   | Nella       |
|Amanda    | CriterioRiunionePosizione1        | Disattivare      |

Le riunioni ospitate da Daniela consentono di attivare il video. Daniela può partecipare alla riunione e attivare il video. Amanda non può attivare il video nella riunione di Daniela perché la politica di Amanda è impostata su non consentire il video. Amanda può vedere i video condivisi da altri partecipanti alla riunione.

Nelle riunioni ospitate da Amanda nessuno può attivare il video, indipendentemente dai criteri video assegnati. Questo significa che Daniela non può attivare il video nelle riunioni di Amanda.  

Se Daniela chiama Amanda con il video, Amanda può rispondere alla chiamata solo con l'audio.  Quando la chiamata è connessa, Amanda può vedere il video di Daniela, ma non può attivare il video. Se Amanda chiama Daniela, Daniela può rispondere alla chiamata con il video e l'audio. Una volta connessa la chiamata, Daniela può attivare o disattivare suo video come desidera.

Per altre informazioni, vedere [gestire l'audio/video per i partecipanti alla riunione](#manage-audiovideo-for-meeting-participants).

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>Quale impostazione del criterio video IP ha la precedenza?

Per un utente, l'impostazione del criterio più restrittiva per il video ha la precedenza. Ecco alcuni esempi.

|Consentire video IP|Modalità per il video IP|Esperienza di riunione|
|---------|---------|---------|
|Organizer **: attivato**<br><br>Partecipante: **attivato** |Partecipante: **disabilitato**        |La **modalità per** l'impostazione del video IP ha la precedenza. Il partecipante a cui è assegnato questo criterio non può attivare o visualizzare i video condivisi da altri.|
|Organizer **: attivato**<br><br>Partecipante: **attivato** |Partecipante: **video in uscita e in arrivo abilitato**          |Il partecipante a cui è assegnato questo criterio può attivare o visualizzare i video condivisi da altri.         |
|Organizer **: attivato**<br><br>Partecipante: **disattivato** |Partecipante: **video in uscita e in arrivo abilitato**         |Prevale l'impostazione **Consenti video IP** . I partecipanti possono vedere solo video in arrivo e non possono inviare video in uscita.         |
|Organizer **: attivato**<br><br>Partecipante: **disattivato** |Partecipante: **disabilitato**         |La **modalità per** l'impostazione del video IP ha la precedenza. Il partecipante non può visualizzare il video in arrivo o in uscita.|
|Organizer: **disattivato**    |       |L'impostazione **Consenti video IP** ha la precedenza perché è disattivata per l'organizzatore. Nessuno può attivare il video nelle riunioni organizzate dall'utente a cui è stato assegnato questo criterio.         |

### <a name="manage-audiovideo-for-meeting-participants"></a>Gestire audio/video per i partecipanti alla riunione

|Se vuoi...  |Impostare le impostazioni dei criteri seguenti  |
|---------|---------|
|Disabilitare l'audio e il video per i partecipanti alle riunioni  |Modalità per l'audio IP: **disabilitato**<br> Modalità per IP video: **disabilitato**<br>Consenti video IP: N/d       |
|Abilitare solo video e audio in entrata per i partecipanti alle riunioni  |Modalità per l'audio IP: **audio in uscita e in ingresso abilitato**<br> Modalità per IP video: **video in uscita e in arrivo abilitato**<br>Consenti video IP: **disattivato**       |
|Disabilitare il video per i partecipanti alle riunioni (i partecipanti hanno solo audio)|  Modalità per l'audio IP: **abilitare l'audio in uscita e in ingresso**<br> Modalità per IP video: **disabilitato**<br>Consenti video IP: N/d        
|Abilitare l'audio e il video per i partecipanti alle riunioni    |Modalità per l'audio IP: abilitato per l' **audio in uscita e in ingresso** (impostazione predefinita)<br> Modalità per IP video: **video in uscita e in arrivo abilitato** (impostazione predefinita)<br>Consenti video **IP: attivato** (impostazione predefinita)    |

Si applicano i criteri più restrittivi tra i criteri dell'organizzatore della riunione e i criteri dell'utente. Ad esempio, se un organizzatore ha un criterio che limita il video e i criteri di un utente non limitano il video, i partecipanti alla riunione ereditano i criteri dell'organizzatore della riunione e non hanno accesso al video nelle riunioni. Questo significa che possono partecipare alla riunione solo con l'audio.

> [!NOTE]
> Quando un utente avvia una chiamata di gruppo a partecipare tramite telefono, il **telefono usa per** la schermata audio non viene visualizzato. Si tratta di un problema noto che stiamo lavorando per risolvere. Per risolvere il problema, selezionare **audio telefono** in **altre opzioni di join**.  

#### <a name="teams-mobile-clients"></a>Client per dispositivi mobili Teams

Per gli utenti dei client di teams mobile, la possibilità di condividere foto e video durante una riunione è determinata anche dall'impostazione **Consenti video IP** o **IP video** . A seconda dell'impostazione del criterio ha la precedenza, la possibilità di condividere video e foto non sarà disponibile. Questa operazione non ha effetto sulla condivisione dello schermo, che viene configurata usando un'impostazione separata della [modalità di condivisione dello schermo](#screen-sharing-mode) . Inoltre, puoi impostare un [criterio di mobilità di teams](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) per impedire agli utenti di dispositivi mobili di usare il video IP tramite una connessione cellulare, il che significa che devono usare una connessione WiFi.

### <a name="media-bit-rate-kbs"></a>Velocità in bit media (KBS)

Questo è un criterio per utente. Questa impostazione determina la velocità in bit per le trasmissioni audio, video e di condivisione di app basate su video nelle chiamate e riunioni dell'utente. Si applica ai flussi multimediali in uplink o downlink per gli utenti nella chiamata o riunione. Questa impostazione consente di controllare in modo granulare la gestione della larghezza di banda dell'organizzazione. In base agli scenari di riunione necessari per gli utenti, è necessario disporre di una larghezza di banda sufficiente per fornire un'esperienza di buona qualità. Il valore minimo è 30 Kbps e il valore massimo dipende dallo scenario della riunione. Per altre informazioni sulla larghezza di banda minima consigliata per una buona qualità di riunioni, chiamate ed eventi live in Teams, vedere [Requisiti di larghezza di banda](prepare-network.md#bandwidth-requirements).

Se non è disponibile una larghezza di banda sufficiente per una riunione, i partecipanti vedranno un messaggio che indica una qualità di rete scadente.

Per le riunioni che necessitano di un'esperienza video di qualità superiore, ad esempio riunioni di CEO e teams Live Events, è consigliabile impostare la larghezza di banda su 10 Mbps. Anche quando viene impostata l'esperienza massima, lo stack multimediale di teams si adatta alle condizioni di larghezza di banda ridotta quando vengono rilevate determinate condizioni di rete, a seconda dello scenario.

## <a name="meeting-policy-settings---content-sharing"></a>Impostazioni dei criteri di riunione - Condivisione di contenuti

- [Modalità condivisione schermo](#screen-sharing-mode)
- [Consenti a un partecipante di fornire o richiedere il controllo](#allow-a-participant-to-give-or-request-control)
- [Consenti a un partecipante esterno di fornire o richiedere il controllo](#allow-an-external-participant-to-give-or-request-control)
- [Consenti la condivisione di PowerPoint](#allow-powerpoint-sharing)
- [Consenti la lavagna](#allow-whiteboard)
- [Consenti note condivise](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>Modalità condivisione schermo

Questa è una combinazione di criterio per organizzatore e criterio per utente. Questa impostazione determina se la condivisione del desktop o della finestra è consentita nella riunione dell'utente. I partecipanti alla riunione a cui non sono assegnati criteri, ad esempio i partecipanti anonimi, guest, B2B e federati, ereditano i criteri dell'organizzatore della riunione.

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Schermo intero**    | La condivisione desktop completo e la condivisione delle applicazioni sono consentite nella riunione |
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
|Daniela   | Globale   | Nella       |
|Pio    | CriterioRiunionePosizione1        | Disattivare   |

Daniela può assegnare il controllo del desktop o della finestra condivisa ad altri partecipanti a una riunione organizzata da Pio, mentre Pio non può concedere il controllo ad altri partecipanti.

Per usare PowerShell per controllare gli utenti autorizzati a concedere il controllo o accettare richieste di controllo, usare il cmdlet AllowParticipantGiveRequestControl.

> [!NOTE]
> Per concedere e assumere il controllo del contenuto condiviso durante la condivisione, entrambe le parti devono usare il client desktop di Teams. Il controllo non è supportato se una delle parti esegue Teams in un browser. Ciò è dovuto a una limitazione tecnica che si prevede di risolvere.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Consenti a un partecipante esterno di fornire o richiedere il controllo

Questo è un criterio per utente. Indipendentemente dal modo in cui l'organizzatore della riunione ha impostato, l'organizzazione ha impostato questo set per un utente non controlla quali partecipanti esterni possono eseguire. Questo parametro controlla se i partecipanti esterni possono avere il controllo o richiedere il controllo dello schermo del condivisore, a seconda di quello che il condivisore ha impostato nei criteri della riunione dell'organizzazione. I partecipanti esterni nelle riunioni di Teams possono essere classificati come segue:  

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
|Daniela   | Globale   | Nella       |
|Amanda   | CriterioRiunionePosizione1        | Disattivare   |

Amanda non può condividere le presentazioni di PowerPoint nelle riunioni, anche se è l'organizzatrice della riunione. Daniela può condividere le presentazioni di PowerPoint anche se la riunione è organizzata da Amanda. Amanda può visualizzare le presentazioni di PowerPoint condivise da altri nella riunione, anche se non può condividere presentazioni di PowerPoint.

### <a name="allow-whiteboard"></a>Consenti la lavagna

Questo è un criterio per utente. Questa impostazione controlla se un utente può condividere la lavagna in una riunione. Gli utenti esterni, inclusi gli utenti anonimi, B2B e federati, ereditano i criteri dell'organizzatore della riunione.

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti la lavagna|
|---------|---------|---------|
|Daniela   | Globale   | Nella       |
|Amanda   | CriterioRiunionePosizione1        | Disattivare   |

Amanda non può condividere la lavagna in una riunione, anche se è l'organizzatrice della riunione. Daniela può condividere la lavagna anche se una riunione è organizzata da Amanda.  

### <a name="allow-shared-notes"></a>Consenti note condivise

Questo è un criterio per utente. Questa impostazione controlla se un utente può creare e condividere note in una riunione. Gli utenti esterni, inclusi gli utenti anonimi, B2B e federati, ereditano i criteri dell'organizzatore della riunione. La scheda **Note riunione** è attualmente supportata solo nelle riunioni con meno di 20 partecipanti.

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti note condivise |
|---------|---------|---------|
|Daniela   | Globale   | Nella       |
|Amanda   | CriterioRiunionePosizione1 | Disattivare |

Daniela può creare note nelle riunioni di Amanda, mentre Amanda non può creare note in alcuna riunione.

## <a name="meeting-policy-settings---participants--guests"></a>Impostazioni dei criteri di riunione - Partecipanti e ospiti

Queste impostazioni controllano i partecipanti che devono aspettare nella sala di attesa prima di essere ammessi alla riunione e il livello di partecipazione consentito in una riunione.

- [Consenti alle persone anonime di avviare una riunione](#let-anonymous-people-start-a-meeting)
- [Ammetti automaticamente le persone](#automatically-admit-people)
- [Consenti agli utenti che chiamano di ignorare la sala di attesa](#allow-dial-in-users-to-bypass-the-lobby)
- [Abilita i sottotitoli in tempo reale](#enable-live-captions)
- [Consentire la chat in riunioni](#allow-chat-in-meetings)

> [!NOTE]
>Le opzioni per partecipare a una riunione variano in base alle impostazioni di ogni gruppo di Teams e al metodo di connessione. Se il gruppo dispone di servizi di audioconferenza e lo usa per la connessione [, vedere audioconferenza](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365). Se il gruppo teams non dispone di servizi di audioconferenza, vedere [partecipare a una riunione in teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

### <a name="let-anonymous-people-start-a-meeting"></a>Consenti alle persone anonime di avviare una riunione

Si tratta di un criterio per organizzatore che consente le riunioni di conferenza telefonica con accesso esterno di primo livello. Questa impostazione controlla se gli utenti con accesso esterno possono partecipare alla riunione senza un utente autenticato dall'organizzazione in presenza. Per impostazione predefinita, questa impostazione è disattivata, che indica che gli utenti con accesso esterno aspetteranno nella sala di attesa fino a quando un utente autenticato dell'organizzazione non si unisce alla riunione.

> [!NOTE]
> Se questa impostazione è disattivata e un utente con accesso esterno si unisce prima alla riunione e viene inserito nella sala di attesa, un utente dell'organizzazione deve partecipare alla riunione con un client di teams per ammettere l'utente dalla sala di attesa. Non sono disponibili controlli della sala di attesa per gli utenti con accesso esterno.

### <a name="automatically-admit-people"></a>Ammetti automaticamente le persone

Questo è un criterio per organizzatore. Questa impostazione controlla se gli utenti si uniscono direttamente a una riunione o restano in sala di attesa finché non vengono ammessi da un utente autenticato. Questa impostazione non è applicabile agli utenti con accesso esterno.

![Screenshot che mostra una riunione con un utente in sala di attesa](media/meeting-policies-lobby.png)

 Gli organizzatori di riunioni possono fare clic **Opzioni riunione** nell'invito alla riunione per modificare questa impostazione per ogni riunione pianificata.

> [!NOTE]
> Nelle opzioni della riunione l'impostazione è denominata "chi può bypassare la sala d'attesa". Se si modifica l'impostazione predefinita per qualsiasi utente, questa verrà applicata a tutte le nuove riunioni organizzate dall'utente e a tutte le riunioni precedenti in cui l'utente non ha modificato le opzioni di riunione.
  
|Valore dell'impostazione  |Comportamento di partecipazione |
|---------|---------|
|**Tutti**   |Tutti i partecipanti accedono direttamente alla riunione senza passare dalla sala di attesa. Sono inclusi utenti autenticati, utenti esterni di organizzazioni attendibili (federati), Guest e utenti anonimi.     |
|**Tutti gli utenti dell'organizzazione e delle organizzazioni federate**     |Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest e gli utenti provenienti da organizzazioni attendibili, partecipano direttamente alla riunione senza attendere nella sala di attesa.  Gli utenti anonimi attendono nella sala di attesa.   |
|**Tutti gli utenti dell'organizzazione**    |Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest, accedono direttamente alla riunione senza passare dalla sala di attesa.  Gli utenti di organizzazioni attendibili e utenti anonimi attendono nella sala di attesa. Questa è l'impostazione predefinita.           |
|**Solo organizzatore**    |Solo gli organizzatori della riunione possono partecipare alla riunione direttamente senza attendere nella sala di attesa. Tutti gli altri utenti, inclusi quelli autenticati all'interno dell'organizzazione, gli utenti guest, gli utenti di organizzazioni attendibili e gli utenti anonimi devono attendere nella sala di attesa.           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Consenti agli utenti che chiamano di ignorare la sala di attesa

Questo è un criterio per organizzatore. Questa impostazione consente di controllare se le persone che effettuano l'accesso tramite telefono si uniscono direttamente alla riunione oppure aspettano in sala d'attesa, indipendentemente dall'impostazione **Ammetti automaticamente le persone**. Per impostazione predefinita, questa impostazione è disattivata. Quando questa impostazione è disattivata, gli utenti con accesso esterno aspetteranno nella sala di attesa fino a quando un utente dell'organizzazione non partecipa alla riunione con un client teams e li ammette. Quando questa impostazione è attivata, gli utenti con accesso esterno si uniranno automaticamente alla riunione quando un utente dell'organizzazione partecipa alla riunione.

> [!NOTE]
> Se un utente con accesso esterno entra in una riunione prima che un utente dell'organizzazione partecipi alla riunione, verrà inserito nella sala di attesa fino a quando un utente dell'organizzazione non partecipa alla riunione usando un client di teams e li ammette. Se si modifica l'impostazione predefinita per qualsiasi utente, questa verrà applicata a tutte le nuove riunioni organizzate dall'utente e a tutte le riunioni precedenti in cui l'utente non ha modificato le opzioni di riunione.

### <a name="enable-live-captions"></a>Abilita i sottotitoli in tempo reale

Questo è un criterio per utente e si applica durante una riunione. Questa impostazione controlla se, l'opzione **Abilita i sottotitoli in tempo reale** è disponibile nelle riunioni a cui l'utente partecipa, per l'attivazione e la disattivazione dei sottotitoli in tempo reale.  

![Screenshot che mostra l'opzione Abilita i sottotitoli in tempo reale](media/meeting-policies-live-captions.png)

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Disabilitato ma l'utente può eseguire l'override**     | I sottotitoli in tempo reale non sono attivati automaticamente per l'utente durante una riunione. L'utente vede l'opzione **Abilita i sottotitoli in tempo reale** nel menu di riversamento ( **...** ). Questa è l'impostazione predefinita. |
|**Disattiva**     | I sottotitoli in tempo reale sono disabilitati per l'utente durante le riunioni. L'utente non ha a disposizione l'opzione per attivarli.          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>Consenti l'uso della chat nelle riunioni 

Si tratta di un'impostazione per partecipante. Questa impostazione determina se la chat della riunione è consentita nella riunione dell'utente.

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a>Impostazioni dei criteri riunione-modalità ruolo relatore designato

Questo è un criterio per utente. Questa impostazione consente di modificare il valore predefinito dell'utente **che può presentare** l'impostazione in **Opzioni riunione** nel client teams. Questa impostazione del criterio ha effetto su tutte le riunioni, incluse le riunioni di riunione ora.

**Chi può presentarsi?** l'impostazione consente agli organizzatori della riunione di scegliere chi può essere relatore in una riunione. Per altre informazioni, vedere [modificare le impostazioni dei partecipanti per una riunione di Team](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) e [ruoli in una riunione teams](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Al momento, è possibile usare PowerShell solo per configurare questa impostazione di criteri. È possibile modificare un criterio di riunione di team esistenti usando il cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . In alternativa, crea un nuovo criterio riunione teams usando il cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e assegnalo agli utenti.

Per specificare il valore predefinito dell'utente **che può presentare** l'impostazione in teams, imposta il parametro **DesignatedPresenterRoleMode** su una delle opzioni seguenti:

- **EveryoneUserOverride** : tutti i partecipanti alla riunione possono essere relatori. Questo è il valore predefinito. Questo parametro corrisponde all'impostazione **Everyone** in teams.
- **EveryoneInCompanyUserOverride** : gli utenti autenticati dell'organizzazione, inclusi gli utenti guest, possono essere relatori. Questo parametro corrisponde all'impostazione **utenti nell'organizzazione** in teams.
- **OrganizerOnlyUserOverride** : solo l'organizzatore della riunione può essere un relatore e tutti i partecipanti alla riunione sono designati come partecipanti. Questo parametro corrisponde all'impostazione **solo me** in teams.

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
- Imposta il parametro su **Teams** per abilitare solo il componente aggiuntivo riunione teams in Outlook. Questa impostazione dei criteri garantisce che tutte le riunioni future abbiano un collegamento per la riunione di teams. Non esegue la migrazione dei collegamenti alle riunioni di Skype for business esistenti in teams. Questa impostazione dei criteri non influisce sulla presenza, la chat, le chiamate PSTN o altre funzionalità di Skype for business, quindi gli utenti continueranno a usare Skype for business per queste funzionalità.

  Se si imposta il parametro su **Teams** e quindi si torna a **TeamsAndSfB** , entrambi i componenti aggiuntivi per le riunioni sono abilitati. Tuttavia, tieni presente che i collegamenti alle riunioni di join di teams esistenti non verranno migrati in Skype for business. Solo le riunioni di Skype for business programmate dopo la modifica avranno un collegamento a una riunione Skype for business.

## <a name="meeting-policy-settings---video-filters-mode"></a>Impostazioni dei criteri riunione-modalità filtri video

Questo è un criterio per utente. Questa impostazione controlla se gli utenti possono personalizzare lo sfondo del video in una riunione.

Al momento, è possibile usare PowerShell solo per impostare questo criterio. È possibile modificare un criterio di riunione di team esistenti usando il cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . In alternativa, crea un nuovo criterio riunione teams usando il cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e quindi assegna il criterio agli utenti.

Per specificare se gli utenti possono personalizzare lo sfondo del video in una riunione, imposta il parametro **VideoFiltersMode** nel modo seguente:

|Valore di impostazione in PowerShell |Comportamento  |
|---------|---------|
|**Nofilters**     |L'utente non può personalizzare lo sfondo del video.|
|**BlurOnly**     |L'utente ha la possibilità di sfocare lo sfondo del video. |
|**BlurandDefaultBackgrounds**     |L'utente ha la possibilità di sfocare lo sfondo del video o scegliere il set predefinito di immagini da usare come sfondo. |
|**AllFilters**     |Use ha la possibilità di sfocare lo sfondo del video, scegliere dal set di immagini predefinito o caricare immagini personalizzate da usare come sfondo. |

> [!NOTE]
> Le immagini caricate dagli utenti non vengono visualizzate dai team. Quando si usa l'impostazione **AllFilters** , è necessario disporre di criteri di organizzazione interni per impedire agli utenti di caricare immagini offensive o inappropriate o immagini che l'organizzazione non ha diritto di usare per gli sfondi delle riunioni di teams.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare criteri agli utenti in teams](assign-policies.md)
- [Rimuovere i criteri di riunione di RestrictedAnonymousAccess teams dagli utenti](meeting-policies-restricted-anonymous-access.md)
