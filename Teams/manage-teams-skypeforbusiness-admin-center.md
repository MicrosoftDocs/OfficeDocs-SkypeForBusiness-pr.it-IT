---
title: Gestire Teams transizione alla nuova interfaccia di amministrazione di Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come gestire le impostazioni a livello di tenant e utente per Teams durante la transizione da Teams nel interfaccia di amministrazione di Microsoft 365 alla nuova interfaccia di amministrazione di Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: 83b65724099aa46bfe1f1719430e70d8da86ce33
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675088"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gestire Teams durante la transizione alla nuova Interfaccia di amministrazione di Microsoft Teams.

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Novità dell'interfaccia di amministrazione di Microsoft Teams  

La nuova esperienza dell'interfaccia di amministrazione fornirà un'esperienza unificata per gestire sia Teams che Skype for Business. Stiamo offrendo funzionalità aggiuntive, approfondimenti end-to-end e la possibilità di gestire le impostazioni di Teams a livello di utente.

![Screenshot dell'interfaccia di amministrazione di Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Impostazioni eseguita la migrazione alla nuova interfaccia di amministrazione di Microsoft Teams

La tabella seguente identifica le sezioni dell'esperienza di Teams di cui è stata eseguita la migrazione e mostra la relazione tra le impostazioni correnti e i criteri nel nuovo portale di amministrazione.

|Sezione di Teams in interfaccia di amministrazione di Microsoft 365  |Nome impostazione (livello tenant)  |Criteri dell'interfaccia di amministrazione di Microsoft Teams   |Livello: tenant o utente   |
|---------|---------|---------|---------|
|Generale     |Mostrare l'organigramma nel profilo personale        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  Inquilino       |
|Generale     |Usare Skype for Business per i destinatari che non hanno Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Integrazione di e-mail     |Consentire agli utenti di inviare messaggi di posta elettronica ai canali         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Integrazione di e-mail     |Elenco Mittenti consentiti         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |Inquilino         |
|Archiviazione cloud personalizzata     |Casella         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Archiviazione cloud personalizzata     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Archiviazione cloud personalizzata     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Archiviazione cloud personalizzata     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Archiviazione cloud personalizzata     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Impostazioni per tipo di utente/licenza     |Attivare o disattivare Microsoft Teams per tutti gli utenti          |Deprecato<sup>1</sup>        |         |
|Team e canali     |         |Reindirizza a Gestione Azure Active Directory gruppo (come nell'esperienza corrente).              |Utente         |
|Team e canali     |         |Reindirizza a Gestione di gruppi AAD (come l'esperienza corrente).             |Utente          |
|App|Abilitare le nuove app esterne per impostazione predefinita|Impostazioni delle app a livello di organizzazione|Inquilino|
|App|Consenti app esterne|Impostazioni delle app a livello di organizzazione|Inquilino|
|App|Consenti il sideload di app esterne<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|Utente|
|App|App predefinite<sup>3</sup>|TeamsAppPermissionPolicy|Utente|
|App|App esterne<sup>3</sup>|TeamsAppPermissionPolicy|Utente|
|Chiamate e riunioni     |Consentire la pianificazione per le riunioni private         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utente          |
|Chiamate e riunioni     |Consenti riunione canale ad-hoc         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utente          |
|Chiamate e riunioni     |Consentire la pianificazione per le riunioni del canale         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utente          |
|Chiamate e riunioni     |Consentire video nelle riunioni         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utente          |
|Chiamate e riunioni     |Consentire la condivisione dello schermo nelle riunioni         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utente          |
|Chiamate e riunioni     |Consenti chiamate private         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |Utente          |
|Messaggistica     |Abilitare Giphy in modo che gli utenti possano aggiungere GIF alle conversazioni         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Classificazione del contenuto         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Abilitare meme che gli utenti possono modificare e aggiungere alle conversazioni         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Abilitare gli adesivi che gli utenti possono modificare e aggiungere alle conversazioni         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Consentire ai proprietari di eliminare tutti i messaggi         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Consentire agli utenti di modificare i propri messaggi         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Consentire agli utenti di eliminare i propri messaggi         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Consente agli utenti di chattare in privato         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |

<sup>1</sup> Deprecato per i guest. L'abilitazione o la disabilitazione dei guest ora può essere gestita nell'interfaccia di amministrazione di Microsoft Teams. L'abilitazione/disabilitazione di Teams for Business Enterprise, Edu Student ed Edu Faculty sarà presto deprecata. Questa operazione deve essere gestita assegnando licenze nel interfaccia di amministrazione di Microsoft 365. Vedere [Gestire l'accesso degli utenti a Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> Il sideload è suddiviso nel modo seguente:

- Consentire a un utente di trasferire localmente le app che possono essere gestite a livello di utente in [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy).
- Consentire agli utenti di un tenant di interagire con app personalizzate che possono essere gestite a livello di tenant nelle impostazioni delle app a livello di organizzazione.

<sup>3</sup> Le app predefinite e le app esterne possono essere abilitate e disabilitate a livello di utente in TeamsAppPermissionPolicy. Inoltre, le app possono essere bloccate a livello di tenant nelle impostazioni delle app a livello di organizzazione che sostituiscono qualsiasi impostazione a livello di utente e tenant.

> [!NOTE]
> Si continuerà a usare il dashboard Gruppi nel interfaccia di amministrazione di Microsoft 365 per la configurazione correlata a Teams e canali. Impostazioni per le app rimarranno nell'area Teams del interfaccia di amministrazione di Microsoft 365 e la migrazione verrà eseguita in un secondo momento.

## <a name="manage-settings-during-the-migration"></a>Gestire le impostazioni durante la migrazione

È possibile continuare a modificare le impostazioni nel interfaccia di amministrazione di Microsoft 365 e nell'interfaccia di amministrazione di Skype for Business fino al completamento della migrazione di una sezione per il tenant.

La tabella seguente mostra dove è possibile gestire le caratteristiche durante la migrazione.

|Funzionalità  |interfaccia di amministrazione di Microsoft Teams                      |Skype for Business interfaccia di amministrazione (legacy)  |interfaccia di amministrazione di Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|criteri messaggistica Teams, riunioni ed eventi live     |     X    |         |         |
|criteri di aggiornamento di Teams     |    X     |         |         |
|Impostazioni guest per messaggistica, riunioni e voce     |   X      |         |         |
|Gestione del ciclo di vita Teams   |    X    |      |       |
|Teams Impostazioni   |    X    |      |       |
|Impostazioni di accesso esterno     |    X    |      |       |
|Gestione utenti    |         |         |    X     |
|Audioconferenza     |    X     |    X     |         |
|Piani per chiamate     |    X    |    X     |         |
|Sistema telefonico    |    X    |     X    |         |
|gestione dei numeri di Telefono     |    X    |   X      |         |
|Licenze per le funzionalità vocali del cloud     |         |         |    X     |
|Operatori automatici     |    X    |          |         |
|Code di chiamata     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gestire le impostazioni dopo la migrazione

Al termine della migrazione di queste impostazioni, verranno disabilitate nel interfaccia di amministrazione di Microsoft 365 e nell'interfaccia di amministrazione di Skype for Business e potranno quindi essere gestite nella nuova interfaccia di amministrazione di Microsoft Teams.
