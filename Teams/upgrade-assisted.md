---
title: Aggiornamenti assistiti | Skype business online per Teams aggiornamento
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Panoramica degli aggiornamenti assistiti da Skype for Business Online a Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 684e7e73932ea2af84518219cf8a9717a732174a
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2021
ms.locfileid: "61562828"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamenti assistiti da Skype for Business Online a Microsoft Teams

Microsoft offre aggiornamenti assistiti a Teams per aiutare le organizzazioni a eseguire una transizione efficace da Skype for Business Online, ritirato il 31 luglio 2021. Se l'organizzazione esegue l'aggiornamento da *Skype for Business Online* o *Skype for Business Online* con un ambiente ibrido (utenti sia in Skype for Business **Online** che Skype for Business Server ) gli aggiornamenti assistiti riducono il numero di attività tecniche che è necessario eseguire e consentono di concentrarsi più sulla preparazione dell'organizzazione, sulla consapevolezza degli utenti e sulla formazione Teams utenti.

È consigliabile consultare le indicazioni per [l'aggiornamento prima](https://aka.ms/SkypeToTeams) dell'aggiornamento. Le indicazioni sull'aggiornamento includono attività consigliate e risorse utili per completare un aggiornamento da Skype for Business Online a Teams. Queste indicazioni si applicano a qualsiasi organizzazione che pianifica un aggiornamento a Teams, che gestirà tutti gli aspetti dell'aggiornamento o userà il processo assistito.

## <a name="notifications-for-scheduled-customers"></a>Notifiche per i clienti programmati

Skype for Business clienti online pianificati per gli aggiornamenti assistiti a Teams riceveranno una serie di notifiche di aggiornamento. Queste notifiche inizieranno 30 giorni prima della data di aggiornamento pianificata. Queste notifiche verranno recapitate come post Di pianificazione per la modifica nel Centro messaggi di Microsoft 365, notifiche del dashboard di aggiornamento nell'interfaccia di amministrazione di Teams e contrassegni in-app agli utenti finali. 

Le notifiche di aggiornamento includeranno la data pianificata dell'aggiornamento assistito e un collegamento alle risorse di aggiornamento e alla formazione per facilitare l'adozione e l'uso di Teams.

## <a name="the-assisted-upgrade-experience"></a>Esperienza di aggiornamento assistito

Gli aggiornamenti assistiti sono iniziati ad agosto 2021 con date specifiche del tenant condivise nelle notifiche di pianificazione menzionate in precedenza.

L'esperienza di aggiornamento assistito varia leggermente a seconda che si abbia un Skype for Business solo online o un Skype for Business Online con ambiente ibrido:

- **Skype for Business solo online Il** processo di aggiornamento assistito applica il `TeamsUpgradeOverridePolicy` criterio all'organizzazione. Quando viene applicato questo criterio, tutti gli utenti Skype for Business online verranno inseriti in Teams Solo utenti.
- **Skype for Business Online con ambienti ibridi** ibridi possono avere utenti che rientrano in una delle categorie seguenti:

  - Utenti locali ospitati in Skype for Business Server
  - Skype for Business utenti online che si Teams modalità Solo utenti
  - Skype for Business utenti online che non **si Teams** modalità Solo utenti

  Se si ha una combinazione di utenti in ognuna delle categorie elencate sopra, il processo di aggiornamento assistito passa solo agli utenti di Skype for Business Online alla modalità Solo Teams se non sono già in quella modalità. Gli utenti locali Skype for Business utenti non saranno influenzati dal processo di aggiornamento assistito.

> [!NOTE]
> L'organizzazione può continuare a usare Skype for Business Online fino al completamento dell'aggiornamento. Se è stato pianificato un aggiornamento assistito a Teams, è possibile eseguire un aggiornamento personalizzato da Skype for Business Online prima della data di aggiornamento pianificata. Per altre informazioni su come eseguire manualmente l'aggiornamento a Teams, vedere le indicazioni [per l'aggiornamento.](https://aka.ms/SkypeToTeams)
>
> Gli aggiornamenti assistiti non sono disponibili per le distribuzioni locali di Skype for Business Server.

La durata dell'aggiornamento varia in base al volume di utenti e alle caratteristiche della distribuzione. Nella maggior parte dei casi, gli utenti all'interno di un tenant verranno aggiornati entro 24 ore dall'inizio dell'aggiornamento. Durante questo periodo, gli utenti finali avranno ancora accesso Skype for Business funzionalità online. Una volta completato l'aggiornamento e gli utenti si disconnennendono da Skype for Business Online, inizieranno a usare Teams messaggistica, riunioni e chiamate.

## <a name="the-post-upgrade-experience"></a>Esperienza post-aggiornamento

Al termine dell'aggiornamento assistito, la **modalità di coesistenza** per gli utenti aggiornati è impostata su Solo Teams versione. È consigliabile rivedere le considerazioni [Teams modalità Solo prima](teams-only-mode-considerations.md) dell'aggiornamento. La tabella seguente fornisce una panoramica generale dell'esperienza utente Teams solo utenti.

:::row:::
    :::column span="1":::
        **Chat e chiamate**
    :::column-end:::
    :::column span="3":::
        - Tutte le chiamate e le chat vengono avviate e ricevute in Teams
        - Gli utenti possono comunicare (chat/chiamata) con qualsiasi Skype for Business utente
        - Le organizzazioni possono consentire agli Teams utenti di comunicare con gli utenti del servizio Skype consumer gestendo [le autorizzazioni di accesso esterno](manage-external-access.md)
        - Teams utenti che provano ad accedere a Skype for Business Online vengono reindirizzati a Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Riunioni**
    :::column-end:::
    :::column span="3":::
        - Gli utenti pianificano tutte le nuove riunioni in Teams (plug-in sostituito)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Dati migrati**
    :::column-end:::
    :::column span="3":::
        - Contatti esistenti di Skype for Business Online, inclusi federati (ma non liste di distribuzione)
        - La migrazione dei contatti viene eseguita quando gli utenti a Teams per la prima volta.
            > [!IMPORTANT]
            >La migrazione dei contatti deve essere eseguita entro 90 giorni dal completamento dell'aggiornamento.
        - Le riunioni Skype for Business online vengono convertite in Teams riunioni
            > [!IMPORTANT]
            > I clienti con configurazioni Skype for Business online devono usare il servizio di migrazione delle riunioni (MMS) per eseguire la migrazione delle riunioni Skype for Business Online esistenti a Teams riunioni. È consigliabile usare MMS prima della data di aggiornamento assistito. Per altre informazioni su MMS, vedere [Uso del servizio di migrazione delle riunioni (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
    :::column-end:::
:::row-end:::

Se si ha una distribuzione ibrida Skype for Business Server e si esegue l'aggiornamento a Teams, è possibile spostare gli utenti tra Skype for Business Server e Teams al termine dell'aggiornamento.

## <a name="related-content"></a>Contenuti correlati

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Ritiro di Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams solo modalità](teams-only-mode-considerations.md)
