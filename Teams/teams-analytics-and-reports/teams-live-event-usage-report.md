---
title: Microsoft Teams di utilizzo degli eventi live
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report sull Teams di utilizzo degli eventi in tempo reale nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica delle attività Teams eventi live nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea415e849f4255b38432d227a9d26452b3fc9275
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631210"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams di utilizzo degli eventi live

Il Teams di utilizzo degli eventi live nell'interfaccia Microsoft Teams di amministrazione mostra la panoramica delle attività per gli eventi live che si svolgono nell'organizzazione. È possibile visualizzare le informazioni sull'utilizzo, tra cui lo stato dell'evento, l'ora di inizio, le visualizzazioni e il tipo di produzione per ogni evento. È possibile ottenere informazioni approfondite sulle tendenze di utilizzo e vedere chi nell'organizzazione pianifica, presenta e produce eventi live.

## <a name="view-the-live-event-usage-report"></a>Visualizzare il report sull'utilizzo degli eventi in tempo reale

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su Analisi & **report**  >  **utilizzo**. Nella scheda **Visualizza report,** in **Report,** selezionare Teams **di eventi live.**
2. In **Intervallo di date** selezionare un intervallo predefinito o impostare un intervallo personalizzato. È possibile impostare un intervallo in modo da visualizzare i dati fino a un anno, sei mesi prima e dopo la data corrente.
3. (Facoltativo) In **Organizzatore** è possibile scegliere di visualizzare solo gli eventi live organizzati da un utente specifico.
4. Fare clic **su Esegui report.**  

    ![Screenshot del report sull Teams di utilizzo degli eventi in tempo reale nell'Teams di amministrazione con callout](../media/teams-live-event-usage-report-with-callouts.png "Screenshot del report sull Teams di utilizzo degli eventi in tempo reale nell'Teams di amministrazione con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il Teams evento live può essere visualizzato per le tendenze degli ultimi 7, 28 giorni o un intervallo di date personalizzato impostato. |
|**2**   |Ogni report ha una data in cui è stato generato. Il report riflette l'attività quasi in tempo reale quando la pagina viene aggiornata. |
|**3**   |<ul><li>L'asse X del grafico è l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il numero totale di visualizzazione.</li> </ul>Posizionare il puntatore del mouse sul punto in una data specifica per visualizzare il numero di visualizzazioni in tutti gli eventi live in quella data.|
|**4**   |La tabella fornisce una suddivisione di ogni evento live. <ul><li>**Evento** è il nome visualizzato dell'evento live. Fare clic sul nome dell'evento [per ottenere maggiori dettagli](#view-event-details) sull'evento. </li> <li>**Ora inizio** si riferisce alla data e all'ora di inizio dell'evento.</li> <li>**Lo stato dell'evento** indica se l'evento ha avuto luogo.  </li><li>**Organizzatore** è il nome dell'organizzatore dell'evento.</li> <li>**I relatori** sono i nomi dei relatori dell'evento.</li><li>**I produttori** sono i nomi dei produttori di eventi.</li><li>**Visualizzazioni** è il numero di visualizzazioni univoche dopo il completamento dell'evento.</li><li>**Registrazione** indica se l'impostazione di registrazione è attivata o disattivata.</li><li>**Tipo di produzione** indica se l'evento viene prodotto in Teams da un'applicazione o un dispositivo esterno.</li></li> </ul>Si noti che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|

## <a name="notes"></a>Note
Visualizzazione di un massimo di 100 eventi live che corrispondono ai criteri del report corrente. Per visualizzare altri eventi live, applicare filtri data per ridurre le dimensioni dell'elenco.

## <a name="view-event-details"></a>Visualizzare i dettagli dell'evento

La pagina dei dettagli dell'evento live fornisce un riepilogo dei dettagli di un evento live ed elenca tutti i file, incluse le trascrizioni e le registrazioni, associati all'evento. Fare clic su un nome file per visualizzare o scaricare il file.

![Screenshot che mostra i dettagli di un evento live](../media/teams-live-event-usage-report-event-detail.png)

Se l'organizzazione è abilitata per [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN o [Kollective](https://kollective.com) eCDN, è possibile ottenere ulteriori analisi dei partecipanti facendo clic sul collegamento del report del partner.

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).
- [Cosa sono gli eventi live di Teams?](../teams-live-events/what-are-teams-live-events.md)
