---
title: Gestire l'accesso alle app Teams in Microsoft 365
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
description: Gestisci l'accesso alle app Teams in Microsoft 365.
ms.openlocfilehash: 336c550c4fdf506898d6471cb618652fada95a4f
ms.sourcegitcommit: c2a77ef9c1c9e6f00b3a4589bf02b100c37f5801
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2022
ms.locfileid: "64648985"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gestire l'accesso alle app Teams in Microsoft 365

Gli sviluppatori di app possono migliorare le app Microsoft Teams in modo che funzionino in Outlook e su Office.com, oltre all'app che funziona in Teams. Gli utenti finali possono usare le app avanzate in Teams, in Microsoft Outlook e Microsoft Office.com dopo il miglioramento. Attualmente, solo gli utenti finali in Targeted Release possono visualizzare e usare queste app specifiche in Teams, Outlook e Office.com. L'esperienza di amministratore Teams esistente si applica per disciplinare l'accesso a queste app. Nel [Centro messaggi](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280) è disponibile una notifica su questa modifica. Gli amministratori Teams possono consentire a utenti finali specifici di usare le app avanzate o di gestire l'accesso alle app avanzate in Teams, Outlook e su Office.com. Teams amministratori usano l'interfaccia di amministrazione di Teams per gestire l'accesso alle app.

Per l'uso in Outlook e Office.com, un'app avanzata continua a usare le autorizzazioni esistenti concesse in Teams. Non ci sono [modifiche alle autorizzazioni dell'app avanzata](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Di seguito è riportato un elenco delle app avanzate:

* [Murale](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)
* [Progetti Zoho](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube?source=app-details-dialog)

È possibile controllare l'accesso dell'utente finale alle app Teams usando i metodi seguenti. Se sei un amministratore delle app di Office, contatta l'amministratore globale o Teams per gestire l'accesso alle app.

| Opzioni per gestire l'accesso |Portale|Amministratore globale|Teams amministratore|
|--|---|---|--|
| Solo gli utenti finali in Targeted Release possono accedere alla nuova app. Spostare gli utenti a Standard Release. Vedere [Configurare le opzioni Standard o Targeted Release](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | interfaccia di amministrazione di Microsoft 365 | Sì | No |
| Gestire l'accesso alla nuova app per utenti finali specifici. Vedere [Aggiungere criteri di autorizzazione personalizzati](teams-app-permission-policies.md#create-a-custom-app-permission-policy) e [assegnare criteri personalizzati a un utente](policy-assignment-overview.md). | interfaccia di amministrazione di Teams | Sì | Sì |
| Gestire l'accesso alle nuove app per tutti gli utenti finali dell'organizzazione. Vedi [Consentire o bloccare app](manage-apps.md#allow-and-block-apps). | interfaccia di amministrazione di Teams | Sì | Sì |

> [!NOTE]
> È consigliabile usare [l'opzione Standard Release](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) per gestire l'accesso degli utenti finali. Le altre opzioni rimuovono l'accesso dell'utente finale e non potranno più usare l'app esistente in Teams.

> [!NOTE]
> Gli utenti che hanno installato un componente aggiuntivo sul mercato esistente della stessa app in Outlook e Office continueranno a usare tale app. I componenti aggiuntivi non sono Teams app e Teams gli amministratori non possono regolamentarne l'accesso.

## <a name="see-also"></a>Vedere anche

* [Microsoft Teams app progettate per Microsoft 365 disponibili in anteprima in Outlook e Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Informazioni sui ruoli di amministratore in Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Informazioni sui componenti aggiuntivi Outlook](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [In che modo gli sviluppatori estendono Teams app per lavorare su Microsoft 365](/microsoftteams/platform/m365-apps/overview)