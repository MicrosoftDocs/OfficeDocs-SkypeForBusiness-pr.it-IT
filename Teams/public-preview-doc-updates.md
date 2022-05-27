---
title: Anteprima pubblica in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
description: Informazioni sull'anteprima pubblica in Microsoft Teams. Provare le nuove funzionalità e fornire commenti e suggerimenti.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 49ea7fe244b46840e80bfa4093706d314c708dcb
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675068"
---
# <a name="microsoft-teams-public-preview"></a>Anteprima pubblica in Microsoft Teams

> [!NOTE] 
> Le funzionalità incluse nell'anteprima potrebbero non essere complete e potrebbero subire modifiche prima di essere disponibili nella versione pubblica. Sono disponibili solo a scopo di valutazione ed esplorazione. Le funzionalità di anteprima non sono supportate in Office 365 Government Community Cloud (GCC).

L'anteprima pubblica per Microsoft Teams offre accesso anticipato alle funzionalità non rilasciate in Teams. Le anteprime consentono di esplorare e testare le funzionalità imminenti. Microsoft è lieta di ricevere feedback sulle funzionalità presentate nelle anteprime pubbliche. L'anteprima pubblica è abilitata per gli utenti di Teams, pertanto non è necessario preoccuparsi per l'impatto sull'intera organizzazione.

Per un elenco delle funzionalità disponibili nell'anteprima pubblica di Teams, vedere le [note tecniche sull'anteprima pubblica di Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview), [note sulla versione per le funzionalità amministrative di Teams](/OfficeUpdates/teams-admin) e le [Novità di Teams](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).

## <a name="set-the-update-policy"></a>Impostare i criteri di aggiornamento

L'anteprima pubblica è abilitata per singolo utente e l'opzione per attivarla è controllata da un criterio amministrativo. I criteri di aggiornamento vengono usati per gestire gli utenti delle anteprime di Teams e Office che visualizzano le funzionalità non definitive o di anteprima nell'app di Teams. È possibile usare il criterio globale (impostazione predefinita a livello dell'organizzazione) e personalizzarlo oppure creare uno o più criteri personalizzati per gli utenti. Questo criterio deve essere assegnato a utenti specifici in quanto non sovrascrive il criterio globale.

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
