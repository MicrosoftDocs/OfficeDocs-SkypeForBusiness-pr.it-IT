---
title: Usare la telemetria in tempo reale per risolvere i problemi di qualità scarsa delle riunioni
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
description: Usare la telemetria in tempo reale con dettagli su dispositivi, reti e connettività per risolvere i problemi degli utenti con le riunioni Microsoft Teams pianificate.
ms.openlocfilehash: c33e3309995d82fd16e9eb1deb2fa5fe24b04330
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007904"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Usare la telemetria in tempo reale per risolvere i problemi di qualità scarsa delle riunioni

> [!NOTE]
> Questa caratteristica è attualmente in anteprima pubblica.

Questo articolo spiega come usare la telemetria in tempo reale per risolvere i problemi Microsoft Teams qualità scarsa delle riunioni per i singoli utenti. È possibile visualizzare la telemetria in tempo reale se si ha uno dei ruoli seguenti:

- Amministratore di Teams
- Teams Specialista del supporto per le comunicazioni
- Tecnico supporto comunicazioni Teams

Per altre informazioni sui ruoli di Teams, vedere Usare i ruoli di Microsoft Teams [di amministratore](/MicrosoftTeams/using-admin-roles)per gestire Teams .

La telemetria in tempo reale consente agli amministratori IT di esaminare le riunioni pianificate degli utenti importanti e vedere i problemi relativi a audio, video, condivisione di contenuti e rete. Gli amministratori possono usare la telemetria per analizzare questi problemi durante le riunioni e risolvere i problemi in tempo reale.

## <a name="what-is-real-time-telemetry"></a>Che cos'è la telemetria in tempo reale?

Oggi, la risoluzione dei problemi relativi alle singole riunioni è disponibile per Teams amministratori tramite [analisi delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md) al termine della riunione. La telemetria in tempo reale consente agli amministratori di risolvere i problemi relativi alle riunioni pianificate mentre sono in corso.

La telemetria in tempo reale mostra informazioni dettagliate sulle riunioni Teams per ogni utente del proprio account Office 365 aggiornato in tempo reale. Include informazioni su dispositivi, rete, connettività, audio, video e problemi di condivisione dei contenuti, che aiuteranno gli amministratori a risolvere i problemi di qualità delle chiamate in modo più efficace.

Gli amministratori Teams ottenere l'accesso completo a tutti i dati di telemetria in tempo reale per ogni utente. Inoltre, è possibile assegnare Azure Active Directory ruoli al personale di supporto. Per altre informazioni su questi ruoli, vedere Concedere [l'autorizzazione al personale](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)di supporto e help desk.

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Dove trovare la telemetria della risoluzione dei problemi in tempo reale per ogni utente

Per visualizzare tutte le informazioni e i dati della riunione per un utente, passare [all'Teams di amministrazione.](https://admin.teams.microsoft.com) In **Gestione** utenti selezionare un utente e aprire la scheda Riunioni &  >  chiamate nella pagina del profilo dell'utente.  In **Riunioni recenti** verrà visualizzato un elenco delle riunioni a cui l'utente ha partecipato nelle ultime 24 ore per le quali è disponibile la telemetria in tempo reale, incluse le riunioni in corso.  Se la riunione non è in corso o non contiene dati di telemetria in tempo reale, verrà visualizzato nelle **riunioni passate.**

![Screenshot della tabella riunioni recenti.](media/recent-meetings.png)

Per ottenere altre informazioni sui partecipanti a una riunione in corso, inclusi il dispositivo, la rete e le statistiche audio, trovare la riunione **in** Riunioni recenti e selezionare il collegamento nella colonna **Partecipanti.**

![Screenshot della tabella dei dettagli dei partecipanti.](media/participant-details.png)

Per esaminare la telemetria in tempo reale di un determinato utente per una riunione in corso, incluse informazioni su dispositivi, rete, audio, video e dettagli sulla condivisione del contenuto, selezionare **l'ID riunione.**

![Screenshot dei dati della sessione utente di analisi delle chiamate.](media/real-time-telemetry.png)

## <a name="platforms-supported-for-real-time-telemetry"></a>Piattaforme supportate per la telemetria in tempo reale

- Windows
- macOS
- Linux
- Android
- iOS

## <a name="teams-devices-support-with-real-time-telemetry"></a>Teams dispositivi mobili con telemetria in tempo reale

- MTR - Surface Hub
- MTR - Teams schermo
- MTR - Barra di collaborazione
- Dispositivi Telefono IP

## <a name="limitations"></a>Limitazioni

- La telemetria in tempo reale è disponibile solo per le riunioni pianificate. Per le riunioni ad hoc come Riunione, PSTN, chiamate 1:1 e chiamate di gruppo, la telemetria in tempo reale non funziona.
- La telemetria in tempo reale è disponibile solo per i relatori dell'evento live pianificato. Attualmente non è disponibile per i partecipanti all'evento live.
- I dati di telemetria in tempo reale sono disponibili per una riunione in Riunioni **recenti** per 24 ore dopo la fine della riunione. Dopo 24 ore, non è possibile accedere ai dati e la riunione passa a **Riunioni passate.** Se una riunione dura più di 3 ore, la telemetria in tempo reale sarà disponibile solo per *le ultime 3 ore.*
- La telemetria non funziona con le versioni precedenti di Teams. Se non sono disponibili dati di telemetria, provare ad aggiornare il client.
- Se partecipanti esterni o utenti anonimi aderiscono a una riunione, il nome visualizzato verrà visualizzato come non **disponibile** per mantenere la privacy tra tenant.

## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate per utente](set-up-call-analytics.md)

[Usare Microsoft Teams di amministratore per gestire Teams](/MicrosoftTeams/using-admin-roles).
