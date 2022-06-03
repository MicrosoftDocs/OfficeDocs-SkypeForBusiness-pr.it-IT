---
title: Report appuntamenti virtuali connettore EHR di Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Informazioni su come usare il report Appuntamenti virtuali del connettore EHR di Teams nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica dell'utilizzo di appuntamenti virtuali integrati con EHR nell'organizzazione.
ms.openlocfilehash: 0e78b89c934eac101b863bd7b5ba9957939f994b
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883539"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Report appuntamenti virtuali connettore EHR di Microsoft Teams

Il report appuntamenti virtuali del connettore EHR (Electronic Health Record) di Microsoft Teams nell'interfaccia di amministrazione di Microsoft Teams offre un modo semplice e rapido per visualizzare l'utilizzo di appuntamenti virtuali integrati con EHR di Teams nell'organizzazione.

Per visualizzare il report, è necessario essere un amministratore globale, un amministratore di Teams, un lettore globale o un lettore di report.

## <a name="view-the-report"></a>Visualizzare il report

Esistono due modi per accedere al report e visualizzarlo nell'interfaccia di amministrazione di Teams.

- Tramite la [scheda di utilizzo del connettore EHR](#the-ehr-connector-usage-card) nel dashboard
- Direttamente scegliendo [**Appuntamenti virtuali connettore EHR**](#the-teams-ehr-connector-virtual-appointments-report) in **Analytics & report** > **utilizzo**

### <a name="the-ehr-connector-usage-card"></a>Scheda di utilizzo del connettore EHR

Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams scegliere **Dashboard** e quindi passare alla scheda **Appuntamenti virtuali connettore EHR** .

Qui si ottiene una visualizzazione immediata dell'attività di appuntamenti virtuali integrata in EHR di Teams per mese, inclusi gli appuntamenti completati, l'allocazione rimanente e il superamento del limite mensile (a seconda della licenza in uso).

:::image type="content" source="../../media/ehr-connector-report-card.png" alt-text="Screenshot della scheda di utilizzo del connettore EHR nel dashboard dell'interfaccia di amministrazione di Teams." lightbox="../../media/ehr-connector-report-card.png":::

Scegliere **Visualizza dettagli** per visualizzare i dettagli del report. Per acquistare altre licenze, scegliere **Acquista altro**.

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>Report Appuntamenti virtuali connettore EHR di Teams

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Teams, passare a **Analisi & report** > **utilizzo**.
1. Nella scheda **Visualizza report** scegliere **Appuntamenti virtuali connettore EHR** e un intervallo di date. Quindi, seleziona **Esegui report**.

    :::image type="content" source="../../media/ehr-connector-report.png" alt-text="Screenshot del report Appuntamenti virtuali connettore EHR di Teams nell'interfaccia di amministrazione di Teams." lightbox="../../media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report mostra la data per la quale è stato generato il report e l'intervallo di date scelto.|
|**2**   |La tabella fornisce informazioni dettagliate su ogni appuntamento che ha avuto luogo durante l'intervallo di date selezionato. Tenere presente che non verranno visualizzate voci per gli appuntamenti in cui un membro del personale o un paziente non si è unito. <ul><li>**L'ora di inizio (UTC)** è la data e l'ora in cui un membro del personale e un partecipante partecipano all'appuntamento.  </li> <li>**La durata** è la differenza tra l'ora di inizio e la data in cui l'ultima persona lascia l'appuntamento.</li> <li>**Principale** è il nome dell'organizzatore della riunione. <li>**L'indirizzo di posta elettronica principale** è l'indirizzo di posta elettronica dell'organizzatore della riunione.</li> <li> **Reparto** è le informazioni del reparto per l'appuntamento. Se le informazioni non vengono visualizzate correttamente, contattare il team di supporto EHR. Per l'integrazione con Epic, assicurarsi che ```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` sia parte del record di integrazione del provider. </li></li> <li>**Operatori** è il numero totale di membri del personale e partecipanti all'appuntamento.</li> <li>**Entro limite** indica se l'appuntamento rientra nel limite di allocazione. </li> </ul> |
|**3**   |È possibile esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** per scaricare il report. |
|**4**   |Selezionare **Filtro** per filtrare la visualizzazione dei dettagli del report. |
|**5**   |Selezionare **Schermo intero** per visualizzare il report in modalità schermo intero. |
|**6**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella |

> [!NOTE]
> Per altre analisi sugli appuntamenti virtuali integrati con EHR di Teams, vedere [Report sull'utilizzo delle visite virtuali](../../teams-analytics-and-reports/virtual-visits-usage-report.md). Con il report Utilizzo visite virtuali è possibile visualizzare metriche chiave come il totale degli appuntamenti, il tempo di attesa della sala di attesa, la durata degli appuntamenti e nessuna presentazione. Usare queste informazioni per ottenere informazioni approfondite sulle tendenze di utilizzo e ottimizzare gli appuntamenti virtuali per ottenere risultati aziendali migliori.

## <a name="related-articles"></a>Articoli correlati

- [Appuntamenti virtuali con Teams - Integrazione in Cerner EHR](ehr-admin-cerner.md)
- [Appuntamenti virtuali con Teams - Integrazione in Epic EHR](ehr-admin.md) 
