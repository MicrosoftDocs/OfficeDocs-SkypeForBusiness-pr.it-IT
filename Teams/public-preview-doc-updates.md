---
title: Anteprima pubblica in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about the public preview in Microsoft Teams. Try out new features and provide feedback.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: ffdd34d8a36726d96bc44ae766e91ca6ae77280b
ms.sourcegitcommit: b535a70df5bc842f597889582df3eb86371f8139
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2022
ms.locfileid: "68869587"
---
# <a name="microsoft-teams-public-preview"></a>Anteprima pubblica in Microsoft Teams

> [!NOTE] 
> Le funzionalità incluse nell'anteprima potrebbero non essere complete e potrebbero subire modifiche prima di essere disponibili nella versione pubblica. Sono disponibili solo a scopo di valutazione ed esplorazione. Le funzionalità di anteprima non sono supportate in Office 365 Government Community Cloud (GCC).

Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.

Per un elenco delle funzionalità disponibili nell'anteprima pubblica di Teams, visitare [le note tecniche di Microsoft Teams Public Preview](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview), [le note sulla versione per le funzionalità di Amministrazione di Teams](/OfficeUpdates/teams-admin) e [le note sulla versione per Il canale corrente di Office (anteprima).](/officeupdates/current-channel-preview)For a list of what's available in the Teams public preview, visit Microsoft Teams Public Preview tech notes, release notes for Teams Amministrazione Features, and Release Notes for Office Current Channel (Preview).

## <a name="set-the-update-policy"></a>Impostare i criteri di aggiornamento

Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy. Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app. You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users. The policy needs to be assigned to specific users because it doesn't over-write the global policy.

1. Accedere all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).

2. Selezionare **Teams** > **Criteri di aggiornamento di Teams**.

1. Selezionare **Aggiungi** per creare un nuovo criterio o selezionare un criterio esistente per aprire **Aggiorna criterio**.

2. Assegnare un nome al criterio di aggiornamento, aggiungere una descrizione e attivare **Mostra funzionalità di anteprima**.

   -   **Segui anteprima Office** (impostazione predefinita)
       - Questa nuova opzione predefinita abiliterà automaticamente le funzionalità dell'anteprima pubblica di Teams per qualsiasi utente registrato nel Canale corrente di Office (anteprima). 
       - Non sono necessarie altre azioni da parte dell'utente finale.
   -   **Abilitato**
       - Abilitato: questa opzione abilita l'anteprima pubblica di Teams indipendentemente dal fatto che un utente sia o meno registrato nel Canale corrente di Office (Anteprima). 
       - L'utente finale deve anche acconsentire esplicitamente all'anteprima pubblica di Teams nella sua app Teams.

   > [!NOTE]  
   > Per gli utenti esistenti nell'anteprima pubblica di Teams che NON si trovano nel **Canale corrente (Anteprima)**, gli amministratori IT devono passare dall'impostazione predefinita **Segui Office Preview** ad **Abilitata**.
 
   - **Non abilitato** 
     - Le funzionalità di anteprima pubblica di Teams non saranno disponibili per gli utenti finali.

    ![mostra la finestra di dialogo delle impostazioni di anteprima.](media/public-preview-policy.png)  

È anche possibile impostare il criterio tramite PowerShell usando il cmdlet `Set-CsTeamsUpdateManagementPolicy` con il parametro `-AllowPublicPreview`.

## <a name="enable-public-preview"></a>Abilitare l'anteprima pubblica

Per abilitare l'anteprima pubblica su un client desktop o Web, è necessario completare la procedura seguente:

1. Selezionare i tre puntini a sinistra del profilo per visualizzare il menu di Teams.
2. Selezionare **Informazioni** > **Anteprima pubblica**.
3. Selezionare **Passa all'anteprima pubblica**.

> [!NOTE]  
> Questa opzione è disponibile solo quando **Mostra funzionalità di anteprima** è impostato su **Abilitato**.

### <a name="public-preview-for-microsoft-teams-rooms-on-windows"></a>Anteprima pubblica per Microsoft Teams Rooms in Windows

L'anteprima pubblica è disattivata per impostazione predefinita. Quando l'anteprima pubblica è attivata, gli utenti finali hanno accesso alle funzionalità in anteprima pubblica in Teams Rooms abilitate. Per attivare l'anteprima pubblica, aggiungere ```<EnablePublicPreview>True</EnablePublicPreview>``` al file di configurazione XML.

È consigliabile registrare 5-10 dispositivi nell'anteprima pubblica. 

Tutte le funzionalità di anteprima pubblica vengono annunciate in [Anteprima pubblica di Microsoft Teams - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)

## <a name="teams-now-follows-office-preview-users"></a>Ora Teams segue gli utenti di Office Preview

Il nuovo criterio globale predefinito di **Segui Anteprima Office** consentirà agli utenti di essere automaticamente nel canale anteprima pubblica di Teams se si trovano nel Canale corrente (Anteprima) per il client di Office 365 in Windows e Mac.

Microsoft Office continuerà a ricevere gli aggiornamenti dal Canale corrente (Anteprima) e il client di Teams riceverà gli aggiornamenti tramite il canale Anteprima pubblica. Questo criterio NON cambierà i canali di Office in base ai canali di Teams. 

**Come mantenere gli utenti dell'anteprima di Teams esistenti che NON usano il Canale corrente di Office (Anteprima)?**

Per gli utenti esistenti ai quali è stato permesso di acconsentire esplicitamente o rifiutare esplicitamente l'anteprima pubblica di Teams e che vogliono mantenere tale impostazione nella sua forma attuale, è necessario passare dalla nuova impostazione predefinita **Segui Office Preview** ad **Abilitato** (vedere [Impostare i criteri di aggiornamento](#set-the-update-policy))

**Come rifiutare esplicitamente questa impostazione?**

È possibile disabilitare l'impostazione dall'interfaccia di amministrazione di Teams in **Segui Office Preview** selezionando **Non abilitato** (vedere [Impostar i criteri di aggiornamento](#set-the-update-policy))

## <a name="related-topics"></a>Argomenti correlati

[Anteprima pubblica per sviluppatori](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
