---
title: Configurazione di Call Quality Dashboard (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Informazioni su come attivare e usare call quality dashboard e ottenere report di riepilogo sulla qualità delle chiamate.
ms.openlocfilehash: 5f3b9fbb42199892136569ac179907b18da4e460
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245797"
---
# <a name="set-up-the-call-quality-dashboard"></a>Configurare call quality dashboard

Aprire Microsoft Call Quality Dashboard (CQD) all'indirizzo [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (accedere con le credenziali di amministratore). Oppure passare all'interfaccia di amministrazione di Teams e selezionare **Analytics & report** > **Call Quality Dashboard**.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot del pulsante Call quality dashboard nell'interfaccia di amministrazione di Teams.":::

Nella pagina visualizzata fare clic su **Accedi** e immettere l'account amministratore globale o Microsoft informazioni sull'account amministratore di Teams. Dopo il primo accesso, Call Quality Dashboard inizierà a raccogliere ed elaborare i dati. Tenere presente che l'elaborazione di dati sufficienti per visualizzare risultati significativi nei report può richiedere una o più ore.

Call Quality Dashboard mostra la qualità delle chiamate e delle riunioni, a livello di organizzazione, per Microsoft Teams, Skype for Business Online e Skype for Business Server 2019. 

> [!IMPORTANT]
> Per usare Call Quality Dashboard con Skype for Business Server 2019, è necessario [configurare Call Data Connector](/skypeforbusiness/hybrid/configure-call-data-connector). Vedere [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) prima di iniziare.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Assegnare ruoli di amministratore per l'accesso a Call Quality Dashboard

Assegnare [ruoli](/microsoft-365/admin/add-users/about-admin-roles) per l'accesso a Call Quality Dashboard alle persone che ne hanno bisogno.

Se si vuole che gli utenti non amministratori, ad esempio tecnici del supporto e agenti helpdesk, utilizzino Call Quality Dashboard, è possibile assegnare a tali utenti uno dei ruoli seguenti, che consente l'accesso a Call Quality Dashboard. 


|&nbsp;  |Visualizzare i report  |Visualizzare i campi EUII  |Creare report  |Caricare dati di tipo building  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Amministratore globale     |Sì         |Sì         |Sì         |Sì         |
|Amministratore di Teams     |Sì         |Sì         |Sì         |Sì         |
|Amministratore comunicazioni Teams     |Sì         |Sì         |Sì         |Sì         |
|Tecnico supporto comunicazioni Teams     |Sì         |Sì         |Sì         |No         |
|Specialista del supporto tecnico per le comunicazioni di Teams     |Sì         |No         |Sì         |No         |
|amministratore Skype for Business     |Sì         |Sì         |Sì         |Sì         |
|Lettore globale |Sì         |Sì         |Sì         |No         |
|Lettore di report<sup>1</sup>     |Sì         |No         |Sì         |No         |

<sup>1</sup> Oltre a leggere i report di Call Quality Dashboard, Il lettore di report può visualizzare tutti i [report attività](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) nell'interfaccia di amministrazione e tutti i report del [pacchetto di contenuto Microsoft 365 Adoption](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Se non vedi [EUII (informazioni identificabili per l'utente finale)](CQD-data-and-reports.md#euii-data) e hai uno dei ruoli a cui è consentito visualizzare queste informazioni, ricorda che Call Quality Dashboard conserva l'interfaccia utente ue solo per 28 giorni. Tutto ciò che supera i 28 giorni viene eliminato.

Per altre informazioni su questi ruoli, vedere [Informazioni sui ruoli di amministratore Office 365](/office365/admin/add-users/about-admin-roles).


Dopo il primo accesso, Call Quality Dashboard inizierà a raccogliere ed elaborare i dati.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usare Power BI per analizzare i dati di Call Quality Dashboard

Novità di gennaio 2020: [Scaricare i modelli di query di Power BI per Call Quality Dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality Dashboard.

Per altre informazioni, vedere [Usare Power BI per analizzare i dati di Call Quality Dashboard](CQD-Power-BI-query-templates.md) .

## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Caricare i dati di tenant e building](CQD-upload-tenant-building-data.md)

[Call Quality Dashboard - Dati e report](CQD-data-and-reports.md)

[Usare Call Quality Dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality Dashboard](CQD-Power-BI-query-templates.md)
