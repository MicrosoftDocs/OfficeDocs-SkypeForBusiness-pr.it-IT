---
title: Configurare call quality dashboard (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Informazioni su come attivare e usare il dashboard qualità delle chiamate e ottenere report riepilogati sulla qualità delle chiamate.
ms.openlocfilehash: cf4c6d56e4fa646495383b4998e80789d9cdaca67b9cc35d07f613cda4e70b85
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300452"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>Come configurare il dashboard qualità delle chiamate

Apri il dashboard di qualità delle chiamate Microsoft (CQD) all'indirizzo [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (accedi con le credenziali di amministratore). Oppure vai all'interfaccia Teams e seleziona **Call Quality Dashboard**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot of the Call quality dashboard button in Teams admin center":::

Nella pagina visualizzata fare clic su **Accedi** e immettere l'account amministratore globale o Microsoft Teams'account amministratore. Dopo la prima volta che accedi, CQD inizierà a raccogliere ed elaborare i dati. Tenere presente che potrebbero essere sufficienti una o più ore per elaborare dati sufficienti per visualizzare risultati significativi nei report.

CQD mostra la qualità delle chiamate e delle riunioni, a livello di organizzazione, per Microsoft Teams, Skype for Business Online e Skype for Business Server 2019. 

> [!IMPORTANT]
> Per utilizzare CQD con Skype for Business Server 2019, è necessario [configurare il connettore dati di chiamata.](/skypeforbusiness/hybrid/configure-call-data-connector) Prima [di iniziare, vedere Plan Call Data Connector.](/skypeforbusiness/hybrid/plan-call-data-connector)


## <a name="assign-admin-roles-for-access-to-cqd"></a>Assegnare ruoli di amministratore per l'accesso a CQD

[Assegnare](/microsoft-365/admin/add-users/about-admin-roles) ruoli per l'accesso AQD alle persone che devono usarlo.

Se si desidera che gli utenti non amministratori (ad esempio tecnici del supporto tecnico e agenti dell'helpdesk) utilizzino il Dashboard qualità chiamata, è possibile assegnare a tali utenti uno dei ruoli seguenti, che consente l'accesso a CQD. 


|&nbsp;  |Visualizzazione di report  |Visualizzare i campi EUII  |Creazione di rapporti  |Upload di compilazione  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Amministratore globale     |Sì         |Sì         |Sì         |Sì         |
|Teams Amministratore     |Sì         |Sì         |Sì         |Sì         |
|Amministratore delle comunicazioni di Teams     |Sì         |Sì         |Sì         |Sì         |
|Tecnico del supporto delle comunicazioni di Teams     |Sì         |Sì         |Sì         |No         |
|Specialista del supporto delle comunicazioni di Teams     |Sì         |No         |Sì         |No         |
|Amministratore di Skype for Business     |Sì         |Sì         |Sì         |Sì         |
|Ruolo con autorizzazioni di lettura globali |Sì         |Sì         |Sì         |No         |
|Lettore report<sup>1</sup>     |Sì         |No         |Sì         |No         |

<sup>1</sup> Oltre a leggere i report CQD, [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) il lettore di report può visualizzare tutti i report attività nell'interfaccia di amministrazione e tutti i report del pacchetto di contenuto [Microsoft 365 Adoption.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Se non viene visualizzato [EUII (informazioni](CQD-data-and-reports.md#euii-data) identificabili dall'utente finale) e si dispone di uno dei ruoli autorizzati a visualizzare queste informazioni, tenere presente che CQD mantiene solo EUII per 28 giorni. Qualsiasi elemento precedente a 28 giorni viene eliminato.

Per ulteriori informazioni su questi ruoli, vedere [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).


Dopo la prima volta che accedi, CQD inizierà a raccogliere ed elaborare i dati. A partire da dicembre 2019, è ancora possibile accedere alla versione precedente di CQD (cqd.lync.com), anche se il portale legacy offre un collegamento all'ultima versione di CQD (cqd.teams.microsoft.com). Alla fine, la versione precedente di CQD verrà rimossa. A partire dal 1° luglio 2020, la versione precedente di CQD accede ai dati dall'ultimo CQD.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Eseguire la migrazione di dati e report di compilazione dalla versione precedente di CQD

> [!IMPORTANT]
> A partire dal 1° luglio 2020, non è più possibile eseguire la migrazione dei dati e dei report degli edifici dal vecchio CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Usare Power BI per analizzare i dati di Dashboard Qualità della chiamata

Novità di gennaio 2020: [scaricare Power BI modelli di query per CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelli Power BI personalizzabili che puoi usare per analizzare e segnalare i dati CQD.

Leggere [Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md) per altre informazioni.


## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Cosa si intende per CQD?](CQD-what-is-call-quality-dashboard.md)

[Caricare tenant e creare dati](CQD-upload-tenant-building-data.md)

[Dati e report di CQD](CQD-data-and-reports.md)

[Usare CQD per gestire la qualità di chiamate e riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Dashboard Qualità della chiamata](CQD-Power-BI-query-templates.md)
