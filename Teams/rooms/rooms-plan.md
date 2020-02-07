---
title: Pianificare le sale di Microsoft Teams
ms.author: v-lanac
author: lanachin
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
description: Questo articolo illustra le considerazioni relative alla pianificazione per la distribuzione di Microsoft teams rooms, la nuova generazione di sistemi room Skype.
ms.openlocfilehash: 1d5236c522a0f3da6f2c2686e34db9d665a93d15
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825894"
---
# <a name="plan-microsoft-teams-rooms"></a>Pianificare le sale di Microsoft Teams

Questo articolo introduce un approccio end-to-end per pianificare, distribuire e gestire le sale di Microsoft teams nell'ambito della strategia complessiva per riunioni e conferenze.

Le informazioni sulla pianificazione di seguito riguardano l'approccio consigliato e le decisioni chiave che è necessario apportare, con collegamenti a supporto delle informazioni tecniche. Ti consigliamo di rivedere il piano, distribuire e gestire le sezioni anche se sei già completamente distribuito.

## <a name="overview-of-microsoft-teams-rooms"></a>Panoramica delle sale di Microsoft Teams

Microsoft teams Rooms offre un'esperienza di riunione completa che consente la condivisione di video, audio e contenuti HD per le riunioni di tutte le dimensioni, dalle piccole aree di calco alle ampie sale riunioni.

![Una console, un microfono e uno schermo grande montato su una parete della sala riunioni illustrano gli elementi di un esempio di configurazione di Microsoft teams rooms.](../media/room-systems-image1.png "Una console, un microfono e uno schermo grande montato su una parete della sala riunioni illustrano gli elementi di un esempio di configurazione di Microsoft teams rooms.")

La [Guida di Microsoft teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) è un'ottima risorsa per scoprire altre informazioni sulle sale di Microsoft teams e su come può aggiungere valore come parte della distribuzione. In più, ti consigliamo di guardare questo [video introduttivo](https://youtu.be/tNey5KZVCl0). 

## <a name="microsoft-teams-rooms-components"></a>Componenti di Microsoft teams rooms

Microsoft teams rooms include i componenti chiave seguenti per offrire un'esperienza utente ottimale:

- Pannello di controllo touchscreen
- Calcolare
- Applicazione Microsoft teams rooms
- Ancoraggio/estensione
- Periferiche (fotocamera, microfono, altoparlante)
- Schermate esterne (massimo due)
- Ingresso HDMI

Puoi ottenere questi componenti come bundle preinstallati da diversi fornitori oppure puoi acquistare singolarmente i componenti supportati seguendo i [requisiti documentati in questo articolo](requirements.md).

Oltre alla combinazione Surface Pro/Dock, è possibile acquistare anche le sale di Microsoft teams con il pannello di controllo touchscreen, il calcolo, il Dock e le periferiche principali integrate. 

In genere, i bundle e le unità integrate includono il software preinstallato, mentre se si acquistano componenti supportati singolarmente per i sistemi Surface Pro, è necessario installare il software. Per istruzioni, vedere [questo articolo sull'installazione di software nei dispositivi](rooms-scale.md). 

È possibile distribuire le sale di Microsoft teams con Microsoft teams, Skype for business online o le distribuzioni ibride o locali di Skype for business.  Vedere l' [aggiornamento delle licenze della sala riunioni](rooms-licensing.md) per le squadre per informazioni sulle licenze necessarie.

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Si distribuiscono le sale di Microsoft teams nell'organizzazione? </li><li>Come procurerai i tuoi sistemi Microsoft teams rooms, in bundle, come componenti separati o come unità integrata?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi | <ul><li>Identificare chi intraprenderà le attività chiave durante la distribuzione.</li><li>Esaminare le sale riunioni di cui si dispone (e pianificare la configurazione) per comprendere la posizione in cui si vogliono distribuire le sale di Microsoft teams e i dispositivi periferici appropriati per le dimensioni della sala.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificare chi intraprenderà le attività chiave in tutta la distribuzione

Usa l'approccio illustrato di seguito per guidarti alla distribuzione e personalizzare gli output di esempio forniti in questi articoli in base alle esigenze dell'organizzazione.

Prima di tutto, è possibile comprendere le sale riunioni in cui si è in esecuzione e in che modo il lavoro migliore per il futuro, quindi spostarsi selezionando e procurando l'equipaggiamento necessario, preparando i siti, configurando e distribuendo il servizio, gestendo le modifiche e adozione degli utenti e sviluppo di operazioni e procedure di manutenzione.

![Prima di tutto, è possibile capire cosa si ha e che cosa avrebbe funzionato meglio, quindi spostarsi selezionando e procurando l'equipaggiamento necessario, preparando i siti, configurando e distribuendo il servizio, gestendo le modifiche e l'adozione degli utenti e sviluppando operazioni e procedure di manutenzione.](../media/room-systems-image2.png "Prima di tutto, è possibile capire cosa si ha e che cosa avrebbe funzionato meglio, quindi spostarsi selezionando e procurando l'equipaggiamento necessario, preparando i siti, configurando e distribuendo il servizio, gestendo le modifiche e l'adozione degli utenti e sviluppando operazioni e procedure di manutenzione.")

Potrebbe essere necessario coordinare queste attività in diversi team. Offriamo una visualizzazione di alto livello delle principali attività che è necessario includere e suggerimenti per i team che sono in genere coinvolti nella distribuzione e gestione di sistemi per sale riunioni per decidere chi è necessario collaborare.

| Attività                       | Chi può intraprendere l'attività           | Assegnato a | Collegamenti a questo contenuto |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Sale di inventario            | Servizi/team di progetto AV/IT |             | [Inventario delle camere e pianificazione delle funzionalità](#room-inventory-and-capability-planning)        |
| Pianificare le funzionalità          | Team di progetto IT                        |             | [Inventario delle camere e pianificazione delle funzionalità](#room-inventory-and-capability-planning)                       |
| Selezione del dispositivo           | Team di progetto IT/gruppo AV              |             | [Selezione del dispositivo](#device-selection)                      |
| Appalti                | Team di progetto IT/gruppo AV              |             | [Appalti](#procurement)                      |
| Disponibilità del sito             | Servizi/team di progetto AV/IT |             | [Disponibilità del sito](rooms-deploy.md#site-readiness)                      |
| Disponibilità del servizio          | Team di progetto IT                        |             | [Disponibilità del servizio](rooms-deploy.md#service-readiness)                      |
| Configurazione              | Team di progetto IT                        |             | [Configurazione e distribuzione](rooms-deploy.md#configuration-and-deployment)                      |
| Deployment                 | Servizi/team di progetto AV/IT |             | [Elenco di controllo della distribuzione](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Adozione                   | Servizi/team di progetto AV/IT |             | [Adozione](#plan-for-adoption-and-change-management)                      |
| Manutenzione e operazioni | Team di progetto AV/IT              |             | [Panoramica della gestione](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Inventario delle camere e pianificazione delle funzionalità

Il primo passaggio consiste nell'inventariare le sale riunioni e conferenze esistenti dell'organizzazione per comprenderne l'ambiente, le dimensioni della sala, il layout e lo scopo e per identificare le funzionalità per le quali è necessario che ogni sala dell'ambito sia in futuro, ad esempio il più ricco le funzionalità di collaborazione verranno abilitate nella sala. 

Dopo aver creato un inventario delle attrezzature e delle funzionalità in ogni sala esistente, i requisiti per il feed della sala nella pianificazione della selezione del dispositivo consentono di creare una soluzione di conferenza avanzata. Le modalità (audio, video) necessarie per ogni sala, oltre a dimensioni e finalità della sala, giocano un ruolo importante per decidere quale soluzione sia più appropriata per ogni sala. 

Come parte della scoperta, è importante considerare l'acustica e il layout della sala. Ad esempio, controlla che le sedie nella sala non blocchino la visualizzazione della videocamera. Verificare che la sala non abbia l'eco o l'aria condizionata troppo rumorosa e che abbia sufficiente energia per gli schermi e le sale di Microsoft teams. Ci sono molti fattori da considerare che il team o il partner audio-visivo (AV) sarà in grado di consigliare. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Quali sono le camere in ambito per questa distribuzione?</li><li>Quali siti sono in ambito per la distribuzione?</li><li>Chi effettuerà l'inventario delle sale riunioni?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Esaminare le camere in ambito e definire le configurazioni di Microsoft teams rooms.</li></ul>|

_Inventario di esempio/sala riunioni_

| Sito  | Nome sala | Tipo di sala | Numero di persone  | In ambito? | Funzionalità della sala corrente       | Funzionalità future della sala     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| HQ di Londra | Curie         | Media        | 6&ndash;12                  | Sì          | Vivavoce                        | 1 schermata, audio e video + presentazione<br>Accesso PSTN |
| HQ di Sydney | Collina          | Grande         | 12&ndash;16                 | Sì          | Unità AV legacy, 1 schermata e fotocamera | 2 schermi, audio e video + presentazione<br>Accesso PSTN |

## <a name="device-selection"></a>Selezione del dispositivo 

Valutare la soluzione Microsoft teams Rooms più adatta a ogni sala in base alle future funzionalità desiderate per la sala. Decidere quali periferiche AV sono le più adatte, a seconda delle dimensioni e del layout della sala. 

Per indicazioni sul tipo di sistema e periferiche per tipo di sala e dimensioni, vedere l'articolo [requisiti di Microsoft teams Rooms](requirements.md) . 

In base al fornitore che si preferisce, usare le informazioni fornite nell'articolo requisiti per definire le sale di Microsoft teams e la configurazione di dispositivi periferici supportati per ogni tipo di stanza e usarla come modello per la distribuzione. 

**Suggerimento PRO** : alcuni tipi di sala potrebbero non essere applicabili alla distribuzione.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Dall'inventario, quali tipi di sale sono in ambito per la distribuzione?</li><li>Quali sistemi verranno distribuiti per ogni tipo di sala?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a raccogliere materiale operativo chiave per i sistemi scelti e coinvolgere il team di approvvigionamento.</li></ul>|

_Esempio di modello di distribuzione di Microsoft teams Rooms per l'organizzazione_

| **Tipo di stanza/dimensione** | **Numero di persone**  | **Sistema Microsoft teams rooms** | **Periferiche**  | **Display (s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Stato attiva 10' per 9'      | 2&ndash;4                   |                                  |                         |                 |
| Piccolo 16' per 16'     | 4&ndash;6                   |                                  |                         |                 |
| Media 18' per 20'    | 6&ndash;12                  |                                  |                         |                 |
| Grande 15' da 32'     | 12&ndash;16                 |                                  |                         |                 |

**Suggerimento PRO-** Ora è il momento ideale per iniziare a raccogliere informazioni sulla soluzione Microsoft teams Rooms che hai scelto.

## <a name="procurement"></a>Appalti 

Puoi procurare il sistema scelto come bundle o come soluzione integrata tramite partner di dispositivo. Puoi anche acquisire un dock per dispositivi partner e preparare la tua soluzione Microsoft teams Rooms usando un dispositivo Surface Pro e periferiche AV _supportate_ esistenti. 

È possibile acquisire sale di Microsoft Teams da diversi partner elencati nell' [articolo requisiti](requirements.md). Visitare i siti Web dei partner per altre informazioni su queste soluzioni e sulle opzioni di approvvigionamento. 

A seconda della scala e dell'approccio di distribuzione, è possibile decidere di far spedire le sale di Microsoft teams e i dispositivi secondari supportati in una posizione centrale per la configurazione e l'assegnazione iniziali. Questo potrebbe essere un buon approccio per un'implementazione a fasi in molti siti. In alternativa, è possibile scegliere di spedire i bundle direttamente ai siti. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>I componenti verranno spediti direttamente a un sito o a una struttura di staging?</li><li>Chi gestirà lo strumento di gestione temporanea (se si decide di usare uno)?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Pianificare le operazioni.</li><li>Pianificare l'adozione e la gestione delle modifiche.</li></ul>|

## <a name="plan-for-operations"></a>Pianificare le operazioni 

L'organizzazione deve eseguire attività di monitoraggio, amministrazione e gestione su base continuativa ed è fondamentale accettare chi effettuerà queste attività all'inizio della distribuzione. 

Molte organizzazioni hanno un team o un partner AV che gestisce le sale riunioni e i dispositivi. Questo team deve essere coinvolto nell'accettare chi gestirà i dispositivi Microsoft teams Rooms per il monitoraggio delle prestazioni e la distribuzione di aggiornamenti software e hotfix. 

Si consideri la coda dell'helpdesk che instraderà le chiamate correlate a Microsoft teams Rooms֪ e offrirà una FAQ al team dell'helpdesk per comprendere meglio come usare le sale di Microsoft teams e i passaggi principali per la risoluzione dei problemi che possono eseguire. Un buon punto di partenza per le domande frequenti è la [Guida dell'utente](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) e l' [elenco dei problemi noti](known-issues.md).

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà le sale di Microsoft teams.</li><li>Scegliere la coda dell'helpdesk per instradare le chiamate correlate a Microsoft teams rooms.</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Prepararsi ad ospitare gli account. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Pianificare l'adozione e la gestione delle modifiche

I sistemi Microsoft teams Rooms introducono nuove funzionalità agli utenti. È importante riconoscere che si tratta di una modifica per gli utenti e verificare che la campagna identifichi i vantaggi che il nuovo sistema avrà per gli utenti e i principali punti di discussione che possono essere usati per discutere con i loro team. 

Valutare la possibilità di pianificare eventi Show-and-Tell e poster DROPS in ogni sito per informare gli utenti delle nuove funzionalità. È anche possibile creare "guide introduttive" in camera. Valutare la possibilità di trovare un campione di riunioni in ogni sito che può aiutare gli altri a diventare più veloci e iniziare a usare i dispositivi.
