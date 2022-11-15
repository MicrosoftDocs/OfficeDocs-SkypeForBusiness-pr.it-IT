---
title: Report sull'utilizzo di eventi live di Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
description: Informazioni su come usare il report sull'utilizzo di eventi live di Teams nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica dell'attività degli eventi live di Teams nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 970247bf863942a4f938f96e30533ff550d37e94
ms.sourcegitcommit: 73b13cd8a79ba1724b9fb79c8356a7cacafb7dd3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2022
ms.locfileid: "68964982"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Report sull'utilizzo di eventi live di Microsoft Teams

Il report Sull'utilizzo degli eventi live di Teams nell'interfaccia di amministrazione di Microsoft Teams mostra una panoramica delle attività per gli eventi live tenuti nell'organizzazione. È possibile visualizzare le informazioni sull'utilizzo, tra cui lo stato dell'evento, l'ora di inizio, le visualizzazioni e il tipo di produzione per ogni evento. È possibile ottenere informazioni approfondite sulle tendenze di utilizzo e vedere chi nell'organizzazione pianifica, presenta e produce eventi live.

## <a name="view-the-live-event-usage-report"></a>Visualizzare il report sull'utilizzo dell'evento live

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Analisi & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, selezionare **Utilizzo di eventi live di Teams**.
2. In **Intervallo di date** selezionare un intervallo predefinito o impostare un intervallo personalizzato. È possibile impostare un intervallo per visualizzare i dati fino a un anno, sei mesi prima e dopo la data corrente.
3. (Facoltativo) In **Organizzatore** è possibile scegliere di visualizzare solo gli eventi live organizzati da un utente specifico.
4. Fare clic su **Esegui report**.  

   :::image type="content" alt-text="Screenshot del report sull'utilizzo di eventi live di Teams nell'interfaccia di amministrazione di Teams con callout." source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report degli eventi live di Teams può essere visualizzato per le tendenze degli ultimi 7, 28 giorni o un intervallo di date personalizzato impostato. |
|**2**   |Ogni report ha una data per la generazione. Il report riflette l'attività quasi in tempo reale quando la pagina viene aggiornata. |
|**3**   |<ul><li>L'asse X nel grafico rappresenta l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il conteggio totale delle visualizzazioni.</li> </ul>Passare il puntatore del mouse sul punto in una data specificata per visualizzare il numero di visualizzazioni in tutti gli eventi live in tale data.|
|**4**   |La tabella offre una suddivisione di ogni evento live. <ul><li>**Evento** è il nome visualizzato dell'evento live. Fare clic sul nome dell'evento per [ottenere altri dettagli](#view-event-details) sull'evento. </li> <li>**Ora inizio** fa riferimento alla data e all'ora di inizio dell'evento.</li> <li>**Lo stato** dell'evento indica se l'evento è avvenuto.  </li><li>**Organizzatore** è il nome dell'organizzatore dell'evento.</li> <li>**I relatori** sono i nomi dei relatori dell'evento.</li><li>**I produttori** sono i nomi dei produttori di eventi.</li><li>**Visualizzazioni** è il numero di visualizzazioni univoche dopo il completamento dell'evento.</li><li>**La registrazione** indica se l'impostazione di registrazione è attivata o disattivata.</li><li>**Tipo di produzione** indica se l'evento viene prodotto in Teams o da un'applicazione o un dispositivo esterno.</li></li> </ul>Si noti che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|

## <a name="notes"></a>Note
Vengono visualizzati al massimo 100 eventi live che corrispondono ai criteri del report corrente. Per visualizzare altri eventi live, applicare filtri di data per ridurre le dimensioni dell'elenco.

I relatori anonimi non verranno inclusi nel report.

Chiunque guardi la registrazione dell'evento o dell'evento su richiesta non verrà incluso nel conteggio delle visualizzazioni. 

## <a name="view-event-details"></a>Visualizzare i dettagli dell'evento

La pagina dei dettagli dell'evento live offre un riepilogo dei dettagli di un evento live ed elenca tutti i file, incluse trascrizioni e registrazioni, associati all'evento. Fare clic su un nome file per visualizzare o scaricare il file.

:::image type="content" alt-text="Screenshot che mostra i dettagli di un evento live." source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

Se l'organizzazione usa Microsoft eCDN, l'analisi avanzata può essere visualizzata ed esportata dal [dashboard eCDN](https://admin.ecdn.microsoft.com).  Se l'organizzazione è abilitata per [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN o [Kolletive](https://kollective.com) eCDN, è possibile ottenere ulteriori analisi dei partecipanti facendo clic sul collegamento del report partner.

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).
- [Cosa sono gli eventi live di Teams?](../teams-live-events/what-are-teams-live-events.md)
