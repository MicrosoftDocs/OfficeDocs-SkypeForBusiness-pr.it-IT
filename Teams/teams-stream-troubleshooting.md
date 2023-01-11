---
title: Risoluzione dei problemi relativi allo streaming live in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Questo articolo illustra le opzioni di risoluzione dei problemi per gli eventi di streaming di Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d88b8c0f356bcf59319f073c0e75c65a25361cf2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767998"
---
# <a name="troubleshooting-live-events-in-microsoft-teams"></a>Risoluzione dei problemi relativi agli eventi live in Microsoft Teams

> [!IMPORTANT]
> **Cina**: gli utenti residenti in Cina non potranno configurare o partecipare a eventi live di Teams o Yammer o visualizzare video su richiesta perché attualmente, la rete CDN di Azure, su cui si basano queste app, potrebbe non essere accessibile in Cina.
>
> In qualità di amministratore, potrebbe essere necessario configurare una VPN per connettere la rete aziendale affinché queste app funzionino senza problemi. Al termine, gli utenti dell'organizzazione possono pianificare e partecipare a eventi live.

## <a name="before-a-live-event"></a>Prima di un evento live

### <a name="make-sure-all-events-are-reachable-in-your-network"></a>Verificare che tutti gli eventi siano raggiungibili nella rete

#### <a name="general-teams-endpoints"></a>Endpoint generali di Teams

Teams richiede connettività a Internet. Tutti gli endpoint elencati negli [endpoint Office 365 per Teams](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) devono essere raggiungibili dagli utenti di Teams all'interno della rete dell'organizzazione.

#### <a name="teams-encoder-live-events---rmtp-ingest-endpoints"></a>Eventi live di Teams Encoder - endpoint di inserimento RMTP

Per ottenere un feed video per un evento live di Teams Encoder inviato a Teams dal codificatore, è necessario aprire il nome di dominio e le porte nel firewall della rete:

- Domini: *.rtmpingest.mcr.teams.microsoft.com
- Porte: 1935/1936 (per RTMP/RTMPS)

### <a name="make-sure-you-have-enough-upload-bandwidth"></a>Verificare che la larghezza di banda di caricamento sia sufficiente

Quando si produce o si riproduce in streaming un evento live tramite RTMP, è possibile che la larghezza di banda per il caricamento tramite Internet sul sito che spinge lo stream live non sia sufficiente. La larghezza di banda per il caricamento ridotta potrebbe causare la caduta di frame o problemi nel video in tempo reale, che potrebbero causare problemi di riproduzione per gli spettatori.

Assicurarsi che la velocità di caricamento per il computer e la rete che esegue il push del flusso live sia superiore alla velocità in bit impostata per il flusso live. Se si sta eseguendo l'output di un flusso da 5 Mbps dal codificatore, ma la velocità in bit di caricamento è vicina o inferiore a quella, si potrebbero verificare problemi che non sono in grado di caricare lo stream abbastanza velocemente.

Se hai problemi con il caricamento della larghezza di banda, ecco alcune soluzioni che puoi provare:

1. Usa una connessione Ethernet cablata per qualsiasi computer da cui stai spingendo lo stream per evitare interruzioni del WiFi.
1. Ridurre la velocità di bit di codifica del feed live a un valore ben inferiore alla velocità di caricamento massima.

### <a name="preparing-your-network-for-many-concurrent-viewers"></a>Preparazione della rete per molti visualizzatori simultanei

Durante gli eventi live molte persone parteciperanno per guardare il tuo evento in diretta. Questo potrebbe mettere a dura prova la larghezza di banda per il download della rete e di Internet. È necessario valutare l'infrastruttura di rete corrente e assicurarsi che le persone all'interno della rete aziendale dispongano della larghezza di banda necessaria per guardare un evento live. Per ridurre il traffico Internet necessario per gli eventi live sono disponibili due opzioni:

1. Configurare i proxy della cache esistenti all'interno della rete per memorizzare nella cache i video di Teams.
1. Usare una soluzione di distribuzione video eCDN di terze parti per ottimizzare il traffico video.

### <a name="i-cant-create-a-live-event"></a>Non riesco a creare un evento live

In Microsoft Teams e Yammer esistono autorizzazioni che un utente deve essere in grado di creare un evento live a seconda del servizio usato per l'evento live.

1. Verificare che l'amministratore di Teams abbia abilitato la creazione di eventi live.
1. Rivolgersi all'amministratore per verificare di avere una licenza di Teams valida che consente la creazione di eventi live.

### <a name="make-sure-viewers-have-permission-to-watch-the-event"></a>Assicurati che gli spettatori abbiano l'autorizzazione per guardare l'evento

Gli eventi live di Microsoft Teams hanno diversi ruoli per le autorizzazioni per l'evento stesso (Organizzatore, Produttore, Relatore, Partecipante).

Per altre informazioni, vedere [Ruoli del gruppo di eventi di Microsoft Teams](https://support.office.com/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a#bkmk_roles) .

## <a name="producing-a-live-event"></a>Produrre un evento live

### <a name="i-dont-know-how-to-set-up-my-encoder"></a>Non so come configurare il mio codificatore

Il modo più semplice per iniziare consiste nel seguire le istruzioni descritte [nell'articolo Uso di un codificatore per lo streaming live in Microsoft Teams](teams-encoder-setup.md) .

### <a name="my-encoder-isnt-connecting-to-the-server-ingest-url"></a>Il codificatore non si connette all'URL di inserimento server

- Verificare che l'URL RTMP sia stato immesso correttamente come output del codificatore.
- Verifica che la chiave RTMP sia stata immessa correttamente come output del codificatore.
- Controllare lo stato della connessione Internet per verificare che il codificatore sia connesso correttamente e online.
- Potrebbero essere presenti impostazioni di sicurezza della rete o correlate al firewall che potrebbero bloccare l'output della connessione.
- Il codificatore potrebbe non essere supportato con Teams. Consulta l'elenco dei codificatori testati in [Uso di un codificatore per lo streaming live in Microsoft Teams](teams-encoder-setup.md).

### <a name="i-cant-get-rtmps-to-work"></a>Non riesco a far funzionare gli RTMP

- Alcuni codificatori possono supportare un'implementazione diversa che non è supportata da Teams. Consulta l'elenco dei codificatori testati che funzionano con Teams in [Uso di un codificatore per lo streaming live in Microsoft Teams](teams-encoder-setup.md).
- Non tutti i codificatori o le versioni supportano gli RDP. Contatta il produttore o l'autore del software per vedere cosa supporta.

### <a name="i-tried-to-start-setup-and-its-taking-a-long-time"></a>Ho provato ad avviare la configurazione e l'operazione richiede molto tempo

In generale, per completare la configurazione possono essere necessari alcuni minuti prima di poter avviare il push del codificatore. È possibile che, se il servizio è occupato, l'esecuzione dell'operazione possa richiedere più tempo, quindi è consigliabile concedere a se stessi un ampio tempo per avviare la configurazione prima dell'evento live pianificato.

### <a name="i-tried-to-start-setup-but-there-are-too-many-events-happening"></a>Ho provato ad avviare la configurazione, ma ci sono troppi eventi in corso

Se si riceve un messaggio all'inizio di un evento che indica che è stato raggiunto il numero massimo di eventi, contattare un amministratore di Teams, che ha la possibilità di interrompere altri eventi per fare spazio a un evento con priorità più alta.

### <a name="i-cant-see-producer-view"></a>Non è possibile vedere la visualizzazione Producer

1. Potrebbero essere necessari alcuni secondi prima che l'anteprima del produttore venga visualizzata dopo l'avvio della riproduzione in streaming dal codificatore.
1. Assicurarsi che il codificatore sia connesso a Teams.
1. A volte può essere utile aggiornare la pagina in Teams. Potrebbe esserti chiesto se vuoi uscire dalla pagina; questo non influirà sul tuo evento live.
1. Alcune reti potrebbero bloccare l'accesso al contenuto. Assicurarsi che le impostazioni di sicurezza della rete e del firewall consentano il protocollo RTMP e che i [domini necessari](/microsoft-365/enterprise/urls-and-ip-address-ranges) siano inclusi nell'elenco dei domini consentiti. Può essere utile per provare a verificare se funziona in un ambiente di rete diverso, indipendentemente da una rete aziendale, VPN o rete bloccata.

### <a name="my-feed-looks-bad-has-poor-quality-or-is-glitchy"></a>Il mio feed sembra cattivo, ha scarsa qualità o è glitchy

1. Controlla la larghezza di banda per il caricamento dal computer da cui stai spingendo il live streaming. La larghezza di banda bassa può causare interruzioni dei fotogrammi, scarsa qualità o un flusso video dall'aspetto luccicante. È necessaria una larghezza di banda di caricamento superiore alla velocità in bit a cui stai trasmettendo lo streaming.
1. Assicurarsi di usare le impostazioni del codificatore consigliate per Teams. Per altre informazioni, vedi [Configurare manualmente i codificatori per lo streaming di eventi live in Microsoft Teams](teams-encoder-configuration.md) .
1. Verificare che l'audio/video in arrivo nel codificatore non abbia problemi. I feed audio o video di origine indirizzati al codificatore potrebbero presentare problemi, con il conseguente invio di un'esperienza non ottimale agli utenti.
1. Controllare il carico della CPU sul codificatore. È possibile che la CPU sia al massimo con il contenuto di origine e/o con la velocità in bit che si sta tentando di spingere. Se il carico della CPU è troppo elevato, prova a ridurre la complessità delle sovrapposizioni/contenuto dei feed in tempo reale o a ridurre la velocità in bit a cui stai trasmettendo lo streaming.
1. Verificare che il codificatore sia aggiornato. Se si tratta di un codificatore hardware, assicurati di disporre degli ultimi aggiornamenti del firmware. Se si tratta di un codificatore software, assicurati di eseguire l'ultima versione.
1. Provare a reimpostare o riavviare il codificatore. Si noti che se si esegue questa operazione durante un live stream, gli spettatori visualizzeranno un errore durante la riproduzione durante il riavvio del codificatore. Dopo aver riavviato lo streaming live dal codificatore, gli spettatori dovranno ricaricare la pagina per ottenere di nuovo lo streaming live.

### <a name="i-ended-my-live-event-from-my-encoder-but-viewers-are-seeing-an-error"></a>Ho terminato il mio evento live dal mio codificatore, ma gli spettatori vedono un errore

Selezionare **Interrompi evento** prima di disconnettere il codificatore. Se il codificatore è già stato disconnesso, è comunque possibile selezionare **Interrompi evento**, ma gli utenti potrebbero visualizzare un errore.

### <a name="my-viewers-are-seeing-issues"></a>I miei spettatori stanno riscontrando problemi

- Se un singolo visualizzatore segnala un problema, assicurati che abbia una larghezza di banda sufficiente e che sia collegato a Internet per guardare l'evento.
- Se più persone all'interno della stessa rete hanno problemi, potrebbero verificarsi problemi relativi alla congestione della rete. Esaminare [Ridimensionare la distribuzione di video e monitorare il traffico di rete usando eCDN con Microsoft Teams](teams-stream-ecdn.md) per vedere se è possibile identificare una soluzione al problema.
- In molti casi, quando più visualizzatori riscontrano un problema, è in realtà correlato al feed del codificatore.
  - Verificare che il codificatore sia impostato correttamente sulle specifiche descritte nella configurazione del codificatore e configurato correttamente.
  - Verificare che la larghezza di banda di caricamento sia sufficiente per lo streaming. È possibile provare a ridurre la larghezza di banda dell'output del codificatore.
  - A volte la reimpostazione del codificatore è utile, ma è necessario mantenere le stesse impostazioni quando ci si riconnette. I membri del gruppo di destinatari potrebbero visualizzare un errore o un problema nell'evento live.

### <a name="i-or-my-viewers-cant-hear-the-video"></a>Io, o i miei spettatori, non riesco a sentire il video

1. Verificare che il codificatore invii audio.
1. Verifica che il dispositivo audio sia collegato alla rete elettrica.
1. Se in Windows, assicurati che il dispositivo audio corretto sia selezionato e riattivato.
1. In caso di interruzione del codificatore, alcuni browser o dispositivi potrebbero non essere in grado di ripristinare e riprodurre correttamente l'audio.

> [!NOTE]
> Se è stato distribuito Microsoft eCDN come provider di distribuzione video per eventi live, vedere [Risoluzione dei problemi di prestazioni di eCDN](/ecdn/troubleshooting/troubleshoot-ecdn-performance-issues) per ulteriori dettagli sulla risoluzione dei problemi di prestazioni di eCDN che potrebbero verificarsi.
