---
title: Gestire le impostazioni e i criteri delle app personalizzati
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come gestire i criteri e le impostazioni delle app personalizzate per controllare chi nell'organizzazione può caricare app personalizzate in Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 120f19472a0438c6bb76e98e0c8ef473c012c7b7
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681387"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gestire i criteri e le impostazioni delle app personalizzate in Microsoft Teams

> [!NOTE]
> Per usare App Studio, vedi [Attività iniziali sulla piattaforma Microsoft Teams con C#/.NET e App Studio](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) L'ultimo passaggio non funziona ancora, quindi dovrai scaricare lo zip e installarlo nel [vecchio modo in Upload un pacchetto di app per Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload).

Gli amministratori possono usare le impostazioni e i criteri delle app personalizzati per controllare chi nell'organizzazione può caricare app personalizzate in Microsoft Teams. Gli amministratori decidono quali utenti possono caricare app personalizzate e gli amministratori e i proprietari dei team possono determinare se team specifici dell'organizzazione consentono l'aggiunta di app personalizzate.  Dopo aver modificato i criteri dell'app personalizzati, l'applicazione delle modifiche può richiedere alcune ore. Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.

## <a name="overview-of-custom-apps"></a>Panoramica delle app personalizzate

Gli utenti possono aggiungere un'app personalizzata a Teams caricando un pacchetto dell'app (in un file di .zip) direttamente in un team o nel contesto personale. Questa operazione è diversa da come vengono aggiunte le app tramite l'app store Teams. L'aggiunta di un'app personalizzata caricando un pacchetto di app, noto anche come sideload, consente di testare un'app durante lo sviluppo, prima che sia pronta per essere ampiamente distribuita. Consente inoltre di creare un'app solo per uso interno e condividerla con il team senza inviarla al catalogo app Teams nell'app store Teams.

![Screenshot che mostra l'opzione di caricamento di un'app personalizzata nell'App Store.](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Impostazioni e criteri delle app personalizzati

Tre componenti determinano se un utente può caricare un'app personalizzata in un team, offrendoti un controllo capi capibile su chi può aggiungere app personalizzate a un team e quali app personalizzate di teams possono essere aggiunte a:

- [Criteri per le app personalizzate dell'utente](#user-custom-app-policy)
- [Impostazione dell'app personalizzata del team](#team-custom-app-setting)
- [Impostazione dell'app personalizzata a livello di organizzazione](#org-wide-custom-app-setting)

Queste impostazioni non influiscono sulla possibilità di bloccare le app di terze parti.  

### <a name="user-custom-app-policy"></a>Criteri per le app personalizzate dell'utente

[Nell'ambito](teams-app-setup-policies.md) dei criteri di configurazione delle app, gli amministratori possono usare un'impostazione dei criteri **, Upload app personalizzate**, per controllare se un utente può caricare app personalizzate in Teams.

Se questa impostazione è disattivata:

- L'utente non può caricare un'app personalizzata in alcun team dell'organizzazione o nel contesto personale.
- L'utente può interagire con le app personalizzate, a seconda dell'impostazione dell'app personalizzata a livello di organizzazione.

Se questa impostazione è attivata:

- L'utente può caricare app personalizzate nei team che lo consentono e ai team di cui sono proprietari, a seconda dell'impostazione dell'app personalizzata a livello di organizzazione.
- L'utente può caricare app personalizzate nel contesto personale.
- L'utente può interagire con le app personalizzate, a seconda dell'impostazione dell'app personalizzata a livello di organizzazione.

È possibile modificare le impostazioni nel criterio di configurazione globale delle app per includere le app desiderate. Se si vuole personalizzare Teams per gruppi di utenti diversi nell'organizzazione, creare e assegnare uno o più criteri di configurazione delle app personalizzati.

#### <a name="set-a-user-custom-app-policy"></a>Impostare criteri app personalizzati per un utente

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a criteri di **configurazione** **di Teams app** > .
2. Fare clic su **Aggiungi**.
3. Attivare o disattivare **Upload app personalizzate**.
4. Scegliere le altre impostazioni desiderate per il criterio.
5. Fare clic su **Salva**.

### <a name="team-custom-app-setting"></a>Impostazione dell'app personalizzata del team

Gli amministratori e i proprietari del team possono controllare se un team consente l'aggiunta di app personalizzate. Questa impostazione **, Consenti ai membri di caricare app personalizzate**, insieme ai criteri delle app personalizzate di un utente, determina chi può aggiungere app personalizzate a un particolare team.

Se questa impostazione è disattivata:

- I proprietari del team possono aggiungere app personalizzate, se i criteri delle app personalizzate lo consentono.
- I membri del team che non sono proprietari del team non possono aggiungere app personalizzate al team.

Se questa impostazione è attivata:

- I proprietari del team possono aggiungere app personalizzate, se i criteri delle app personalizzate lo consentono.
- I membri del team che non sono proprietari del team possono aggiungere app personalizzate, se i criteri delle app personalizzate lo consentono.

#### <a name="configure-the-team-custom-app-setting"></a>Configurare l'impostazione dell'app personalizzata del team

1. In Teams, passare al team, fare clic su **Altre opzioni ...** >  **Gestire il team**.
2. Fare clic su **Impostazioni** e quindi espandere **Autorizzazioni membro**.
3. Selezionare o deselezionare la casella **di controllo Consenti ai membri di caricare app personalizzate** .

    ![Screenshot che mostra l'impostazione dell'app personalizzata del team.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Impostazione dell'app personalizzata a livello di organizzazione

**L'impostazione Consenti l'interazione con app personalizzate** a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) si applica a tutti gli utenti dell'organizzazione e regola se possono caricare o interagire con app personalizzate. Questa impostazione funge da interruttore master di attivazione/disattivazione per le impostazioni dei criteri app personalizzate dell'utente e del team. È destinato a fungere da interruttore master di attivazione/disattivazione durante gli eventi di sicurezza. Di conseguenza, le impostazioni dei criteri personalizzati per le app di utenti e team non verranno applicate a meno che l'impostazione dell'app personalizzata a livello di organizzazione non sia abilitata anche se sono abilitate le impostazioni dei criteri personalizzati dell'app per utenti e team.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurare l'impostazione dell'app personalizzata a livello di organizzazione

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
2. Fare clic su **Impostazioni app a livello di organizzazione**.
3. In **App personalizzate**, attiva o disattiva **Consenti l'interazione con le app personalizzate**.

    ![Screenshot che mostra le impostazioni delle app personalizzate a livello di organizzazione.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Interazione tra i criteri e le impostazioni delle app personalizzate

Questa tabella riepiloga i criteri e le impostazioni delle app personalizzate, il loro modo di collaborare e l'effetto combinato sul controllo degli utenti dell'organizzazione che possono caricare app personalizzate su Teams.

Supponiamo, ad esempio, di voler consentire solo ai proprietari del team di caricare app personalizzate in team specifici. Impostare quanto segue:

- Attiva l'impostazione **Consenti interazione con app personalizzate** nell'interfaccia di amministrazione di Microsoft Teams.
- Disattiva **Consenti ai membri di caricare app personalizzate** per ogni team in cui vuoi limitare l'accesso.
- Creare e assegnare criteri di configurazione delle app personalizzati nell'interfaccia di amministrazione di Microsoft Teams con l'impostazione **Upload app personalizzate** attivata e assegnarla ai proprietari del team.

|Impostazione dell'app personalizzata a livello di organizzazione |Impostazione dell'app personalizzata del team |Criteri per le app personalizzate dell'utente |Effetto  |
|---------|---------|---------|---------|
| Disattivato    | Disattivato    | Disattivato     |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno, ad eccezione di un Amministrazione del servizio Teams o di un amministratore globale. È possibile usare PowerShell per rimuovere l'app personalizzata.   |
| Disattivato     | Disattivato     | Attivato        |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno, ad eccezione di un Amministrazione del servizio Teams o di un amministratore globale. È possibile usare PowerShell per rimuovere l'app personalizzata.         |
| Disattivato    | Attivato        | Disattivato        |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno, ad eccezione di un Amministrazione del servizio Teams o di un amministratore globale. Puoi usare Windows PowerShell per eliminare app personalizzate.         |
| Disattivato    | Attivato      | Attivato       |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno, ad eccezione di un Amministrazione del servizio Teams o di un amministratore globale. È possibile usare PowerShell per rimuovere l'app personalizzata.         |
| Attivato    | Disattivato       | Disattivato         |  L'utente non può caricare app personalizzate.      |
| Attivato     | Disattivato       | Attivato         | Se l'utente è proprietario del team, può caricare app personalizzate nel team. Se l'utente non è proprietario del team, non può caricare app personalizzate nel team. L'utente può caricare app personalizzate nel contesto personale.     |
| Attivato     | Attivato     | Disattivato         | L'utente non può caricare app personalizzate.       |
| Attivato    | Attivato        | Attivato        | L'utente può caricare app personalizzate nel team, indipendentemente dal fatto che sia proprietario del team. L'utente può caricare app personalizzate nel contesto personale.       |

## <a name="related-topics"></a>Argomenti correlati

[Impostazioni di amministrazione per le app in Teams](admin-settings.md)

[Assegnare i criteri agli utenti in Teams](assign-policies-users-and-groups.md)
