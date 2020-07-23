---
title: Gestire la transizione dei team all'interfaccia di amministrazione di nuovi team
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Informazioni su come gestire le impostazioni utente e a livello di tenant per i team durante la transizione da teams nell'interfaccia di amministrazione di Microsoft 365 al nuovo centro di amministrazione di teams.
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
ms.openlocfilehash: 0dc4e9a4c223422ab743e657d808f5de0f3239e7
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45228892"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gestire Teams durante la transizione alla nuova Interfaccia di amministrazione di Microsoft Teams.
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Qual è il nuovo centro di amministrazione di Microsoft Teams  

La nuova esperienza di interfaccia di amministrazione ti offre un'esperienza unificata per gestire sia team che Skype for business. Stiamo offrendo funzionalità aggiuntive, approfondimenti finali e la possibilità di gestire le impostazioni dei team a livello di utente.

![Screenshot dell'interfaccia di amministrazione di Microsoft teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Impostazioni di migrazione alla nuova interfaccia di amministrazione di Microsoft Teams

La tabella seguente identifica le sezioni dell'esperienza teams che sono state migrate e Mostra la relazione tra le impostazioni correnti e i criteri nel nuovo portale di amministrazione.

|Sezione di teams nell'interfaccia di amministrazione di Microsoft 365  |Impostazione del nome (livello tenant)  |Criteri dell'interfaccia di amministrazione di Microsoft Teams   |Livello: tenant o utente   |
|---------|---------|---------|---------|
|Generale     |Mostra organigramma nel profilo personale        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Tenant       |
|Generale     |Usare Skype for business per i destinatari che non hanno team         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Integrazione di e-mail     |Consentire agli utenti di inviare messaggi di posta elettronica ai canali         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Integrazione di e-mail     |Consenti elenco mittenti         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Tenant         |
|Archiviazione cloud personalizzata     |Casella         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |Egnyte (disponibile a breve)        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Impostazioni per tipo di utente/licenza     |Attivare o disattivare Microsoft teams per tutti gli utenti          |Deprecato<sup>1</sup>        |         |
|Team e canali     |         |Reindirizza alla gestione dei gruppi di Azure Active Directory (lo stesso dell'esperienza corrente).              |Utente         |
|Team e canali     |         |Reindirizza alla gestione del gruppo AAD (lo stesso dell'esperienza corrente).             |Utente          |
|App|Abilitare le nuove app esterne per impostazione predefinita|Impostazioni dell'app a livello di organizzazione|Tenant|
|App|Consentire le app esterne|Impostazioni dell'app a livello di organizzazione|Tenant|
|App|Consenti sideload di app esterne<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Utente|
|App|App predefinite<sup>3</sup>|TeamsAppPermissionPolicy|Utente|
|App|App esterne<sup>3</sup>|TeamsAppPermissionPolicy|Utente|
|Chiamate e riunioni     |Consentire la pianificazione per riunioni private         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utente          |
|Chiamate e riunioni     |Consenti Meetup canale ad-hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utente          |
|Chiamate e riunioni     |Consentire la pianificazione per le riunioni di canale         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utente          |
|Chiamate e riunioni     |Consentire i video nelle riunioni         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utente          |
|Chiamate e riunioni     |Consentire la condivisione dello schermo nelle riunioni         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Utente          |
|Chiamate e riunioni     |Consenti chiamate private         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Utente          |
|Messaggistica     |Abilitare Giphy in modo che gli utenti possano aggiungere gif alle conversazioni         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Classificazione contenuto         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Abilitare i meme che gli utenti possono modificare e aggiungere alle conversazioni         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Abilitare gli adesivi che gli utenti possono modificare e aggiungere alle conversazioni         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Consentire ai proprietari di eliminare tutti i messaggi         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Consentire agli utenti di modificare i propri messaggi         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Consentire agli utenti di eliminare i propri messaggi         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |
|Messaggistica     |Consente agli utenti di chattare in privato         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Utente         |

<sup>1</sup> deprecato per Guest. L'abilitazione/disabilitazione degli ospiti può ora essere gestita nell'interfaccia di amministrazione di Microsoft teams. L'abilitazione/disabilitazione di teams for Business Enterprise, edu Student e edu facoltà sarà deprecata a breve. Questo deve essere gestito assegnando licenze nell'interfaccia di amministrazione di Microsoft 365. Vedere [gestire l'accesso degli utenti a Microsoft teams](user-access.md).
<br><br>
<sup>2</sup> sideload è suddiviso nel modo seguente:

- Consentire a un utente di trasferire localmente le app che possono essere gestite a livello di utente in [TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
- Consenti agli utenti di un tenant di interagire con le app personalizzate che possono essere gestite a livello di tenant nelle impostazioni dell'app per l'intera organizzazione.

<sup>3</sup> le app predefinite e le app esterne possono essere abilitate e disabilitate a livello di utente in TeamsAppPermissionPolicy. Inoltre, le app possono essere bloccate a livello di tenant nelle impostazioni dell'app a livello di organizzazione che sostituisce tutte le impostazioni di utenti e livelli di tenant.

> [!NOTE]
> Si continuerà a usare il dashboard dei gruppi nell'interfaccia di amministrazione di Microsoft 365 per la configurazione relativa a team e canali. Le impostazioni per le app rimarranno nell'area Teams dell'interfaccia di amministrazione di Microsoft 365 e verranno migrate in un secondo momento.

## <a name="manage-settings-during-the-migration"></a>Gestire le impostazioni durante la migrazione

È possibile continuare a modificare le impostazioni nell'interfaccia di amministrazione di Microsoft 365 e nell'interfaccia di amministrazione di Skype for business finché la migrazione per una sezione non è completa per il tenant.

La tabella seguente mostra la posizione in cui è possibile gestire le caratteristiche durante la migrazione.

|Funzionalità  |Interfaccia di amministrazione di Microsoft Teams                      |Interfaccia di amministrazione di Skype for business (legacy)  |Interfaccia di amministrazione di Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Criteri di messaggistica, riunioni e eventi live di Teams     |     X    |         |         |
|Criteri di aggiornamento dei team     |    X     |         |         |
|Impostazioni Guest per la messaggistica, le riunioni e la voce     |   X      |         |         |
|Gestione del ciclo di vita di Teams   |    X    |      |       |
|Impostazioni Teams   |    X    |      |       |
|Impostazioni di accesso esterno     |    X    |      |       |
|Gestione utenti    |         |         |    X     |
|Audioconferenza     |    X     |    X     |         |
|Piani di chiamata     |    X    |    X     |         |
|Sistema telefonico    |    X    |     X    |         |
|Gestione di numeri di telefono     |    X    |   X      |         |
|Licenze per le caratteristiche di cloud Voice     |         |         |    X     |
|Operatori automatici     |    X    |          |         |
|Code di chiamata     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gestire le impostazioni dopo la migrazione

Dopo aver completato la migrazione di queste impostazioni, li disattiveremo nell'interfaccia di amministrazione di Microsoft 365 e nell'interfaccia di amministrazione di Skype for business, che potranno quindi essere gestiti nel nuovo centro di amministrazione di Microsoft teams.
