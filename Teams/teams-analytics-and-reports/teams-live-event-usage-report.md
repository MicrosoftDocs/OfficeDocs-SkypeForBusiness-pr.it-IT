---
title: Report sull'utilizzo degli eventi live di Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report Utilizzo eventi live di Teams nell'interfaccia di amministrazione di Microsoft Teams per una panoramica dell'attività degli eventi live di Teams nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 971e9bc846ad1a7134c1877a1716fc535ae65e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809286"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Report sull'utilizzo degli eventi live di Microsoft Teams

Il report Utilizzo eventi live di Teams nell'interfaccia di amministrazione di Microsoft Teams mostra una panoramica delle attività per gli eventi live tenute nell'organizzazione. È possibile visualizzare le informazioni sull'utilizzo, inclusi lo stato dell'evento, l'ora di inizio, le visualizzazioni e il tipo di produzione per ogni evento. È possibile ottenere informazioni approfondite sulle tendenze di utilizzo e vedere quali utenti dell'organizzazione pianificano, presentano e generano eventi live.

## <a name="view-the-live-event-usage-report"></a>Visualizzare il report sull'utilizzo degli eventi live

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fare clic su **Analisi & report**  >  **sull'utilizzo.** Nella scheda **Visualizza report,** in **Report, selezionare** Utilizzo evento **live di Teams.**
2. In **Intervallo di date** selezionare un intervallo predefinito o impostare un intervallo personalizzato. È possibile impostare un intervallo in modo da visualizzare i dati fino a un anno, sei mesi prima e dopo la data corrente.
3. (Facoltativo) In **Organizzatore** è possibile scegliere di visualizzare solo gli eventi live organizzati da un utente specifico.
4. Fare **clic su Esegui report.**  

    ![Screenshot del report Utilizzo eventi live di Teams nell'interfaccia di amministrazione di Teams con callout](../media/teams-live-event-usage-report-with-callouts.png "Screenshot del report Utilizzo eventi live di Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report degli eventi live di Teams può essere visualizzato per le tendenze degli ultimi 7, 28 giorni o un intervallo di date personalizzato impostato dall'utente. |
|**2**   |Ogni report include la data in cui è stato generato. Il report riflette l'attività in tempo reale quasi in tempo reale quando la pagina viene aggiornata. |
|**3**   |<ul><li>L'asse X nel grafico rappresenta l'intervallo di date selezionato per il report.</li> <li> L'asse Y rappresenta il conteggio totale delle visualizzazione.</li> </ul>Posizionare il puntatore del mouse sul punto in una data specifica per visualizzare il numero di visualizzazioni per tutti gli eventi live di tale data.|
|**4**   |La tabella fornisce un'analisi di ogni evento live. <ul><li>**Evento** è il nome visualizzato dell'evento live. Fare clic sul nome dell'evento [per ottenere maggiori dettagli](#view-event-details) sull'evento. </li> <li>**Ora inizio si** riferisce alla data e all'ora di inizio dell'evento.</li> <li>**Lo stato dell'evento** indica se l'evento è stato effettuato.  </li><li>**Organizzatore** è il nome dell'organizzatore dell'evento.</li> <li>**I relatori** sono i nomi dei relatori dell'evento.</li><li>**I produttori** sono i nomi dei produttori di eventi.</li><li>**Visualizzazioni** è il numero di visualizzazioni univoche dopo il completamento dell'evento.</li><li>**La** registrazione mostra se l'impostazione di registrazione è attivata o disattivata.</li><li>**Production Type** indica se l'evento è prodotto in Teams o da un'applicazione o un dispositivo esterno.</li></li> </ul>Si noti che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|

## <a name="notes"></a>Note
Visualizzare fino a 100 eventi live che corrispondono ai criteri del report corrente. Per visualizzare altri eventi live, applicare filtri di data per ridurre le dimensioni dell'elenco.

## <a name="view-event-details"></a>Visualizzare i dettagli dell'evento

La pagina dei dettagli dell'evento live offre un riepilogo dei dettagli di un evento live ed elenca tutti i file, incluse le trascrizioni e le registrazioni, associati all'evento. Fare clic sul nome di un file per visualizzarlo o scaricarlo.

![Screenshot che mostra i dettagli di un evento live](../media/teams-live-event-usage-report-event-detail.png)

Se la tua organizzazione è abilitata per [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN o [Kollective](https://kollective.com) eCDN, puoi ottenere ulteriori analisi dei partecipanti facendo clic sul collegamento del report del partner.

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report di Teams](teams-reporting-reference.md)
- [Cosa sono gli eventi live di Teams?](../teams-live-events/what-are-teams-live-events.md)
