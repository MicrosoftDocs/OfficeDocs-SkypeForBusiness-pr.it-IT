---
title: report sull'utilizzo delle visite virtuali Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report sull'utilizzo delle visite virtuali nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica delle attività degli appuntamenti virtuali nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91f1aa8ff25b591305c8d5ca41485f7ceec9faca
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853217"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>report sull'utilizzo delle visite virtuali Microsoft Teams

Il report Sull'utilizzo delle visite virtuali nell'interfaccia di amministrazione di Microsoft Teams offre una panoramica di Teams'attività degli appuntamenti virtuali nell'organizzazione. È possibile visualizzare le attività dettagliate per gli appuntamenti virtuali pianificati tramite [l'app Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) e il [connettore EHR (Electronic Health Record) Microsoft Teams](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-appointments-and-electronic-healthcare-record-ehr-integration).

Per visualizzare il report, è necessario essere un amministratore globale o Teams amministratore.

Il report contiene le schede seguenti. Le informazioni visualizzate nel report variano a seconda che si disponga di una licenza per l'app Bookings, il connettore Teams EHR o entrambi.

|Scheda |Descrizione  |
|---------|---------|
|**[Visite virtuali](#virtual-visits)**     |Mostra il numero totale di appuntamenti virtuali, con una suddivisione del numero di appuntamenti pianificati con l'app Bookings e Teams riunioni integrate EHR eseguite dal sistema EHR.         |
|**[Durata](#duration)**     |Mostra la durata media degli appuntamenti e il tempo medio di attesa della sala di attesa dei partecipanti.         |
|**[Bookings](#bookings)**     |Mostra il numero di appuntamenti pianificati tramite l'app Bookings.         |
|**[EHR](#ehr)**     |Mostra il numero di appuntamenti integrati con EHR Teams condotti dal sistema EHR.         |  

Usare questo report per ottenere informazioni approfondite sulle attività e le tendenze virtuali degli appuntamenti nell'organizzazione. Le informazioni possono essere utili per ottimizzare gli appuntamenti virtuali per ottenere risultati di business migliori.

## <a name="view-the-virtual-visits-usage-report"></a>Visualizzare il report sull'utilizzo delle visite virtuali

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione Microsoft Teams scegliere **Analisi &** **reportUsa** >  report. Nella scheda **Visualizza report** , in **Report**, selezionare **Utilizzo visite virtuali**.
2. In **Intervallo di date** selezionare un intervallo di date di 7, 30 o 90 giorni. Quindi, scegliere **Esegui report**.

> [!NOTE]
> Per impostazione predefinita, l'analisi delle visite virtuali è attivata e il report è disponibile. Con questo report, l'utente concede a Microsoft l'autorizzazione a raccogliere dati sugli appuntamenti virtuali nell'organizzazione. Per informazioni sui criteri di conservazione dei dati, vedere [Conservazione, eliminazione e distruzione dei dati in Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).
>
>Se si vuole disattivare il report per l'organizzazione, è possibile farlo in **Impostazioni** nell'angolo in alto a destra della pagina. L'applicazione di questa impostazione può richiedere da 0 (zero) a 2 ore dopo la modifica.

## <a name="interpret-the-report"></a>Interpretare il report

### <a name="virtual-visits"></a>Visite virtuali

I grafici visualizzati variano a seconda che si disponga di una licenza per l'app Bookings, il connettore Teams EHR o entrambi. Per altre informazioni, vedere [Gestire l'app Bookings](../bookings-app-admin.md) e [Integrazione in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) o [Integrazione in Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="Screenshot della scheda Visite virtuali del report Utilizzo visite virtuali che mostra i callout numerati." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data per la generazione del report. I report in genere riflettono una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |L'asse X è l'intervallo di date selezionato per il report. L'asse Y è il numero di appuntamenti.<br>Passare il puntatore del mouse sul punto in una data specificata per visualizzare il numero di appuntamenti in tale data.|
|**3**   |È possibile filtrare gli elementi visualizzati nel grafico selezionando un elemento nella legenda. Ad esempio, selezionare **Totale Bookings Visite virtuali** o **Totale visite virtuali EHR** per visualizzare solo le informazioni pertinenti. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**4**   |La tabella fornisce informazioni dettagliate su ogni appuntamento che ha avuto luogo durante l'intervallo di date selezionato. <ul><li>**L'ora di inizio (UTC)** è la data e l'ora in cui un membro del personale e un partecipante partecipano alla riunione o quando si è verificata la prima attività nella riunione.  </li> <li>**L'ID riunione** è l'ID univoco della riunione.</li> <li>**Il tempo di attesa della sala d'attesa** è il tempo tra il momento in cui un partecipante entra per la prima volta nella sala di attesa quando lo stesso partecipante o un altro partecipante viene ammesso alla riunione da un membro del personale.</li><li>**La durata** è la differenza tra l'ora di inizio e la data in cui l'ultima persona esce dalla riunione. Se sia un membro del personale che un partecipante non hanno partecipato alla riunione, la durata viene visualizzata come 0 (zero).</li> <li>**Lo stato** mostra lo stato della riunione. <ul><li>**Completato**: se uno o più membri del personale e partecipanti accedono alla riunione e la riunione è terminata. Oppure, se uno o più partecipanti accedono alla riunione e la riunione è terminata.</li> <li> **Nessuna presentazione**: se un membro del personale partecipa alla riunione ma nessun altro utente partecipa e la riunione è terminata. </li></ul> </li> <li>**Tipo di riunione** indica se l'appuntamento virtuale è stato pianificato tramite l'app Bookings o il connettore EHR Teams.</li> <li>**Partecipanti** è il numero totale di membri del personale e partecipanti alla riunione.</li> <li>**L'SMS inviato** indica se è stata inviata una notifica SMS ai partecipanti. </li> </li> </ul> |
|**5**   |Selezionare **Impostazioni** per aprire il riquadro **di analisi Visite virtuali**. Da qui è possibile disattivare o attivare i report delle visite virtuali per l'organizzazione e aggiungere o rimuovere colonne nella tabella. Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**6**   |È possibile esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi nella scheda **Download** scegliere **Scarica** per scaricare il report quando è pronto.|

### <a name="duration"></a>Durata

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="Screenshot della scheda Durata del report utilizzo visite virtuali che mostra i callout numerati." lightbox="../media/virtual-visits-usage-report-duration.png":::

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data per la generazione del report. I report in genere riflettono una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |L'asse X è l'intervallo di date selezionato per il report. L'asse Y è il numero di minuti.<br>Passare il puntatore del mouse sul punto in una data specificata per visualizzare la durata media dell'appuntamento o il tempo medio di attesa della sala di attesa per una data specificata.  |
|**3**   |È possibile filtrare gli elementi visualizzati nel grafico selezionando un elemento nella legenda. Ad esempio, seleziona **Durata media visita virtuale** o **Tempo medio di attesa della sala di attesa** per visualizzare solo le informazioni pertinenti. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**4**   |La tabella fornisce informazioni dettagliate su ogni appuntamento che ha avuto luogo durante l'intervallo di date selezionato. <ul><li>**L'ora di inizio (UTC)** è la data e l'ora in cui un membro del personale e un partecipante partecipano alla riunione o quando si è verificata la prima attività nella riunione.  </li> <li>**L'ID riunione** è l'ID univoco della riunione.</li> <li>**Il tempo di attesa della sala d'attesa** è il tempo tra il momento in cui un partecipante entra per la prima volta nella sala di attesa quando lo stesso partecipante o un altro partecipante viene ammesso alla riunione da un membro del personale.</li><li>**La durata** è la differenza tra l'ora di inizio e la data in cui l'ultima persona esce dalla riunione. Se sia un membro del personale che un partecipante non hanno partecipato alla riunione, la durata viene visualizzata come 0 (zero).</li> <li>**Lo stato** mostra lo stato della riunione. <ul><li>**Completato**: se uno o più membri del personale e partecipanti accedono alla riunione e la riunione è terminata. Oppure, se uno o più partecipanti accedono alla riunione e la riunione è terminata.</li> <li> **Nessuna presentazione**: se un membro del personale partecipa alla riunione ma nessun altro utente partecipa e la riunione è terminata. </li></ul> </li> <li>**Tipo di riunione** indica se l'appuntamento virtuale è stato pianificato tramite l'app Bookings o il connettore EHR Teams.</li> <li>**Partecipanti** è il numero totale di membri del personale e partecipanti alla riunione.</li> <li>**L'SMS inviato** indica se è stata inviata una notifica SMS ai partecipanti. </li> </li> </ul>|
|**5**   |Selezionare **Impostazioni** per aprire il riquadro **di analisi Visite virtuali**. Da qui è possibile disattivare o attivare i report delle visite virtuali per l'organizzazione e aggiungere o rimuovere colonne nella tabella. Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**6**   |È possibile esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi nella scheda **Download** scegliere **Scarica** per scaricare il report quando è pronto.|
### <a name="bookings"></a>Bookings

Vedrai questa scheda se hai una licenza che include l'app Bookings. Per altre informazioni, vedere [Gestire l'app Bookings](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="Screenshot della scheda Bookings del report utilizzo visite virtuali che mostra i callout numerati." lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data per la generazione del report. I report in genere riflettono una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |L'asse X è l'intervallo di date selezionato per il report. L'asse Y è il numero di appuntamenti Bookings.<br>Passare il puntatore del mouse sul punto in una data specificata per visualizzare il numero di appuntamenti Bookings che si sono verificati in tale data.|
|**3**   |La tabella fornisce informazioni dettagliate su ogni appuntamento che ha avuto luogo durante l'intervallo di date selezionato. <ul><li>**L'ora di inizio (UTC)** è la data e l'ora in cui un membro del personale e un partecipante partecipano alla riunione o quando si è verificata la prima attività nella riunione.  </li> <li>**L'ID riunione** è l'ID univoco della riunione.</li> <li>**Il tempo di attesa della sala d'attesa** è il tempo tra il momento in cui un partecipante entra per la prima volta nella sala di attesa quando lo stesso partecipante o un altro partecipante viene ammesso alla riunione da un membro del personale.</li><li>**La durata** è la differenza tra l'ora di inizio e la data in cui l'ultima persona esce dalla riunione. Se sia un membro del personale che un partecipante non hanno partecipato alla riunione, la durata viene visualizzata come 0 (zero).</li> <li>**Lo stato** mostra lo stato della riunione. <ul><li>**Completato**: se uno o più membri del personale e partecipanti accedono alla riunione e la riunione è terminata. Oppure, se uno o più partecipanti accedono alla riunione e la riunione è terminata.</li> <li> **Nessuna presentazione**: se un membro del personale partecipa alla riunione ma nessun altro utente partecipa e la riunione è terminata. </li></ul> </li> <li>**Tipo di riunione** indica se l'appuntamento virtuale è stato pianificato tramite l'app Bookings o il connettore EHR Teams.</li> <li>**Partecipanti** è il numero totale di membri del personale e partecipanti alla riunione.</li> <li>**L'SMS inviato** indica se è stata inviata una notifica SMS ai partecipanti. </li> </li> </ul>|
|**4**   |Selezionare **Impostazioni** per aprire il riquadro **di analisi Visite virtuali**. Da qui è possibile disattivare o attivare i report delle visite virtuali per l'organizzazione e aggiungere o rimuovere colonne nella tabella. Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |È possibile esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi nella scheda **Download** scegliere **Scarica** per scaricare il report quando è pronto.|
### <a name="ehr"></a>EHR

Questa scheda viene visualizzata se si ha una licenza che include il connettore Teams EHR. Per ulteriori informazioni, vedi [Integrazione in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) o [Integrazione in Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="Screenshot della scheda EHR del report utilizzo visite virtuali che mostra i callout numerati." lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data per la generazione del report. I report in genere riflettono una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |L'asse X è l'intervallo di date selezionato per il report. L'asse Y è il numero di appuntamenti EHR.<br>Passare il puntatore del mouse sul punto in una data specificata per visualizzare il numero di appuntamenti EHR in tale data.|
|**3**   |La tabella fornisce informazioni dettagliate su ogni appuntamento che ha avuto luogo durante l'intervallo di date selezionato. <ul><li>**L'ora di inizio (UTC)** è la data e l'ora in cui un membro del personale e un partecipante partecipano alla riunione o quando si è verificata la prima attività nella riunione.  </li> <li>**L'ID riunione** è l'ID univoco della riunione.</li> <li>**Il tempo di attesa della sala d'attesa** è il tempo tra il momento in cui un partecipante entra per la prima volta nella sala di attesa quando lo stesso partecipante o un altro partecipante viene ammesso alla riunione da un membro del personale.</li><li>**La durata** è la differenza tra l'ora di inizio e la data in cui l'ultima persona esce dalla riunione. Se sia un membro del personale che un partecipante non hanno partecipato alla riunione, la durata viene visualizzata come 0 (zero).</li> <li>**Lo stato** mostra lo stato della riunione. <ul><li>**Completato**: se uno o più membri del personale e partecipanti accedono alla riunione e la riunione è terminata. Oppure, se uno o più partecipanti accedono alla riunione e la riunione è terminata.</li> <li> **Nessuna presentazione**: se un membro del personale partecipa alla riunione ma nessun altro utente partecipa e la riunione è terminata. </li></ul> </li> <li>**Tipo di riunione** indica se l'appuntamento virtuale è stato pianificato tramite l'app Bookings o il connettore EHR Teams.</li> <li>**Partecipanti** è il numero totale di membri del personale e partecipanti alla riunione.</li> <li>**L'SMS inviato** indica se è stata inviata una notifica SMS ai partecipanti. </li> </li> </ul>|
|**4**   |Selezionare **Impostazioni** per aprire il riquadro **di analisi Visite virtuali**. Da qui è possibile disattivare o attivare i report delle visite virtuali per l'organizzazione e aggiungere o rimuovere colonne nella tabella. Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |È possibile esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi nella scheda **Download** scegliere **Scarica** per scaricare il report quando è pronto.|

> [!NOTE]
> Se l'organizzazione vuole partecipare all'anteprima privata per consentire agli utenti non amministratori, ad esempio i decisori aziendali, di accedere al report e [visualizzarlo, contattaci](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>Articoli correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).
- [Appuntamenti virtuali con Teams e l'app Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Appuntamenti virtuali con Teams - Integrazione in Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Appuntamenti virtuali con Teams - Integrazione in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
