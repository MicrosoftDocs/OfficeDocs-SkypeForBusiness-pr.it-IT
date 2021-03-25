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
description: Informazioni su come attivare e usare il dashboard qualità delle chiamate e ottenere report di riepilogo sulla qualità delle chiamate.
ms.openlocfilehash: 2d671de0e2ddc5d4c2a4e321cf90e2e2f0dbe770
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162697"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Configurare call quality dashboard (CQD)

Aprire microsoft Call Quality Dashboard (CQD) all'indirizzo [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (accedere con le credenziali di amministratore). Oppure vai all'interfaccia di amministrazione di Teams e seleziona **Call Quality Dashboard**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

Nella pagina visualizzata fare clic su **Accedi e** immettere l'account amministratore globale o le informazioni sull'account di amministratore del servizio Microsoft Teams. Dopo la prima volta che si accede, CQD inizierà a raccogliere ed elaborare i dati. Tenere presente che potrebbero essere sufficienti una o più ore per elaborare dati sufficienti per visualizzare risultati significativi nei report.

CQD mostra la qualità delle chiamate e delle riunioni, a livello di organizzazione, per Microsoft Teams, Skype for Business Online e Skype for Business Server 2019. 

> [!IMPORTANT]
> Per usare CQD con Skype for Business Server 2019, è necessario [configurare Call Data Connector.](/skypeforbusiness/hybrid/configure-call-data-connector) Vedere [Pianificare Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) prima di iniziare.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Assegnare ruoli di amministratore per l'accesso a CQD

Assegnare [ruoli](/microsoft-365/admin/add-users/about-admin-roles) per l'accesso a CQD alle persone che devono usarlo.

Se si vuole che gli utenti non amministratori, ad esempio tecnici del supporto tecnico e agenti helpdesk, usino call quality dashboard, è possibile assegnare a tali utenti uno dei ruoli seguenti, che consente l'accesso a CQD. 


|  |Visualizzare i report  |Visualizzare i campi EUII  |Creare report  |Caricare i dati dell'edificio  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Amministratore globale     |Sì         |Sì         |Sì         |Sì         |
|Amministratore del servizio Teams     |Sì         |Sì         |Sì         |Sì         |
|Amministratore comunicazioni Teams     |Sì         |Sì         |Sì         |Sì         |
|Tecnico supporto comunicazioni Teams     |Sì         |Sì         |Sì         |No         |
|Specialista del supporto tecnico di Teams Communications     |Sì         |No         |Sì         |No         |
|Amministratore di Skype for Business     |Sì         |Sì         |Sì         |Sì         |
|Lettore globale |Sì         |Sì         |Sì         |No         |
|Lettore report<sup>1</sup>     |Sì         |No         |Sì         |No         |

<sup>1</sup> Oltre a leggere i report CQD, [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) l'utilità per la lettura dei report può visualizzare tutti i report attività nell'interfaccia di amministrazione e tutti i report del pacchetto di contenuto [Microsoft 365 Adoption.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Se l'interfaccia [EUII (informazioni](CQD-data-and-reports.md#euii-data) identificabili dall'utente finale) non è visualizzata e si ha uno dei ruoli autorizzati a visualizzare queste informazioni, tenere presente che CQD mantiene solo EUII per 28 giorni. Qualsiasi elemento più vecchio di 28 giorni viene eliminato.

Per altre informazioni su questi ruoli, vedere Informazioni sui ruoli di amministratore [di Office 365.](/office365/admin/add-users/about-admin-roles)


Dopo la prima volta che si accede, CQD inizierà a raccogliere ed elaborare i dati. A partire da dicembre 2019 è ancora possibile accedere alla versione precedente di CQD (cqd.lync.com), anche se il portale legacy offre un collegamento all'ultima versione di CQD (cqd.teams.microsoft.com). Alla fine, la versione precedente di CQD verrà rimossa. A partire dal 1° luglio 2020, la versione precedente di CQD accede ai dati dall'ultima versione di CQD.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Eseguire la migrazione di dati e report di compilazione dalla versione precedente di CQD

> [!IMPORTANT]
> A partire dal 1° luglio 2020, non è più possibile eseguire la migrazione di dati e report di generazione dal vecchio CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Usare Power BI per analizzare i dati CQD

Novità di gennaio 2020: [Scaricare i modelli di query di Power BI per CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati CQD.

Leggere [Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md) per altre informazioni.


## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Caricare i dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md)

[Dati e report CQD](CQD-data-and-reports.md)

[Usare CQD per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione dei flussi in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md)