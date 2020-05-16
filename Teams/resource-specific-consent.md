---
title: Consenso specifico delle risorse in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sulle impostazioni che è necessario configurare per controllare se i proprietari dei team dell'organizzazione possono dare il consenso alle app.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a0565f5126c899ed5fbf9527aa30f83c3bee3b
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256602"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consenso specifico delle risorse in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Il consenso specifico delle risorse in Microsoft teams consente ai proprietari del team di consentire alle app di accedere ai dati del team. Esempi di questo tipo di accesso includono la possibilità di leggere i messaggi del canale, creare ed eliminare canali e creare e rimuovere le schede dei canali.

Come amministratore, puoi controllare se i proprietari del team dell'organizzazione possono dare il consenso tramite le impostazioni configurate usando il modulo PowerShell di Azure Active Directory (Azure AD) o il portale di Azure e l'interfaccia di amministrazione di Microsoft teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Imposta se i proprietari del team possono dare il consenso alle app

Ecco le impostazioni che devi impostare per controllare se i proprietari del team possono dare il consenso alle app. Assicurarsi di esaminare tutte le impostazioni seguenti.

### <a name="settings-in-azure-ad"></a>Impostazioni in Azure AD

Le due impostazioni seguenti determinano se i proprietari del team possono dare il consenso alle app.

> [!IMPORTANT]
> La modifica di queste impostazioni non influisce sull'accesso ai dati per le app a cui è già stato concesso il consenso. Ad esempio, se si configurano queste impostazioni per impedire ai proprietari del team di concedere il consenso, queste modifiche non rimuovono l'accesso ai dati già concesso.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>L'impostazione "gli utenti possono acconsentire alle app per l'accesso ai dati aziendali per loro conto"

Questa impostazione controlla se gli utenti dell'organizzazione possono acconsentire alle app per loro conto. Per consentire ai proprietari del team di dare il consenso, questa impostazione deve essere impostata su **Sì**. Per gestire questa impostazione, eseguire le operazioni seguenti:

1. In Azure Portal passa a **Enterprise applications**  >  **impostazioni utente delle**applicazioni Enterprise.
2. In **applicazioni aziendali**, imposta **gli utenti possono consentire alle app di accedere ai dati aziendali per loro conto** in **No** o **Yes**.

È anche possibile gestire questa impostazione usando PowerShell. Per altre informazioni, vedere [configurare il contenuto utente nelle applicazioni](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>Impostazione "EnableGroupSpecificConsent"

Questa impostazione controlla se gli utenti dell'organizzazione possono consentire alle app di accedere ai dati aziendali per i gruppi di cui sono proprietari. Questa impostazione deve essere abilitata per i proprietari del team per dare il consenso. Per istruzioni su come gestire questa impostazione usando PowerShell, vedere Configurare il [consenso del proprietario del gruppo alle app che accedono ai dati del gruppo](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Impostazioni nell'interfaccia di amministrazione di Microsoft Teams

Oltre alle impostazioni in Azure AD, le [impostazioni dell'app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings) nella pagina [Manage Apps](manage-apps.md) , indipendentemente dal fatto che un'app sia bloccata o consentita nella pagina [Gestisci](manage-apps.md#allow-and-block-apps) app, e i [criteri di autorizzazione dell'app](teams-app-permission-policies.md) assegnati al proprietario del team determinano se il proprietario del team può concedere il consenso.

> [!IMPORTANT]
> La modifica di queste impostazioni non influisce sull'accesso ai dati per le app a cui è già stato concesso il consenso. Ad esempio, se si disabilitano le app di terze parti a livello di organizzazione o se si bloccano app specifiche per evitare che i proprietari del team diano il consenso, queste modifiche non rimuovono l'accesso ai dati già concesso.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Impostazione "Consenti app di terze parti" nelle impostazioni dell'app a livello di organizzazione

Questa impostazione dell'app a livello di organizzazione controlla se gli utenti possono usare app di terze parti. Questa impostazione deve essere attivata per consentire ai proprietari del team di fornire il consenso. Per gestire questa impostazione, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Teams Apps**  >  **Manage Apps**, quindi fai clic su **impostazioni dell'app a livello di organizzazione**.
2. In **app di terze parti**disattivare o attivare **Consenti app**di terze parti.

    ![Screenshot dell'impostazione "Consenti app di terze parti in teams"](media/resource-specific-consent-org-wide-setting.png)

Possono essere necessarie fino a 24 ore prima che le modifiche diventino effettive.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Consentire o bloccare l'app a livello di organizzazione

Quando blocchi o Consenti un'app nella pagina [Gestisci](manage-apps.md#allow-and-block-apps) app, questa app è bloccata o consentita per tutti gli utenti dell'organizzazione. I proprietari del team possono concedere il consenso a un'app solo se l'app è consentita. Per consentire o bloccare un'app a livello di organizzazione, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.
2. Nella pagina Gestisci app selezionare l'app e quindi fare clic su **blocca** per bloccarla o fare clic su **Consenti** per consentirla.

    ![Screenshot delle app bloccate nelle impostazioni a livello di organizzazione](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Criteri di autorizzazione delle app assegnati al proprietario del team

I proprietari del team possono concedere solo il consenso alle app che il criterio di autorizzazione dell'app consente loro di eseguire. Per visualizzare e gestire i criteri di autorizzazione delle app assegnati a un proprietario del team, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**.
2. Fare doppio clic sul nome visualizzato del proprietario del team e quindi fare clic su **criteri**.
3. I criteri assegnati al proprietario del team sono elencati in **criteri di autorizzazione**per le app.
    - Per assegnare un criterio diverso, fare clic su **modifica**e quindi selezionare il criterio che si vuole assegnare.
    - Per modificare le impostazioni dei criteri assegnati al proprietario del team, fare clic sul nome del criterio e quindi apportare le modifiche desiderate.  

## <a name="uploading-custom-apps"></a>Caricamento di app personalizzate

Quando si carica un'app personalizzata (nota anche come sideload) che usa il consenso specifico delle risorse, l'app deve provenire dal tenant in cui è installato. In altre parole, la registrazione dell'app Azure AD deve essere di questo tenant. Gli amministratori globali sono esentati da questa restrizione e possono caricare app personalizzate da qualsiasi tenant, direttamente in un team (sideload) o nel catalogo dell'app tenant.

## <a name="related-topics"></a>Argomenti correlati

- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
