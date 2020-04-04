---
title: Gestire i criteri e le impostazioni dell'app personalizzata
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come gestire i criteri e le impostazioni delle app personalizzate per controllare chi nell'organizzazione può caricare app personalizzate in Microsoft teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 7c3c7958994c50e1ae0e90ed13437601dabc0688
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140657"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gestire i criteri e le impostazioni dell'app personalizzata in Microsoft Teams

> [!NOTE]
> Per usare app Studio vedere [Introduzione alla piattaforma Microsoft teams con C#/.NET e App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) l'ultimo passaggio non funziona ancora, quindi è necessario scaricare il zip e installarlo alla vecchia maniera in [caricare un pacchetto dell'app in Microsoft teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).

Come amministratore, puoi usare le impostazioni e i criteri delle app personalizzati per controllare chi nell'organizzazione può caricare app personalizzate in Microsoft teams. Gli amministratori decidono quali utenti possono caricare app personalizzate e gli amministratori e i proprietari del team possono determinare se specifici team dell'organizzazione consentano l'aggiunta di app personalizzate.  Dopo aver modificato i criteri delle app personalizzate, è possibile che siano necessarie fino a 24 ore affinché le modifiche abbiano effetto. Per gestire questi criteri è necessario essere un amministratore globale o un servizio di teams.

## <a name="overview-of-custom-apps"></a>Panoramica delle app personalizzate

Gli utenti possono aggiungere un'app personalizzata ai team caricando un pacchetto dell'app (in un file zip) direttamente in un team o nel contesto personale. Questo è diverso dal modo in cui le app vengono aggiunte all'app store teams. L'aggiunta di un'app personalizzata caricando un pacchetto dell'app, noto anche come sideload, consente di testare un'app mentre è in fase di sviluppo, prima che sia pronta per essere ampiamente distribuita. Consente inoltre di creare un'app solo per uso interno e condividerla con il team senza inviarla al catalogo app teams nell'app store teams.

![Screenshot che mostra l'opzione carica un'app personalizzata nell'App Store](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Criteri e impostazioni delle app personalizzate

Tre componenti determinano se un utente può caricare un'app personalizzata in un team, dandoti il controllo granulare su chi può aggiungere app personalizzate a un team e su quali possono essere aggiunte le app personalizzate di teams:

- [Criteri delle app personalizzate per l'utente](#user-custom-app-policy)
- [Impostazione dell'app personalizzata del team](#team-custom-app-setting)
- [Impostazione dell'app personalizzata a livello di organizzazione](#org-wide-custom-app-setting)

Queste impostazioni non influiscono sulla possibilità di bloccare le app di terze parti.  

### <a name="user-custom-app-policy"></a>Criteri delle app personalizzate per l'utente

Come parte dei [criteri di configurazione delle app](teams-app-setup-policies.md), gli amministratori possono usare un'impostazione di criteri, **caricare app personalizzate**per controllare se un utente può caricare app personalizzate in teams.
 
Se questa impostazione è disattivata:

- L'utente non può caricare un'app personalizzata in un team dell'organizzazione o nel contesto personale.
- L'utente può interagire con le app personalizzate, a seconda dell'impostazione dell'app personalizzata a livello di organizzazione.

Se questa impostazione è attivata:

- L'utente può caricare app personalizzate in team che lo permettono e ai team per cui sono proprietari, a seconda dell'impostazione dell'app personalizzata a livello di organizzazione.
- L'utente può caricare app personalizzate nel contesto personale. 
- L'utente può interagire con le app personalizzate, a seconda dell'impostazione dell'app personalizzata a livello di organizzazione.

Per includere le app desiderate, è possibile modificare le impostazioni dei criteri di configurazione dell'app globale. Per personalizzare i team per diversi gruppi di utenti dell'organizzazione, creare e assegnare uno o più criteri di configurazione dell'app personalizzati.

#### <a name="set-a-user-custom-app-policy"></a>Impostare criteri delle app personalizzate per l'utente

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di configurazione**delle **app teams**.
2. Fare clic su **Aggiungi**.
3. Attivare o disattivare **carica app personalizzate**.
4. Scegliere le altre impostazioni desiderate per il criterio.
5. Fare clic su **Salva**.

### <a name="team-custom-app-setting"></a>Impostazione dell'app personalizzata del team

Gli amministratori e i proprietari del team possono controllare se un team consente l'aggiunta di app personalizzate. Questa impostazione **consente ai membri di caricare app personalizzate**, insieme ai criteri delle app personalizzate di un utente, che determina chi può aggiungere app personalizzate a un team specifico.
 
Se questa impostazione è disattivata:

- I proprietari del team possono aggiungere app personalizzate, se il loro criterio per le app personalizzate lo consente.
- I membri del team che non sono proprietari del team non possono aggiungere app personalizzate al team.

Se questa impostazione è attivata:

- I proprietari del team possono aggiungere app personalizzate, se il loro criterio di app personalizzato lo consente.
- I membri del team che non sono proprietari del team possono aggiungere app personalizzate, se i loro criteri di app personalizzati lo consentono.

#### <a name="configure-the-team-custom-app-setting"></a>Configurare l'impostazione dell'app personalizzata del team

1. In teams, vai al team, fai clic su **altre opzioni ˙ ˙ ˙** > **Manage team**.
2. Fare clic su **Impostazioni**e quindi su Espandi autorizzazioni per i **membri**.
3. Selezionare o deselezionare la casella **di controllo Consenti ai membri di caricare app personalizzate** .

    ![Schermata che mostra l'impostazione dell'app personalizzata del team](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Impostazione dell'app personalizzata a livello di organizzazione

L'impostazione **Consenti l'interazione con** le app personalizzate per l'intera organizzazione, nella pagina [Manage Apps](manage-apps.md) si applica a tutti gli utenti dell'azienda e determina se possono caricare o interagire con le app personalizzate. Questa impostazione esegue l'override dei criteri e delle impostazioni dell'app utente e team personalizzati. È progettato per fungere da interruttore di attivazione/disattivazione master durante gli eventi di sicurezza.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurare l'impostazione dell'app personalizzata a livello di organizzazione

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle >  **app teams****Manage Apps**.
2. Fare clic su **impostazioni app a livello di organizzazione**.
3. In **app personalizzate**attivare o disattivare **Consenti l'interazione con le app personalizzate**.

    ![Schermata che mostra le impostazioni dell'app personalizzate a livello di organizzazione](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Funzionamento dei criteri e delle impostazioni delle app personalizzate

Questa tabella riepiloga i criteri e le impostazioni delle app personalizzate, il modo in cui collaborano e il loro effetto combinato sul controllo di chi nell'organizzazione può caricare app personalizzate in teams.

Ad esempio, supponiamo che tu voglia consentire solo ai proprietari del team di caricare app personalizzate in team specifici. Impostare le operazioni seguenti:
- Attivare l'impostazione **Consenti interazione con le app personalizzate** nell'interfaccia di amministrazione di Microsoft teams.
- Disattivare i **membri Consenti per caricare le app personalizzate** per ogni team a cui si vuole limitare l'accesso.
- Creare e assegnare un criterio di configurazione dell'app personalizzata nell'interfaccia di amministrazione di Microsoft teams con l'impostazione **carica app personalizzate** attivata e assegnarla ai proprietari del team.

|Impostazione dell'app personalizzata a livello di organizzazione |Impostazione dell'app personalizzata del team |Criteri delle app personalizzate per l'utente |Effetto  |
|---------|---------|---------|---------|
| Disattivare    | Disattivare    | Disattivare     |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno. Puoi usare PowerShell per rimuovere l'app personalizzata.   |
| Disattivare     | Disattivare     | Nella        |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno. Puoi usare PowerShell per rimuovere l'app personalizzata.         |
| Disattivare    | Nella        | Disattivare        |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno. Puoi usare Windows PowerShell per eliminare app personalizzate.         |
| Disattivare    | Nella      | Nella       |L'interazione con tutte le app personalizzate è bloccata per l'organizzazione. Le app personalizzate non possono essere caricate da nessuno. Puoi usare PowerShell per rimuovere l'app personalizzata.         |
| Nella    | Disattivare       | Disattivare         |  L'utente non può caricare app personalizzate.      |
| Nella     | Disattivare       | Nella         | Se l'utente è un proprietario del team, può caricare le app personalizzate nel team. Se l'utente non è un proprietario del team, non può caricare le app personalizzate nel team. L'utente può caricare app personalizzate nel contesto personale.     |
| Nella     | Nella     | Disattivare         | L'utente non può caricare app personalizzate.       |
| Nella    | Nella        | Nella        | L'utente può caricare app personalizzate nel team, indipendentemente dal fatto che l'utente sia un proprietario del team. L'utente può caricare app personalizzate nel contesto personale.       |

 ## <a name="related-topics"></a>Argomenti correlati
 
- [Impostazioni di amministrazione per le app in Teams](admin-settings.md)
