---
title: Usare Power BI per analizzare i dati di CQD per Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Usare Power BI per analizzare i dati di CQD per Microsoft Teams.
ms.openlocfilehash: a06a3cb76cd778c132b3e8745b279035e875f16e
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588329"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usare Power BI per analizzare i dati di CQD per Microsoft Teams

Novità di gennaio 2020: scaricare i modelli di query di [Power BI per CQD.](https://www.microsoft.com/download/details.aspx?id=102291) Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di CQD.

Per i report call quality dashboard (CQD) in Teams, se si preferisce usare Power BI per eseguire query e segnalare i dati, scaricare i modelli CQD di Power BI. Quando si aprono i modelli in Power BI, viene chiesto di accedere con le credenziali di amministratore di CQD. È possibile personalizzare questi modelli di query e distribuirli a chiunque nell'organizzazione abbia una licenza di Power BI e autorizzazioni di amministratore di CQD.

Prima di usare questi file PBIT, è necessario installare Power BI Connector per [Microsoft CQD](CQD-Power-BI-connector.md) usando il file *MicrosoftCallQuality.pqx* incluso nel [download.](https://www.microsoft.com/download/details.aspx?id=102291) 

Assicurarsi di avere il ruolo di [accesso di CQD giusto](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) per accedere ai report di Power BI. 

|  |  |
|---------|---------|
|<strong>(Nuovo!)</strong> CQD Teams Operatore automatico & Report cronologico coda di chiamata.pbit     |  In questo modello sono disponibili i tre report seguenti:</p><li>Operatore automatico - che mostra l'analisi delle chiamate in arrivo nei tuoi operatori automatici.</li><li>Coda di chiamata: mostra i dati analitici delle chiamate in arrivo nelle tue code di chiamata.</li><li>Sequenza temporale agente: mostra una sequenza temporale degli agenti attivi nelle chiamate in coda di chiamata.</li><br>Per ulteriori informazioni, leggi il Operatore automatico & [cronologico della coda di chiamata.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |Questo report è progettato per consentire di eseguire il drill-up da un singolo utente per individuare la causa principale a valle della bassa qualità delle chiamate per l'utente (ad esempio, l'utente si trova in un edificio in cui si verificano problemi di rete).         |
|CQD Location Enhanced Report.pbit     | Ridefinire i report sulla posizione di CQD SPD. Include 9 report che forniscono informazioni sulla qualità delle chiamate, l'edificio WiFi, l'affidabilità e la tariffa RMC (Rate My Call) con altri drill-thrus da parte dell'utente o dell'edificio.  Assicurarsi di caricare i dati dell'edificio per ottimizzare l'esperienza di creazione di report.        |
|CQD Mobile Device Report.pbit     | Fornisce informazioni specifiche per gli utenti di dispositivi mobili, tra cui qualità delle chiamate, affidabilità e valuta le chiamate. Visualizzare i report sulle reti mobili, le reti WiFi e i report sui sistemi operativi mobili (Android, iOS).        |
|CQD PSTN Direct Routing Report.pbit     |Fornisce informazioni dettagliate specifiche per le chiamate PSTN che passano attraverso il routing diretto. Per altre informazioni, vedere l'uso del report di routing diretto PSTN di [CQD.](CQD-PSTN-report.md)         |
|CQD Summary Report.pbit     |Visualizzazioni migliori, presentazione migliorata, maggiore densità di informazioni e date di distribuzione. Questi report facilitano l'identificazione dei valori anomali. Esegui il drill-down della qualità delle chiamate in base alla posizione con una mappa interattiva facile da usare. 9 nuovi report:</p>- Qualità complessiva<br>- Affidabilità generale<br>- RMC (Rate My Call) Overall<br>- Qualità conferenza<br>- Qualità P2P<br>- Affidabilità delle conferenze<br>- Affidabilità P2P<br>- Conferenza RMC<br>- RMC P2P         |
|<strong>(Nuovo!)</strong> Report sull'utilizzo di CQD Teams.pbit     | Mostra in che modo gli utenti dell'organizzazione usano Teams e quanto. Assicurarsi di caricare i dati dell'edificio per ottimizzare l'esperienza di creazione di report. Per altre informazioni, vedere [Usare il report Power BI di CQD per visualizzare l'utilizzo di Microsoft Teams.](CQD-teams-utilization-report.md)        |
|Report CQD User Feedback (Rate My Call) (Rate My Call).     | Mostra Valuta i dati della chiamata in un modo che puoi utilizzare facilmente per supportare le chiamate per la tua organizzazione. Riferimento incrociato con verbi per identificare le opportunità di formazione degli utenti finali.        |

> [!TIP]
> Dopo aver configurato i report di Power BI per i dati di CQD, aggiungerli come scheda a un canale. Dopo aver selezionato **+** in un canale, selezionare **Power BI** e quindi trovare il report. Per altre informazioni, leggere [Report di incorporamento con la scheda Power BI per Teams.](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams) Tenere presente che solo le persone con una licenza di Power BI e le credenziali di amministratore di CQD possono accedere a questi report.


## <a name="related-topics"></a>Argomenti correlati

[Dimensioni e misure disponibili in Dashboard Qualità della chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Dashboard Qualità della chiamata](stream-classification-in-call-quality-dashboard.md)

[Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Analisi delle chiamate e Dashboard Qualità della chiamata](difference-between-call-analytics-and-call-quality-dashboard.md)
 
