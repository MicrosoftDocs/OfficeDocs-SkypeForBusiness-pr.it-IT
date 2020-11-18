---
title: Usare Power BI per analizzare i dati di Call Quality dashboard per Microsoft Teams
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
description: Usare Power BI per analizzare i dati di Call Quality dashboard per Microsoft teams.
ms.openlocfilehash: 4889428096209b9856d75caf11348ac036b4c7b0
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085570"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usare Power BI per analizzare i dati di Call Quality dashboard per Microsoft Teams

Novità di gennaio 2020: [scaricare i modelli di query di Power BI per Call Quality dashboard](https://www.microsoft.com/download/details.aspx?id=102291). Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality dashboard.

Per i report di Call Quality Dashboard (Call Quality Dashboard) in teams, se si preferisce usare Power BI per eseguire query e segnalare i dati, scaricare i modelli di Call Quality dashboard Power BI. Quando si aprono i modelli in Power BI, viene chiesto di accedere con le credenziali di amministratore di Call Quality dashboard. È possibile personalizzare questi modelli di query e distribuirli a tutti gli utenti dell'organizzazione che hanno una licenza di Power BI e le autorizzazioni di amministratore di Call Quality dashboard.

Prima di poter usare questi file di PBIT, è necessario [installare il connettore Power BI per Microsoft Call Quality dashboard](CQD-Power-BI-connector.md) usando il file *MicrosoftCallQuality. PQX* incluso nel [download](https://www.microsoft.com/download/details.aspx?id=102291). 

Verificare di avere il ruolo di [accesso Call Quality dashboard](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) appropriato per accedere ai report di Power bi. 

|  |  |
|---------|---------|
|<strong>(Nuovo!)</strong> Operatore automatico di Call Quality dashboard teams & report cronologico delle code di chiamata. PBIT     |  Questo modello fornisce i tre report seguenti:</p><li>Operatore automatico: visualizzazione di analisi per le chiamate in arrivo agli operatori automatici.</li><li>Coda di chiamata: visualizzazione di analisi per le chiamate in arrivo nelle code di chiamata.</li><li>Sequenza temporale dell'agente: visualizzazione di una sequenza temporale di agenti attivi nelle chiamate alla coda di chiamata.</li><br>Per altre informazioni, vedere [usare il report di Power bi Call Quality dashboard per visualizzare l'operatore automatico & report cronologico delle code di chiamata](CQD-teams-aa-cq-historical-report.md).        |
|Report sull'helpdesk di Call Quality dashboard. PBIT     |L'integrazione di dati edilizi e EUII, questo report è progettato per consentire di eseguire il drill-up da un singolo utente per trovare la causa radice a Monte di una qualità di chiamata scadente per l'utente (ad esempio, l'utente si trova in un edificio in cui si verificano problemi di rete).         |
|Call Quality dashboard posizione avanzata report. PBIT     | Ripensare i report sulla posizione di Call Quality dashboard SPD. Include 9 report, fornendo la qualità delle chiamate, la creazione di Wi-Fi, l'affidabilità e le informazioni sulle chiamate di tipo RMC con ulteriori drill-thru per edificio o per utente.  Assicurarsi di caricare i dati dell'edificio per massimizzare l'esperienza di creazione di report.        |
|Report dispositivo mobile call Quality dashboard. PBIT     | Offre approfondimenti specifici per gli utenti di dispositivi mobili, tra cui la qualità delle chiamate, l'affidabilità e la tariffa chiamata. Visualizzare i report di rete mobile, rete WiFi e sistemi operativi mobili (Android, iOS).        |
|Report di routing diretto PSTN Call Quality dashboard. PBIT     |Fornisce informazioni specifiche per le chiamate PSTN che passano attraverso il routing diretto. Per altre informazioni, vedere [usare il report di routing diretto PSTN di Call Quality dashboard](CQD-PSTN-report.md).         |
|Report di riepilogo di Call Quality dashboard. PBIT     |Visualizzazioni migliori, presentazione migliorata, maggiore densità di informazioni e date di rotolamento. Questi report semplificano l'identificazione degli outlier. Eseguire il drill-down nella qualità delle chiamate per posizione con una mappa interattiva facile da usare. 9 nuovi report:</p>-Qualità complessiva<br>-Affidabilità complessiva<br>-RMC (Vota la mia chiamata) globale<br>-Qualità conferenza<br>-Qualità P2P<br>-Affidabilità per le conferenze<br>-Affidabilità P2P<br>-RMC conferenza<br>-RMC P2P         |
|<strong>(Nuovo!)</strong> Report sull'utilizzo di teams Call Quality dashboard. PBIT     | Mostra come gli utenti dell'organizzazione usano team e quanto. Assicurarsi di caricare i dati dell'edificio per massimizzare l'esperienza di creazione di report. Per altre informazioni, vedere [usare il report di Power bi Call Quality dashboard per visualizzare l'utilizzo di Microsoft teams](CQD-teams-utilization-report.md).        |
|Feedback degli utenti di Call Quality Dashboard (Vota la mia chiamata) report. PBIT     | Mostra il tasso di dati della chiamata in modo che sia possibile usare facilmente per supportare la chiamata per l'organizzazione. Riferimento incrociato con Verbatims per identificare le opportunità di formazione per gli utenti finali.        |

> [!TIP]
> Dopo aver configurato i report di Power BI per i dati di Call Quality dashboard, aggiungerli come scheda a un canale. Dopo aver selezionato **+** un canale, selezionare **Power bi** e quindi trovare il report. Per altre informazioni, leggere [incorpora report con la scheda Power BI per Teams](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams). Tenere presente che solo gli utenti con una licenza di Power BI e le credenziali di amministratore di Call Quality dashboard possono accedere ai report.


## <a name="related-topics"></a>Argomenti correlati

[Dimensioni e misure disponibili in Dashboard Qualità della chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Dashboard Qualità della chiamata](stream-classification-in-call-quality-dashboard.md)

[Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Analisi delle chiamate e Dashboard Qualità della chiamata](difference-between-call-analytics-and-call-quality-dashboard.md)
 
