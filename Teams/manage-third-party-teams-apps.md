---
title: Gestire l'accesso Teams app in più Microsoft 365
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Gestire l'accesso Teams app in Microsoft 365.
ms.openlocfilehash: a9a0eb67323874e725510342e1e6810dcc5c0b0d
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593001"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gestire l'accesso Teams app in più Microsoft 365

Gli sviluppatori di app possono migliorare le Microsoft Teams per lavorare in Outlook e su Office.com, oltre all'app che lavora in Teams. Gli utenti finali possono usare le app migliorate in Teams, in Microsoft Outlook e Microsoft Office.com dopo il miglioramento. Attualmente, solo gli utenti finali in Targeted Release possono visualizzare e usare queste app specifiche in Teams, Outlook e Office.com. L'esperienza Teams di amministrazione si applica per regolamentare l'accesso a queste app. Una notifica su questa modifica è disponibile nel [centro messaggi](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Gli amministratori di Teams possono consentire a specifici utenti finali di usare le app migliorate o di gestire l'accesso alle app avanzate in Teams, in Outlook e in Office.com. Teams amministratori usano l'interfaccia Teams di amministrazione per gestire l'accesso alle app.

Per l'uso in Outlook e Office.com, un'app avanzata continua a usare le autorizzazioni esistenti concesse in Teams. Le autorizzazioni [dell'app](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs) avanzata non vengono modificate.

Di seguito è riportato un elenco delle app migliorate:

* [Affresco](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d?source=app-details-dialog)

È possibile controllare l'accesso degli utenti finali alle app Teams usando i metodi seguenti. Se si è un amministratore di Office app, contattare l'amministratore globale o l'amministratore Teams per gestire l'accesso alle app.

| Opzioni per gestire l'accesso |Portale|Amministratore globale|Teams amministratore|
|--|---|---|--|
| Solo gli utenti finali in Targeted Release possono accedere alla nuova app. Spostare gli utenti nella versione Standard. Vedere [Configurare le opzioni Standard o Targeted Release](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | interfaccia di amministrazione di Microsoft 365 | Sì | No |
| Gestire l'accesso alla nuova app per utenti finali specifici. Vedere [Aggiungere criteri di autorizzazione personalizzati](teams-app-permission-policies.md#create-a-custom-app-permission-policy) e [assegnare i criteri personalizzati a un utente](policy-assignment-overview.md). | Teams di amministrazione | Sì | Sì |
| Gestire l'accesso alle nuove app per tutti gli utenti finali dell'organizzazione. Vedere [Consentire o bloccare le app](manage-apps.md#allow-and-block-apps). | Teams di amministrazione | Sì | Sì |

> [!NOTE]
> È consigliabile usare [l'opzione Versione standard per](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) gestire l'accesso degli utenti finali. Le altre opzioni rimuovono l'accesso dell'utente finale e non potranno più usare l'app esistente in Teams.

> [!NOTE]
> Gli utenti che hanno installato un componente aggiuntivo sul mercato esistente della stessa app in Outlook e Office continueranno a usare l'app. I componenti aggiuntivi non sono Teams app e Teams gli amministratori non possono governare l'accesso.

## <a name="see-also"></a>Vedere anche

* [Microsoft Teams app progettate per Microsoft 365 in anteprima per Outlook e Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Comprendere i ruoli di amministratore in Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Informazioni Outlook componenti aggiuntivi](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Come gli sviluppatori estendono Teams le app in modo che funzionino in Microsoft 365](/microsoftteams/platform/m365-apps/overview)
