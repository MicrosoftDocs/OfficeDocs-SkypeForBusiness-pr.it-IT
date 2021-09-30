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
ms.localizationpriority: medium
description: Usare Power BI per analizzare i dati CQD per Microsoft Teams.
ms.openlocfilehash: 4a96a53454f1f4d89feed3ea87342a7991d7975c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013770"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usare Power BI per analizzare i dati di CQD per Microsoft Teams

Novità di gennaio 2020: [Scaricare Power BI di query per CQD](https://www.microsoft.com/download/details.aspx?id=102291). Modelli Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati CQD.

Per i report CQD (Call Quality Dashboard) in Teams, se si preferisce usare Power BI per eseguire query e segnalare i dati, scaricare i modelli Power BI CQD. Quando si aprono i modelli in Power BI, verrà richiesto di accedere con le credenziali di amministratore di CQD. È possibile personalizzare questi modelli di query e distribuirli a chiunque nell'organizzazione abbia una licenza Power BI e autorizzazioni di amministratore di CQD.

Prima di poter usare questi file PBIT, è necessario installare il connettore Power BI per [Microsoft CQD](CQD-Power-BI-connector.md) usando il file *MicrosoftCallQuality.pqx* incluso nel [download.](https://www.microsoft.com/download/details.aspx?id=102291) 

Assicurarsi di avere il ruolo [di accesso CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) giusto per accedere ai Power BI report. 

|&nbsp;|&nbsp;|
|---------|---------|
|<strong>(Nuovo!)</strong> Report cronologico Teams Operatore automatico & coda di chiamata.pbit     |  Questo modello fornisce i tre report seguenti:</p><li>Operatore automatico: mostra l'analisi delle chiamate in arrivo nei tuoi operatori automatici.</li><li>Coda di chiamata: mostra l'analisi delle chiamate in arrivo nelle code di chiamata.</li><li>Sequenza temporale agente: mostra una visualizzazione sequenza temporale degli agenti attivi nelle chiamate in coda di chiamata.</li><br>Per altre informazioni, vedere report [Operatore automatico & cronologia della coda di chiamata.](aa-cq-cqd-historical-reports.md)        |
|Report helpdesk CQD.pbit     |Integrando i dati di edificio e EUII, questo report è progettato per consentire di eseguire il drill-up da un singolo utente per trovare la causa radice a monte della scarsa qualità delle chiamate per tale utente (ad esempio, l'utente si trova in un edificio in cui si verificano problemi di rete).         |
|CQD Location Enhanced Report.pbit     | Ri-immaginando i report sulla posizione di CQD SPD. Include 9 report, che forniscono informazioni sulla qualità delle chiamate, l'edificio WiFi, l'affidabilità e la tariffa delle chiamate personali (RMC) con ulteriori drill-thrus per edificio o per utente.  Assicurarsi di caricare i dati dell'edificio per ottimizzare l'esperienza di creazione di report.        |
|CQD Mobile Device Report.pbit     | Fornisce informazioni specifiche per gli utenti di dispositivi mobili, tra cui qualità delle chiamate, affidabilità e tariffa chiamata. Visualizza i report sulla rete mobile, la rete WiFi e il sistema operativo mobile (Android, iOS).        |
|Report di routing diretto PSTN CQD.pbit     |Fornisce informazioni dettagliate specifiche per le chiamate PSTN che passano attraverso il routing diretto. Per altre informazioni, vedere [Uso del report di routing diretto PSTN CQD.](CQD-PSTN-report.md)         |
|Report di riepilogo CQD.pbit     |Visualizzazioni migliori, presentazione migliorata, maggiore densità di informazioni e date di distribuzione. Questi report semplificano l'identificazione degli outlier. Eseguire il drill-into della qualità delle chiamate in base alla posizione con una mappa interattiva facile da usare. 9 nuovi report:</p>- Qualità generale<br>- Affidabilità generale<br>- RMC (Rate My Call) Overall<br>- Qualità conferenza<br>- Qualità P2P<br>- Affidabilità delle conferenze<br>- Affidabilità P2P<br>- RMC conferenza<br>- RMC P2P         |
|<strong>(Nuovo!)</strong> Report utilizzo Teams CQD.pbit     | Mostra come gli utenti dell'organizzazione usano Teams e quanto. Assicurarsi di caricare i dati dell'edificio per ottimizzare l'esperienza di creazione di report. Per altre informazioni, vedere [Usare il report Power BI CQD per visualizzare Microsoft Teams utilizzo.](CQD-teams-utilization-report.md)        |
|Report CQD User Feedback (Rate My Call)     | Mostra i dati valuta le chiamate personali in un modo che è possibile usare facilmente per supportare le chiamate per l'organizzazione. Riferimento incrociato con verbatims per identificare le opportunità di formazione degli utenti finali.        |

> [!TIP]
> Dopo aver configurato i report Power BI per i dati CQD, aggiungerli come scheda a un canale. Dopo aver selezionato **+** in un canale, selezionare **Power BI** e quindi trovare il report. Per altre informazioni, vedere [Incorpora report con la scheda](/power-bi/service-embed-report-microsoft-teams)Power BI per Teams . Tenere presente che solo le persone con una Power BI e le credenziali di amministratore di CQD possono accedere a questi report.


## <a name="related-topics"></a>Argomenti correlati

[Dimensioni e misure disponibili in Dashboard Qualità della chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Dashboard Qualità della chiamata](stream-classification-in-call-quality-dashboard.md)

[Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Analisi delle chiamate e Dashboard Qualità della chiamata](./monitor-call-quality-qos.md)
