---
title: Gestire l'accesso anonimo dei partecipanti alle riunioni di Teams (amministratori IT)
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Per i professionisti IT - Scopri come funziona la partecipazione anonima alle riunioni in Microsoft Teams.
ms.openlocfilehash: fe4dbec2bc606838bd5cafbaec5ef9d9ecdd8a88
ms.sourcegitcommit: 1f4a0b7cf03f63438bb37668d053853494c92168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2023
ms.locfileid: "69948688"
---
# <a name="manage-anonymous-participant-access-to-teams-meetings-it-admins"></a>Gestire l'accesso anonimo dei partecipanti alle riunioni di Teams (amministratori IT)

I partecipanti anonimi alle riunioni ospitate dall'organizzazione sono persone che non possono essere verificate. Ad esempio:

- Persone che non hanno eseguito l'accesso a Teams con un account aziendale o dell'istituto di istruzione 
- Persone da organizzazioni non attendibili (configurate con [accesso esterno](manage-external-access.md)) e da organizzazioni attendibili ma che non sono considerate attendibili per l'organizzazione.

La partecipazione a una riunione anonima è controllata da un'impostazione a livello di organizzazione e da criteri a livello di utente. Per partecipare a una riunione anonima al lavoro:
- L'impostazione **Utenti anonimi può partecipare a una riunione** di Teams (a livello di organizzazione) deve essere attivata.
- All'organizzatore della riunione deve essere assegnato un criterio di riunione di Teams in cui l'opzione **Consenti alle persone anonime di partecipare a un controllo della riunione** è attivata.

La partecipazione anonima è attivata per impostazione predefinita per l'organizzazione e nei criteri predefiniti per le riunioni globali.

Si noti che se è abilitata la partecipazione anonima, i criteri di sala di attesa influiscono sul modo in cui i partecipanti anonimi partecipano alle riunioni. Per informazioni dettagliate, vedere [Controllare chi può ignorare la sala di attesa della riunione in Microsoft Teams](who-can-bypass-meeting-lobby.md).

#### <a name="meetings-with-trusted-organizations"></a>Riunioni con organizzazioni attendibili

Quando si configurano organizzazioni attendibili per le riunioni esterne e la chat, i partecipanti alle riunioni di tali organizzazioni possono essere considerati anonimi se le impostazioni di accesso esterno non sono configurate correttamente per entrambe le organizzazioni. Per informazioni dettagliate, vedere [Organizzazioni attendibili per le riunioni esterne e la chat](manage-external-access.md).

## <a name="manage-anonymous-meeting-join-for-the-organization"></a>Gestire l'accesso a una riunione anonima per l'organizzazione

L'impostazione di partecipazione a una riunione anonima a livello di organizzazione deve essere attivata per consentire a tutti gli utenti dell'organizzazione di creare riunioni che consentano partecipanti anonimi.

> [!Important]
> L'impostazione **Partecipanti anonimi che possono partecipare a una riunione** a livello di organizzazione verrà rimossa in futuro. È consigliabile lasciare **attivata** questa impostazione e usare il controllo **criterio Consenti a utenti anonimi di partecipare a una riunione** a livello di utente per consentire o impedire l'accesso anonimo alla riunione.

Per configurare l'accesso anonimo a una riunione per l'organizzazione
1. Passare all'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com).

1. Nel riquadro di spostamento sinistro, andare a **Riunioni** > **Impostazioni di riunione**.

1. In **Partecipanti** impostare **i partecipanti anonimi che possono partecipare a una riunione** su **Attivato** (consigliato) o **Disattivato**.

    ![Screenshot delle impostazioni dei partecipanti per le riunioni nell'interfaccia di amministrazione.](media/meeting-settings-participants.png "Screenshot delle impostazioni dei partecipanti per le riunioni di Teams nell'interfaccia di amministrazione di Microsoft Teams")

1. Selezionare **Salva**.

## <a name="manage-which-meeting-organizers-can-allow-anonymous-meeting-join"></a>Gestire gli organizzatori della riunione che possono consentire l'accesso anonimo alla riunione

È possibile controllare quali utenti o gruppi possono ospitare riunioni che includono partecipanti anonimi. A questo scopo, assegnare criteri di riunione con partecipazione a una riunione anonima attivata a ogni organizzatore della riunione che deve ospitare riunioni con partecipanti anonimi.

Per configurare l'accesso anonimo a una riunione per specifici organizzatori di riunioni
1. Passare all'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com).

1. Nel riquadro di spostamento sinistro passare a **Criteri****riunione riunioni** > .

1. Selezionare il criterio da modificare.

1. Impostare **Consenti alle persone anonime di partecipare a una riunione** su **Attivato**.

1. Selezionare **Salva**.

L'applicazione delle modifiche ai criteri delle riunioni può richiedere fino a 24 ore.

## <a name="configure-anonymous-meeting-join-using-powershell"></a>Configurare la partecipazione a una riunione anonima con PowerShell

È possibile controllare se i partecipanti anonimi possono partecipare alle riunioni usando:

- Il `-DisableAnonymousJoin` parametro in [Set-CsTeamsMeetingConfiguration per configurare](/powershell/module/skype/set-csteamsmeetingconfiguration) l'impostazione a livello di organizzazione. È consigliabile lasciare questo set su False e usare Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting per controllare l'aggiunta anonima a livello di utente o gruppo.
- Parametro `-AllowAnonymousUsersToJoinMeeting` in [Set-CsTeamsMeetingPolicy per configurare](/powershell/module/skype/set-csteamsmeetingpolicy) un criterio riunione a livello utente

Per consentire ai partecipanti anonimi di partecipare alle riunioni, è necessario configurare entrambi per consentire l'accesso anonimo impostando i valori seguenti:

- `Set-CsTeamsMeetingConfiguration -DisableAnonymousJoin` impostato su **$false**
- `Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting` impostato su **$true** per gli organizzatori della riunione interessati

## <a name="block-anonymous-join-for-specific-client-types"></a>Bloccare l'aggiunta anonima per tipi di client specifici

Quando i partecipanti anonimi sono autorizzati a partecipare alle riunioni, possono usare il client di Teams o un client personalizzato creato usando [Servizi di comunicazione di Azure](/azure/communication-services/). 

Gli amministratori possono bloccare uno di questi tipi di client utilizzando il `-BlockedAnonymousJoinClientTypes` parametro in [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy#-blockedanonymousjoinclienttypes).

## <a name="anonymous-participants-meeting-experience"></a>Esperienza di riunione dei partecipanti anonimi

I partecipanti anonimi non hanno tutte le stesse funzionalità degli altri partecipanti alla riunione. Ad esempio, partecipanti anonimi:

- Non è possibile accedere alla chat della riunione prima e dopo la riunione
- Non hanno accesso alle schede profilo (schede profilo in Microsoft 365 - supporto tecnico Microsoft)

### <a name="how-anonymous-participants-interact-with-apps-in-meetings"></a>In che modo i partecipanti anonimi interagiscono con le app durante le riunioni

Per impostazione predefinita, è abilitata l'impostazione che consente ai partecipanti anonimi di interagire con le app nelle riunioni.

Per configurare l'accesso all'app per i partecipanti anonimi alla riunione

1. Passare all'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com).

1. Nel riquadro di spostamento sinistro, andare a **Riunioni** > **Impostazioni di riunione**.

1. In **Partecipanti** impostare  **Partecipanti anonimi che possono interagire con le app nelle riunioni** su **Attivato** o **Disattivato**.

È anche possibile controllare questa operazione con PowerShell usando `Set-CsTeamsMeetingConfiguration -DisableAppInteractionForAnonymousUsers`.

I partecipanti anonimi ereditano i criteri di autorizzazione per le app Teams globali (predefinite a livello di organizzazione). I partecipanti anonimi possono interagire con le app nelle riunioni di Teams, a condizione che l'app sia abilitata in tale criterio e **che i partecipanti anonimi possano interagire con le app nelle riunioni** sia **attivata**.

Si noti che i partecipanti anonimi possono interagire solo con le app già disponibili in una riunione e non possono acquisire e/o gestire queste app.

## <a name="related-topics"></a>Argomenti correlati

[Partecipare a una riunione senza un account di Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Uso dell'interfaccia di amministrazione di Microsoft Teams per configurare i criteri a livello di organizzazione](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[I partecipanti esterni ricevono "Accedi a Teams per partecipare o contattare l'organizzatore della riunione"](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)

[Assegnare criteri in Teams- Guida introduttiva](policy-assignment-overview.md)