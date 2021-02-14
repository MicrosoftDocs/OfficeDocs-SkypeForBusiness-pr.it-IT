---
title: Consenso specifico delle risorse in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sulle impostazioni che è necessario configurare per controllare se i proprietari dei team nell'organizzazione possono fornire il consenso alle app.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6267f4b42890716ca31fd1b44de435af50ad6ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815676"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consenso specifico delle risorse in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Il consenso specifico delle risorse in Microsoft Teams consente ai proprietari dei team di dare il consenso alle app per accedere ai dati del team. Esempi di tale accesso includono la possibilità di leggere i messaggi del canale, creare ed eliminare canali e creare e rimuovere schede dei canali.

Come amministratore, puoi controllare se i proprietari dei team nella tua organizzazione possono dare il consenso tramite le impostazioni configurate usando il modulo PowerShell di Azure Active Directory (Azure AD) o il portale di Azure e l'interfaccia di amministrazione di Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Specificare se i proprietari del team possono concedere il consenso alle app

Ecco le impostazioni che è necessario configurare per controllare se i proprietari del team possono fornire il consenso alle app. Assicurarsi di controllare tutte le impostazioni seguenti.

### <a name="settings-in-azure-ad"></a>Impostazioni in Azure AD

Le due impostazioni seguenti determinano se i proprietari del team possono fornire il consenso alle app.

> [!IMPORTANT]
> La modifica di queste impostazioni non influisce sull'accesso ai dati per le app con il consenso già concesso. Ad esempio, se si configurano queste impostazioni per impedire ai proprietari dei team di concedere il consenso, queste modifiche non rimuovono l'accesso ai dati già concesso.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Impostazione "Gli utenti possono acconsentire alle app che accedono ai dati aziendali per loro conto"

Questa impostazione controlla se gli utenti dell'organizzazione possono acconsentire alle app per loro conto. Per consentire ai proprietari dei team di fornire il consenso, questa impostazione deve essere impostata su **Sì.** Per gestire questa impostazione, eseguire le operazioni seguenti:

1. Nel portale di Azure passare a Impostazioni utente **delle applicazioni**  >  **enterprise.**
2. Nelle **applicazioni Enterprise** impostare **l'opzione Gli utenti possono acconsentire alle app che accedono ai** dati aziendali per conto loro su **No** o **Sì.**

È anche possibile gestire questa impostazione con PowerShell. Per altre informazioni, vedere [Configurare il contenuto utente per le applicazioni.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)

#### <a name="the-enablegroupspecificconsent-setting"></a>Impostazione "EnableGroupSpecificConsent"

Questa impostazione controlla se gli utenti dell'organizzazione possono acconsentire alle app che accedono ai dati aziendali per i gruppi di loro proprietà. Questa impostazione deve essere abilitata per i proprietari del team per fornire il consenso. Per la procedura su come gestire questa impostazione con PowerShell, vedere Configurare il consenso del proprietario del gruppo per le app che accedono [ai dati del gruppo.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Impostazioni nell'interfaccia di amministrazione di Microsoft Teams

Oltre alle impostazioni in Azure AD, le [](manage-apps.md) impostazioni delle [app](manage-apps.md#manage-org-wide-app-settings) a livello di organizzazione [](manage-apps.md#allow-and-block-apps) nella pagina Gestisci app, se un'app è bloccata o consentita nella pagina Gestisci app e i criteri di autorizzazione per le [app](teams-app-permission-policies.md) assegnati al proprietario del team determinano se un proprietario del team può fornire il consenso.

> [!IMPORTANT]
> La modifica di queste impostazioni non influisce sull'accesso ai dati per le app con il consenso già concesso. Ad esempio, se disattivi app di terze parti a livello di organizzazione o se blocchi app specifiche per impedire ai proprietari del team di fornire il consenso, queste modifiche non rimuovono l'accesso ai dati già concesso.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Impostazione "Consenti app di terze parti" nelle impostazioni delle app a livello di organizzazione

Questa impostazione dell'app a livello di organizzazione controlla se gli utenti dell'organizzazione possono usare app di terze parti. Questa impostazione deve essere attivata per consentire ai proprietari dei team di fornire il consenso. Per gestire questa impostazione, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a Gestisci app di **Teams** e quindi fare clic su  >  Impostazioni app a livello **di organizzazione.**
2. In **App di terze parti,** disattiva o attiva Consenti app di terze **parti.**

    ![Screenshot dell'impostazione "Consenti app di terze parti in Teams"](media/resource-specific-consent-org-wide-setting.png)

Possono essere necessarie fino a 24 ore prima che le modifiche diventino effettive.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Consentire o bloccare l'app a livello di organizzazione

Quando si blocca o si [](manage-apps.md#allow-and-block-apps) consente un'app nella pagina Gestisci app, l'app viene bloccata o consentita a tutti gli utenti dell'organizzazione. I proprietari del team possono dare il consenso a un'app solo se l'app è consentita. Per consentire o bloccare un'app a livello dell'organizzazione, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams.
2. Nella pagina Gestisci app selezionare l'app  e quindi fare clic su Blocca per bloccarla o su Consenti **per** consentirla.

    ![Screenshot delle app bloccate nelle impostazioni a livello di organizzazione](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Criteri di autorizzazione per le app assegnati al proprietario del team

I proprietari del team possono dare il consenso solo alle app che i criteri di autorizzazione per le app consentono di eseguire. Per visualizzare e gestire i criteri di autorizzazione per le app assegnati a un proprietario del team, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Utenti.**
2. Fare doppio clic sul nome visualizzato del proprietario del team e quindi fare clic su **Criteri.**
3. I criteri assegnati al proprietario del team sono elencati in **Criteri di autorizzazione app.**
    - Per assegnare un criterio diverso, fare clic su **Modifica** e quindi selezionare il criterio da assegnare.
    - Per modificare le impostazioni del criterio assegnato al proprietario del team, fare clic sul nome del criterio e quindi apportare le modifiche desiderate.  

## <a name="uploading-custom-apps"></a>Caricamento di app personalizzate

Quando si carica un'app personalizzata (anche nota come sideload) che usa il consenso specifico della risorsa, l'app deve provengono dal tenant in cui viene installata. In altre parole, la registrazione dell'app Azure AD deve essere di questo tenant. Gli amministratori globali non sono esenti da questa restrizione e possono caricare app personalizzate da qualsiasi tenant, direttamente in un team (sideload) o nel catalogo app tenant.

## <a name="related-topics"></a>Argomenti correlati

- [Autorizzazioni RSC disponibili](https://aka.ms/teams-rsc)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
