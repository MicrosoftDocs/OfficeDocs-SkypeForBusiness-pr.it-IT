---
title: Gestire la transizione di Teams alla nuova interfaccia di amministrazione di Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Informazioni su come gestire le impostazioni a livello di tenant e utente per Teams durante la transizione da Teams nell'interfaccia di amministrazione di Microsoft 365 alla nuova interfaccia di amministrazione di Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: ee63c3d49a8c4b4bf047f0df3910bec39a4d5541
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790418"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gestire Teams durante la transizione alla nuova Interfaccia di amministrazione di Microsoft Teams.
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Che cos'è la nuova interfaccia di amministrazione di Microsoft Teams?  

La nuova interfaccia di amministrazione offre un'esperienza unificata per gestire sia Teams che Skype for Business. Stiamo offrendo funzionalità aggiuntive, approfondimenti end-to-end e la possibilità di gestire le impostazioni di Teams a livello utente.

![Screenshot dell'interfaccia di amministrazione di Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Le impostazioni sono migrate alla nuova interfaccia di amministrazione di Microsoft Teams

La tabella seguente identifica le sezioni dell'esperienza di Teams di cui è stata eseguita la migrazione e mostra la relazione tra le impostazioni correnti e i criteri nel nuovo portale di amministrazione.

|Sezione di Teams nell'interfaccia di amministrazione di Microsoft 365  |Nome impostazione (livello tenant)  |Criteri dell'interfaccia di amministrazione di Microsoft Teams   |Livello: Tenant o Utente   |
|---------|---------|---------|---------|
|Generale     |Mostra organigramma nel profilo personale        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Tenant       |
|Generale     |Usare Skype for Business per i destinatari che non hanno Teams         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Integrazione di e-mail     |Consenti agli utenti di inviare e-mail ai canali         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Integrazione di e-mail     |Elenco Mittenti consentiti         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Tenant         |
|Archiviazione cloud personalizzata     |Box         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |Egnyte        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Impostazioni per utente/tipo di licenza     |Attivare o disattivare Microsoft Teams per tutti gli utenti          |Deprecato<sup>1</sup>        |         |
|Team e canali     |         |Reindirizza a Gestione gruppi di Azure Active Directory (uguale all'esperienza corrente).              |Utente         |
|Team e canali     |         |Reindirizza alla gestione dei gruppi AAD (uguale all'esperienza corrente).             |Utente          |
|App|Abilitare le nuove app esterne per impostazione predefinita|Impostazioni dell'app a livello di organizzazione|Tenant|
|App|Consenti app esterne|Impostazioni dell'app a livello di organizzazione|Tenant|
|App|Consenti sideload di app esterne<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Utente|
|App|App predefinite<sup>3</sup>|TeamsAppPermissionPolicy|Utente|
|App|App esterne<sup>3</sup>|TeamsAppPermissionPolicy|Utente|
|Chiamate e riunioni     |Consentire la pianificazione di riunioni private         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utente          |
|Chiamate e riunioni     |Consentire l'incontro di canale ad hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utente          |
|Chiamate e riunioni     |Consentire la pianificazione delle riunioni del canale         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utente          |
|Chiamate e riunioni     |Consentire i video nelle riunioni         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utente          |
|Chiamate e riunioni     |Consentire la condivisione dello schermo nelle riunioni         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utente          |
|Chiamate e riunioni     |Consenti chiamate private         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Utente          |
|Messaggistica     |Abilitare Giphy in modo che gli utenti possano aggiungere GIF alle conversazioni         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Valutazione del contenuto         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Abilitare i meme che gli utenti possono modificare e aggiungere alle conversazioni         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Abilitare gli sticker che gli utenti possono modificare e aggiungere alle conversazioni         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Consenti ai proprietari di eliminare tutti i messaggi         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Consentire agli utenti di modificare i propri messaggi         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Consentire agli utenti di eliminare i propri messaggi         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Consente agli utenti di chattare in privato         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |

<sup>1</sup> Deprecato per gli utenti Guest. L'abilitazione o disabilitazione dei guest ora può essere gestita nell'interfaccia di amministrazione di Microsoft Teams. Abilitazione/disabilitazione di Teams for Business Enterprise, Edu Student ed Edu Faculty saranno presto deprecati. Questo deve essere gestito assegnando licenze nell'interfaccia di amministrazione di Microsoft 365. Vedere [Gestire l'accesso degli utenti a Microsoft Teams.](user-access.md)
<br><br>
<sup>2</sup> Il sideload viene suddiviso nel modo seguente:

- Consenti a un utente di sideload di app che possono essere gestite a livello utente in [TeamsAppSetupPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)
- Consentire agli utenti di un tenant di interagire con app personalizzate che possono essere gestite a livello di tenant nelle impostazioni delle app a livello di organizzazione.

<sup>3</sup> Le app predefinite e le app esterne possono essere abilitate e disabilitate a livello utente in TeamsAppPermissionPolicy. Inoltre, le app possono essere bloccate a livello di tenant nelle impostazioni delle app a livello di organizzazione, che sostituiscono qualsiasi impostazione a livello di utente e tenant.

> [!NOTE]
> Continuerai a usare il dashboard Gruppi nell'interfaccia di amministrazione di Microsoft 365 per la configurazione relativa a Teams e canali. Le impostazioni per le app rimarranno nell'area Teams dell'interfaccia di amministrazione di Microsoft 365 e verranno migrate in un secondo momento.

## <a name="manage-settings-during-the-migration"></a>Gestire le impostazioni durante la migrazione

Puoi continuare a modificare le impostazioni nell'interfaccia di amministrazione di Microsoft 365 e nell'interfaccia di amministrazione di Skype for Business fino al completamento della migrazione di una sezione per il tuo tenant.

La tabella seguente mostra dove è possibile gestire le caratteristiche durante la migrazione.

|Funzionalità  |Interfaccia di amministrazione di Microsoft Teams                      |Interfaccia di amministrazione di Skype for Business (legacy)  |Interfaccia di amministrazione di Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Criteri messaggistica, riunioni ed eventi live di Teams     |     X    |         |         |
|Criteri di aggiornamento di Teams     |    X     |         |         |
|Impostazioni guest per messaggistica, riunioni e voce     |   X      |         |         |
|Gestione del ciclo di vita dei team   |    X    |      |       |
|Impostazioni di Teams   |    X    |      |       |
|Impostazioni di accesso esterno     |    X    |      |       |
|Gestione degli utenti    |         |         |    X     |
|Audioconferenza     |    X     |    X     |         |
|Piani per chiamate     |    X    |    X     |         |
|Sistema telefonico    |    X    |     X    |         |
|Gestione dei numeri di telefono     |    X    |   X      |         |
|Funzionalità vocali per le licenze per cloud     |         |         |    X     |
|Operatori automatici     |    X    |          |         |
|Code di chiamata     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gestire le impostazioni dopo la migrazione

Una volta completata la migrazione, queste impostazioni verranno disabilitate nell'interfaccia di amministrazione di Microsoft 365 e nell'interfaccia di amministrazione di Skype for Business e potranno essere gestite nella nuova interfaccia di amministrazione di Microsoft Teams.
