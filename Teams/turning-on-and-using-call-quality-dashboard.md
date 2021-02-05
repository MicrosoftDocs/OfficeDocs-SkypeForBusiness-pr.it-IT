---
title: Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)
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
description: Informazioni su come attivare e usare il dashboard qualità chiamata e ottenere report riepilogativi sulla qualità delle chiamate.
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112844"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)

Aprire Microsoft Call Quality Dashboard (Call Quality Dashboard) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (accedere con le credenziali di amministratore). Oppure passa all'interfaccia di amministrazione di teams e seleziona **chiama Quality dashboard**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot del pulsante dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

Nella pagina visualizzata fare clic su Accedi e immettere l'account **di** amministratore globale o le informazioni dell'account di amministratore del servizio Microsoft teams. Dopo aver effettuato l'accesso per la prima volta, Call Quality dashboard inizierà a raccogliere ed elaborare i dati. Tieni presente che potrebbero essere necessarie una o più ore per elaborare dati sufficienti per visualizzare i risultati significativi nei report.

Call Quality dashboard mostra la qualità delle chiamate e delle riunioni a livello di organizzazione per Microsoft teams, Skype for business online e Skype for Business Server 2019. 

> [!IMPORTANT]
> Per usare Call Quality Dashboard con Skype for Business Server 2019, è necessario configurare il [connettore dati chiamata](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector). Vedere [pianificare il connettore dati chiamata](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) prima di iniziare.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Assegnare ruoli di amministratore per Access a Call Quality dashboard

Assegnare [ruoli](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) per accedere a Call Quality dashboard alle persone che devono usarle.

Se si vuole che gli utenti non amministratori (ad esempio gli ingegneri del supporto tecnico e gli agenti dell'helpdesk) usino il dashboard qualità chiamata, è possibile assegnare agli utenti uno dei ruoli seguenti, che consente di accedere a Call Quality dashboard. 


|  |Visualizzare i report  |Visualizzare i campi EUII  |Creare report  |Caricare i dati dell'edificio  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Amministratore globale     |Sì         |Sì         |Sì         |Sì         |
|Amministratore del servizio Teams     |Sì         |Sì         |Sì         |Sì         |
|Amministratore comunicazioni Teams     |Sì         |Sì         |Sì         |Sì         |
|Tecnico supporto comunicazioni Teams     |Sì         |Sì         |Sì         |No         |
|Specialista supporto comunicazioni Teams     |Sì         |No         |Sì         |No         |
|Amministratore di Skype for business     |Sì         |Sì         |Sì         |Sì         |
|Lettore globale |Sì         |Sì         |Sì         |No         |
|Lettore report<sup>1</sup>     |Sì         |No         |Sì         |No         |

<sup>1</sup> oltre a leggere i report di Call Quality dashboard, l'utilità di lettura report può visualizzare tutti i report [attività](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) nell'interfaccia di amministrazione e tutti i report del [pacchetto di contenuto Microsoft adoption 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Se non si vedono [EUII (informazioni identificative per gli utenti finali)](CQD-data-and-reports.md#euii-data) e si ha uno dei ruoli consentiti per vedere queste informazioni, tenere presente che Call Quality dashboard mantiene solo EUII per 28 giorni. Viene eliminato qualsiasi valore antecedente a 28 giorni.

Per altre informazioni su questi ruoli, vedere [informazioni sui ruoli di amministratore di Office 365](/office365/admin/add-users/about-admin-roles).


Dopo aver effettuato l'accesso per la prima volta, Call Quality dashboard inizierà a raccogliere ed elaborare i dati. A partire da dicembre 2019, è comunque possibile accedere alla versione precedente di Call Quality Dashboard (cqd.lync.com), anche se il portale legacy fornisce un collegamento all'ultima Call Quality Dashboard (cqd.teams.microsoft.com). Alla fine, la versione precedente di Call Quality dashboard verrà disattivata. A partire dal 1 ° luglio 2020, la versione precedente di Call Quality dashboard accede ai dati dall'ultima Call Quality dashboard.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Eseguire la migrazione di dati e report da una versione precedente di Call Quality dashboard

> [!IMPORTANT]
> A partire dal 1 ° luglio 2020, non è più possibile eseguire la migrazione dei dati dell'edificio e i report dal vecchio Call Quality Dashboard ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Usare Power BI per analizzare i dati di Call Quality dashboard

Novità di gennaio 2020: [scaricare i modelli di query di Power BI per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality dashboard.

Leggere [usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md) per altre informazioni.


## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md)

[Che cos'è Call Quality dashboard?](CQD-what-is-call-quality-dashboard.md)

[Caricare i dati del tenant e della creazione](CQD-upload-tenant-building-data.md)

[Dati e report di Call Quality dashboard](CQD-data-and-reports.md)

[Usare Call Quality dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in Call Quality dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md)
