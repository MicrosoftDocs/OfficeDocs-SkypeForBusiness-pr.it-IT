---
title: Gestire Teams la transizione alla nuova interfaccia Teams di amministrazione
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come gestire le impostazioni utente e a livello di tenant per Teams durante la transizione da Teams nel interfaccia di amministrazione di Microsoft 365 alla nuova interfaccia Teams di amministrazione.
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
ms.openlocfilehash: 727aa58f3e7a91336355730ce5f0a552ea09fdc9
ms.sourcegitcommit: b2566e64e02cb51d18836630d3aa9b6f27b924da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491736"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gestire Teams durante la transizione alla nuova Interfaccia di amministrazione di Microsoft Teams.

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Che cos'è la nuova interfaccia Microsoft Teams di amministrazione  

La nuova esperienza dell'interfaccia di amministrazione offre un'esperienza unificata per gestire sia i Teams che Skype for Business. Microsoft offre funzionalità aggiuntive, approfondimenti end-to-end e la possibilità di gestire Teams impostazioni a livello di utente.

![Screenshot dell'interfaccia Microsoft Teams di amministrazione.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Impostazioni è stata eseguita la migrazione alla nuova interfaccia Microsoft Teams di amministrazione

La tabella seguente identifica le sezioni dell'esperienza Teams di cui è stata eseguita la migrazione e mostra la relazione tra le impostazioni correnti e i criteri nel nuovo portale di amministrazione.

|Sezione di Teams in interfaccia di amministrazione di Microsoft 365  |Nome impostazione (livello tenant)  |Microsoft Teams dell'interfaccia di amministrazione   |Livello: tenant o utente   |
|---------|---------|---------|---------|
|Generale     |Mostra organigramma nel profilo personale        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  Tenant       |
|Generale     |Usare Skype for Business per i destinatari che non hanno Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Tenant         |
|Integrazione di e-mail     |Consentire agli utenti di inviare messaggi di posta elettronica ai canali         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Tenant         |
|Integrazione di e-mail     |Elenco Consenti mittenti         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |Tenant         |
|Spazio di archiviazione cloud personalizzato     |Casella         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Tenant         |
|Spazio di archiviazione cloud personalizzato     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Tenant         |
|Spazio di archiviazione cloud personalizzato     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Tenant         |
|Spazio di archiviazione cloud personalizzato     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Tenant         |
|Spazio di archiviazione cloud personalizzato     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Tenant         |
|Impostazioni in base al tipo di utente/licenza     |Attivare o Microsoft Teams per tutti gli utenti          |Deprecato<sup>1</sup>        |         |
|Team e canali     |         |Reindirizza a Azure Active Directory di gruppo (come nell'esperienza corrente).              |Utente         |
|Team e canali     |         |Reindirizza a Gestione gruppi AAD (come nell'esperienza corrente).             |Utente          |
|App|Abilitare le nuove app esterne per impostazione predefinita|Impostazioni dell'app a livello di organizzazione|Tenant|
|App|Consenti app esterne|Impostazioni dell'app a livello di organizzazione|Tenant|
|App|Consenti sideload delle app esterne<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|Utente|
|App|App predefinite<sup>3</sup>|TeamsAppPermissionPolicy|Utente|
|App|App esterne<sup>3</sup>|TeamsAppPermissionPolicy|Utente|
|Chiamate e riunioni     |Consentire la pianificazione di riunioni private         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utente          |
|Chiamate e riunioni     |Consenti riunione canale ad hoc         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utente          |
|Chiamate e riunioni     |Consentire la pianificazione per le riunioni del canale         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utente          |
|Chiamate e riunioni     |Consentire video nelle riunioni         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utente          |
|Chiamate e riunioni     |Consentire la condivisione dello schermo nelle riunioni         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Utente          |
|Chiamate e riunioni     |Consenti chiamate private         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |Utente          |
|Messaggistica     |Abilitare Giphy in modo che gli utenti possano aggiungere GIF alle conversazioni         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Classificazione del contenuto         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Abilitare i meme che gli utenti possono modificare e aggiungere alle conversazioni         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Abilitare adesivi che gli utenti possono modificare e aggiungere alle conversazioni         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Consenti ai proprietari di eliminare tutti i messaggi         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Consentire agli utenti di modificare i propri messaggi         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Consentire agli utenti di eliminare i propri messaggi         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |
|Messaggistica     |Consente agli utenti di chattare privatamente         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Utente         |

<sup>1 Deprecato</sup> per guest. L'abilitazione/disabilitazione di Guest ora può essere gestita nell'Microsoft Teams di amministrazione. Abilitazione/disabilitazione Teams per le aziende Enterprise, Edu Student e Edu Faculty saranno presto deprecati. Questa operazione deve essere gestita assegnando licenze nel interfaccia di amministrazione di Microsoft 365. Vedere [Gestire l'accesso degli utenti Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> Il sideload viene suddiviso nel modo seguente:

- Consentire a un utente di sideload delle app che possono essere gestite a livello di utente in [TeamsAppSetupPolicy.](/powershell/module/skype/set-csteamsappsetuppolicy)
- Consentire agli utenti di un tenant di interagire con app personalizzate che possono essere gestite a livello di tenant nelle impostazioni dell'app a livello di organizzazione.

<sup>3</sup> Le app predefinite e le app esterne possono essere abilitate e disabilitate a livello di utente in TeamsAppPermissionPolicy. Inoltre, le app possono essere bloccate a livello di tenant nelle impostazioni dell'app a livello di organizzazione, che sostituiscono qualsiasi impostazione a livello di utente e tenant.

> [!NOTE]
> Si continuerà a usare il dashboard Gruppi nel interfaccia di amministrazione di Microsoft 365 per la configurazione relativa a Teams e canali. Impostazioni per le app rimarrà nell'area Teams del interfaccia di amministrazione di Microsoft 365 e verrà eseguita la migrazione in un secondo momento.

## <a name="manage-settings-during-the-migration"></a>Gestire le impostazioni durante la migrazione

È possibile continuare a modificare le impostazioni nell'interfaccia di amministrazione di Microsoft 365 e nell'interfaccia di amministrazione Skype for Business fino al completamento della migrazione per una sezione per il tenant.

La tabella seguente mostra dove è possibile gestire le caratteristiche durante la migrazione.

|Funzionalità  |Microsoft Teams di amministrazione                      |Skype for Business di amministrazione (legacy)  |interfaccia di amministrazione di Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Teams Criteri di messaggistica, riunioni ed eventi live     |     X    |         |         |
|Teams Criteri di aggiornamento     |    X     |         |         |
|Impostazioni guest per Messaggistica, Riunioni e Voce     |   X      |         |         |
|Teams Gestione del ciclo di vita   |    X    |      |       |
|Teams Impostazioni   |    X    |      |       |
|Impostazioni di accesso esterno     |    X    |      |       |
|Gestione utenti    |         |         |    X     |
|Audioconferenza     |    X     |    X     |         |
|Piani per chiamate     |    X    |    X     |         |
|Sistema telefonico    |    X    |     X    |         |
|Telefono gestione dei numeri     |    X    |   X      |         |
|Funzionalità vocali di Licensing per Cloud     |         |         |    X     |
|Operatori automatici     |    X    |          |         |
|Code di chiamata     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gestire le impostazioni dopo la migrazione

Al termine della migrazione di queste impostazioni, le disabiliteremo nell'interfaccia di amministrazione di Microsoft 365 e nell'interfaccia di amministrazione di Skype for Business e potranno essere gestite nella nuova interfaccia di amministrazione di Microsoft Teams.
