---
title: Usare Power BI per analizzare i dati di Call Quality Dashboard per Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
description: Usare Power BI per analizzare i dati di Call Quality Dashboard per Microsoft Teams.
ms.openlocfilehash: 45dca06abc3ee2a8980c3b963e22fbc8646e15a4
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270701"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usare Power BI per analizzare i dati di Call Quality Dashboard per Microsoft Teams

Novità di luglio 2022: il nuovo modello QER (Quality of Experience) è stato aggiunto ai modelli di [query di Power BI per il download di CQD](https://www.microsoft.com/download/details.aspx?id=102291). QER è un potente modello di creazione di report che sostituisce i modelli di query di Power BI originali di Call Quality Dashboard rilasciati nel 2020. Anche se i modelli originali rimarranno disponibili a scopo dimostrativo, non sono più supportati ed è consigliabile che i clienti passino al modello QER, che continuerà a ricevere gli aggiornamenti. Si noti che ciò non si applica al Call Quality Dashboard Operatore automatico di Teams & Rapporto storico coda di chiamata.

Per i report di Call Quality Dashboard (CQD) in Teams, se si preferisce usare Power BI per eseguire query e segnalare i dati, scaricare i modelli di Power BI di Call Quality Dashboard. Quando si aprono i modelli in Power BI, viene chiesto di accedere con le credenziali di amministratore di Call Quality Dashboard. È possibile personalizzare questi modelli di query e distribuirli a chiunque nell'organizzazione disponga di una licenza di Power BI e delle autorizzazioni di amministratore di Call Quality Dashboard.

Prima di usare questi file PBIT, è necessario [installare Power BI Connector per Microsoft CQD](CQD-Power-BI-connector.md) usando il file *MicrosoftCallQuality.pqx* incluso nel [download](https://www.microsoft.com/download/details.aspx?id=102291). 

Assicurarsi di avere il ruolo di accesso corretto a [Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) per accedere ai report di Power BI. 

|Pbit |Descrizione |
|:----------|:---------|
|<strong>(Novità)</strong> QER.pbit     |  Il modello Rapporto sulla qualità dell'esperienza (QER) consente ai clienti di identificare in modo proattivo i problemi che influiscono sull'esperienza di chiamata e riunione di Teams prima dell'escalation. Vengono inoltre forniti report per consentire agli amministratori di rispondere rapidamente all'escalation dei problemi e contribuire a rispondere alla domanda "Cosa è successo durante la riunione?"  Questo modello fornisce i report seguenti:</p><li>Ricerca: consente la ricerca in base all'URL della riunione, all'ID conferenza, alla subnet o all'UPN.</li><li>Dettagli sull'integrità delle riunioni: metriche dettagliate per una singola riunione.</li><li>Dettagli integrità utente: metriche dettagliate per un singolo utente.</li><li>Media Health - Panoramica di alto livello degli indicatori di integrità chiave (KHI) per l'integrità generale delle chiamate e delle riunioni tenant.</li><li>Configurazione supporti: analizza gli errori di configurazione dei supporti.</li><li>Affidabilità dei supporti: analizzare i problemi di affidabilità dei supporti.</li><li>Integrità audio/video/condivisione: verifica l'integrità delle schede KHI di livello intermedio per l'audio, il video o la condivisione.</li><li>Dettagli sull'integrità audio/video/condivisione: esamina metriche dettagliate su audio, video o integrità della condivisione.</li><li>VPN: esamina l'impatto della VPN sull'integrità delle riunioni. (VPN stimata o mappata)</li><li>Primi 10 report: identificare le aree problematiche nel tenant.</li><li>Dailies : rivedi il rapporto giornaliero degli KHI.</li><li>Utilizzo: uso generale delle chiamate e delle riunioni.</li><li>Feedback degli utenti: consente di esaminare il feedback dei sondaggi degli utenti, noto anche come Valuta la mia chiamata.</li><li>Trasporto: identificare le reti che bloccano UDP.</li><li>Dispositivi: esamina l'impatto dei dispositivi.</li><li>Client: esaminare le metriche basate sul client.</li><li>Creazione di dati: esaminare il file di dati dell'edificio in Call Quality Dashboard.</li><li>Integrità PSTN e Dettagli utente: due report che forniscono un riepilogo generale e l'integrità dei singoli utenti per le chiamate basate su PSTN.</li><li>Metriche di rete: due report che visualizzano i dettagli delle metriche di rete non elaborate per instabilità, perdita di pacchetti e latenza.</li> <br/> Questo modello sostituisce i modelli deprecati come indicato di seguito.|
|CQD Teams Auto Attendant & Call Queue Historical Report.pbit     |  Questo modello fornisce i tre report seguenti:</p><li>Operatore automatico: mostra i dati analitici per le chiamate in arrivo agli operatori automatici.</li><li>Coda di chiamata, che mostra i dati analitici per le chiamate in arrivo nelle code di chiamata.</li><li>Sequenza temporale agente: mostra una visualizzazione sequenza temporale degli agenti attivi nelle chiamate in coda di chiamata.</li><br>Per saperne di più, leggi [Operatore automatico & Rapporto storico coda di chiamata](aa-cq-cqd-historical-reports.md). |
|CQD Teams Utilization Report.pbit     | Mostra in che modo gli utenti dell'organizzazione usano Teams e quanto. Assicurarsi di caricare i dati dell'edificio per ottimizzare l'esperienza di creazione dei report. Per altre informazioni, vedere [Usare il report di Power BI di CQD per visualizzare l'utilizzo di Microsoft Teams](CQD-teams-utilization-report.md). |
|CQD PSTN Direct Routing Report.pbit <br/> *(Deprecato)*    | Modello di esempio che fornisce informazioni specifiche per le chiamate PSTN che passano attraverso il routing diretto. Per altre informazioni, vedere [Uso del report routing diretto PSTN CQD](CQD-PSTN-report.md). |
|Call Quality Dashboard Helpdesk Report.pbit <br/> *(Deprecato)*     |Integrando dati building ed EUII, questo modello illustra come creare un report per consentire il drill-through da un singolo utente per trovare la causa radice upstream di bassa qualità delle chiamate per l'utente (ad esempio, l'utente si trova in un edificio che presenta problemi di rete). |
|CQD Location Enhanced Report.pbit <br/> *(Deprecato)*     | Questo modello di esempio ri-immagina i report sulla posizione di CQD SPD. Include 9 report, con informazioni aggiuntive sulla qualità delle chiamate, sulla creazione di wi-fi, sull'affidabilità e sulla tariffa delle chiamate (RMC, Rate My Call) con ulteriori drill-thrus per edificio o per utente. Assicurarsi di caricare i dati dell'edificio per ottimizzare l'esperienza di creazione dei report. |
|CQD Mobile Device Report.pbit <br/> *(Deprecato)*     | Questo modello di esempio fornisce informazioni dettagliate appositamente ottimizzate per gli utenti di dispositivi mobili, tra cui Qualità chiamata, Affidabilità e Valuta la mia chiamata. Visualizza i report sulla rete mobile, sulla rete WiFi e sul sistema operativo per dispositivi mobili (Android, iOS). |
|Call Quality Dashboard - Riepilogo Report.pbit <br/> *(Deprecato)*    | Dimostrazione di come CQD combinato con Power BI può offrire visualizzazioni migliori, presentazioni migliorate, una maggiore densità di informazioni e date di distribuzione. Questi report semplificano l'identificazione dei valori anomali. Analizzare la qualità delle chiamate in base alla posizione con una mappa interattiva facile da usare. Nove nuovi report:</p>- Qualità complessiva<br>- Affidabilità complessiva<br>- RMC (Valuta la mia chiamata) in generale<br>- Qualità conferenza<br>- Qualità P2P<br>- Affidabilità delle conferenze<br>- Affidabilità P2P<br>- Conference RMC<br>- P2P RMC         |
|CQD User Feedback (Rate My Call) Report.pbit <br/> *(Deprecato)*    | Dimostrazione di un report di Power BI con l'opzione Valuta chiamata personale in modo da poter essere usata facilmente per supportare le chiamate per l'organizzazione. Riferimento incrociato con verbatims per identificare le opportunità di formazione degli utenti finali. |

> [!TIP]
> Dopo aver configurato i report di Power BI per i dati di Call Quality Dashboard, aggiungerli come scheda a un canale. Dopo aver selezionato **+** in un canale, selezionare **Power BI** e quindi trovare il report. Per altre informazioni, vedere [Incorporare il report con la scheda Power BI per Teams](/power-bi/service-embed-report-microsoft-teams). Tenere presente che solo le persone con una licenza di Power BI e le credenziali di amministratore di Call Quality Dashboard possono accedere a questi report.

## <a name="related-topics"></a>Argomenti correlati

[Dimensioni e misure disponibili in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Dashboard Qualità della chiamata](stream-classification-in-call-quality-dashboard.md)

[Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Analisi delle chiamate e Dashboard Qualità della chiamata](./monitor-call-quality-qos.md)
