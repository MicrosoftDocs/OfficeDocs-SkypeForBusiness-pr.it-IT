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
ms.openlocfilehash: 8becd4a83bb544747fa59a823bae37461c3642c3
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783895"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamenti assistiti da Skype for Business Online a Microsoft Teams

Microsoft ha ritirato Skype for Business Online il 31 luglio 2021.  Microsoft fornisce un processo di aggiornamento assistito per aiutare le organizzazioni a spostare gli utenti rimanenti Skype for Business Online Teams solo.  Gli aggiornamenti assistiti Microsoft riducono il numero di attività tecniche e semplificano la transizione a un mondo senza Skype for Business Online, indipendentemente dal fatto che l'organizzazione sia:
 - Un'organizzazione online pura che deve eseguire l'aggiornamento *da Skype for Business Online* per diventare solo Teams o
 - Un'organizzazione ibrida con utenti sia in *Skype for Business Online*  che in un ambiente *Skype for Business Server* locale, che deve aggiornare solo gli utenti di Skype for Business *Online* a Teams solo.

È consigliabile consultare le indicazioni per [l'aggiornamento prima](https://aka.ms/SkypeToTeams) dell'aggiornamento. Le indicazioni sull'aggiornamento includono attività consigliate e risorse utili per completare un aggiornamento da Skype for Business Online a Teams. Queste indicazioni si applicano a qualsiasi organizzazione che pianifica un aggiornamento a Teams, indipendentemente dal fatto che gestirà tutti gli aspetti dell'aggiornamento o userà il processo assistito.

## <a name="the-assisted-upgrade-experience"></a>Esperienza di aggiornamento assistito
i clienti di Skype for Business Online pianificati per gli aggiornamenti assistiti a Teams riceveranno vari moduli di *notifica: Pianificare* i post di modifica nel Centro messaggi di Microsoft 365, aggiornare le notifiche del dashboard nell'interfaccia di amministrazione di Teams e i contrassegni in-app agli utenti finali. La notifica di aggiornamento nel Centro messaggi e nell'interfaccia di amministrazione di Teams include la data pianificata dell'aggiornamento assistito, oltre a un collegamento per aggiornare le risorse e la formazione per agevolare l'adozione e l'uso di Teams.

L'esperienza di aggiornamento assistito varia leggermente a seconda che l'organizzazione abbia utenti ospitati in un ambiente Skype for Business Server locale:
- **Organizzazioni online pure** Per le organizzazioni *senza* alcun criterio Skype per gli utenti di Busineess Server, `TeamsUpgradeOverridePolicy` il processo di aggiornamento assistito applica il criterio all'organizzazione. Quando si applica questo criterio, tutti gli utenti di Skype for Business Online verranno inseriti in Teams Solo utenti.
- **Organizzazioni ibride con utenti** Skype for Business locali Sono incluse le organizzazioni con tutti gli utenti ospitati in Skype for Business Server, indipendentemente dalla configurazione ibrida. Queste organizzazioni possono includere utenti che rientrano in una delle categorie seguenti:

  - Utenti locali ospitati in Skype for Business Server (che possono o non possono usare Teams, ma non sono Teams solo utenti)
  - Teams solo gli utenti ospitati in Skype for Business Online
  - Non-Teams Solo gli utenti ospitati in Skype for Business Online

Il processo di aggiornamento assistito avrà effetto solo sull'ultima categoria di utenti: non Teams Solo gli utenti ospitati in Skype for Business Online verranno aggiornati alla modalità solo Teams utenti. Gli utenti locali Skype for Business e gli utenti di TeamsOnly esistenti non saranno influenzati dal processo di aggiornamento assistito.

> [!NOTE]
> L'organizzazione può continuare a usare Skype for Business Online fino al completamento dell'aggiornamento. Se è stato pianificato un aggiornamento assistito a Teams, è possibile eseguire un aggiornamento personalizzato da Skype for Business Online prima della data di aggiornamento pianificata. Per altre informazioni su come eseguire manualmente l'aggiornamento a Teams, vedere le indicazioni [per l'aggiornamento](https://aka.ms/SkypeToTeams).

La durata dell'aggiornamento varia in base al volume di utenti e alle caratteristiche della distribuzione. Nella maggior parte dei casi, gli utenti all'interno di un tenant verranno aggiornati entro 24 ore dall'inizio dell'aggiornamento. Durante questo periodo, gli utenti finali avranno ancora accesso Skype for Business funzionalità online. Una volta completato l'aggiornamento e gli utenti si disconnennendono da Skype for Business Online, inizieranno a usare Teams messaggistica, riunioni e chiamate.

## <a name="the-post-upgrade-experience"></a>Esperienza post-aggiornamento

Al termine dell'aggiornamento assistito, la **modalità di coesistenza** per gli utenti aggiornati è Teams solo. È consigliabile rivedere le considerazioni [Teams modalità Solo prima](teams-only-mode-considerations.md) dell'aggiornamento. La tabella seguente fornisce una panoramica generale dell'esperienza utente Teams solo utenti.

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
        - Le Skype for Business online esistenti vengono convertite in Teams riunioni
            > [!IMPORTANT]
            > I clienti con configurazioni Skype for Business Online devono usare il servizio di migrazione delle riunioni (MMS) per eseguire la migrazione delle riunioni Skype for Business Online esistenti a Teams riunioni. È consigliabile usare MMS prima della data di aggiornamento assistito. Per altre informazioni su MMS, vedere [Uso del servizio di migrazione delle riunioni (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
    :::column-end:::
:::row-end:::

Se si ha una distribuzione ibrida Skype for Business Server e si esegue l'aggiornamento a Teams, è possibile spostare gli utenti tra Skype for Business Server e Teams al termine dell'aggiornamento.

## <a name="related-content"></a>Contenuti correlati

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Ritiro di Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams solo modalità](teams-only-mode-considerations.md)
