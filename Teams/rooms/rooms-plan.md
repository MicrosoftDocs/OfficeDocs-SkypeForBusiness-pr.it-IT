---
title: Piano per Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Questo articolo spiega le considerazioni pertinenti per la pianificazione della distribuzione di Microsoft Teams Room, la nuova generazione di Skype Room Systems.
ms.openlocfilehash: ccc24aea1a45d2aa75c3b1a5de668b520483c2bd
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662471"
---
# <a name="plan-microsoft-teams-rooms"></a>Pianificare le sale di Microsoft Teams

Questo articolo presenta un approccio end-to-end alla pianificazione, distribuzione e gestione delle sale di Microsoft Teams nell'ambito della strategia generale di riunioni e sale riunioni.

Di seguito sono riportate informazioni sulla pianificazione che illustrano l'approccio consigliato e le decisioni chiave che è necessario prendere, con collegamenti a informazioni tecniche di supporto. È consigliabile rivedere le sezioni Piano, Distribuisci e Gestisci anche se si è già completamente distribuiti.

## <a name="overview-of-microsoft-teams-rooms"></a>Panoramica delle sale di Microsoft Teams

Microsoft Teams Rooms offre un'esperienza completa di riunione che porta video HD, audio e condivisione di contenuti alle riunioni di tutte le dimensioni, dalle piccole aree più comuni alle grandi sale riunioni.

![Una console, un microfono e uno schermo di grandi dimensioni montati su una parete di una sala riunioni illustrano gli elementi di un esempio di configurazione di Sale di Microsoft Teams.](../media/room-systems-image1.png "Una console, un microfono e uno schermo di grandi dimensioni montati su una parete di una sala riunioni illustrano gli elementi di un esempio di configurazione di Sale di Microsoft Teams.")

[L'aiuto di Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) è una risorsa importante per saperne di più sulle sale di Microsoft Teams e su come può aggiungere valore durante la distribuzione. Inoltre, ti consigliamo di guardare questo [video di panoramica.](https://youtu.be/tNey5KZVCl0) 

## <a name="microsoft-teams-rooms-components"></a>Componenti di Microsoft Teams Rooms

Microsoft Teams Rooms include i seguenti componenti principali per offrire un'esperienza utente ottimale:

- Pannello di controllo touchscreen
- Calcolare
- Applicazione Microsoft Teams Rooms
- Dock/extender
- Periferiche (videocamera, microfono, altoparlante)
- Schermi esterni (al massimo due)
- Ingresso HDMI

È possibile acquistare questi componenti come pacchetti preinstallati da diversi fornitori oppure acquistare i componenti supportati singolarmente seguendo i requisiti documentati [in questo articolo.](requirements.md)

Oltre alla combinazione Surface Pro/Dock, è anche possibile acquistare sale di Microsoft Teams con il pannello di controllo touchscreen, il calcolo, il dock e i principali dispositivi periferiche integrati. 

In genere, i pacchetti e le unità integrate includono software preinstallato, mentre se acquisti i componenti supportati singolarmente per i sistemi Surface Pro, dovrai installare il software. Per istruzioni, vedere [questo articolo sull'installazione di software nei dispositivi.](rooms-scale.md) 

È possibile distribuire le sale di Microsoft Teams con Microsoft Teams, Skype for Business Online o distribuzioni ibride o locali di Skype for Business.  Per informazioni [sulle licenze necessarie,](rooms-licensing.md) vedere l'aggiornamento delle licenze per le sale riunioni di Teams.

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verranno distribuite le sale di Microsoft Teams nell'organizzazione? </li><li>Come si procurono i sistemi Microsoft Teams Rooms in bundle, come componenti separati o come unità integrata?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi | <ul><li>Identificare chi dovrà svolgere le attività chiave durante l'intera distribuzione.</li><li>Esaminare le sale riunioni disponibili (e pianificare la configurazione) per sapere dove distribuire le sale di Microsoft Teams e i dispositivi periferiche appropriati per le dimensioni della sala.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificare chi dovrà svolgere le attività chiave durante l'intera distribuzione

Usare l'approccio illustrato di seguito per eseguire le operazioni di distribuzione e personalizzare gli output di esempio forniti in questi articoli in base alle esigenze dell'organizzazione.

Iniziare con la comprensione delle sale riunioni disponibili e con la pianificazione della migliore soluzione per il futuro, quindi passare alla selezione e alla distribuzione delle apparecchiature necessarie, alla configurazione dei siti, alla configurazione e alla distribuzione del servizio, alla gestione delle modifiche e dell'adozione da parte degli utenti e allo sviluppo di operazioni e procedure di manutenzione.

![Iniziare con la comprensione del proprio sito e con la pianificazione della soluzione più adatta alle proprie necessità, quindi spostarsi selezionando e procurando le apparecchiature necessarie, preparando i siti, configurando e distribuendo il servizio, gestendo le modifiche e l'adozione da parte degli utenti e sviluppando operazioni e procedure di manutenzione.](../media/room-systems-image2.png "Iniziare con la comprensione del proprio sito e con la pianificazione della soluzione più adatta alle proprie necessità, quindi spostarsi selezionando e procurando le apparecchiature necessarie, preparando i siti, configurando e distribuendo il servizio, gestendo le modifiche e l'adozione da parte degli utenti e sviluppando operazioni e procedure di manutenzione.")

Potrebbe essere necessario coordinare queste attività tra diversi team. Microsoft offre una descrizione generale delle principali attività da gestire, oltre a suggerimenti per i team in genere coinvolti nella distribuzione e nella gestione dei sistemi delle sale riunioni, per aiutare a decidere con chi è necessario collaborare.

| Attività                       | Chi può intraprendere l'attività           | Assegnato a | Collegamenti a questo contenuto |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Sale dell'inventario            | Strutture / Team AV /Team di progetto IT |             | [Inventario delle chat room e pianificazione delle funzionalità](#room-inventory-and-capability-planning)        |
| Funzionalità del piano          | Team di progetto IT                        |             | [Inventario delle chat room e pianificazione delle funzionalità](#room-inventory-and-capability-planning)                       |
| Selezione del dispositivo           | Team di progetto IT/team AV              |             | [Selezione del dispositivo](#device-selection)                      |
| Approvvigionamento                | Team di progetto IT/team AV              |             | [Approvvigionamento](#procurement)                      |
| Conformità del sito             | Strutture / Team AV /Team di progetto IT |             | [Conformità del sito](rooms-deploy.md#site-readiness)                      |
| Prontezza del servizio          | Team di progetto IT                        |             | [Prontezza del servizio](rooms-deploy.md#service-readiness)                      |
| Configurazione              | Team di progetto IT                        |             | [Configurazione e distribuzione](rooms-deploy.md#configuration-and-deployment)                      |
| Deployment                 | Strutture / Team AV /Team di progetto IT |             | [Elenco di controllo per la distribuzione](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Adozione                   | Strutture / Team AV /Team di progetto IT |             | [Adozione](#plan-for-adoption-and-change-management)                      |
| Manutenzione e operazioni | Team AV /Team di progetto IT              |             | [Panoramica della gestione](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Inventario delle chat room e pianificazione delle funzionalità

Il primo passaggio consiste nell'eseguire l'inventario delle sale riunioni e conferenze esistenti dell'organizzazione per comprenderne l'ambiente, le dimensioni, il layout e lo scopo e per identificare le funzionalità che si vuole che ogni sala nell'ambito abbia in futuro, ad esempio quali funzionalità di collaborazione più avanzate saranno abilitate nella sala. 

Dopo aver creato un inventario delle apparecchiature e delle funzionalità in ogni sala esistente, i requisiti per il feed della sala nella pianificazione della selezione del dispositivo per creare una soluzione di conferenza completa. Le modalità (audio, video) necessarie per ogni stanza, oltre alle dimensioni e allo scopo della sala, svolgono tutti un ruolo importante nel decidere quale soluzione è più appropriata per ogni stanza. 

Come parte della tua scoperta, è fondamentale considerare l'acustica e il layout della stanza. Ad esempio, verificare che le sedie nella stanza non blocchino la vista della fotocamera. Verificare che la stanza non abbia un'eco eccessiva o condizioni d'aria rumorose e che abbia una potenza sufficiente per gli schermi e le sale di Microsoft Teams. Ci sono molti fattori da considerare sul fatto che il team audio-visivo (AV) o il partner sarà in grado di fornire consigli. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Quali chat room sono nell'ambito per questa distribuzione?</li><li>Quali siti sono nell'ambito della distribuzione?</li><li>Chi farà l'inventario delle sale riunioni?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Esaminare le sale nell'ambito e definire le configurazioni di Sale di Microsoft Teams per loro.</li></ul>|

_Esempio di inventario di riunioni/sale riunioni_

| Sito  | Nome chat room | Tipo di sala | Numero di persone  | Nell'ambito? | Funzionalità della chat room corrente       | Funzionalità future per le chat room     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| London HQ | Curie         | Media.        | 6 &ndash; 12                  | Sì          | Vivavoce                        | 1 schermo, audio e video più presentazione<br>Accesso PSTN |
| Sydney HQ | Hill          | Grande         | 12 &ndash; 16                 | Sì          | Unità AV legacy, 1 schermo e fotocamera | 2 schermi, audio e video più presentazione<br>Accesso PSTN |

## <a name="device-selection"></a>Selezione del dispositivo 

Valutare quale soluzione Sale di Microsoft Teams è la più adatta per ogni sala in base alle funzionalità future desiderate per la sala. Stabilire quali sono le periferiche AV più adatte, a seconda delle dimensioni della stanza e del layout. 

Per indicazioni sul tipo di sistema e periferiche per tipo e dimensioni della sala, vedere l'articolo sui requisiti per le sale [di Microsoft Teams.](requirements.md) 

In base al fornitore che si preferisce, usare le informazioni fornite nell'articolo sui requisiti per definire le sale di Microsoft Teams e la configurazione delle periferiche supportate per ogni tipo di sala e usarle come modello per la distribuzione. 

**Suggerimento per professionisti:** alcuni tipi di chat room potrebbero non essere applicabili per la distribuzione.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Quali tipi di chat room hanno l'ambito per la distribuzione dell'inventario?</li><li>Quali sistemi verranno distribuiti per ogni tipo di sala?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a raccogliere materiale operativo chiave per i sistemi scelti e coinvolgere il team di approvvigionamento.</li></ul>|

_Modello di distribuzione sale di Microsoft Teams di esempio per l'organizzazione_

| **Tipo/dimensioni sala** | **Numero di persone**  | **Sistema Microsoft Teams Rooms** | **Periferiche**  | **Display(s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Focus 10' by 9'      | 2 &ndash; 4                   |                                  |                         |                 |
| Piccoli 16' per 16'     | 4 &ndash; 6                   |                                  |                         |                 |
| Media 18' per 20'    | 6 &ndash; 12                  |                                  |                         |                 |
| Grande 15' per 32'     | 12 &ndash; 16                 |                                  |                         |                 |

**Suggerimento per professionisti -** È il momento giusto per iniziare a raccogliere informazioni sulla soluzione Room di Microsoft Teams scelta.

## <a name="procurement"></a>Approvvigionamento 

È possibile acquistare il sistema scelto come bundle o come soluzione integrata tramite partner di dispositivi. Puoi anche acquisire un dock di dispositivi partner e preparare la tua soluzione Microsoft Teams Rooms utilizzando un dispositivo Surface Pro e le periferiche _AV_ esistenti supportate. 

È possibile acquisire sale di Microsoft Teams da diversi partner elencati nell'articolo [dei requisiti.](requirements.md) Visita i siti Web dei partner per altre informazioni su queste soluzioni e le opzioni di approvvigionamento. 

A seconda della scala di distribuzione e dell'approccio, si potrebbe decidere di spedire le sale di Microsoft Teams e le periferiche supportate in una posizione centrale per la configurazione e l'assegnazione iniziali. Si tratta di un buon approccio per un'implementazione a fasi in molti siti. In caso contrario, puoi scegliere di spedire i pacchetti direttamente ai tuoi siti. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>I componenti verranno spediti direttamente a un sito o a una struttura di preparazione?</li><li>Chi gestirà la struttura di gestione temporanea (se si decide di usarla)?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Pianificare le operazioni.</li><li>Pianificare l'adozione e la gestione delle modifiche.</li></ul>|

## <a name="plan-for-operations"></a>Pianificare le operazioni 

L'organizzazione deve eseguire attività di monitoraggio, amministrazione e gestione su base continuativa ed è fondamentale concordare chi eseguirà queste attività all'inizio della distribuzione. 

Molte organizzazioni hanno un team o un partner AV che gestisce le sale riunioni e i dispositivi. Questo team dovrebbe essere coinvolto nell'accettare chi gestirà i dispositivi di Microsoft Teams Room per monitorare le prestazioni e distribuire aggiornamenti software e aggiornamenti rapidi. 

Considerare la coda helpdesk a cui instradare le chiamate di Microsoft Teams Rooms֪ e fornire una domanda frequente al team helpdesk, in modo che possa comprendere meglio come usare le sale di Microsoft Teams e le principali procedure di risoluzione dei problemi che possono eseguire. Un buon punto di partenza per queste domande frequenti è la [Guida per l'utente](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) e [i problemi noti.](known-issues.md)

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà le sale di Microsoft Teams.</li><li>Decidere a quale coda helpdesk instradare le sale di Microsoft Teams.</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Preparare l'hosting degli account. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Pianificare l'adozione e la gestione delle modifiche

I sistemi Microsoft Teams Rooms introducono nuove funzionalità agli utenti. È importante riconoscere che si tratta di un cambiamento per gli utenti e assicurarsi che la campagna identifichi i vantaggi che il nuovo sistema avrà per gli utenti e i principali punti di discussione che possono usare per discutere con i loro team. 

Prendere in considerazione la pianificazione di eventi show-and-tell in ogni sito per informare gli utenti delle nuove funzionalità. È anche possibile creare "guide introduttive" nella sala. È consigliabile trovare un campione delle riunioni in ogni sito per aiutare gli altri a diventare subito disponibili e iniziare a usare i dispositivi.
