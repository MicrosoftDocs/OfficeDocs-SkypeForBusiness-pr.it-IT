---
title: Usare i dati di telemetria in tempo reale per risolvere problemi di scarsa qualità delle riunioni
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Usare la telemetria in tempo reale con dettagli su dispositivi, reti e connettività per risolvere i problemi degli utenti con le riunioni pianificate di Microsoft Teams.
ms.openlocfilehash: 26ee7b809d7b18bb07a7f8ae57852c2333b26d94
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789621"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Usare i dati di telemetria in tempo reale per risolvere problemi di scarsa qualità delle riunioni

Questo articolo spiega come usare Real-Time Analytics (RTA) per risolvere problemi di scarsa qualità delle riunioni di Microsoft Teams per i singoli utenti. È possibile accedere a Real-Time Analytics se si ha uno dei ruoli seguenti:

- Amministratore di Teams
- Specialista del supporto tecnico per le comunicazioni di Teams
- Tecnico supporto comunicazioni Teams

Per altre informazioni sui ruoli di amministratore di Teams, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](/MicrosoftTeams/using-admin-roles).

Real-Time Analytics consente agli amministratori IT di esaminare le riunioni pianificate degli utenti importanti e vedere i problemi audio, video, di condivisione di contenuti e relativi alla rete. Gli amministratori possono usare questa telemetria per analizzare questi problemi durante le riunioni e risolvere i problemi in tempo reale.

## <a name="what-is-real-time-analytics"></a>Che cos'è Real-Time Analytics?

Oggi, la risoluzione dei problemi delle singole riunioni è disponibile per gli amministratori di Teams tramite [Call Analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) al termine della riunione. Real-Time Analytics consente agli amministratori di risolvere i problemi relativi alle riunioni pianificate mentre sono in corso.

Real-Time Analytics mostra informazioni dettagliate sulle riunioni di Teams per ogni utente nel tuo account Office 365, aggiornato in tempo reale. Include informazioni su dispositivi, rete, connettività, audio, video e problemi di condivisione dei contenuti, che aiuteranno gli amministratori a risolvere i problemi relativi alla qualità delle chiamate in modo più efficace.

Gli amministratori di Teams hanno accesso completo a tutti i dati di telemetria in tempo reale per ogni utente. È anche possibile assegnare ruoli di Azure Active Directory al supporto del personale. Per altre informazioni su questi ruoli, vedere [Concedere l'autorizzazione al supporto e al personale dell'help desk](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Dove trovare la telemetria per la risoluzione dei problemi in tempo reale per utente

Per visualizzare tutte le informazioni e i dati della riunione per un utente, passare [all'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com). In **Utenti** > **Gestisci utenti** selezionare un utente e aprire la scheda **Riunioni & chiamate** nella pagina del profilo dell'utente. In **Riunioni recenti** vedrai un elenco delle riunioni a cui l'utente ha partecipato nelle ultime 24 ore *, a cui è disponibile la telemetria in tempo reale*, incluse le riunioni in corso. Se la riunione non è in corso o non ha dati di telemetria in tempo reale, verrà visualizzata nelle **riunioni precedenti**.

:::image type="content" alt-text="Screenshot della tabella delle riunioni recenti." source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

Per ottenere informazioni aggiuntive sui partecipanti a una riunione in corso, incluse le statistiche sul dispositivo, sulla rete e sull'audio, trovare la riunione in **Riunioni recenti** e selezionare il collegamento sotto la colonna **Partecipanti** .

:::image type="content" alt-text="Screenshot della tabella dei dettagli dei partecipanti." source="media/participant-details-edit.png" lightbox="media/participant-details-edit.png":::

Per esaminare la telemetria di un determinato utente per una riunione in corso, incluse informazioni sui dettagli relativi a dispositivo, rete, audio, video e condivisione di contenuti, selezionare **l'ID riunione**.

:::image type="content" alt-text="Screenshot dei dati della sessione utente di analisi delle chiamate." source="media/real-time-telemetry-edit.png" lightbox="media/real-time-telemetry-edit.png":::

## <a name="details-and-measures-available-in-real-time-analytics"></a>Dettagli e misure disponibili in Real-Time Analytics

### <a name="device-information"></a>Informazioni sul dispositivo
| Nome | Descrizione | Possibili motivi per i valori vuoti|
|:---|:---|:---|
| Dispositivo di acquisizione audio | Nome del dispositivo di acquisizione audio (ad esempio: microfono) in uso | Il sistema potrebbe non avere un nome associato al dispositivo (ad esempio: Desktop remoto o dispositivo "Audio remoto" della macchina virtuale)  |
| Dispositivo di rendering audio | Nome del dispositivo di rendering audio (ad esempio altoparlanti o cuffie) in uso | Il sistema potrebbe non avere un nome associato al dispositivo (ad esempio: Desktop remoto o dispositivo "Audio remoto" della macchina virtuale)  |
| Dispositivo di acquisizione video | Nome del dispositivo di acquisizione video in uso | L'utente non invia video dall'endpoint monitorato |

### <a name="connectivity-information"></a>Informazioni sulla connettività
| Metrica | Unità/Valori possibili | Descrizione | Possibili motivi per i valori vuoti|
|:---|:---|:---|:---|
| Tipo di rete | &bull; Ethernet <br/> &bull; Wi-Fi | Tipo di connessione di rete in uso | |
| forza Wi-Fi | &bull; Eccellente: -50 dBm o superiore <br/> &bull; Buono: -51 dBm a -64 dBm<br/> &bull; Scarsa: -65 dBm o inferiore | Potenza della connessione Wi-Fi corrente dell'utente | L'utente non è connesso a Wi-Fi |
| Wi-Fi canale | Numero intero | Canale su cui il punto di accesso della rete Wi-Fi trasmette | L'utente non è connesso a Wi-Fi |
| Tipo fisico | Stringa <br/> &bull; Esempio: 802.11ac | Tipo di infrastruttura wireless in uso | L'utente non è connesso a Wi-Fi |
| Wi-Fi band | 2,4 GHz o 5 GHz | Wi-Fi banda a cui l'utente è connesso | L'utente non è connesso a Wi-Fi |
| Posizione | Stringa | Paese in cui si trova l'utente | Le informazioni sulla posizione dell'utente sono bloccate o non disponibili |
| Indirizzo IP locale | Stringa (IP:Porta) | Indirizzo IP locale dell'endpoint dell'utente e della porta multimediale | |
| Indirizzo IP riflessivo del server | Stringa (IP:Porta) | Indirizzo IP pubblico dell'endpoint dell'utente e della porta multimediale | |
| Tipo di connettività | UDP o TCP | Protocollo di livello di trasporto in uso; UDP è preferito per i supporti in tempo reale | |

### <a name="user-signals"></a>Segnali utente
I segnali dell'utente identificano quando un utente sta partecipando attivamente alla chiamata, non parla ma viene riattivato o è disattivato. Attualmente, i segnali utente sono disponibili solo per l'audio.

| Modalità | Valori possibili | Descrizione |
|:---|:---|:---|
| Audio | &bull; Riattivato, partecipante che parla <br/> &bull; Riattivato, non in parlato <br/> &bull; Disattivato | Indica il comportamento dell'utente per la parte audio della chiamata  |


### <a name="audio"></a>Audio
|Nome misura |Unità |Soglia buona |Descrizione |
|:---|:---|:---|:---|
|Jitter |Millisecondi |Meno di 30 ms |L'instabilità è una misura della variazione del ritardo dei pacchetti per un flusso di dati. Quando questo è troppo alto, l'audio può diventare discontinuo. | 
|Perdita pacchetti |Percentuale |Meno del 5% |La perdita di pacchetti si verifica quando i pacchetti di dati non raggiungono la destinazione. La percentuale di pacchetti persi si basa sul numero totale di pacchetti inviati. |
|Round Trip Time |Millisecondi |Meno di 500 ms |Il tempo di round trip è il tempo necessario a un singolo pacchetto per passare dal client all'endpoint remoto e tornare al client. Un tempo di round trip elevato può causare ritardi nella riproduzione dello stream. Un esempio è quando due persone in una riunione parlano inavvertitamente l'una sull'altra a causa del ritardo. Mostrata solo per l'audio in uscita. |
|Bitrate |Kilobit al secondo (Kbps) |Maggiore di 24 Kbps |Velocità effettiva del flusso audio espressa in kilobit al secondo. |
| Codec | Stringa <br/> &bull; Esempio: RASO | Solo informazioni | Visualizza il codec audio inviato e ricevuto. È possibile ricevere un codec diverso da quello inviato. |


### <a name="video"></a>Video
|Nome misura |Unità |Soglia buona |Descrizione |
|:---|:---|:---|:---|
|Round Trip Time |Millisecondi |Meno di 500 ms |Il tempo di round trip è il tempo necessario a un singolo pacchetto per passare dal client all'endpoint remoto e tornare al client. Un tempo di round trip elevato può causare ritardi nella riproduzione dello stream. Un esempio è quando due persone in una riunione parlano inavvertitamente l'una sull'altra a causa del ritardo. |
|Bitrate |Megabit al secondo (Mbps) | Solo informazioni |Velocità effettiva del flusso video espressa in megabit al secondo. |
|Frequenza fotogrammi (video) |Fotogrammi al secondo |360p o superiore: 25-30 FPS <br/> 270p o inferiore: 7-15 FPS |Per i flussi video in uscita, la frequenza dei fotogrammi (FPS) è il numero di fotogrammi al secondo del video inviato dal client. I valori inferiori al previsto possono suggerire vincoli di risorse di sistema, larghezza di banda di rete insufficiente o dispositivi di acquisizione video non correttamente usati. Diverse risoluzioni hanno intervalli FPS diversi accettabili. |
|Codec |Stringa | Solo informazioni |Visualizza il codec video e la modalità di rendering del flusso video in uscita. Esempio: H264 SW HW indica un flusso video H264 che usa il rendering hardware e software.|
|Risoluzione |Pixel | Solo informazioni |La risoluzione del video da inviare. La risoluzione video in uscita è dinamica, in base ai requisiti più elevati di un endpoint nella riunione. Un client in grado di trasmettere video 1920 x 1080 invierà video 640 x 360 solo se nessun client visualizza il video dell'utente in un fotogramma superiore a 640 x 360 |


### <a name="application-sharing-vbss"></a>Condivisione applicazioni (VBSS)
|Nome misura |Unità |Soglia buona |Descrizione |
|:---|:---|:---|:---|
|Perdita pacchetti |Percentuale |Meno del 5% |La perdita di pacchetti si verifica quando i pacchetti di dati non raggiungono la destinazione. La percentuale di pacchetti persi si basa sul numero totale di pacchetti inviati. |
|Round Trip Time |Millisecondi |Meno di 500 ms |Il tempo di round trip è il tempo necessario a un singolo pacchetto per passare dal client all'endpoint remoto e tornare al client. Un tempo di round trip elevato può causare ritardi nella riproduzione dello stream. Un esempio è quando due persone in una riunione parlano inavvertitamente l'una sull'altra a causa del ritardo. |
|Bitrate |Megabit al secondo (Mbps) | Solo informazioni |Velocità effettiva del flusso VBSS espressa in megabit al secondo. |
|Frequenza fotogrammi |Fotogrammi al secondo (FPS) | Solo informazioni |Per VBSS, la frequenza dei fotogrammi è compatibile con il contenuto per garantire che vengano inviati tutti i frame necessari per garantire una buona esperienza evitando al contempo l'invio di frame, se non sono necessari. Ad esempio, la condivisione di un documento di testo su schermo richiede solo 1 fotogramma al secondo per produrre una buona esperienza, mentre la condivisione di un video o di contenuti con più attività aumenterà i fotogrammi al secondo fino a un massimo di 30 FPS per produrre un'esperienza più fluida. |
|Codec |Stringa | Solo informazioni |Visualizza il codec e la modalità di rendering del flusso VBSS. Esempio: H264 SW HW indica un flusso VBSS H264 che usa il rendering hardware e software.|
|Risoluzione |Pixel | Solo informazioni |Risoluzione del flusso VBSS inviato e ricevuto. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>Piattaforme client supportate per la telemetria in tempo reale

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> Il client Web di Teams (incluso VDI) non supporta il recapito della telemetria in tempo reale.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Dispositivi Teams con supporto per la telemetria in tempo reale

- MTR - Surface Hub
- MTR - Teams Display
- MTR - Barra di collaborazione
- Dispositivi telefono IP

> [!NOTE]
> I dispositivi che hanno eseguito l'accesso alla riunione con soluzioni Cloud Video Interop (CVI) non sono supportati in Real-Time Analytics.


## <a name="limitations"></a>Limitazioni

- La telemetria in tempo reale è disponibile solo per le riunioni pianificate e riunione immediata. Per le chiamate PSTN, 1:1 e di gruppo, la telemetria in tempo reale non è disponibile.
- La telemetria in tempo reale è disponibile solo per i relatori di eventi live pianificati. Attualmente non è disponibile per i partecipanti a eventi live.
- I dati di telemetria in tempo reale sono disponibili per una riunione in **Riunioni recenti** per 24 ore dopo la fine della riunione. Dopo 24 ore, non è possibile accedere ai dati e la riunione passa alle **riunioni passate**. Se una riunione dura più di 3 ore, la telemetria in tempo reale sarà disponibile solo per le *ultime 3 ore*.
- La telemetria non è disponibile in tempo reale quando si usano versioni precedenti di Teams. Se non sono disponibili dati di telemetria, provare ad aggiornare il client.
- Se i partecipanti esterni o gli utenti anonimi partecipano a una riunione, il loro nome visualizzato risulta **non disponibile** per mantenere la privacy tra tenant.

> [!NOTE]
> Nell'ambito di un'anteprima pubblica a tempo limitato, i dati di telemetria in tempo reale sono attualmente disponibili per **7 giorni** dopo la fine di una riunione. Al termine dell'anteprima, solo i tenant con licenze per i componenti aggiuntivi Advanced Communications avranno la telemetria disponibile per il periodo prolungato di 7 giorni. Tutti gli altri inquilini saranno soggetti ai limiti indicati.

## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate per utente](set-up-call-analytics.md)

[Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](/MicrosoftTeams/using-admin-roles).
