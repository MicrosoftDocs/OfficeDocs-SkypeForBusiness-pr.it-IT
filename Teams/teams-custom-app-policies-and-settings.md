---
title: Gestire impostazioni e criteri delle app personalizzati
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come gestire impostazioni e criteri di app personalizzati per controllare chi all'interno dell'organizzazione può caricare app personalizzate in Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 4e9863508d7b10c76ed29bfcb0fec79ca7a33dc5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821006"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gestire impostazioni e criteri delle app personalizzati in Microsoft Teams

> [!NOTE]
> Per usare App Studio, vedi Inizia sulla piattaforma Microsoft Teams con [C#/.NET](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) e App Studio L'ultimo passaggio non funziona ancora, quindi dovrai scaricare il zip e installarlo nel modo precedente in Carica un pacchetto app in [Microsoft Teams.](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)

Gli amministratori possono usare impostazioni e criteri personalizzati per le app per controllare chi all'interno dell'organizzazione può caricare app personalizzate in Microsoft Teams. Gli amministratori decidono quali utenti possono caricare app personalizzate e gli amministratori e i proprietari del team possono determinare se specifici team dell'organizzazione consentono l'aggiunta di app personalizzate.  Dopo aver modificato i criteri dell'app personalizzati, l'applicazione delle modifiche può richiedere alcune ore. Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.

## <a name="overview-of-custom-apps"></a>Panoramica delle app personalizzate

Gli utenti possono aggiungere un'app personalizzata a Teams caricando un pacchetto dell'app (in un file CON ESTENSIONE ZIP) direttamente in un team o nel contesto personale. Questo è diverso dal modo in cui le app vengono aggiunte tramite l'app store di Teams. L'aggiunta di un'app personalizzata caricando un pacchetto dell'app, noto anche come sideload, consente di testare un'app in fase di sviluppo, prima che sia pronta per essere distribuita. Consente anche di creare un'app solo per uso interno e condividerla con il team senza inviarla al catalogo app di Teams nell'App Store di Teams.

![Screenshot che mostra l'opzione per caricare un'app personalizzata nell'App Store](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Criteri e impostazioni delle app personalizzati

Tre componenti determinano se un utente può caricare un'app personalizzata in un team, per avere un controllo capillare su chi può aggiungere app personalizzate a un team e a quali app personalizzate dei team è possibile aggiungere:

- [Criteri per le app personalizzate dell'utente](#user-custom-app-policy)
- [Impostazione dell'app personalizzata del team](#team-custom-app-setting)
- [Impostazione dell'app personalizzata a livello di organizzazione](#org-wide-custom-app-setting)

Queste impostazioni non influiscono sulla possibilità di bloccare app di terze parti.  

### <a name="user-custom-app-policy"></a>Criteri per le app personalizzate dell'utente

Come parte dei criteri di configurazione delle [app,](teams-app-setup-policies.md)gli amministratori possono usare un'impostazione dei **criteri,** Carica app personalizzate, per controllare se un utente può caricare app personalizzate in Teams.
 
Se questa impostazione è disattivata:

- L'utente non può caricare un'app personalizzata in alcun team dell'organizzazione o nel contesto personale.
- L'utente può interagire con le app personalizzate, a seconda dell'impostazione dell'app personalizzata a livello di organizzazione.

Se questa impostazione è attivata:

- L'utente può caricare app personalizzate nei team che lo consentono e in team di cui sono proprietari, a seconda dell'impostazione dell'app personalizzata a livello di organizzazione.
- L'utente può caricare app personalizzate nel contesto personale. 
- L'utente può interagire con le app personalizzate, a seconda dell'impostazione dell'app personalizzata a livello di organizzazione.

È possibile modificare le impostazioni nel criterio di configurazione globale delle app per includere le app desiderate. Se si vuole personalizzare Teams per diversi gruppi di utenti dell'organizzazione, creare e assegnare uno o più criteri di configurazione delle app personalizzati.

#### <a name="set-a-user-custom-app-policy"></a>Impostare criteri per le app personalizzati dell'utente

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a Criteri di configurazione **delle app di**  >  **Teams.**
2. Fare clic su **Aggiungi**.
3. Attivare o disattivare Carica **app personalizzate.**
4. Scegliere le altre impostazioni desiderate per il criterio.
5. Fare clic su **Salva**.

### <a name="team-custom-app-setting"></a>Impostazione dell'app personalizzata del team

Amministratori e proprietari del team possono controllare se un team consente l'aggiunta di app personalizzate. Questa impostazione, **Consenti ai** membri di caricare app personalizzate, insieme ai criteri per le app personalizzate di un utente determina chi può aggiungere app personalizzate a un determinato team.
 
Se questa impostazione è disattivata:

- I proprietari dei team possono aggiungere app personalizzate, se i criteri delle app personalizzati lo consentono.
- I membri del team che non sono proprietari di team non possono aggiungere app personalizzate al team.

Se questa impostazione è attivata:

- I proprietari dei team possono aggiungere app personalizzate, se i criteri delle app personalizzati lo consentono.
- I membri del team che non sono proprietari del team possono aggiungere app personalizzate, se i criteri delle app personalizzate lo consentono.

#### <a name="configure-the-team-custom-app-setting"></a>Configurare l'impostazione dell'app personalizzata del team

1. In Teams, vai al team, fai clic su **Altre opzioni ̇ ̇ ̇** Gestisci  >  **team.**
2. Fare **clic su** Impostazioni e quindi espandere Autorizzazioni **membro.**
3. Selezionare o deselezionare la **casella di controllo Consenti ai membri di caricare app** personalizzate.

    ![Screenshot che mostra l'impostazione dell'app personalizzata del team](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Impostazione dell'app personalizzata a livello di organizzazione

**L'impostazione** Consenti interazione con app personalizzate [](manage-apps.md) a livello di organizzazione nella pagina Gestisci app si applica a tutti gli utenti dell'organizzazione e determina se possono caricare o interagire con le app personalizzate. Questa impostazione funge da interruttore di attivazione/disattivare master per le impostazioni dei criteri delle app personalizzate dell'utente e del team. È destinato a fungere da interruttore master di attivazione/disattivare durante gli eventi di sicurezza. Di conseguenza, le impostazioni dei criteri per le app personalizzate di utenti e team non verranno applicate a meno che l'impostazione dell'app personalizzata a livello di organizzazione non sia abilitata anche se sono abilitate le impostazioni dei criteri per le app personalizzate di utenti e team.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurare l'impostazione dell'app personalizzata a livello di organizzazione

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams.
2. Fare clic **su Impostazioni app a livello di organizzazione.**
3. In **App personalizzate** attivare o disattivare Consenti interazione con le app **personalizzate.**

    ![Screenshot che mostra le impostazioni dell'app personalizzata a livello di organizzazione](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Come funzionano insieme le impostazioni e i criteri delle app personalizzate

Questa tabella riepiloga i criteri e le impostazioni delle app personalizzati, il modo in cui funzionano insieme e l'effetto combinato sul controllo di chi nell'organizzazione può caricare app personalizzate in Teams.

Si supponga, ad esempio, di volere consentire solo ai proprietari dei team di caricare app personalizzate in team specifici. Impostare quanto segue:
- Attivare **l'impostazione Consenti interazione con app** personalizzate nell'interfaccia di amministrazione di Microsoft Teams.
- Disattiva Consenti ai **membri di caricare app personalizzate** per ogni team per cui vuoi limitare l'accesso.
- Creare e assegnare criteri di configurazione delle app  personalizzati nell'interfaccia di amministrazione di Microsoft Teams con l'opzione Carica app personalizzate attivata e assegnarla ai proprietari del team.

|Impostazione dell'app personalizzata a livello di organizzazione |Impostazione dell'app personalizzata del team |Criteri per le app personalizzate dell'utente |Effetto  |
|---------|---------|---------|---------|
| Disattivato    | Disattivato    | Disattivato     |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno tranne un amministratore di servizio di Teams o un amministratore globale. È possibile usare PowerShell per rimuovere l'app personalizzata.   |
| Disattivato     | Disattivato     | Attivato        |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno tranne un amministratore di servizio di Teams o un amministratore globale. È possibile usare PowerShell per rimuovere l'app personalizzata.         |
| Disattivato    | Attivato        | Disattivato        |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno tranne un amministratore di servizio di Teams o un amministratore globale. È possibile usare Windows PowerShell per eliminare app personalizzate.         |
| Disattivato    | Attivato      | Attivato       |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno tranne un amministratore di servizio di Teams o un amministratore globale. È possibile usare PowerShell per rimuovere l'app personalizzata.         |
| Attivato    | Disattivato       | Disattivato         |  L'utente non può caricare app personalizzate.      |
| Attivato     | Disattivato       | Attivato         | Se l'utente è proprietario di un team, può caricare app personalizzate nel team. Se l'utente non è proprietario di un team, non può caricare app personalizzate nel team. L'utente può caricare app personalizzate nel contesto personale.     |
| Attivato     | Attivato     | Disattivato         | L'utente non può caricare app personalizzate.       |
| Attivato    | Attivato        | Attivato        | L'utente può caricare app personalizzate nel team, indipendentemente dal fatto che l'utente sia proprietario del team. L'utente può caricare app personalizzate nel contesto personale.       |

## <a name="related-topics"></a>Argomenti correlati
 
[Impostazioni di amministrazione per le app in Teams](admin-settings.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)