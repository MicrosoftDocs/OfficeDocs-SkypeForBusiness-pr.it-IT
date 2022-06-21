---
title: Consenso specifico delle risorse in Microsoft Teams
author: guptaashish
ms.author: guptaashish
ms.reviewer: nkramer
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sulle impostazioni da configurare per controllare se i proprietari dei team dell'organizzazione possono concedere il consenso alle app.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b5ef3f94c511dfe86ab7b153bfa8dd3ea1a04fa
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190497"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consenso specifico delle risorse in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Il consenso specifico delle risorse in Microsoft Teams consente ai proprietari del team di concedere il consenso alle app per accedere ai dati del team. Esempi di questo tipo di accesso includono la possibilità di leggere i messaggi dei canali, creare ed eliminare canali e creare e rimuovere le schede dei canali.

Gli amministratori possono controllare se i proprietari dei team dell'organizzazione possono concedere il consenso tramite le impostazioni configurate usando il modulo PowerShell di Azure Active Directory (Azure AD) o il portale di Azure e l'interfaccia di amministrazione di Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Specificare se i proprietari del team possono concedere il consenso alle app

Ecco le impostazioni che è necessario impostare per controllare se i proprietari del team possono concedere il consenso alle app. Assicurati di rivedere tutte le impostazioni seguenti.

### <a name="settings-in-azure-ad"></a>Impostazioni in Azure AD

Le due impostazioni seguenti determinano se i proprietari del team possono dare il consenso alle app.

> [!IMPORTANT]
> La modifica di queste impostazioni non influisce sull'accesso ai dati per le app a cui è già stato concesso il consenso. Ad esempio, se configuri queste impostazioni per impedire ai proprietari del team di dare il consenso, queste modifiche non rimuove l'accesso ai dati già concesso.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>L'impostazione "Gli utenti possono acconsentire alle app che accedono ai dati aziendali per conto loro"

Questa impostazione controlla se gli utenti dell'organizzazione possono acconsentire alle app per loro conto. Per consentire ai proprietari del team di concedere il consenso, questa impostazione deve essere impostata su **Sì**. Per gestire questa impostazione, eseguire le operazioni seguenti:

1. Nella portale di Azure passare ad **applicazioni** >  Enterprise **Impostazioni utente**.
2. In **applicazioni Enterprise**, imposta **Gli utenti possono acconsentire alle app che accedono ai dati aziendali per conto loro su** **No** o **Sì**.

È anche possibile gestire questa impostazione con PowerShell. Per altre informazioni, vedere [Configurare il contenuto dell'utente per le applicazioni](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>Impostazione "EnableGroupSpecificConsent"

Questa impostazione controlla se gli utenti dell'organizzazione possono acconsentire alle app che accedono ai dati aziendali per i gruppi di cui sono proprietari. Questa impostazione deve essere abilitata per consentire ai proprietari del team di fornire il consenso. Per istruzioni su come gestire questa impostazione tramite PowerShell, vedere [Configurare il consenso del proprietario del gruppo per le app che accedono ai dati del gruppo](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Impostazioni nell'interfaccia di amministrazione di Microsoft Teams

Oltre alle impostazioni di Azure AD, [le impostazioni delle app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings) nella pagina [Gestisci app](manage-apps.md) , se un'app è bloccata o consentita nella pagina [Gestisci app](manage-apps.md#allow-and-block-apps) e i [criteri di autorizzazione dell'app](teams-app-permission-policies.md) assegnati al proprietario del team determinano se un proprietario del team può dare il consenso.

> [!IMPORTANT]
> La modifica di queste impostazioni non influisce sull'accesso ai dati per le app a cui è già stato concesso il consenso. Ad esempio, se disabiliti app di terze parti a livello di organizzazione o blocchi app specifiche per impedire ai proprietari del team di dare il consenso, queste modifiche non rimuovono l'accesso ai dati già concesso.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>L'impostazione "Consenti app di terze parti" nelle impostazioni delle app a livello di organizzazione

Questa impostazione dell'app a livello di organizzazione controlla se gli utenti dell'organizzazione possono usare app di terze parti. Questa impostazione deve essere attivata per consentire ai proprietari del team di dare il consenso. Per gestire questa impostazione, eseguire le operazioni seguenti:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Teams app** > **Gestisci app** e quindi fare clic su **Impostazioni app a livello di organizzazione**.
2. In **App di terze parti** disattiva o attiva **Consenti app di terze parti**.

    ![Screenshot dell'impostazione "Consenti app di terze parti in Teams"](media/resource-specific-consent-org-wide-setting.png)

Possono essere necessarie fino a 24 ore prima che le modifiche diventino effettive.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Consentire o bloccare l'app a livello di organizzazione

Quando si blocca o si consente un'app nella pagina [Gestisci app](manage-apps.md#allow-and-block-apps) , l'app viene bloccata o consentita a tutti gli utenti dell'organizzazione. I proprietari del team possono dare il consenso a un'app solo se l'app è consentita. Per consentire o bloccare un'app a livello di organizzazione, eseguire le operazioni seguenti:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
2. Nella pagina Gestisci app selezionare l'app e quindi fare clic su **Blocca** per bloccarla o su **Consenti** per consentirla.

    ![Screenshot delle app bloccate nelle impostazioni a livello di organizzazione.](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Criteri di autorizzazione dell'app assegnati al proprietario del team

I proprietari del team possono dare il consenso solo alle app che i criteri di autorizzazione dell'app consentono loro di eseguire. Per visualizzare e gestire i criteri di autorizzazione dell'app assegnati a un proprietario del team, eseguire le operazioni seguenti:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti**.
2. Fare doppio clic sul nome visualizzato del proprietario del team e quindi su **Criteri**.
3. I criteri assegnati al proprietario del team sono elencati in **Criteri di autorizzazione app**.
    - Per assegnare un criterio diverso, fare clic su **Modifica** e quindi selezionare il criterio da assegnare.
    - Per modificare le impostazioni del criterio assegnato al proprietario del team, fare clic sul nome del criterio e quindi apportare le modifiche desiderate.  

## <a name="uploading-custom-apps"></a>Caricamento di app personalizzate

Quando si carica un'app personalizzata (anche nota come sideload) che usa il consenso specifico delle risorse, l'app deve provenire dal tenant in cui viene installata. In altre parole, la registrazione dell'app Azure AD deve provenire da questo tenant. Gli amministratori globali sono esenti da questa restrizione e possono caricare app personalizzate da qualsiasi tenant, direttamente in un team (sideload) o nel catalogo app tenant.

## <a name="related-topics"></a>Argomenti correlati

- [Autorizzazioni RSC disponibili](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
