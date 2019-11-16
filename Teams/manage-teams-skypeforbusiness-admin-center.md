---
title: Gestire Teams durante la transizione alla nuova Interfaccia di amministrazione di Microsoft Teams.
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Informazioni su come gestire le impostazioni dell'utente e dell'intero tenant per i team durante la transizione dall'esperienza teams nell'interfaccia di amministrazione di Microsoft 365 al nuovo centro di amministrazione di Microsoft teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 0d473ffa67b21c4ec3a160a8687a1688ea1d1cf5
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "37570582"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gestire Teams durante la transizione alla nuova Interfaccia di amministrazione di Microsoft Teams.
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Che cos'è il nuovo centro di amministrazione di Microsoft Teams?  

La nuova esperienza di interfaccia di amministrazione ti offre un'esperienza unificata per gestire sia team che Skype for business. Stiamo offrendo funzionalità aggiuntive, approfondimenti finali e la possibilità di gestire le impostazioni dei team a livello di utente.

![Screenshot dell'interfaccia di amministrazione di Microsoft teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Impostazioni di migrazione alla nuova interfaccia di amministrazione di Microsoft Teams

La tabella seguente identifica le sezioni dell'esperienza teams che sono state migrate e Mostra la relazione tra le impostazioni correnti e i criteri nel nuovo portale di amministrazione.

|Sezione di teams nell'interfaccia di amministrazione di Microsoft 365  |Impostazione del nome (livello tenant)  |Criteri dell'interfaccia di amministrazione di Microsoft Teams   |Livello: tenant o utente   |
|---------|---------|---------|---------|
|Generale     |Mostra organigramma nel profilo personale        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Tenant       |
|Generale     |Usare Skype for business per i destinatari che non hanno team         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Integrazione della posta elettronica     |Consentire agli utenti di inviare messaggi di posta elettronica ai canali         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Integrazione della posta elettronica     |Consenti elenco mittenti         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Tenant         |
|Archiviazione cloud personalizzata     |Casella         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Archiviazione cloud personalizzata     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Impostazioni per tipo di utente/licenza     |Attivare o disattivare Microsoft teams per tutti gli utenti          |Deprecato<sup>1</sup>        |         |
|Team e canali     |         |Reindirizza alla gestione dei gruppi di Azure Active Directory (lo stesso dell'esperienza corrente).              |Utente         |
|Team e canali     |         |Reindirizza alla gestione del gruppo AAD (lo stesso dell'esperienza corrente).             |Utente          |
|Applicazioni|Abilitare le nuove app esterne per impostazione predefinita|Impostazioni dell'app a livello di organizzazione|Tenant|
|Applicazioni|Consentire le app esterne|Impostazioni dell'app a livello di organizzazione|Tenant|
|Applicazioni|Consenti sideload di app esterne<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Utente|
|Applicazioni|App predefinite<sup>3</sup>|TeamsAppPermissionPolicy|Utente|
|Applicazioni|App esterne<sup>3</sup>|TeamsAppPermissionPolicy|Utente|
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

- Consentire a un utente di trasferire localmente le app che possono essere gestite a livello di utente in [TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
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
|Piani di chiamata     |         |    X     |         |
|Sistema telefonico    |         |     X    |         |
|Gestione di numeri di telefono     |         |   X      |         |
|Licenze per le caratteristiche di cloud Voice     |         |         |    X     |
|Operatori automatici     |         |    X     |         |
|Code di chiamata     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Gestire le impostazioni dopo la migrazione

Una volta completata la migrazione di queste impostazioni, le disattiveremo nell'interfaccia di amministrazione di Office 365 e nell'interfaccia di amministrazione di Skype for business, che potranno quindi essere gestite nel nuovo centro di amministrazione di Microsoft teams.


## <a name="edu-migration-june-july-2019"></a>EDU Migration giugno-luglio 2019

Durante il periodo di giugno e luglio 2019 i restanti tenant EDU verranno migrati dall'esperienza di amministrazione precedente (nell'interfaccia di amministrazione di Microsoft 365) all'interfaccia di amministrazione di teams. Controllare il centro messaggi (nell'interfaccia di amministrazione di Microsoft 365) per sapere quando verrà eseguita la migrazione. Ecco cosa si vedrà dopo la migrazione:

|Sezione di teams nell'interfaccia di amministrazione di Microsoft 365  |Impostazione del nome (livello tenant)  |Criteri dell'interfaccia di amministrazione di Microsoft Teams   |Livello: tenant o utente   |
|---------|---------|---------|---------|  
| Messaggistica  |I proprietari possono eliminare i messaggi inviati |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |
| Messaggistica | Gli utenti possono eliminare i messaggi inviati |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |
| Messaggistica  | Gli utenti possono modificare i messaggi inviati |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)  |Utente|
| Messaggistica | Consentire agli utenti di chattare |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |
| Messaggistica | Usare Giphy nelle conversazioni | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |
| Messaggistica | Valutazione del contenuto di Giphy | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |
| Messaggistica | Usare memi nelle conversazioni  |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |
| Messaggistica | Usare gli adesivi nelle conversazioni |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |

Ecco inoltre le impostazioni disponibili solo nell'interfaccia di amministrazione di Microsoft teams:

|Impostazione del nome | Criteri dell'interfaccia di amministrazione di Microsoft Teams | Livello: tenant o utente
|-------------|-------------------------------------|---------|
|Consenti anteprime URL | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |
|Consentire a un utente di rimuovere utenti da una chat di gruppo |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |
|Consentire all'utilità di lettura immersiva di visualizzare i messaggi |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| Utente |
|Consentire agli utenti di tradurre i messaggi |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| Utente |
|Conferme di lettura | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |
|Gli utenti possono inviare notifiche prioritarie | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Utente |
|Creazione di messaggi vocali |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| Utente |
|Nei dispositivi mobili, visualizzare i canali preferiti sopra le chat recenti |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| Utente |
