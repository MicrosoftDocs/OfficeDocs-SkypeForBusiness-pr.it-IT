---
title: Note sulla versione per Microsoft Teams Rooms (Windows)
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: L'amministratore può leggere le note sulla versione per Microsoft Teams Rooms, che elencano i miglioramenti cumulativi in Microsoft Teams Rooms.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f91c286f08046d1a521d3758f1fc297bf2aa0d59
ms.sourcegitcommit: ad8447b683381bc07f993bf843a93a4bdb77d840
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "65187022"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Note sulla versione per Microsoft Teams Rooms

Questo articolo descrive i miglioramenti cumulativi in Microsoft Teams Rooms.

Esistono due tipi di aggiornamenti per Teams Rooms: aggiornamenti delle app Teams Rooms e Teams web-client. 

Teams Rooms gli aggiornamenti delle app avvengono tramite il Microsoft Store o tramite [l'aggiornamento manuale](manual-update.md). In questo modo viene aggiornata l'applicazione piattaforma UWP (Universal Windows Platform) (UWP) installata localmente nel dispositivo.

Teams gli aggiornamenti client Web avvengono tramite i servizi di recapito delle app Web Teams. Si tratta di un servizio basato sul cloud che non richiede un aggiornamento dell'applicazione UWP locale installata nel dispositivo.

Per altre informazioni su come Teams gli aggiornamenti, vedi [Teams processo di aggiornamento](../teams-client-update.md)

Teams Rooms è disciplinato dai criteri moderni relativi al ciclo di vita. Per altre informazioni, vedere [Teams processo di aggiornamento](../teams-client-update.md#servicing-agreement).

## <a name="version-history"></a>Cronologia versioni

|Rilascio |Pubblicato su <br/> Microsoft Store |
|--- |--- |
|4.12.126.0 |4/27/2022 |
|4.11.17.0 |3/3/2022 |
|4.11.12.0 |1/24/2022 |
|versione Teams Web-Client | Dicembre 2021 |
|versione Teams Web-Client | Ottobre 2021 |
|4.10.10.0 |10/1/2021 |
|4.9.12.0 |07/28/2021 |
|4.8.31.0 |05/12/2021 |
|4.8.25.0 |04/22/2021 |
|4.8.19.0 |04/06/2021 |
|4.7.19.0 |02/03/2021 |
|4.7.15.0 |12/11/2020 |
|4.6.23.0 |10/19/2020 |
|4.6.20.0 |09/30/2020 |
|4.5.37.0 |08/14/2020 |
|4.5.35.0 |07/23/2020 |
|4.4.63.0 |06/25/2020 |
|4.4.41.0 |05/06/2020 |
|4.4.25.0 |03/31/2020 |
|4.3.42.0 |03/02/2020 |
|4.3.33.0 |1/10/2020 |
|4.3.23.0 |12/13/2019 |
|4.2.4.0 |10/07/2019 |
|4.1.22.0 |08/15/2019 |
|4.0.105.0 |07/10/2019 |
|4.0.85.0 |04/08/2019 |
|4.0.78.0 |03/14/2019 |
|4.0.76.0 |03/04/2019 |
|4.0.64.0 |12/14/2018 |
|4.0.51.0 |11/17/2018 |
|4.0.31.0 |10/16/2018 |
|4.0.27.0 |10/1/2018 |
|4.0.19.0 |08/31/2018 |
|4.0.18.0 |08/27/2018 |
|4.0.8.0 |07/06/2018 |
|3.1.115.0|06/18/2018 |
|3.1.113.0|06/13/2018 |
|3.1.112.0|06/05/2018 |
|3.1.104.0|04/16/2018 |
|3.1.100.0|03/16/2018 |
|3.1.99.0 |3/14/2018 |
|3.1.98.0 |3/8/2018 |
|3.0.16.0 |11/27/2017 |
|3.0.15.0 |10/3/2017 |
|3.0.12.0 |9/1/2017 |
|3.0.8.0 |11/16/2017 |
|3.0.6.0 |11/16/2017 |
|2.0.2.0 |03/15/2017 |
|RTM (1.0.8) |12/7/2016 |

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Microsoft Teams Rooms introduzione delle funzionalità e risoluzione dei problemi

### <a name="4121260-4272022"></a>4.12.126.0 (4/27/2022)

Introdotto in questo aggiornamento:
- Gli amministratori IT possono registrare un dispositivo Teams sale per ricevere le funzionalità di anteprima pubblica tramite l'impostazione XML. Dopo la registrazione, il dispositivo inizierà a ricevere le funzionalità beta. Tutte le funzionalità disponibili per i test beta vengono annunciate in [Microsoft Teams Public Preview - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview) <sup>1,2</sup>  
- L'amministratore IT può impostare la risoluzione dello schermo della sala e il ridimensionamento in remoto tramite le impostazioni <sup>XML2</sup>
- L'amministratore IT può disabilitare l'eliminazione del rumore microsoft tramite l'impostazione <sup>XML3</sup> 
- L'amministratore IT può ignorare la pulizia della cartella di download nel dispositivo tramite l'impostazione della chiave del Registro di <sup>sistema4</sup>
- Consentire agli utenti di partecipare a Teams riunione ospitata in un altro cloud (ad esempio, il cliente GCCH può partecipare a riunioni Teams ospitate nel cloud commerciale e viceversa) 
- Teams rooms ora blocca l'avvio del browser Edge dagli URL in PowerPoint Live come misura di sicurezza aggiuntiva per Teams sale con touchscreen 
- L'esperienza Riunione immediata è stata migliorata per aggiungere istruzioni agli utenti per invitare gli utenti alla sala 
- Supporto per Windows 10 rilascio delle funzionalità 21H2 per Teams chat room   
- Il nuovo punto di ingresso Cortana nella schermata iniziale, il pulsante Condividi/Presenta è tornato 

> <sup>1</sup> Le istruzioni per la registrazione dell'anteprima pubblica dei dispositivi Windows MTR sono disponibili [qui](../public-preview-doc-updates.md#enable-public-preview)
> 
> <sup>2</sup> La risoluzione dello schermo della sala e il ridimensionamento remoto tramite XML sono disponibili [qui](../rooms/xml-config-file.md#set-front-of-room-scale-and-resolution)
>
> <sup>3</sup> Al momento, viene rilasciata solo l'impostazione amministratore. Il controllo e l'abilitazione dell'eliminazione del rumore seguono la versione 4.12 del maggio 2022. 
>
> <sup>4</sup> Le istruzioni per la pulizia del dispositivo sono disponibili [qui](../rooms/rooms-operations.md#collecting-logs-on-microsoft-teams-rooms)
> 
> 
> [!NOTE]
> Windows 10 aggiornamento delle funzionalità 21H2 verrà aggiornato dopo 7 giorni dall'installazione dell'applicazione oppure gli amministratori possono usare l'aggiornamento manuale per velocizzare l'installazione. Microsoft Teams Rooms versione 4.12 dell'applicazione con queste modifiche, inizierà a essere distribuita ad aprile 2022 e completerà l'implementazione tra 2-3 settimane. Gli aggiornamenti dell'applicazione vengono distribuiti tramite Windows store e l'applicazione viene installata automaticamente. L'implementazione viene eseguita Microsoft Teams Rooms solo in Windows. Cosa occorre fare per prepararsi: è consigliabile inviare una notifica agli utenti su questa esperienza aggiornata e aggiornare la formazione e la documentazione in base alle esigenze.

### <a name="411170-332022"></a>4.11.17.0 (3/3/2022)

Introdotto in questo aggiornamento:
- Correzione di bug per l'inquadratura della fotocamera che migliorerà tutto il contenuto nella visualizzazione fotocamera.

### <a name="411120-1242022"></a>4.11.12.0 (1/24/2022)

Introdotto in questo aggiornamento:
- Layout Front Row (Anteprima) per MTR in Windows <sup>1</sup> 
- Impostazione amministratore per impostare il layout Front row come predefinito  
- Aggiornamento dell'app Riunione immediata e chiamata solo per Teams, Teams modalità client <sup>predefinite1,2</sup>
- Passare da una videocamera all'altra in Teams <sup>riunioni1</sup> 
- Impostazione predefinita della videocamera 
- Cortana aggiornamento dell'icona push-to-talk nella console MTR 
- Inclusione di una licenza di Azure AD Premium 1 in SKU Room Standard e Premium 
- supporto dei criteri di accesso condizionale AAD <sup>3</sup> 
- Cortana attivazione vocale abilitata per impostazione predefinita nella Configurazione guidata
- Supporto per i controlli PTZ <sup>remoti4</sup>

> <sup>1</sup> Queste funzionalità verranno distribuite con Teams client Web e l'implementazione verrà completata nelle prossime due settimane. Per altre informazioni, vedere [Teams aggiornamenti](../teams-client-update.md).
> 
> <sup>2</sup> sale Teams su Windows in esecuzione solo in Microsoft Teams o Skype for Business e Microsoft Teams (impostazione predefinita) vengono aggiornate con le nuove esperienze riunione e chiamata, tuttavia altre modalità non sono interessate da questo aggiornamento.
> 
> <sup>3</sup> Vedere altri dettagli sulla configurazione [di AAD criteri di accesso condizionale](../rooms/rooms-authentication.md#azure-ad-conditional-access) per Teams Rooms.
> 
> <sup>4</sup> Per questa funzionalità è necessario che gli amministratori IT configurino Teams'app controlli PTZ remoti del client desktop.
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>aggiornamento del client Web Teams Rooms (dicembre 2021)

Introdotto in questo aggiornamento:
- Il layout video diviso in due front of room viene visualizzato quando il contenuto non viene condiviso

### <a name="teams-rooms-web-client-update-october-2021"></a>aggiornamento del client Web Teams Rooms (ottobre 2021)

Introdotto in questo aggiornamento:
- Controllo dell'elenco unificato con Teams client desktop con raggruppamento di riunioni strutturate, opzioni e controlli per i relatori e i partecipanti, aumentare l'ordinamento delle mani e la possibilità di invitare utenti dalla chat o dall'invito alla riunione direttamente dal roster 
- Universal bar call controls alignment with desktop client in meeting call controls, Layout button and meeting status information
- Supporto dinamico della galleria per schermi a singola e doppia facciata
- Unified layout picker for front of room layout option consolidated
- Mettere in evidenza o aggiungere più partecipanti a Teams riunioni
- Supporto per riunioni di grandi dimensioni con controlli per relatori e partecipanti accessibili toccando partecipante dall'elenco
- Possibilità di bloccare una riunione per le riunioni in cui la sala è organizzatore, nonché la consapevolezza della riunione bloccata
- Supporto a consumo per la modalità relatore (weatherman) quando un utente remoto condivide contenuto con l'opzione di visualizzazione Relatore
- Supporto di reazione nelle riunioni Teams 

> [!NOTE]
> Gli aggiornamenti dei client Web sono disponibili per tutti i Teams Rooms con le versioni 4.10 e 4.9 delle applicazioni. Gli amministratori potranno iscriversi a Teams Rooms programma di anteprima pubblica per ottenere presto l'anteprima delle funzionalità del client Web.

### <a name="410100-1012021"></a>4.10.10.0 (10/1/2021)

Introdotto in questo aggiornamento:
- Room remote consente agli utenti di controllare le funzionalità di base della sala utilizzando Teams sul proprio cellulare *
- Logitech scribe content camera support for BLE button for sharing into meeting
- Le bolle di chat forniscono notifiche per nella chat della riunione per attirare l'attenzione su ciò che viene detto usando la chat della riunione *
- Il supporto per la raccolta di grandi dimensioni e la modalità Insieme è ora disponibile in GCC High
- Nuove competenze aggiunte a Cortana, Aggiungi persona per nome alla riunione e Chiama per nome 
- Cortana Push to Talk è abilitato per impostazione predefinita in tutti i dispositivi. Per altre informazioni, vedi [Cortana assistenza vocale in Teams](../cortana-in-teams.md).

> [!NOTE]
> Supporto 19H1 deprecato. La versione del sistema operativo min supportata da 4.10 è 19H2.

> [!NOTE]
> *Queste funzionalità vengono distribuite con Teams servizio e funzionano con tutte le versioni delle applicazioni successive alla 4.9.

> [!NOTE]
> Per partecipare alla riunione pianificata sia dall'app per dispositivi mobili Teams che da MTR-W, trovare l'account della sala nell'elenco dei partecipanti nell'app Teams Mobile e premere il menu "Controlla questa sala" ed è possibile controllare i controlli chiamata dall'app.

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

Introdotto in questo aggiornamento:
- Microsoft Teams modalità solo è ora disponibile nelle impostazioni dell'applicazione, quindi non è più necessario configurare un account Skype for Business. In questa modalità, i dispositivi connessi alla modalità solo Teams partecipano a riunioni Skype for Business come utente guest.
- Correzione per l'audio HDMI che causa una riduzione del volume delle chiamate. La funzionalità audio HDMI viene abilitata automaticamente per tutti i dispositivi con build dell'applicazione 4.9.12.0.

> [!NOTE]
> Con Skype for Business che raggiunge la fine del ciclo di vita, è consigliabile eseguire l'aggiornamento alla modalità solo Teams.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

Introdotto in questo aggiornamento:
- Supporto per Windows 10 20H2 

> [!NOTE]
> Crestron UC-Engine (data della versione BIOS contenente "KYSKLi") Teams Rooms presentano problemi di compatibilità e i driver aggiornati verranno forniti dagli OEM di sistema nel prossimo futuro. Windows 10 20H2 non sarà disponibile per questi dispositivi. Per altre informazioni sul supporto per Windows versione, vedere [Windows 10 supporto per i rilasci](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

Introdotto in questo aggiornamento:
- Correzione di un problema a causa del quale le informazioni sulla sala nelle console Teams Rooms non vengono visualizzate per gli account della chat room nascosti all'elenco indirizzi globale

> [!NOTE]
> I clienti GCCH possono scaricare il pacchetto di aggiornamento da [Aggiornare manualmente un dispositivo Microsoft Teams Rooms](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

Introdotto in questo aggiornamento:
- supporto Government Community Cloud High (GCCH) per Teams Rooms. I clienti GCCH con dispositivi Teams Rooms esistenti possono scaricare la versione 4.8.19.0 da [Aggiornare manualmente un dispositivo Microsoft Teams Rooms](manual-update.md)
- Partecipare a riunioni con zoom con una qualità video migliore (supporto 720p) e ricevere la raccolta video dei partecipanti
- Skype for Business banner di errore di accesso rimosso per Teams modalità predefinita. Questa modifica supporta le organizzazioni che rimuovono Skype for Business'infrastruttura
- Teams riunioni partecipano all'analisi dei collegamenti ora gestisce i collegamenti di Microsoft Defender Advanced Threat Protection Cassaforte per consentire di partecipare facilmente a Teams esterni
- Correzione del problema di ridimensionamento del contenuto condiviso nelle riunioni di Skype for Business quando il PC del condivisore ha un DPI personalizzato impostato in Windows
- Correzioni di qualità e affidabilità

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

Introdotto in questo aggiornamento:
- Correzioni di qualità e affidabilità

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

Introdotto in questo aggiornamento:

- Condividere l'audio HDMI con i partecipanti alla riunione in Teams riunione
- Cortana le competenze vocali (anteprima)
- Impedire l'audio in base alle autorizzazioni audio quando Teams Rooms partecipa come partecipante. Per altre informazioni, vedere [Gestire le autorizzazioni audio dei partecipanti in riunioni Teams](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a).
- Mettere in evidenza il video di un utente dalla console Teams Room e utilizzare il video in evidenza sugli schermi della sala

> [!NOTE]
> Cortana le competenze vocali sono disponibili per alcune periferiche audio selezionate per i tenant che si trovano nel Stati Uniti. Altri paesi o aree geografiche verranno aggiunti in futuro. Per altre informazioni, vedi [Cortana assistenza vocale in Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

Introdotto in questo aggiornamento:

- Correzione per il mezzo schermo bianco quando si richiama la tastiera su schermo in Teams riunione

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

Introdotto in questo aggiornamento:

- Vedere altri video con la raccolta video 3x3 davanti agli schermi della sala  
- Avviare i sottotitoli locali in tempo reale da MTR
- Partecipare a riunioni zoom da Teams Rooms con partecipazione diretta guest (anteprima)

> [!NOTE]
> La raccolta video 3x3 e i sottotitoli locali in tempo reale vengono forniti tramite il servizio Microsoft Teams. Queste funzionalità sono disponibili per tutti i dispositivi Teams Rooms con l'applicazione 4.5.37.0 e versioni successive.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

Introdotto in questo aggiornamento:

- Riunioni coordinate tra Microsoft Teams e Surface Hub 2S
- Correzione dell'errore di accesso a Skype for Business quando viene installato [l'aggiornamento Windows 10 KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) o [l'aggiornamento Windows 10 KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709)

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

Introdotto in questo aggiornamento:

- Partecipare a riunioni Cisco WebEx da Teams Rooms con partecipazione diretta degli utenti guest
- abilitare e registrazione automatica dell'interfaccia di amministrazione di Teams
- Supporto per i rilasci di Windows 10 1909
- Passare al layout della raccolta video anche quando il contenuto è presente
- Supporto virtuale per alzare le mani per i partecipanti e controlli per il relatore
- Impostazione del volume predefinita regolabile per le conferenze e l'altoparlante predefinito
- Cercare e chiamare utenti federati (tenant) da Teams Room

> [!IMPORTANT]
> La versione 4.5 è l'ultima versione che supporta Windows 10 versione 1803. Le versioni future non saranno disponibili per i sistemi con Windows 10 versione 1803. Per altre informazioni sul supporto per Windows versione, vedere [Windows 10 supporto per i rilasci](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

Introdotto in questo aggiornamento:

- Correzioni di qualità e affidabilità
- Correzione per il problema "l'applicazione non si avvia dopo l'aggiornamento alla 4.4.41.0"

> [!NOTE]
> Se il dispositivo non viene aggiornato automaticamente alla versione 4.4.63.0, seguire i passaggi descritti in [Microsoft Teams Rooms'applicazione non si avvia dopo l'aggiornamento alla versione 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update) per risolvere il problema.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

Introdotto in questo aggiornamento:

- Correzioni dell'affidabilità per l'avvio dell'applicazione in Windows 10 Kiosk

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

Introdotto in questo aggiornamento:

- Supporto dell'autenticazione moderna per Exchange e Skype for Business
- Supporto per le chiamate di emergenza dinamiche per Teams (componenti di servizio necessari e rilasciati con circuiti client Teams)
- Possibilità di disabilitare il contenuto duplicato al di fuori della riunione per le sale con doppio schermo tramite XML
- Schermata iniziale dell'applicazione
- Avvisi del software open source (OSS) nelle impostazioni del dispositivo

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

Introdotto in questo aggiornamento:

- Aggiornamenti dei criteri per "aggiornamenti Windows per le aziende"
- Correzione per la segnalazione di eventi del dispositivo che mostrano un errore in Monitoraggio di Azure

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

Introdotto in questo aggiornamento:

- Correzione di un problema di ridimensionamento/sfarfallio di una finestra che si verifica in determinate configurazioni
- L'elaborazione del calendario per le riunioni di terze parti è stata rimossa
- Cortana impostazione di stato rimossa

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

Introdotto in questo aggiornamento:

- Risposta automatica alle chiamate basate sulla prossimità e impostazione dell'amministratore per controllare
- Aggiornamento dell'interfaccia utente Impostazioni dell'amministratore del dispositivo con l'aggiunta della configurazione del dispositivo nella scheda Informazioni
- Controllo sala torna alla schermata principale
- Sala riunioni SKU disponibile in GCC
- Supporto della fotocamera contenuto per il sistema basato su Surface Pro (build minima dell'app richiesta: 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

Introdotto in questo aggiornamento:

- supporto Windows 10 1903. L'aggiornamento di Windows 10 1903 viene offerto dopo pochi giorni dall'aggiornamento dell'app
- Correzioni per la tastiera su schermo non visualizzata in modo affidabile

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

Introdotto in questo aggiornamento:

- Una nuova funzionalità della fotocamera dei contenuti che consente agli utenti di includere in modo intelligente una lavagna tradizionale nelle riunioni di Teams
- Ulteriori miglioramenti all'interfaccia utente della console per ridurre il disordine e spostare Impostazioni in una nuova barra laterale accessibile tramite Altro nella console
- Pulsante condividi disabilitato se il cavo di contenuto locale non è connesso o se una fotocamera del contenuto non è collegata
- Risoluzione di un problema con la tastiera virtuale a causa del quale non è possibile visualizzarla per la prima volta solo dopo il riavvio del sistema MTR
- Correzioni di qualità e affidabilità

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Introdotto in questo aggiornamento:

- Skype room system store app rebrand to "Microsoft Teams Rooms"
- interfaccia utente della console Microsoft Teams Rooms riallineata a Microsoft Teams
- Aggiornamento del tema: mantieni l'immagine di sfondo personalizzata solo sulla parte anteriore degli schermi della sala, rendendo lo sfondo della console un colore neutro per garantire che i controlli dell'interfaccia utente della console soddisfino il contrasto dei colori( requisiti di accessibilità
- Barra universale per i controlli delle chiamate in riunione per chiamate/riunioni Teams per garantire un'esperienza coerente con Microsoft Teams client PC/Web/<sup>mobile1</sup>
- Valutazione del feedback sulla qualità delle chiamate dopo Teams chiamate/<sup>riunioni1</sup>
- Ricevere/eseguire il rendering di Microsoft Whiteboard Microsoft Teams Rooms visualizzazione della sala quando vengono condivisi da PC/Web/client Teams <sup>mobile1</sup> <sup>2</sup>
- Rimosso il supporto per gli aggiornamenti di Windows 10 versione 1809 a causa di problemi di compatibilità con Microsoft Teams Rooms client. il supporto per Windows 10 versione 19H1 verrà aggiunto nelle versioni future

<sup>1</sup> implementazione del servizio Microsoft Teams con circuiti Teams. Questa funzionalità può essere disponibile prima o dopo l'aggiornamento del client 4.0.105.0

<sup>2</sup> Richiede agli amministratori IT di attivare Microsoft Whiteboard. Inoltre, se si ha una parte anteriore abilitata per il tocco dello schermo della sala, è necessario calibrare più schermi touch utilizzando le impostazioni di Windows con l'accesso dell'amministratore del dispositivo per iniziare a usare Microsoft Whiteboard per la collaborazione da uno schermo della sala condiviso in una riunione di Teams

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Introdotto in questo aggiornamento:

- Risolve un problema con la funzionalità "Invia feedback"
- Ottimizzazioni in preparazione per il prossimo aggiornamento del dispositivo Microsoft Teams Rooms a Windows 10 versione 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Introdotto in questo aggiornamento:

- Correzione del bug "Blocca all'avvio dell'app" che interessava i dispositivi nella build RS2 legacy Windows 10.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introdotto in questo aggiornamento:

- Tastierino numerico DTMF per Microsoft Teams riunioni P2P e chiamate PSTN. Per rendere Microsoft Teams client chiamante predefinito, gli amministratori devono impostare IsTeamsDefaultClient su true
- Aggiungere il video in arrivo di un partecipante remoto a schermo intero davanti allo schermo della sala. Usa il comando "Aggiungi" nell'elenco dei partecipanti sulla console
- Miglioramenti alle notifiche della sala di attesa con l'aggiunta della notifica Davanti alla sala
- La parte anteriore dell'icona di trasmissione dello schermo della sala è stata rimossa quando Bluetooth beacon non è abilitato in Microsoft Teams Rooms dispositivo
- Correzione per il problema del controllo del volume nelle riunioni Teams

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introdotto in questo aggiornamento:

- Visualizzare il contenuto su schermi Front of Room (FoR) su sistemi di sale a doppio schermo
- Miglioramenti dell'interfaccia utente per i tema e la parte anteriore della sala
- Supporto sul lato client TLS 1.2. Per i clienti locali, l'abilitazione della comunicazione tramite TLS 1.2 per Microsoft Teams Rooms richiede l'aggiornamento cumulativo 9 (CU9) Skype for Business Server 2015 o l'aggiornamento cumulativo 1 (CU1) Skype for Business Server 2019.

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introdotto in questo aggiornamento:

- Supporto del doppio schermo (davanti alla sala) per riunioni Teams

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introdotto in questo aggiornamento:

- Correzioni di qualità e affidabilità

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introdotto in questo aggiornamento:

- Modifiche al codice necessarie per preparare l'app Microsoft Teams Rooms per un aggiornamento successivo Windows 10 versione 1803
- Risolvere il problema di formattazione con le EULA localizzate (in particolare norvegese) che impedisce di andare oltre la finestra di configurazione della Configurazione guidata del contratto di licenza EULA
- Modifiche al codice necessarie per eseguire Microsoft Teams Rooms applicazione in Lync Room Systems legacy. Altre informazioni [sono disponibili qui](./lrs-migration.md).

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

Introdotto in questo aggiornamento:

- Hotfix per l'applicazione Crestron non si avvia che normalmente sarebbe accessibile quando viene premuto il pulsante dell'app su un dispositivo Crestron SR. Microsoft Teams Rooms riavvio dell'app richiesto dopo l'installazione della 4.0.19.0.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

Introdotto in questo aggiornamento:

- Miglioramenti delle funzionalità "Segnala un problema" in modalità Teams (equivalente a "Invia feedback" in modalità Skype for Business)
- Consenti la possibilità di tornare dalla modalità Teams alla modalità Skype for Business per le chiamate SIP
- Miglioramenti dell'accessibilità (Assistente vocale, Lente di ingrandimento)
- Riavvia automaticamente l'app quando necessario dopo l'applicazione delle modifiche al provisioning XML
- Correzioni varie

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introdotto in questo aggiornamento:

- Questo aggiornamento consente il supporto per riunioni Skype for Business *e* Teams sui dispositivi Room Systems. Teams è disattivata per impostazione predefinita dopo l'applicazione dell'aggiornamento. Gli amministratori possono abilitare Teams localmente nelle impostazioni del dispositivo o tramite push XML remoto.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introdotto in questo aggiornamento:

- Correzione dell'errore di risoluzione osservato in alcuni sistemi durante l'avvio dell'app.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

Introdotto in questo aggiornamento:

- Modifiche che consentono a Microsoft di gestire in modo più flessibile gli aggiornamenti di Windows.
- Nessuna modifica all'esperienza utente finale.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introdotto in questo aggiornamento:

- Correzione per risolvere i problemi di velocità di risposta della console osservati nei dispositivi basati su Surface Pro 2017 connessi a due display front-of-room e al caricamento video
- Controllo automatico per assicurarsi che il sistema esegua lo script di provisioning più recente

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introdotto in questo aggiornamento:

- Correzione per migliorare il comportamento della tastiera su schermo nei sistemi basati su Windows 10 versione 1709
- Miglioramenti per preparare i futuri aggiornamenti del sistema operativo

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introdotto in questo aggiornamento:

- Applicazione aggiornata per migliorare la telemetria

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introdotto in questo aggiornamento:

- Risolve un problema a causa del quale possono verificarsi problemi intermittenti di partecipazione alle riunioni
- Risolve un problema noto che causa il blocco del dispositivo

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

Introdotto in questo aggiornamento:

- Correzioni di bug/arresti anomali per migliorare la stabilità
- Supporto per console di dimensioni variabili
- Offload dell'elaborazione audio della periferica (elenco di supporti aggiuntivi consentiti)
- Ottimizzazioni che consentono ai professionisti IT di creare immagini fai da te con Windows 10 aggiornamento di gennaio della versione 1709 e successive.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introdotto in questo aggiornamento:

- Risolve un problema con la funzionalità "Invia feedback".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introdotto in questo aggiornamento:

- Supporto per hardware dock [Polycom SERIE MSR](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Supporto per [Logitech Brio](https://www.logitech.com/product/brio)
- Risoluzione di un problema a causa del quale gli schermi (console e front-of-room) non riescono ad attivare la modalità sospensione quando non è presente alcuna attività nella chat room

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introdotto in questo aggiornamento:

- Viene eseguito su un tablet Surface Pro (2017)
- Supporta Windows 10 Enterprise Creator's Update (lingua inglese, build 1703)
- Supporto per hardware dock [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Supporto OEM per i controlli dell'ambiente (Crestron)

La versione a 64 bit di Windows 10 Enterprise Anniversary Edition (lingua inglese, versione 1607) non è più supportata a partire dalla versione Microsoft Teams Rooms 3.0.12.0 (aggiornamento 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introdotto in questo aggiornamento:

- Risoluzione dei problemi riscontrati durante la ricerca di utenti federati tramite il campo di ricerca Partecipanti. Prima di questa correzione, i risultati della ricerca per gli utenti federati esterni potrebbero non essere stati risolti correttamente e restituire invece risultati non corretti.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introdotto in questo aggiornamento:

- supporto Dual-Screen (per la parità di sistema legacy)
- Temi (temi predefiniti e possibilità di impostare un tema personalizzato)
- Possibilità di inviare feedback per le build pubbliche
- Miglioramento della telemetria per l'affidabilità dell'accesso alle riunioni
- Segnalazione OMS migliorata
- Possibilità per l'amministratore IT di configurare i dispositivi in remoto

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introdotto in questo aggiornamento:

- Selezione da parte dell'utente in-app dei dispositivi USB audio e video della sala riunioni
- Report sullo stato della console room integrata per i clienti che usano Microsoft Operations Management Suite, ora Monitoraggio di Azure

### <a name="release-to-market-1272016"></a>Rilascio sul mercato (7/12/2016)

**Caratteristiche:**

 **Progettato per Skype for Business**

- Partecipazione con un tocco alle riunioni Skype
- Riunione Skype esperienza ottimizzata per le stanze con video HD che riempie lo schermo e audio wide-band HD
- Tutti i partecipanti possono connettersi al Riunione Skype utilizzando il dispositivo desiderato ovunque si trovino
- Invitare persone dalla directory in cui è possibile visualizzarne immediatamente la disponibilità o tramite telefonata
- Supporta Skype for Business servizi di conferenza PSTN e chiamate PSTN per sostituire il telefono autonomo per conferenze nella tua sala

 **Trasforma qualsiasi Sala riunioni**

- App dedicata Riunione Skype ottimizzata per il centro del controller touch del tavolo e la grande parte anteriore dello schermo della sala
- Riutilizzare gli investimenti esistenti davanti allo schermo della sala o ai proiettori
- Funziona in tutti i tipi di spazi per riunioni, dagli spazi rannicchiati alle grandi sale riunioni
- Sono disponibili dispositivi audio e video certificati Skype for Business per diverse dimensioni della stanza
- Inserimento cablato incorporato per proiettare la condivisione desktop nella sala e nella Riunione Skype

 **Facile da distribuire, semplice da gestire**

- Accessorio sempre acceso che riattiva automaticamente gli schermi quando rileva persone nella stanza
- Distribuzione e aggiornamento semplici dell'app UWP (piattaforma UWP (Universal Windows Platform)) Riunione Skype
- Windows AppLocker blocca il dispositivo nell'app Riunione Skype
- Monitorato e gestito come dispositivo Windows 10 Enterprise tramite Intune e Configuration Manager (MDM)
- affidabilità di livello Enterprise
- Basso sforzo di formazione degli utenti finali a causa della familiare interfaccia utente Skype
- Funziona su Surface Pro 4 tablet

<a name="See"> </a>
## <a name="see-also"></a>Vedere anche

[Guida Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Predisporre l'ambiente](rooms-prep.md)

[Supporto per le versioni Microsoft Teams Rooms Current Branch](rooms-lifecycle-support.md)

[Problemi noti](known-issues.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).
