---
title: Usare Power BI per analizzare i dati di Call Quality dashboard per Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Usare Power BI per analizzare i dati di Call Quality dashboard per Microsoft teams.
ms.openlocfilehash: 155bde0373880befc770d745ca246b76d4c63eec
ms.sourcegitcommit: 543f650ad4aff73bccfe7a60b66fb944b4e3c119
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2020
ms.locfileid: "42572894"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usare Power BI per analizzare i dati di Call Quality dashboard per Microsoft Teams

Novità di gennaio 2020: [scaricare i modelli di query di Power BI per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality dashboard.

Per i report di Call Quality dashboard in teams, se si preferisce usare Power BI per eseguire query e segnalare i dati, scaricare i modelli di Power BI di Call Quality dashboard. Quando si aprono i modelli in Power BI, viene chiesto di accedere con le credenziali di amministratore di Call Quality dashboard. È possibile personalizzare questi modelli di query e distribuirli a tutti gli utenti dell'organizzazione che hanno una licenza di Power BI e le autorizzazioni di amministratore di Call Quality dashboard.

Prima di poter usare questi file di PBIX, è necessario [installare il connettore Power BI per Microsoft Call Quality dashboard](CQD-Power-BI-connector.md) usando il file *MicrosoftCallQuality. PQX* incluso nel [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


|  |  |
|---------|---------|
|Report sull'helpdesk di Call Quality dashboard. pbix     |L'integrazione di dati edilizi e EUII, questo report è progettato per consentire di eseguire il drill-up da un singolo utente per trovare la causa radice a Monte di una qualità di chiamata scadente per l'utente (ad esempio, l'utente si trova in un edificio in cui si verificano problemi di rete).         |
|Call Quality dashboard posizione avanzata report. pbix     | Ripensare i report sulla posizione di Call Quality dashboard SPD. Include 9 report, fornendo la qualità delle chiamate, la creazione di Wi-Fi, l'affidabilità e le informazioni sulle chiamate di tipo RMC con ulteriori drill-thru per edificio o per utente.        |
|Report dispositivo mobile call Quality dashboard. pbix     | Offre approfondimenti specifici per gli utenti di dispositivi mobili, tra cui la qualità delle chiamate, l'affidabilità e la tariffa chiamata. Visualizzare i report di rete mobile, rete WiFi e sistemi operativi mobili (Android, iOS).        |
|Report di routing diretto PSTN Call Quality dashboard. pbix     |Fornisce informazioni specifiche per le chiamate PSTN che passano attraverso il routing diretto. Per altre informazioni, vedere [usare il report di routing diretto PSTN di Call Quality dashboard](CQD-PSTN-report.md).         |
|Report di riepilogo di Call Quality dashboard. pbix     |Visualizzazioni migliori, presentazione migliorata, maggiore densità di informazioni e date di rotolamento. Questi report semplificano l'identificazione degli outlier. Eseguire il drill-down nella qualità delle chiamate per posizione con una mappa interattiva facile da usare. 9 nuovi report:</p>-Qualità complessiva<br>-Affidabilità complessiva<br>-RMC (Vota la mia chiamata) globale<br>-Qualità conferenza<br>-Qualità P2P<br>-Affidabilità per le conferenze<br>-Affidabilità P2P<br>-RMC conferenza<br>-RMC P2P         |
|<strong>(Nuovo!)</strong> Report sull'utilizzo di teams Call Quality dashboard. pbix     | Mostra come gli utenti dell'organizzazione usano team e quanto. Per altre informazioni, vedere [usare il report di Power bi Call Quality dashboard per visualizzare l'utilizzo di Microsoft teams](CQD-teams-utilization-report.md).        |
|Feedback degli utenti di Call Quality Dashboard (Vota la mia chiamata) report. pbix     | Mostra il tasso di dati della chiamata in modo che sia possibile usare facilmente per supportare la chiamata per l'organizzazione. Riferimento incrociato con Verbatims per identificare le opportunità di formazione per gli utenti finali.        |


## <a name="related-topics"></a>Argomenti correlati

[Dimensioni e misure disponibili in Dashboard Qualità della chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Dashboard Qualità della chiamata](stream-classification-in-call-quality-dashboard.md)

[Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Analisi delle chiamate e Dashboard Qualità della chiamata](difference-between-call-analytics-and-call-quality-dashboard.md)
 