---
title: Microsoft Teams utilizzo delle visite virtuali
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
description: Informazioni su come usare il report sull'utilizzo delle visite virtuali nell'interfaccia di amministrazione Microsoft Teams per ottenere una panoramica dell'attività Visite virtuali nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b3432ea92ad89c5304d81b266fce61fb9b95d5b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435850"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams utilizzo delle visite virtuali

Il report sull'utilizzo delle visite virtuali nell'interfaccia Microsoft Teams di amministrazione offre una panoramica Teams'attività Visite virtuali nell'organizzazione. È possibile visualizzare le attività dettagliate per gli appuntamenti virtuali pianificati tramite [l'app Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) e il connettore [Microsoft Teams Electronic Health Record (EHR](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-visits-and-electronic-healthcare-record-ehr-integration)).

Per visualizzare il report, è necessario essere un amministratore globale o Teams amministratore.

Il report contiene le schede seguenti. Le informazioni visualizzate nel report dipendono dal fatto che si abbia una licenza per l'app Bookings, il connettore Teams EHR o entrambi.

|SCHEDA |Descrizione  |
|---------|---------|
|**[Visite virtuali](#virtual-visits)**     |Mostra il numero totale di visite virtuali, con un'analisi del numero di visite pianificate tramite l'app Bookings e Teams riunioni integrate con EHR condotte dal sistema EHR.         |
|**[Durata](#duration)**     |Mostra la durata media delle visite e il tempo medio di attesa della sala d'attesa dei partecipanti.         |
|**[Bookings](#bookings)**     |Mostra il numero di visite pianificate tramite l'app Bookings.         |
|**[EHR](#ehr)**     |Mostra il numero di Teams visite integrate con EHR effettuate dal sistema EHR.         |  

Usare questo report per ottenere informazioni approfondite sulle attività e sulle tendenze delle visite virtuali nell'organizzazione. Queste informazioni consentono di ottimizzare le visite virtuali per ottenere risultati aziendali migliori.

## <a name="view-the-virtual-visits-usage-report"></a>Visualizzare il report sull'utilizzo di Visite virtuali

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione scegliere **Analisi &** **reportUsage** >  report. Nella scheda **Visualizza report** , in **Report**, selezionare **Utilizzo visite virtuali**.
2. In **Intervallo di date** selezionare un intervallo di date di 7, 30 o 90 giorni. Quindi, scegliere **Esegui report**.

> [!NOTE]
> Per impostazione predefinita, l'analisi delle visite virtuali è disponibile e il report. Usando questo report, si assegna a Microsoft l'autorizzazione per raccogliere dati sulle visite virtuali nell'organizzazione. Per informazioni sui criteri di conservazione dei dati, vedere Conservazione, eliminazione e distruzione dei dati [in Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).
>
>Se si vuole disattivare il report per l'organizzazione, è possibile **farlo in Impostazioni** nell'angolo in alto a destra della pagina. Questa impostazione può richiedere da 0 (zero) a 2 ore dopo la modifica.

## <a name="interpret-the-report"></a>Interpretare il report

### <a name="virtual-visits"></a>Visite virtuali

I grafici visualizzati variano a seconda che si abbia una licenza per l'app Bookings, il connettore Teams EHR o entrambi. Per altre informazioni, vedere [Gestire l'app Bookings](../bookings-app-admin.md) e [Integrazione in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) o [Integrazione in Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="Screenshot della scheda Visite virtuali del report sull'utilizzo delle visite virtuali che mostra callout numerati." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data in cui è stato generato il report. I report in genere riflettono una latenza da 24 a 48 ore dal momento dell'attività. |
|**2**   |L'asse X è l'intervallo di date selezionato per il report. L'asse Y è il numero di visite.<br>Posizionare il puntatore del mouse sul punto in una data specifica per visualizzare il numero di visite in tale data.|
|**3**   |È possibile filtrare gli elementi visualizzati nel grafico selezionando un elemento nella legenda. Ad esempio, selezionare **Total Bookings Virtual Visits** o **Total EHR Virtual Visits** per visualizzare solo le informazioni relative a ognuna. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**4**   |La tabella fornisce informazioni dettagliate su ogni visita che ha avuto luogo durante l'intervallo di date selezionato. <ul><li>**L'ora di inizio (UTC)** è la data e l'ora in cui un membro del personale e un partecipante sono presenti alla riunione o quando si è verificata la prima attività nella riunione.  </li> <li>**ID riunione** è l'ID univoco della riunione.</li> <li>**Il tempo di attesa** della sala di attesa è il tempo che deve essere compreso tra il momento in cui un partecipante partecipa per la prima volta alla sala di attesa quando lo stesso partecipante o un altro partecipante viene ammesso alla riunione da un membro del personale.</li><li>**Durata** è la differenza di tempo tra l'ora di inizio e la data in cui l'ultima persona lascia la riunione. Se sia un membro del personale che un partecipante non hanno fatto parte della riunione, la durata viene visualizzata come 0 (zero).</li> <li>**Lo stato** mostra lo stato della riunione. <ul><li>**Completato**: se uno o più membri del personale e partecipanti aderiscono alla riunione e la riunione è terminata. Oppure, se uno o più partecipanti aderiscono alla riunione e la riunione è terminata.</li> <li> **Nessuna presentazione**: se un membro del personale partecipa alla riunione ma nessun altro utente partecipa e la riunione è terminata. </li></ul> </li> <li>**Il tipo di** riunione indica se l'appuntamento virtuale è stato pianificato tramite l'app Bookings o il Teams EHR.</li> <li>**Partecipanti è** il numero totale di membri del personale e partecipanti alla riunione.</li> <li>**SMS inviato** indica se è stata inviata una notifica SMS ai partecipanti. </li> </li> </ul> |
|**5**   |Selezionare **Impostazioni** per aprire il **riquadro analisi visite** virtuali. Da qui è possibile disattivare o attivare il report Visite virtuali per l'organizzazione e aggiungere o rimuovere colonne nella tabella. Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**6**   |È possibile esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi nella scheda **Download** scegliere **Scarica** per scaricare il report quando è pronto.|

### <a name="duration"></a>Durata

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="Screenshot della scheda Durata del report sull'utilizzo delle visite virtuali che mostra i callout numerati." lightbox="../media/virtual-visits-usage-report-duration.png":::

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data in cui è stato generato il report. I report in genere riflettono una latenza da 24 a 48 ore dal momento dell'attività. |
|**2**   |L'asse X è l'intervallo di date selezionato per il report. L'asse Y è il numero di minuti.<br>Posizionare il puntatore del mouse sul punto in una data specifica per visualizzare la durata media della visita o il tempo medio di attesa della sala d'attesa per una data specifica.  |
|**3**   |È possibile filtrare gli elementi visualizzati nel grafico selezionando un elemento nella legenda. Ad esempio, selezionare **Durata media visita virtuale** o **Tempo** medio di attesa della sala di attesa per visualizzare solo le informazioni correlate a ognuna di essi. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**4**   |La tabella fornisce informazioni dettagliate su ogni visita che ha avuto luogo durante l'intervallo di date selezionato. <ul><li>**L'ora di inizio (UTC)** è la data e l'ora in cui un membro del personale e un partecipante sono presenti alla riunione o quando si è verificata la prima attività nella riunione.  </li> <li>**ID riunione** è l'ID univoco della riunione.</li> <li>**Il tempo di attesa** della sala di attesa è il tempo che deve essere compreso tra il momento in cui un partecipante partecipa per la prima volta alla sala di attesa quando lo stesso partecipante o un altro partecipante viene ammesso alla riunione da un membro del personale.</li><li>**Durata** è la differenza di tempo tra l'ora di inizio e la data in cui l'ultima persona lascia la riunione. Se sia un membro del personale che un partecipante non hanno fatto parte della riunione, la durata viene visualizzata come 0 (zero).</li> <li>**Lo stato** mostra lo stato della riunione. <ul><li>**Completato**: se uno o più membri del personale e partecipanti aderiscono alla riunione e la riunione è terminata. Oppure, se uno o più partecipanti aderiscono alla riunione e la riunione è terminata.</li> <li> **Nessuna presentazione**: se un membro del personale partecipa alla riunione ma nessun altro utente partecipa e la riunione è terminata. </li></ul> </li> <li>**Il tipo di** riunione indica se l'appuntamento virtuale è stato pianificato tramite l'app Bookings o il Teams EHR.</li> <li>**Partecipanti è** il numero totale di membri del personale e partecipanti alla riunione.</li> <li>**SMS inviato** indica se è stata inviata una notifica SMS ai partecipanti. </li> </li> </ul>|
|**5**   |Selezionare **Impostazioni** per aprire il **riquadro analisi visite** virtuali. Da qui è possibile disattivare o attivare il report Visite virtuali per l'organizzazione e aggiungere o rimuovere colonne nella tabella. Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**6**   |È possibile esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi nella scheda **Download** scegliere **Scarica** per scaricare il report quando è pronto.|
### <a name="bookings"></a>Bookings

Questa scheda viene visualizzata se si ha una licenza che include l'app Bookings. Per altre informazioni, vedere [Gestire l'app Bookings](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="Screenshot della scheda Bookings del report sull'utilizzo delle visite virtuali che mostra i callout numerati." lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data in cui è stato generato il report. I report in genere riflettono una latenza da 24 a 48 ore dal momento dell'attività. |
|**2**   |L'asse X è l'intervallo di date selezionato per il report. L'asse Y è il numero di visite di Bookings.<br>Posizionare il puntatore del mouse sul punto in una data specifica per visualizzare il numero di visite di Bookings che si sono verificate in tale data.|
|**3**   |La tabella fornisce informazioni dettagliate su ogni visita che ha avuto luogo durante l'intervallo di date selezionato. <ul><li>**L'ora di inizio (UTC)** è la data e l'ora in cui un membro del personale e un partecipante sono presenti alla riunione o quando si è verificata la prima attività nella riunione.  </li> <li>**ID riunione** è l'ID univoco della riunione.</li> <li>**Il tempo di attesa** della sala di attesa è il tempo che deve essere compreso tra il momento in cui un partecipante partecipa per la prima volta alla sala di attesa quando lo stesso partecipante o un altro partecipante viene ammesso alla riunione da un membro del personale.</li><li>**Durata** è la differenza di tempo tra l'ora di inizio e la data in cui l'ultima persona lascia la riunione. Se sia un membro del personale che un partecipante non hanno fatto parte della riunione, la durata viene visualizzata come 0 (zero).</li> <li>**Lo stato** mostra lo stato della riunione. <ul><li>**Completato**: se uno o più membri del personale e partecipanti aderiscono alla riunione e la riunione è terminata. Oppure, se uno o più partecipanti aderiscono alla riunione e la riunione è terminata.</li> <li> **Nessuna presentazione**: se un membro del personale partecipa alla riunione ma nessun altro utente partecipa e la riunione è terminata. </li></ul> </li> <li>**Il tipo di** riunione indica se l'appuntamento virtuale è stato pianificato tramite l'app Bookings o il Teams EHR.</li> <li>**Partecipanti è** il numero totale di membri del personale e partecipanti alla riunione.</li> <li>**SMS inviato** indica se è stata inviata una notifica SMS ai partecipanti. </li> </li> </ul>|
|**4**   |Selezionare **Impostazioni** per aprire il **riquadro analisi visite** virtuali. Da qui è possibile disattivare o attivare il report Visite virtuali per l'organizzazione e aggiungere o rimuovere colonne nella tabella. Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |È possibile esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi nella scheda **Download** scegliere **Scarica** per scaricare il report quando è pronto.|
### <a name="ehr"></a>EHR

Questa scheda viene visualizzata se si ha una licenza che include il connettore Teams EHR. Per altre informazioni, vedere [Integrazione in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) o [Integrazione in Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="Screenshot della scheda EHR del report sull'utilizzo delle visite virtuali che mostra i callout numerati." lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data in cui è stato generato il report. I report in genere riflettono una latenza da 24 a 48 ore dal momento dell'attività. |
|**2**   |L'asse X è l'intervallo di date selezionato per il report. L'asse Y è il numero di visite EHR.<br>Posizionare il puntatore del mouse sul punto in una data specifica per visualizzare il numero di visite EHR in tale data.|
|**3**   |La tabella fornisce informazioni dettagliate su ogni visita che ha avuto luogo durante l'intervallo di date selezionato. <ul><li>**L'ora di inizio (UTC)** è la data e l'ora in cui un membro del personale e un partecipante sono presenti alla riunione o quando si è verificata la prima attività nella riunione.  </li> <li>**ID riunione** è l'ID univoco della riunione.</li> <li>**Il tempo di attesa** della sala di attesa è il tempo che deve essere compreso tra il momento in cui un partecipante partecipa per la prima volta alla sala di attesa quando lo stesso partecipante o un altro partecipante viene ammesso alla riunione da un membro del personale.</li><li>**Durata** è la differenza di tempo tra l'ora di inizio e la data in cui l'ultima persona lascia la riunione. Se sia un membro del personale che un partecipante non hanno fatto parte della riunione, la durata viene visualizzata come 0 (zero).</li> <li>**Lo stato** mostra lo stato della riunione. <ul><li>**Completato**: se uno o più membri del personale e partecipanti aderiscono alla riunione e la riunione è terminata. Oppure, se uno o più partecipanti aderiscono alla riunione e la riunione è terminata.</li> <li> **Nessuna presentazione**: se un membro del personale partecipa alla riunione ma nessun altro utente partecipa e la riunione è terminata. </li></ul> </li> <li>**Il tipo di** riunione indica se l'appuntamento virtuale è stato pianificato tramite l'app Bookings o il Teams EHR.</li> <li>**Partecipanti è** il numero totale di membri del personale e partecipanti alla riunione.</li> <li>**SMS inviato** indica se è stata inviata una notifica SMS ai partecipanti. </li> </li> </ul>|
|**4**   |Selezionare **Impostazioni** per aprire il **riquadro analisi visite** virtuali. Da qui è possibile disattivare o attivare il report Visite virtuali per l'organizzazione e aggiungere o rimuovere colonne nella tabella. Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |È possibile esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi nella scheda **Download** scegliere **Scarica** per scaricare il report quando è pronto.|

> [!NOTE]
> Se l'organizzazione vuole partecipare all'anteprima privata per gli utenti non amministratori, ad esempio i decisori aziendali, per accedere a questo report e [visualizzarlo, contattaci](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>Articoli correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).
- [Visite virtuali con Teams e l'app Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Visite virtuali con Teams - Integrazione in Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Visite virtuali con Teams - Integrazione in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
