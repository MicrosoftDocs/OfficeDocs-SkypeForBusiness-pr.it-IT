---
title: Pianificare la spostamento dei team di StaffHub in turni in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: gumariam,aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Ottenere indicazioni su come pianificare la procedura per spostare i team di StaffHub in turni in Microsoft teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78b31bb0c17db9ef379b54c02433569ba4d46aff
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37639582"
---
# <a name="plan-to-move-your-staffhub-teams-to-shifts-in-microsoft-teams"></a>Pianificare la spostamento dei team di StaffHub in turni in Microsoft Teams

> [!IMPORTANT]
> Efficace 31 dicembre 2019, Microsoft StaffHub sarà ritirato. Stiamo costruendo funzionalità di StaffHub in Microsoft teams. Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo. StaffHub smetterà di funzionare per tutti gli utenti il 31 dicembre 2019. Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams. Per altre informazioni, vedere [Microsoft StaffHub per ritirarsi](microsoft-staffhub-to-be-retired.md). 

La transizione da StaffHub a teams inizia quando si avvia la pianificazione per la modifica. Per assicurarti che il passaggio a teams abbia successo, abbiamo creato una sequenza temporale di esempio che illustra un tipico piano di transizione. La sequenza temporale di esempio delinea le attività di pianificazione per prepararsi allo spostamento e consente di spostare i team di StaffHub dell'organizzazione in teams.

Usare la sequenza temporale come indicazioni per pianificare il passaggio da StaffHub a teams e personalizzarlo in base alle esigenze dell'organizzazione. Assicurarsi di esaminare le risorse collegate ai passaggi della sequenza temporale.

## <a name="prepare-to-move-your-staffhub-teams-to-teams"></a>Preparare per trasferire i team di StaffHub in teams

|Passaggio |Indicazioni  |Risorsa |
|---------|---------|---------|
|1    |Preparare e identificare gli stakeholder         |         |
|2     |Esaminare la documentazione relativa alla transizione da StaffHub a teams e teams onboarding         |[StaffHub da ritirarsi](microsoft-staffhub-to-be-retired.md)<br><br>[Spostare i team di StaffHub in turni in teams](move-staffhub-teams-to-shifts-in-teams.md)<br><br>[Iniziare a usare Teams](../../get-started-with-teams-quick-start.md)         |
|3    |Abilitare i gruppi di Office 365 per l'organizzazione        |[Gruppi e team di Office 365](../../Office-365-groups.md)      |
|4    |Verificare che i prerequisiti siano soddisfatti         |[Verificare che i prerequisiti vengano soddisfatti](move-staffhub-teams-to-shifts-in-teams.md#check-that-prerequisites-are-met)       |
|5   |Assegnare licenze teams agli utenti di StaffHub nell'organizzazione|[Assegnare licenze Teams](move-staffhub-teams-to-shifts-in-teams.md#assign-teams-licenses)<br><br>[Gestire l'accesso degli utenti ai team](../../user-access.md)      |
|6    |Installare il modulo di PowerShell StaffHub        |[Installare il modulo di PowerShell StaffHub](install-the-staffhub-powershell-module.md)        |
|7     |Determinare la sequenza temporale e identificare gli utenti di StaffHub per il passaggio a teams       |[Eseguire un report per mostrare l'utilizzo di Active StaffHub](run-report-to-show-staffhub-usage.md) |
|8     |Identificare gli utenti di StaffHub che non hanno un account di Azure AD (come "inattivo" in StaffHub) e collegarne un account     |[Collegare un account di Azure AD per i membri del team di StaffHub che non ne hanno uno](move-staffhub-teams-to-shifts-in-teams.md#link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one)        |
|9    |Creare contenuto di formazione per gli utenti personalizzati per l'organizzazione         |[Preparare un piano di preparazione degli utenti per i team](../../upgrade-user-readiness.md)     |
|10    |Comunicare agli utenti di StaffHub la transizione ai turni in teams         |[StaffHub alla comunicazione tramite posta elettronica di esempio in teams agli utenti](staffhub-to-teams-email-template.md)         |
|11     |Installare i client Teams         |[Ottenere client per Teams](../../get-clients.md) |
|12    |Assegnare i criteri di configurazione dell'app FirstLineWorker agli utenti (o creare e assegnare criteri di configurazione dell'app personalizzati) per aggiungere l'app turni ai client Teams  |[Assegnare i criteri di configurazione dell'app FirstlineWorker agli utenti](move-staffhub-teams-to-shifts-in-teams.md#assign-the-firstlineworker-app-setup-policy-to-users)         |
|13     |Formare gli utenti su come usare turni e team         |[Utenti a bordo di Teams](move-staffhub-teams-to-shifts-in-teams.md#onboard-users-to-teams)<br><br>[Sposta la documentazione della Guida](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)<br><br>[Documentazione della Guida di Teams](https://support.office.com/teams)<br><br>[Video di formazione su Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)       |
|14     |Esaminare l'elenco dei team di StaffHub per assicurarsi che tutti gli utenti di tali team vengano spostati in teams. Rimuovere gli utenti che non devono essere nella programmazione. |         |

## <a name="move-your-organizations-staffhub-teams-to-teams"></a>Trasferire i team di StaffHub dell'organizzazione in teams

|Passaggio |Indicazioni |Risorsa  |
|---------|---------|---------|
|1  |Identificare un team pilota e cambiare un team          |[Trasferire un team di StaffHub](move-staffhub-teams-to-shifts-in-teams.md#move-a-staffhub-team)          |
|2    |Convalidare il team pilota e individuare eventuali problemi di trasferimento. Aggiornare la documentazione di formazione in base alle esigenze.         |         |
|3     |Identificare team pilota aggiuntivi e trasferire da cinque a dieci Team         |[Trasferire i team di StaffHub](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|4     |Identificare i team di StaffHub rimanenti e spostarli in un approccio graduale         |[Trasferire i team di StaffHub](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|5     |Continuare a supportare i turni e i team         |         |
|6     |Se è abilitata la reimpostazione della password self-service, eseguire un report per supportare i problemi di accesso in teams       |[Eseguire un report per la configurazione di reimpostazione della password in self-service](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)        |
