---
title: Gestire gli accessi alle app di Teams in Microsoft 365
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Informazioni su come gestire l'accesso alle app di Teams in Microsoft 365.
ms.openlocfilehash: 73a90aec04b6e3dcccda6aa4902506ff9eacccc4
ms.sourcegitcommit: 117adad5224dbf84f53b98341cd6a899ffc4eab1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2022
ms.locfileid: "68673442"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gestire gli accessi alle app di Teams in Microsoft 365

Gli sviluppatori di app possono migliorare le app di Microsoft Teams per lavorare in Outlook e in Office.com, oltre all'app che lavora in Teams. Gli utenti finali possono usare le app avanzate in Teams, in Microsoft Outlook e Microsoft Office.com dopo il miglioramento. Attualmente, solo gli utenti finali in Targeted Release possono visualizzare e usare queste app specifiche in Teams, Outlook e Office.com. L'esperienza di amministrazione di Teams esistente si applica per controllare l'accesso a queste app. Una notifica relativa a questa modifica è disponibile nel [Centro messaggi](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Gli amministratori di Teams possono consentire a utenti finali specifici di usare le app avanzate o di gestire l'accesso alle app avanzate in Teams, in Outlook e in Office.com. Gli amministratori di Teams usano l'interfaccia di amministrazione di Teams per gestire l'accesso alle app.

Per l'uso in Outlook e Office.com, un'app avanzata continua a usare le autorizzazioni esistenti concesse in Teams. Non ci sono [modifiche alle autorizzazioni dell'app avanzata](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Le app avanzate sono elencate di seguito:

* [Adobe Acrobat Sign](https://teams.microsoft.com/l/app/0f56a9d1-f502-40f9-a9e8-816d7adbb68b?source=app-details-dialog)
* [ELearning Bigger Brains](https://teams.microsoft.com/l/app/12345514-afee-abcd-acde-c5b34109abcd?source=app-details-dialog)
* [Bookings](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=app-details-dialog)
* [e2e-assure](https://teams.microsoft.com/l/app/8bdf3437-e038-4a93-abdc-00461630f6c3?source=app-details-dialog)
* [ESi-Tik](https://teams.microsoft.com/l/app/fe9627db-f23e-42b1-b454-d4d1ca5af33e?source=app-details-dialog)
* Lente
* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [I miei adesivi](https://teams.microsoft.com/l/app/46fae4d0-faf5-11e9-80f3-53ad33b77bce?source=app-details-dialog)
* [Strumenti PDF](https://teams.microsoft.com/l/app/ca4b5141-5c46-47bc-a05e-2733d9bd69aa?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [Priority Matrix](https://teams.microsoft.com/l/app/5be2b320-a5b7-4221-893c-dee506e4e365?source=app-details-dialog)
* [Smart Connect per Jira](https://teams.microsoft.com/l/app/6402de97-ce33-4386-bf28-b37e9e139c09?source=app-details-dialog)
* [Pianificazione rapida](https://teams.microsoft.com/l/app/bf280b0d-b87d-4158-9f2a-70b63674cd27?source=app-details-dialog)
* [Semplificare](https://teams.microsoft.com/l/app/aa6e7fb6-34ac-4947-9c13-3565c66e368b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* Assistente trascrizione TNA2
* [Umbiko](https://teams.microsoft.com/l/app/23fc1de6-dda0-4043-9ebb-a555e845843d?source=app-details-dialog)
* [Waldo](https://teams.microsoft.com/l/app/1d041f16-ab49-4627-bfda-6b60ad2cab6a?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)

È possibile controllare l'accesso degli utenti finali alle app di Teams usando i metodi seguenti. Se si è un amministratore delle app di Office, contattare l'amministratore globale o l'amministratore di Teams per gestire l'accesso alle app.

| Opzioni per gestire l'accesso |Portale|Amministratore globale|Amministratore di Teams|
|--|---|---|--|
| Solo gli utenti finali in Targeted Release possono accedere alla nuova app. Spostare gli utenti nella versione Standard. Vedere [Configurare le opzioni di rilascio Standard o Mirato](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Interfaccia di amministrazione di Microsoft 365 | Sì | No |
| Gestire l'accesso alla nuova app per utenti finali specifici. Vedere [Aggiungere un criterio di autorizzazione personalizzato](teams-app-permission-policies.md#create-an-app-permission-policy) e [assegnare il criterio personalizzato a un utente](policy-assignment-overview.md). | Interfaccia di amministrazione di Teams | Sì | Sì |
| Gestire l'accesso alle nuove app per tutti gli utenti finali dell'organizzazione. Vedere [Consentire o bloccare le app](manage-apps.md#allow-and-block-apps). | Interfaccia di amministrazione di Teams | Sì | Sì |

> [!NOTE]
> È consigliabile usare [l'opzione di versione Standard](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) per gestire l'accesso degli utenti finali. Le altre opzioni rimuovono l'accesso dell'utente finale e non potranno più usare l'app esistente in Teams.

> [!NOTE]
> Gli utenti che hanno installato un componente aggiuntivo sul mercato esistente della stessa app in Outlook e Office continueranno a usare tale app. I componenti aggiuntivi non sono app di Teams e gli amministratori di Teams non possono controllare l'accesso.

## <a name="related-articles"></a>Articoli correlati

* [Le app di Microsoft Teams progettate per Microsoft 365 disponibili in anteprima in Outlook e Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Informazioni sui ruoli di amministratore in Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Informazioni sui componenti aggiuntivi di Outlook](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [In che modo gli sviluppatori estendono le app di Teams in modo che funzionino in Microsoft 365](/microsoftteams/platform/m365-apps/overview)
