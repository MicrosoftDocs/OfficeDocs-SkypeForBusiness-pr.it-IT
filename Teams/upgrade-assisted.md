---
title: Aggiornamenti assistiti | Aggiornamento da Skype Business Online a Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Panoramica degli aggiornamenti assistiti da Skype for Business online a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995197"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamenti assistiti da Skype for Business online a Microsoft Teams

Microsoft offre aggiornamenti assistiti a Teams per aiutare le organizzazioni a eseguire correttamente la transizione da Skype for Business online man mano che il servizio si ritira il 31 luglio 2021. Gli aggiornamenti assistiti riducono il numero di attività tecniche da eseguire e consentono di concentrarsi più sulla preparazione dell'organizzazione, sulla consapevolezza degli utenti e sulla formazione di Teams.

È consigliabile consultare le indicazioni per [l'aggiornamento prima](https://aka.ms/SkypeToTeams) dell'aggiornamento. Le nostre indicazioni sull'aggiornamento includono attività consigliate e risorse utili per completare un aggiornamento da Skype for Business Online a Teams. Queste indicazioni si applicano a qualsiasi organizzazione che pianifica un aggiornamento a Teams, che gestisci tutti gli aspetti dell'aggiornamento o usi il processo assistito.

> [!NOTE]
> Se è pianificato un aggiornamento assistito a Teams, è possibile eseguire il proprio aggiornamento da Skype for Business Online prima della data di aggiornamento pianificata. Per altre informazioni su come eseguire manualmente l'aggiornamento a Teams, vedere le [indicazioni per l'aggiornamento.](https://aka.ms/SkypeToTeams)
>
> L'aggiornamento assistito non è disponibile per le distribuzioni locali di Skype for Business Server.

## <a name="notifications-for-scheduled-customers"></a>Notifiche per i clienti programmati

I clienti di Skype for Business Online pianificati per gli aggiornamenti assistiti a Teams riceveranno una serie di notifiche di aggiornamento. Queste notifiche inizieranno 90 giorni prima della data di aggiornamento pianificata. Queste notifiche verranno recapitate come post Di pianificazione per la modifica nel Centro messaggi di Microsoft 365, notifiche del dashboard di aggiornamento nell'interfaccia di amministrazione di Teams e contrassegni in-app agli utenti finali. 

Le notifiche sull'aggiornamento includeranno la data pianificata dell'aggiornamento assistito e un collegamento alle risorse di aggiornamento e alla formazione per facilitare l'adozione e l'uso di Teams.

## <a name="the-assisted-upgrade-experience"></a>Esperienza di aggiornamento assistito

Gli aggiornamenti assistiti inizieranno ad agosto 2021 con date specifiche del tenant condivise nelle notifiche di pianificazione menzionate in precedenza.

La durata dell'aggiornamento varia in base al volume di utenti e alle caratteristiche della distribuzione. Tuttavia, nella maggior parte dei casi, gli utenti all'interno di un tenant verranno aggiornati entro 24 ore dall'inizio dell'aggiornamento. Durante questo periodo, gli utenti finali avranno ancora accesso alla funzionalità skype for business online. Una volta completato l'aggiornamento e gli utenti si disconnennendono da Skype for Business online, inizieranno a usare Teams per messaggistica, riunioni e chiamate.

## <a name="the-post-upgrade-experience"></a>Esperienza post-aggiornamento

Al termine dell'aggiornamento assistito, la modalità di **coesistenza** per gli utenti aggiornati è impostata su Solo Teams e può essere modificata solo in una modalità di coesistenza diversa da Microsoft. È consigliabile esaminare le considerazioni [relative alla modalità Solo Teams prima](teams-only-mode-considerations.md) dell'aggiornamento. La tabella seguente fornisce una panoramica generale dell'esperienza utente solo di Teams.

:::row:::
    :::column span="1":::
        **Chat e chiamate**
    :::column-end:::
    :::column span="3":::
        - Tutte le chiamate e le chat vengono avviate e ricevute in Teams
        - Gli utenti possono comunicare (chat/chiamata) con qualsiasi utente di Skype for Business
        - Le organizzazioni possono consentire agli utenti di Teams di comunicare con gli utenti del servizio skype consumer gestendo [le autorizzazioni di accesso esterno](manage-external-access.md)
        - Gli utenti di Teams che provano ad accedere a Skype for Business online verranno reindirizzati a Teams
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
        - Contatti esistenti da Skype for Business Online, inclusi federati (ma nessuna lista di distribuzione
        - Le riunioni skype for business online esistenti vengono convertite in riunioni di Teams
    :::column-end:::
:::row-end:::

## <a name="related-content"></a>Contenuti correlati

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Ritiro di Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Considerazioni sulla modalità Solo Teams](teams-only-mode-considerations.md)
