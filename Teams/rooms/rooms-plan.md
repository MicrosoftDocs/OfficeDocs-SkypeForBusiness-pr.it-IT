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
description: Questo articolo illustra le considerazioni di pianificazione pertinenti per la distribuzione di Microsoft Teams Rooms, la nuova generazione di Skype Room Systems.
ms.openlocfilehash: d07783e2e3df7b4a8c2563b39fb702369751d139
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646987"
---
# <a name="plan-microsoft-teams-rooms"></a>Pianificare Microsoft Teams Rooms

Questo articolo introduce un approccio end-to-end alla pianificazione, alla distribuzione e all'Microsoft Teams Rooms nell'ambito della strategia generale per riunioni e sale riunioni.

Di seguito sono riportate informazioni sulla pianificazione che illustrano l'approccio consigliato e le decisioni chiave da prendere, con collegamenti a informazioni tecniche di supporto. È consigliabile esaminare le sezioni Pianificare, Distribuire e Gestire anche se si è già completamente distribuiti.

## <a name="overview-of-microsoft-teams-rooms"></a>Panoramica delle Microsoft Teams Rooms

Microsoft Teams Rooms offre un'esperienza di riunione completa che consente di condividere video, audio e contenuti HD in riunioni di tutte le dimensioni, da piccole aree di riunione a sale riunioni di grandi dimensioni.

![Una console, un microfono e uno schermo di grandi dimensioni montati su una parete di una sala riunioni illustrano gli elementi di un esempio Microsoft Teams Rooms configurazione.](../media/room-systems-image1.png "Una console, un microfono e uno schermo di grandi dimensioni montati su una parete di una sala riunioni illustrano gli elementi di un esempio Microsoft Teams Rooms configurazione.")

[Microsoft Teams Rooms guida](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) è un'ottima risorsa per saperne di più sulle Microsoft Teams Rooms e su come può aggiungere valore come parte della distribuzione. Inoltre, è consigliabile guardare questo [video di panoramica.](https://youtu.be/tNey5KZVCl0) 

## <a name="microsoft-teams-rooms-components"></a>Microsoft Teams Rooms componenti

Microsoft Teams Rooms include i componenti chiave seguenti per offrire un'esperienza utente ottimale:

- Pannello di controllo touchscreen
- Calcolare
- Microsoft Teams Rooms applicazione
- Dock/estensore
- Dispositivi periferici (fotocamera, microfono, altoparlante)
- Schermi esterni (massimo due)
- Ingresso HDMI

È possibile acquistare questi componenti come pacchetti preinstallati da diversi fornitori oppure acquistare i componenti supportati singolarmente seguendo i requisiti documentati [in questo articolo.](requirements.md)

Oltre alla combinazione Surface Pro/dock, è anche possibile acquistare Microsoft Teams Rooms con il pannello di controllo touchscreen, il calcolo, il dock e i principali dispositivi periferici integrati. 

In genere, i pacchetti e le unità integrate includono software preinstallato, mentre se si acquistano i componenti supportati singolarmente per i sistemi Surface Pro, è necessario installare il software. Per istruzioni, vedere [questo articolo sull'installazione di software nei dispositivi.](rooms-scale.md) 

È possibile distribuire Microsoft Teams Rooms con Microsoft Teams, Skype for Business Online o Skype for Business distribuzioni ibride o locali.  Per informazioni [sulle licenze necessarie,](rooms-licensing.md) vedere l'Teams Sala riunioni gestione licenze.

| &nbsp;   |  &nbsp;   |
|-----------|------------|
|![decidere la distribuzione](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Si distribuiranno Microsoft Teams Rooms nell'organizzazione? </li><li>Come si acquistano i Microsoft Teams Rooms, in bundle, come componenti separati o come unità integrate?</li></ul> |
| ![identificare le attività](../media/audio_conferencing_image9.png)<br/>Passaggi successivi | <ul><li>Identificare gli utenti che intraprenderanno le attività principali durante l'intera distribuzione.</li><li>Esaminare le sale riunioni disponibili (e pianificare la configurazione) per capire dove si vuole distribuire Microsoft Teams Rooms e i dispositivi periferici appropriati per le dimensioni della sala.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment&quot;></a>Identificare gli utenti che intraprenderanno le attività principali durante la distribuzione

Usare l'approccio illustrato di seguito per illustrare la distribuzione e personalizzare gli output di esempio forniti in questi articoli in base alle esigenze dell'organizzazione.

Iniziare con la comprensione delle sale riunioni disponibili e l'implementazione delle soluzioni più ottimali in futuro, quindi passare alla selezione e all'acquisto delle apparecchiature necessarie, alla pre-elaborazione dei siti, alla configurazione e alla distribuzione del servizio, alla gestione delle modifiche e all'adozione degli utenti e allo sviluppo di operazioni e procedure di manutenzione.

![Iniziare con la comprensione delle risorse disponibili e l'implementazione delle soluzioni più ottimali, quindi passare alla selezione e all'acquisto delle apparecchiature necessarie, alla preparazione dei siti, alla configurazione e alla distribuzione del servizio, alla gestione delle modifiche e all'adozione degli utenti e allo sviluppo di operazioni e procedure di manutenzione.](../media/room-systems-image2.png &quot;Iniziare con la comprensione delle risorse disponibili e l'implementazione delle soluzioni più ottimali, quindi passare alla selezione e all'acquisto delle apparecchiature necessarie, alla preparazione dei siti, alla configurazione e alla distribuzione del servizio, alla gestione delle modifiche e all'adozione degli utenti e allo sviluppo di operazioni e procedure di manutenzione.")

Potrebbe essere necessario coordinare queste attività in diversi team. Microsoft offre una visualizzazione generale delle attività principali da coprire e suggerimenti per i team che in genere sono coinvolti nella distribuzione e nella gestione dei sistemi delle sale riunioni, per decidere con chi è necessario collaborare.

| Attività                       | Who intraprendere l'attività           | Assegnato a | Collegamenti a questo contenuto |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Sale dell'inventario            | Strutture / team AV / TEAM IT Project Team |             | [Inventario delle chat room e pianificazione delle funzionalità](#room-inventory-and-capability-planning)        |
| Pianificare le funzionalità          | Team Project IT                        |             | [Inventario delle chat room e pianificazione delle funzionalità](#room-inventory-and-capability-planning)                       |
| Selezione del dispositivo           | Team IT Project /AV Team              |             | [Selezione del dispositivo](#device-selection)                      |
| Approvvigionamento                | Team IT Project /AV Team              |             | [Approvvigionamento](#procurement)                      |
| Conformità del sito             | Strutture / team AV / TEAM IT Project Team |             | [Conformità del sito](rooms-deploy.md#site-readiness)                      |
| Prontezza del servizio          | Team Project IT                        |             | [Prontezza del servizio](rooms-deploy.md#service-readiness)                      |
| Configurazione              | Team Project IT                        |             | [Configurazione e distribuzione](rooms-deploy.md#configuration-and-deployment)                      |
| Deployment                 | Strutture / team AV / TEAM IT Project Team |             | [Elenco di controllo per la distribuzione](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Adozione                   | Strutture / team AV / TEAM IT Project Team |             | [Adozione](#plan-for-adoption-and-change-management)                      |
| Manutenzione e operazioni | Team AV/TEAM IT Project Team              |             | [Panoramica della gestione](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Inventario delle chat room e pianificazione delle funzionalità

Il primo passaggio consiste nell'eseguire l'inventario delle sale riunioni e delle conferenze esistenti dell'organizzazione per comprenderne l'ambiente, le dimensioni, il layout e lo scopo e per identificare le funzionalità che si vuole che ogni sala nell'ambito abbia in futuro, ad esempio quali funzionalità di collaborazione più avanzate verranno abilitate nella sala. 

Dopo aver creato un inventario delle apparecchiature e delle funzionalità in ogni sala esistente, i requisiti per il feed della sala nella selezione del dispositivo prevedeno di creare una soluzione di conferenza completa. Le modalità (audio, video) necessarie per ogni stanza, oltre alle dimensioni e allo scopo della stanza, svolgono un ruolo importante nel decidere quale soluzione è più appropriata per ogni sala. 

Nell'ambito della scoperta, è fondamentale considerare l'acustica e il layout delle chat room. Ad esempio, verificare che le sedie nella stanza non blocchino la visualizzazione della fotocamera. Verificare che la stanza non abbia un'eco eccessiva o un condizionamento rumoroso e che abbia una potenza sufficiente per gli schermi e le Microsoft Teams Rooms. Ci sono molti fattori da considerare su cui il team o il partner audio-visivo (AV) sarà in grado di consigliare. 

| &nbsp;   | &nbsp;    |
|-----------|------------|
| ![ammortizzazioni](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Esaminare le chat room nell'ambito e definire Microsoft Teams Rooms relative configurazioni.</li></ul>|

_Inventario di esempio per riunioni/sale riunioni_

| Sito  | Nome della chat room | Tipo di chat room | Numero di persone  | Nell'ambito? | Funzionalità correnti della chat room       | Funzionalità future per le chat room     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| Sede centrale di Londra | Curie         | Media.        | 6 &ndash; 12                  | Sì          | Vivavoce                        | 1 schermo, audio e video più presentazione<br>Accesso PSTN |
| Sede centrale di Sydney | Collina          | Grande         | 12 &ndash; 16                 | Sì          | Unità AV legacy, 1 schermo e fotocamera | 2 schermi, audio e video più presentazione<br>Accesso PSTN |

## <a name="device-selection"></a>Selezione del dispositivo 

Valutare quale Microsoft Teams Rooms più adatta per ogni stanza in base alle funzionalità future desiderate per la sala. Decidere quali dispositivi av sono più adatti, a seconda delle dimensioni della stanza e del layout. 

Per indicazioni sul tipo di dispositivi di sistema e di periferiche in base al tipo e alle dimensioni della stanza, vedere l'articolo Microsoft Teams Rooms [requisiti di](requirements.md) sistema. 

In base al fornitore preferito, usare le informazioni fornite nell'articolo sui requisiti per definire la configurazione del Microsoft Teams Rooms e dei dispositivi periferici supportati per ogni tipo di sala e usarla come modello per la distribuzione. 

**Pro suggerimento:** alcuni tipi di chat room potrebbero non essere applicabili per la distribuzione.

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![chat room nell'ambito](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Dall'inventario, quali tipi di chat room sono nell'ambito della distribuzione?</li><li>Quali sistemi verranno distribuiti per ogni tipo di chat room?</li></ul>|
| ![raccogliere materiale](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a raccogliere materiale operativo chiave per i sistemi scelti e coinvolgere il team di approvvigionamento.</li></ul>|

_Modello Microsoft Teams Rooms di distribuzione per l'organizzazione_

| **Tipo/dimensioni della stanza** | **Numero di persone**  | **Microsoft Teams Rooms sistema** | **Dispositivi periferici**  | **Display(s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Stato attivo 10' per 9'      | 2 &ndash; 4                   |                                  |                         |                 |
| Piccolo 16' per 16'     | 4 &ndash; 6                   |                                  |                         |                 |
| Medio 18' per 20'    | 6 &ndash; 12                  |                                  |                         |                 |
| Grande 15' per 32'     | 12 &ndash; 16                 |                                  |                         |                 |

**Pro suggerimento -** È il momento giusto per iniziare a raccogliere informazioni sulla Microsoft Teams Rooms soluzione scelta.

## <a name="procurement"></a>Approvvigionamento 

È possibile acquistare il sistema scelto come bundle o come soluzione integrata tramite i partner di dispositivi. È anche possibile acquisire un dock di dispositivi partner e preparare la propria soluzione di Microsoft Teams Rooms usando un dispositivo Surface Pro e i dispositivi _av_ supportati esistenti. 

È possibile acquisire Microsoft Teams Rooms da un certo numero di partner elencati nell'articolo [requisiti.](requirements.md) Visita i siti Web dei partner per saperne di più su queste soluzioni e opzioni di approvvigionamento. 

A seconda della scala di distribuzione e dell'approccio, è possibile decidere di spedire i dispositivi Microsoft Teams Rooms e le periferiche supportate in una posizione centrale per la configurazione iniziale e l'assegnazione. Questo potrebbe essere un buon approccio per un'implementazione a fasi in molti siti. In caso contrario, è possibile scegliere di spedire i pacchetti direttamente ai siti. 

|   &nbsp; |  &nbsp;   |
|-----------|------------|
| ![componenti di spedizione](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>I componenti verranno spediti direttamente a un sito o a una struttura di gestione temporanea?</li><li>Who gestirà la struttura di gestione temporanea (se si decide di usarla)?</li></ul>|
| ![pianificare le operazioni](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Pianificare le operazioni.</li><li>Pianificare l'adozione e la gestione delle modifiche.</li></ul>|

## <a name="plan-for-operations"></a>Pianificare le operazioni 

L'organizzazione deve eseguire attività di monitoraggio, amministrazione e gestione su base continuativa ed è fondamentale concordare chi eseguirà queste attività nelle prime fasi della distribuzione. 

Molte organizzazioni hanno un team o un partner AV che gestisce le sale riunioni e i dispositivi. Questo team dovrebbe essere coinvolto nel concordare chi gestirà i dispositivi Microsoft Teams Rooms in futuro per monitorare le prestazioni e distribuire aggiornamenti software e aggiornamenti rapidi. 

Valutare la coda dell'helpdesk da instradare Microsoft Teams Rooms Microsoft Teams Rooms</DICT__Microsoft⚐Teams⚐Rooms> e le procedure di risoluzione dei problemi principali che possono eseguire. Un buon punto di partenza per queste domande frequenti è la [Guida dell'utente](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) e [i problemi noti.](known-issues.md)

|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![scegliere manager](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà i Microsoft Teams Rooms.</li><li>Decidere a quale coda dell'helpdesk instradare Microsoft Teams Rooms chiamate correlate.</li></ul>|
| ![preparare gli account host](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Preparare l'hosting degli account. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Pianificare l'adozione e la gestione delle modifiche

Microsoft Teams Rooms nuovi sistemi introducono nuove funzionalità per gli utenti. È importante riconoscere che si tratta di una modifica per gli utenti e assicurarsi che la campagna identifichi i vantaggi che il nuovo sistema avrà per gli utenti e i principali punti di discussione che i lead possono usare per discutere con i loro team. 

È consigliabile pianificare eventi di presentazione e poster in ogni sito per informare gli utenti delle nuove funzionalità. È anche possibile creare "guide introduttive" all'ambiente locale. È consigliabile trovare un campione di riunioni in ogni sito che possa aiutare gli altri utenti a diventare sempre più veloci e a iniziare a usare i dispositivi.
