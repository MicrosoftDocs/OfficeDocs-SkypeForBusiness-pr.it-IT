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
ms.openlocfilehash: 3fe95852fe88f64539ffa562d64619c1300b083b
ms.sourcegitcommit: abe942c294ed5fca70efdf039d38d611b9c21fe9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2022
ms.locfileid: "63689153"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gestire l'accesso Teams app in più Microsoft 365

Gli sviluppatori di app possono aggiornare le app Microsoft Teams per lavorare in Outlook e in Office.com, oltre all'app che lavora in Teams. Gli utenti finali possono usare le app aggiornate in Teams, in Microsoft Outlook e Microsoft Office.com dopo l'aggiornamento. Attualmente, solo gli utenti finali in Targeted Release possono visualizzare e usare queste app specifiche in Teams, Outlook e Office.com. L'esperienza Teams di amministrazione si applica per regolamentare l'accesso a queste app. Una notifica su questa modifica è disponibile nel [centro messaggi](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Gli amministratori di Teams possono consentire a specifici utenti finali di usare le app aggiornate o gestire l'accesso alle app aggiornate in Teams, Outlook e Office.com. Teams amministratori usano l'interfaccia Teams di amministrazione per gestire l'accesso alle app.

Per l'uso in Outlook e Office.com, un'app aggiornata continua a usare le autorizzazioni esistenti concesse in Teams. Le autorizzazioni [dell'app aggiornata non vengono modificate](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

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

* [Comprendere i ruoli di amministratore in Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Informazioni Outlook componenti aggiuntivi](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Come gli sviluppatori estendono Teams le app in modo che funzionino in Microsoft 365](/microsoftteams/platform/m365-apps/overview)
