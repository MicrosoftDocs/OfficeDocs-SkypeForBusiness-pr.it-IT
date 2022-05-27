---
title: Piano per Microsoft Teams Rooms
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Questo articolo illustra le considerazioni rilevanti relative alla pianificazione per la distribuzione di Microsoft Teams Rooms, la nuova generazione di Skype Room Systems.
ms.openlocfilehash: 5dea2485221fa2755c567fd3ce619c232b4bb6a9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676138"
---
# <a name="plan-microsoft-teams-rooms"></a>Pianificare Microsoft Teams Rooms

Questo articolo introduce un approccio end-to-end alla pianificazione, alla distribuzione e al funzionamento delle Microsoft Teams Rooms nell'ambito della strategia generale per le sale riunioni e le sale riunioni.

Di seguito sono disponibili informazioni di pianificazione che  coprono l'approccio consigliato e le decisioni principali da prendere, con collegamenti a informazioni tecniche di supporto. È consigliabile rivedere le sezioni Pianificare, distribuire e gestire anche se è già stata completamente distribuita.

## <a name="overview-of-microsoft-teams-rooms"></a>Panoramica di Microsoft Teams Rooms

Microsoft Teams Rooms offre un'esperienza di riunione completa che porta video HD, audio e condivisione di contenuti a riunioni di tutte le dimensioni, dalle piccole aree di conferenze alle grandi sale riunioni.

![Un utente tocca una console Teams Rooms, con uno schermo in background.](../media/room-systems-image1.jpg "Un utente tocca una console Teams Rooms, con uno schermo in background")
 [Microsoft Teams Rooms guida](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) è un'ottima risorsa per saperne di più su Microsoft Teams Rooms e su come può aggiungere valore nell'ambito della distribuzione.

## <a name="microsoft-teams-rooms-components"></a>Microsoft Teams Rooms componenti

Microsoft Teams Rooms include i componenti chiave seguenti per offrire un'esperienza utente ottimale:

- Console touchscreen
- Modulo di calcolo
- applicazione Microsoft Teams Rooms
- Periferiche (fotocamera, microfono, altoparlante)
- Schermi esterni (massimo due)
- Ingresso HDMI

È possibile ottenere questi componenti come bundle preinstallati da un certo numero di fornitori oppure acquistare singolarmente i componenti supportati seguendo i [requisiti descritti in questo articolo](requirements.md).

È possibile distribuire Microsoft Teams Rooms con Microsoft Teams o Skype for Business distribuzioni locali.  Per informazioni sulle licenze necessarie, vedere Teams Sala riunioni [Licensing Update](rooms-licensing.md).

| &nbsp;   |  &nbsp;   |
|-----------|------------|
|![decidere la distribuzione.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Si distribuiranno Microsoft Teams Rooms nell'organizzazione? </li><li>Come procurate i vostri sistemi di Microsoft Teams Rooms?</li></ul> |
| ![identificare le attività.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi | <ul><li>Identificare chi eseguirà le attività principali durante l'intera distribuzione.</li><li>Esaminare le sale riunioni disponibili (e pianificare la configurazione) per capire dove distribuire Microsoft Teams Rooms e le periferiche appropriate per le dimensioni della sala.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificare chi eseguirà le attività principali durante l'intera distribuzione

Usare l'approccio illustrato di seguito per illustrare la distribuzione e personalizzare gli output di esempio forniti in base alle esigenze dell'organizzazione.

Iniziare con la comprensione di quali sale riunioni si dispone e immaginare cosa sarebbe più adatto per voi in futuro, quindi spostarsi selezionando e procurando le apparecchiature necessarie, preparando i siti, configurando e distribuendo il servizio, gestendo le modifiche e l'adozione da parte degli utenti, e sviluppando le operazioni e le procedure di manutenzione.

![Iniziare con la comprensione di ciò che si ha e immaginare cosa sarebbe più adatto alle proprie esigenze, quindi spostarsi selezionando e procurando le apparecchiature necessarie, preparando i siti, configurando e distribuendo il servizio, gestendo le modifiche e l'adozione da parte degli utenti e sviluppando le operazioni e le procedure di manutenzione.](../media/room-systems-image2.png "Iniziare con la comprensione di ciò che si ha e immaginare cosa sarebbe più adatto alle proprie esigenze, quindi spostarsi selezionando e procurando le apparecchiature necessarie, preparando i siti, configurando e distribuendo il servizio, gestendo le modifiche e l'adozione da parte degli utenti e sviluppando le operazioni e le procedure di manutenzione.")

Potrebbe essere necessario coordinare queste attività in diversi team. Viene fornita una visualizzazione generale delle principali attività da trattare, oltre a suggerimenti per i team che sono tipicamente coinvolti nella distribuzione e gestione dei sistemi delle sale riunioni, per aiutare l'utente a decidere con chi lavorare.

| Attività                       | Who potrebbe intraprendere l'attività           | Assegnato a | Collegamenti a questo contenuto |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Sale dell'inventario            | Strutture / team AV / Team Project IT |             | [Pianificazione dell'inventario delle sale e delle funzionalità](#room-inventory-and-capability-planning) |
| Pianificare le funzionalità          | Team Project IT                        |             | [Pianificazione dell'inventario delle sale e delle funzionalità](#room-inventory-and-capability-planning) |
| Selezione del dispositivo           | Team it Project/AV              |             | [Selezione del dispositivo](#device-selection) |
| Appalti                | Team it Project/AV              |             | [Appalti](#procurement) |
| Preparazione del sito             | Strutture / team AV / Team Project IT |             | [Preparazione del sito](rooms-deploy.md#site-readiness) |
| Prontezza del servizio          | Team Project IT                        |             | [Prontezza del servizio](rooms-deploy.md#service-readiness) |
| Configurazione              | Team Project IT                        |             | [Configurazione e distribuzione](rooms-deploy.md#configuration-and-deployment) |
| Deployment                 | Strutture / team AV / Team Project IT |             | [Elenco di controllo per la distribuzione](console.md#microsoft-teams-rooms-deployment-checklist) |
| Adozione                   | Strutture / team AV / Team Project IT |             | [Adozione](#plan-for-adoption-and-change-management) |
| Manutenzione e operazioni | Team AV/team Project IT              |             | [Panoramica della gestione](rooms-manage.md) |

## <a name="room-inventory-and-capability-planning"></a>Pianificazione dell'inventario delle sale e delle funzionalità

Il primo passaggio consiste nell'inventariare gli spazi riunioni e le sale riunioni esistenti dell'organizzazione per comprenderne l'ambiente, le dimensioni, il layout e lo scopo. È quindi possibile identificare le funzionalità che si desidera che ogni stanza abbia, ad esempio fotocamere intelligenti, lavagna, fotocamera contenuto e così via.

Dopo aver creato un inventario delle attrezzature e delle funzionalità in ogni chat room esistente, i requisiti per tale sala vengono inseriti nella pianificazione della selezione del dispositivo per creare una soluzione di conferenza avanzata. Le modalità (audio e video) necessarie per ogni chat room, oltre alle dimensioni e allo scopo della chat room, svolgono tutti un ruolo importante nella scelta della soluzione più appropriata per ogni chat room.

Come parte della scoperta, è fondamentale considerare l'acustica e il layout della stanza. Ad esempio, controlla che le sedie nella stanza non blocchino la visualizzazione della fotocamera. Verifica che la stanza non abbia un'eco eccessiva o un aria condizionata rumorosa e che disponga di alimentazione sufficiente per gli schermi e le Microsoft Teams Rooms. Esistono molti fattori da considerare per cui il team o il partner audio-visivo (AV) sarà in grado di consigliare.

| &nbsp;   | &nbsp;    |
|-----------|------------|
| ![camere deplyment.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Esaminare le chat room nell'ambito e definire le relative configurazioni di Microsoft Teams Rooms.</li></ul>|

_Inventario di esempio per riunioni/sale riunioni_

| Sito      | Nome chat room | Tipo di sala | Numero di persone | Nell'ambito? | Funzionalità attuali della chat room           | Funzionalità future per le chat room |
|-----------|-----------|-----------|------------------|-----------|-------------------------------------|--------------------------|
| Sede centrale di Londra | Curie     | Media.    | 6&ndash;12       | Sì       | Vivavoce                        | 1 schermo, audio e video più presentazione<br>Accesso PSTN |
| Sede centrale di Sydney | Collina      | Grande     | 12&ndash;16      | Sì       | Unità AV legacy, 1 schermo e fotocamera | 2 schermi, audio e video più presentazione<br>Accesso PSTN |

## <a name="device-selection"></a>Selezione del dispositivo

Valutare quale Microsoft Teams Rooms soluzione è più adatta per ogni chat room in base alle funzionalità future desiderate per la chat room. Decidi quali periferiche AV sono più adatte, a seconda delle dimensioni e del layout della stanza.

Per indicazioni sul tipo di sistema e dispositivi periferici in base al tipo e alle dimensioni della stanza, vedere l'articolo [sui requisiti di Microsoft Teams Rooms](requirements.md).

In base al fornitore che si preferisce, usare le informazioni fornite nell'articolo sui requisiti per definire la configurazione dei dispositivi periferici Microsoft Teams Rooms e supportati per ogni tipo di chat room e usarla come modello per la distribuzione.

**suggerimento Pro**: alcuni tipi di chat room potrebbero non essere applicabili per la distribuzione.

| &nbsp; | &nbsp; |
|---|---|
| ![stanze nell'ambito.](../media/audio_conferencing_image7.png) <br/>Punti decisionali | <ul><li>Dall'inventario, quali tipi di sale si trovano nell'ambito per la distribuzione?</li><li>Quali sistemi verranno distribuiti per ogni tipo di chat room?</li></ul> |
| ![raccogliere materiale.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi | <ul><li>Inizia a raccogliere materiale operativo chiave per i sistemi scelti e coinvolgi il tuo team di approvvigionamento.</li></ul> |

_Esempio di modello di distribuzione Microsoft Teams Rooms per l'organizzazione_

| Tipo/dimensione stanza     | Numero di persone | Microsoft Teams Rooms sistema | Periferiche | Display(i)      |
|--------------------|------------------|------------------------------|--------------------|-----------------|
| Focus 10' di 9'    | 2&ndash;4        |                              |                    |                 |
| Piccolo 16' per 16'   | 4&ndash;6        |                              |                    |                 |
| Media 18' di 20'  | 6&ndash;12       |                              |                    |                 |
| Grande 15' per 32'   | 12&ndash;16      |                              |                    |                 |

**Pro suggerimento:** è il momento ideale per iniziare a raccogliere informazioni sulla soluzione Microsoft Teams Rooms scelta.

## <a name="procurement"></a>Appalti

Puoi procurarti il sistema scelto come bundle o soluzione integrata tramite partner di dispositivo.

È possibile acquisire Microsoft Teams Rooms da un certo numero di partner elencati [nell'articolo sui requisiti](requirements.md). Visita i siti Web dei partner per ulteriori informazioni su queste soluzioni e opzioni di approvvigionamento.

A seconda della scala e dell'approccio di distribuzione, si potrebbe decidere di spedire i dispositivi periferici Microsoft Teams Rooms e supportati in una posizione centrale per la configurazione iniziale e l'assegnazione. Questo potrebbe essere un buon approccio per un'implementazione a fasi in molti siti. In alternativa, è possibile scegliere di spedire i bundle direttamente nei siti.

| &nbsp; | &nbsp; |
|---|---|
| ![componenti della spedizione.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>I componenti verranno spediti direttamente in un sito o in una struttura di gestione temporanea?</li><li>Who gestirà la struttura di preparazione (se decidete di utilizzarla)?</li></ul> |
| ![piano operativo.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Pianificare le operazioni.</li><li>Pianificare l'adozione e la gestione delle modifiche.</li></ul> |

## <a name="plan-for-operations"></a>Pianificare le operazioni

L'organizzazione deve eseguire attività di monitoraggio, amministrazione e gestione su base continuativa ed è fondamentale accettare chi eseguirà queste attività nelle prime fasi della distribuzione.

Molte organizzazioni hanno un team o un partner AV che gestisce le sale riunioni e i dispositivi. In alternativa, puoi chiedere a Microsoft di aiutarti a gestire Teams Rooms sfruttando Microsoft Teams Rooms Premium. Decidere chi gestirà i dispositivi Microsoft Teams Rooms in futuro per monitorare le prestazioni, nonché distribuire aggiornamenti software e aggiornamenti rapidi.

Valuta a quale coda helpdesk instradare le chiamate correlate a Microsoft Teams Rooms e fornisci le domande frequenti al team helpdesk in modo che possa comprendere meglio come usare Microsoft Teams Rooms e le principali procedure di risoluzione dei problemi che possono eseguire. Un buon punto di partenza per queste domande frequenti è la [Guida dell'utente](https://support.microsoft.com/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) e [i problemi noti](known-issues.md).

| &nbsp; | &nbsp; |
|---|---|
| ![scegliere manager.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà Microsoft Teams Rooms.</li><li>Decidi a quale coda helpdesk instradare le chiamate correlate Microsoft Teams Rooms.</li></ul> |
| ![preparare gli account host.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi |<ul><li>Prepararsi ad ospitare gli account.</li></ul> |

## <a name="plan-for-adoption-and-change-management"></a>Pianificare l'adozione e la gestione delle modifiche

Microsoft Teams Rooms sistemi presentano nuove funzionalità agli utenti. È importante riconoscere che si tratterà di un cambiamento per gli utenti e assicurarsi che la campagna di marketing interna identifichi i vantaggi che il nuovo sistema avrà per gli utenti e i principali punti di discussione che i lead possono usare per discutere con i loro team.

È consigliabile pianificare eventi di presentazione e rilascio di poster in ogni sito per informare gli utenti delle nuove funzionalità. È anche possibile creare "guide introduttive" in sala. È consigliabile trovare un campione di riunioni in ogni sito che possa aiutare gli altri a diventare subito operativi e iniziare a usare i dispositivi.
