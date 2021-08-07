---
title: Note sulla versione per Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: L'amministratore può leggere le note sulla versione per Microsoft Teams Rooms, che elencano i miglioramenti cumulativi Microsoft Teams Rooms.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f870f746a5ff085fc997d9071ba243e43a8046b0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772727"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Note sulla versione per Microsoft Teams Rooms

Questo articolo illustra i miglioramenti cumulativi Microsoft Teams Rooms.

## <a name="version-history"></a>Cronologia versioni

|Rilascio |Pubblicato in <br/> Microsoft Store |
|--- |--- |
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

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Microsoft Teams Rooms introduzione alle funzionalità e risoluzione dei problemi

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

Introdotto in questo aggiornamento:
- Microsoft Teams è ora disponibile nelle impostazioni dell'applicazione, quindi non è più necessario configurare un account Skype for Business account. In questa modalità, i dispositivi connessi a Teams solo in modalità Skype for Business riunioni come utente guest.
- Correzione dell'audio HDMI che causa un volume di chiamata inferiore. La funzionalità audio HDMI viene abilitata automaticamente per tutti i dispositivi con la build dell'applicazione 4.9.12.0.

> [!NOTE]
> Con Skype for Business fine del ciclo di vita, è consigliabile eseguire l'aggiornamento alla modalità Teams solo fine vita.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

Introdotto in questo aggiornamento:
- Windows 10 20H2 

> [!NOTE]
> Crestron UC-Engine (data della versione del BIOS che contiene "KYSKLi") Teams Rooms problemi di compatibilità e i driver aggiornati verranno forniti dagli OEM di sistema nel prossimo futuro. Windows 10 20H2 non verrà offerto a questi dispositivi. Per altre informazioni sul supporto Windows versione, vedere Windows 10 [versione.](./rooms-lifecycle-support.md#windows-10-release-support)

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

Introdotto in questo aggiornamento:
- Correzione per un problema per cui le informazioni sulle chat room Teams Rooms console non vengono visualizzate per gli account della chat room nascosti all'elenco indirizzi globale

> [!NOTE]
> I clienti GCCH possono scaricare il pacchetto di aggiornamento da [Aggiornare manualmente un Microsoft Teams Rooms dispositivo](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

Introdotto in questo aggiornamento:
- Government Community Cloud Supporto elevato (GCCH) per Teams Rooms. I clienti GCCH con dispositivi Teams Rooms esistenti possono scaricare la versione 4.8.19.0 da Aggiornare manualmente [un Microsoft Teams Rooms dispositivo](manual-update.md)
- Partecipare alle riunioni zoom con una migliore qualità video (supporto di 720p) e ricevere la raccolta video dei partecipanti
- Skype for Business banner di errore di accesso rimosso per Teams modalità predefinita. Questa modifica supporta la rimozione dell'infrastruttura Skype for Business aziendale
- Teams le riunioni che aderiscono all'analisi dei collegamenti ora gestisce i collegamenti Cassaforte Microsoft Defender Advanced Thread Protection per consentire l'aggiunta di Teams esterni senza problemi
- Risolvere il problema di ridimensionamento del contenuto condiviso Skype for Business riunioni quando nel PC del condivisore è impostato un valore DPI personalizzato in Windows
- Correzioni di qualità e affidabilità

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

Introdotto in questo aggiornamento:
- Correzioni di qualità e affidabilità

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

Introdotto in questo aggiornamento:

- Condividere l'audio HDMI con i partecipanti alla riunione Teams riunione
- Cortana vocali (anteprima)
- Impedire l'riattivazione dell'audio in base alle autorizzazioni audio Teams la chat room viene aggiunta come partecipante. Per altre informazioni, vedere Gestire le autorizzazioni audio dei partecipanti [nelle Teams riunioni.](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a)
- Mettere in evidenza il video di qualcuno dalla console Teams Room e usare il video in evidenza sugli schermi delle chat room

> [!NOTE]
> Cortana voce sono disponibili per le periferiche audio selezionate per i tenant che si trovano negli Stati Uniti. Altri paesi o aree geografiche verranno aggiunti in futuro. Per altre informazioni, vedere Cortana [assistenza vocale in Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

Introdotto in questo aggiornamento:

- Correzione per il mezzo schermo bianco quando si richiama la tastiera su schermo in una Teams riunione

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

Introdotto in questo aggiornamento:

- Guarda altri video con la raccolta video 3x3 davanti agli schermi della sala  
- Avviare sottotitoli codificati in tempo reale locali da MTR
- Partecipare alle riunioni di Zoom Teams Rooms con l'accesso guest diretto (anteprima)

> [!NOTE]
> La raccolta video 3x3 e i sottotitoli codificati in tempo reale locali vengono recapitati tramite il Microsoft Teams servizio. Queste funzionalità sono disponibili per tutti i Teams Rooms con l'applicazione 4.5.37.0 e versioni successive.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

Introdotto in questo aggiornamento:

- Riunioni coordinate tra Microsoft Teams e Surface Hub 2S
- Correzione dell'Skype di accesso a Windows 10'aggiornamento [KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) o Windows 10 è installato [l'aggiornamento KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709)

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

Introdotto in questo aggiornamento:

- Partecipare alle riunioni Cisco WebEx da Teams Rooms con l'accesso guest diretto
- Teams Abilitazione e registrazione automatica dell'interfaccia di amministrazione
- Windows 10 rilascio del 1909
- Passare al layout della raccolta video anche quando il contenuto è presente
- Supporto virtuale per alzare le mani per i partecipanti e i controlli per il relatore
- Impostazione del volume predefinita regolabile per i servizi di conferenza e l'altoparlante predefinito
- Cercare e chiamare utenti federati (tenant) da Teams Room

> [!IMPORTANT]
> La versione 4.5 è l'ultima versione per supportare Windows 10 1803; le versioni future non verranno offerte ai sistemi Windows 10 versione 1803. Per altre informazioni sul supporto Windows versione, vedere Windows 10 [versione.](./rooms-lifecycle-support.md#windows-10-release-support)

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

Introdotto in questo aggiornamento:

- Correzioni di qualità e affidabilità
- Correzione per il problema "L'applicazione non viene avviata dopo l'aggiornamento alla versione 4.4.41.0"

> [!NOTE]
> Se il dispositivo non viene aggiornato automaticamente alla versione 4.4.63.0, seguire la procedura descritta nell'applicazione Microsoft Teams Rooms non viene avviata dopo l'aggiornamento alla [versione 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update) per risolvere il problema.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

Introdotto in questo aggiornamento:

- Correzioni di affidabilità per l'avvio delle applicazioni in Windows 10 Kiosk

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

Introdotto in questo aggiornamento:

- Supporto dell'autenticazione moderna per Exchange e Skype for Business
- Supporto per chiamate di emergenza dinamiche per Teams (componenti di servizio necessari e rilasciati Teams squilli dei client)
- Possibilità di disabilitare il contenuto duplicato fuori riunione per le sale con doppio display con XML
- Schermata iniziale dell'applicazione
- Avvisi sul software Open Source (OSS) nelle impostazioni del dispositivo

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

Introdotto in questo aggiornamento:

- Aggiornamenti dei criteri per "Windows aggiornamenti per le aziende"
- Correzione per la segnalazione di eventi del dispositivo che mostra un errore in Monitor di Azure

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

Introdotto in questo aggiornamento:

- Correzione di un problema di ridimensionamento/sfarfallio della finestra visualizzato in determinate configurazioni
- Elaborazione del calendario per le riunioni di terze parti rimossa
- Cortana stato di rimozione

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

Introdotto in questo aggiornamento:

- Rispondere automaticamente alle chiamate basate sulla prossimità e all'impostazione dell'amministratore per controllare questo
- L'amministratore Impostazioni'interfaccia utente con l'aggiunta della configurazione del dispositivo nella scheda Informazioni
- Controllo sala torna alla schermata principale
- Sala riunioni SKU disponibile in GCC
- Supporto della fotocamera Surface Pro sistema basato su contenuto (build minima dell'app richiesta: 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

Introdotto in questo aggiornamento:

- Windows 10 1903. Windows 10'aggiornamento 1903 viene offerto tra pochi giorni dopo l'aggiornamento dell'app
- Correzioni per la tastiera su schermo non visualizzate in modo affidabile

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

Introdotto in questo aggiornamento:

- Una nuova funzionalità della fotocamera del contenuto che consente agli utenti di includere in modo intelligente una lavagna tradizionale nella riunione Teams riunione
- Altri miglioramenti all'interfaccia utente della console per ridurre i messaggi secondari e Impostazioni in una nuova barra laterale a cui si accede tramite Altro nella console
- Pulsante Di condivisione disabilitato se il cavo del contenuto locale non è connesso o se una fotocamera del contenuto non è connessa
- È stato risolto un problema relativo alla tastiera virtuale in cui l'errore si verificava la prima volta solo dopo il riavvio del sistema MTR
- Correzioni di qualità e affidabilità

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Introdotto in questo aggiornamento:

- Skype Riequilibrio dell'app Room System Store in "Microsoft Teams Rooms"
- Microsoft Teams Rooms'interfaccia utente della console riallineata a Microsoft Teams
- Aggiornamento del tema: mantenere l'immagine di sfondo personalizzata solo davanti agli schermi della sala, rendendo lo sfondo della console un colore neutro per garantire che i controlli dell'interfaccia utente della console soddisfino il contrasto dei colori, requisiti di accessibilità
- Barra universale per i controlli delle chiamate in riunione per Teams chiamate/riunioni per offrire un'esperienza coerente con Microsoft Teams pc/Web/client mobili<sup>1</sup>
- Valutazione del feedback sulla qualità delle chiamate dopo Teams chiamate/riunioni<sup>1</sup>
- Ricezione/rendering Microsoft Whiteboard sul Microsoft Teams Rooms della chat room quando viene condiviso da PC/ Web/ Mobile Teams client<sup>1</sup> <sup>2</sup>
- È stato rimosso il supporto Windows 10 aggiornamenti della versione 1809 a causa di problemi di compatibilità con Microsoft Teams Rooms client. Windows 10 Il supporto della versione 19H1 verrà aggiunto nelle versioni future

<sup>1</sup> Microsoft Teams di servizio con Teams squilli. Questa funzionalità potrebbe essere disponibile prima o dopo l'aggiornamento del client 4.0.105.0

<sup>2</sup> Richiede agli amministratori IT di attivare Microsoft Whiteboard. Inoltre, se si dispone di una parte anteriore abilitata per il tocco dello schermo della sala, è necessario calibrare più schermi tocco usando le impostazioni di Windows con l'accesso dell'amministratore del dispositivo per iniziare a usare Microsoft Whiteboard per la collaborazione da uno schermo della sala condiviso in una riunione di Teams

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Introdotto in questo aggiornamento:

- Risolve un problema con la funzionalità "Invia feedback"
- Ottimizzazioni in preparazione per il prossimo aggiornamento Microsoft Teams Rooms dispositivo a Windows 10 versione 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Introdotto in questo aggiornamento:

- Correzione del bug "Blocca all'avvio dell'app" che ha interessato i dispositivi nella build legacy Windows 10 RS2.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introdotto in questo aggiornamento:

- Tastierino DTMF per Microsoft Teams riunioni P2P e chiamate PSTN. Per impostare Microsoft Teams client chiamante predefinito, gli amministratori devono impostare IsTeamsDefaultClient su true
- Aggiungere il video in arrivo di un partecipante remoto a schermo intero davanti allo schermo della sala. Usare il comando "Aggiungi" dall'elenco dei partecipanti nella console
- Miglioramenti alle notifiche della sala d'attesa con l'aggiunta della notifica Davanti alla sala
- Icona di fusione dello schermo della sala rimossa quando Bluetooth beacon non è abilitato Microsoft Teams Rooms dispositivo
- Risolvere il problema di controllo del volume nelle Teams riunioni

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introdotto in questo aggiornamento:

- Visualizzare il contenuto su entrambi gli schermi Front of Room (FoR) nei sistemi di sala a doppio schermo
- Miglioramenti all'interfaccia utente di Theming e Front of Room
- Supporto lato client TLS 1.2. Per i clienti locali, l'abilitazione delle comunicazioni tramite TLS 1.2 per Microsoft Teams Rooms richiede Skype for Business Server 2015 l'aggiornamento cumulativo 9 (CU9) o Skype for Business Server 2019 cumulativo 1 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introdotto in questo aggiornamento:

- Supporto dual display (fronte sala) per Teams riunioni

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introdotto in questo aggiornamento:

- Correzioni di qualità e affidabilità

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introdotto in questo aggiornamento:

- Modifiche del codice necessarie per preparare l'app Microsoft Teams Rooms per un Windows 10 versione 1803
- Risolvere i problemi di formattazione con gli EULA localizzati (in particolare il norvegese) che impediscono l'avanzamento oltre la finestra di configurazione di Exchange 2010
- Modifiche al codice necessarie per eseguire Microsoft Teams Rooms'applicazione nei sistemi lync room legacy. Per altre [informazioni, vedere .](./lrs-migration.md)

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

Introdotto in questo aggiornamento:

- Aggiornamento rapido per l'avvio dell'applicazione Crestron che normalmente sarebbe accessibile quando si preme il pulsante dell'app in un dispositivo Crestron SR. Microsoft Teams Rooms riavvio dell'app richiesto dopo l'installazione di 4.0.19.0.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

Introdotto in questo aggiornamento:

- Miglioramenti alla funzionalità "Segnala un problema" in Teams (equivalente a "Invia feedback" in Skype for Business modalità)
- Abilitare la possibilità di tornare dalla modalità Teams alla modalità Skype for Business per le chiamate SIP
- Miglioramenti all'accessibilità (Assistente vocale, Lente di ingrandimento)
- Riavvia automaticamente l'app quando necessario dopo l'applicazione delle modifiche al provisioning XML
- Correzioni varie

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introdotto in questo aggiornamento:

- Questo aggiornamento abilita il supporto Skype for Business *e* Teams riunioni nei dispositivi Room Systems. Teams è disattivato per impostazione predefinita dopo l'applicazione dell'aggiornamento. Gli amministratori possono abilitare la Teams locale nelle impostazioni del dispositivo o tramite un push xml remoto.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introdotto in questo aggiornamento:

- Correzione dell'errore osservato in alcuni sistemi durante l'avvio dell'app.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

Introdotto in questo aggiornamento:

- Modifiche che consentono a Microsoft di gestire in modo più flessibile Windows aggiornamenti.
- Nessuna modifica all'esperienza utente finale.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introdotto in questo aggiornamento:

- Correzione per risolvere i problemi di velocità di risposta della console osservati nei dispositivi basati su Surface Pro 2017 connessi a due schermi front-of-room e all'inserimento di video
- Controllo automatico per assicurarsi che il sistema eserciti lo script di provisioning più recente

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introdotto in questo aggiornamento:

- Correzione per migliorare il comportamento di OSK (tastiera su schermo) nei sistemi basati su Windows 10 versione 1709
- Miglioramenti per prepararsi per gli aggiornamenti futuri del sistema operativo

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introdotto in questo aggiornamento:

- Applicazione aggiornata per migliorare la telemetria

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introdotto in questo aggiornamento:

- Risolve un problema per cui possono verificarsi problemi di partecipazione a riunioni intermittenti
- Risolve un problema noto che causa il blocco di un dispositivo

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

Introdotto in questo aggiornamento:

- Correzioni di bug/arresti anomalo per migliorare la stabilità
- Supporto per console di dimensioni variabili
- Offload dell'elaborazione audio periferica (elenco di supporti aggiuntivi consentiti)
- Ottimizzazioni che consentono ai professionisti IT di creare immagini personalizzate con Windows 10 aggiornamento di gennaio 1709 e successive.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introdotto in questo aggiornamento:

- Risolve un problema con la funzionalità "Invia feedback".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introdotto in questo aggiornamento:

- Supporto per [l'hardware dock polycom serie MSR](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Supporto per [Logitech Brio](https://www.logitech.com/product/brio)
- Risolve un problema per cui gli schermi (console e front-of-room) non riescono a entrare in modalità sospensione quando non ci sono attività nella chat room

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introdotto in questo aggiornamento:

- Viene eseguito su un tablet Surface Pro (2017)
- Supporta Windows 10 Enterprise Creator's Update (lingua inglese, build 1703)
- Supporto per [l'hardware del dock Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Supporto OEM per i controlli dell'ambiente (Crestron)

La versione a 64 bit di Windows 10 Enterprise Anniversary Edition (lingua inglese, versione 1607) non è più supportata a Microsoft Teams Rooms versione 3.0.12.0 (aggiornamento 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introdotto in questo aggiornamento:

- Risolve i problemi osservati durante la ricerca di utenti federati tramite il campo di ricerca Partecipanti. In precedenza, i risultati della ricerca per gli utenti federati esterni potrebbero non essere stati risolti correttamente e invece restituiti risultati non corretti.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introdotto in questo aggiornamento:

- Dual-Screen (per la parità di sistema legacy)
- Temi (temi predefiniti e possibilità di impostare temi personalizzati)
- Possibilità di inviare commenti e suggerimenti per le build pubbliche
- Telemetria migliorata per l'affidabilità delle partecipate alle riunioni
- Creazione di report OMS migliorata
- Possibilità per l'amministratore IT di configurare i dispositivi in remoto

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introdotto in questo aggiornamento:

- Selezione utente in-app di dispositivi USB audio e video della sala riunioni
- Report sullo stato della console della chat room integrato per i clienti che usano Microsoft Operations Management Suite, ora Azure Monitor

### <a name="release-to-market-1272016"></a>Rilascio sul mercato (7/12/2016)

**Caratteristiche:**

 **Progettato per Skype for Business**

- Partecipazione con un solo tocco Skype riunioni
- Riunione Skype ottimizzata per le sale con video HD con riempimento dello schermo e audio wide band HD
- Tutti i partecipanti possono connettersi al Riunione Skype usando il dispositivo scelto ovunque si trovino
- Invita persone dalla tua directory dove puoi vedere immediatamente la loro disponibilità o tramite una telefonata
- Supporta Skype for Business servizi di conferenza PSTN e chiamate PSTN per sostituire il telefono da conferenza autonomo nella stanza

 **Trasforma qualsiasi Sala riunioni**

- App dedicata Riunione Skype ottimizzata per il centro del controller del tocco da tavolo e la grande parte anteriore dello schermo della sala
- Riutilizzare gli investimenti esistenti davanti al display o ai proiettori della sala
- Funziona in tutti i tipi di spazi riunioni, dagli spazi più piccoli alle sale riunioni di grandi dimensioni
- I Skype for Business audio e video certificati sono disponibili per diverse dimensioni della sala
- Inserimento cablato incorporato per proiettare la condivisione desktop nella chat room e nel Riunione Skype

 **Facile da distribuire, semplice da gestire**

- Appliance always-on che riattiva automaticamente gli schermi quando rileva le persone nella stanza
- Distribuzione e aggiornamento semplici dell'app UWP (Universal Windows Platform) Riunione Skype App
- Windows AppLocker blocca il dispositivo nell'app Riunione Skype app
- Monitorato e gestito come dispositivo Windows 10 Enterprise tramite Intune e Configuration Manager (MDM)
- Enterprise livello di affidabilità
- Scarso sforzo di formazione degli utenti finali a causa della Skype interfaccia utente
- Viene eseguito su Surface Pro 4 tablet

<a name="See"> </a>
## <a name="see-also"></a>Vedere anche

[Guida Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Predisporre l'ambiente](rooms-prep.md)

[Supporto per le Microsoft Teams Rooms Current Branch](rooms-lifecycle-support.md)

[Problemi noti](known-issues.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).
