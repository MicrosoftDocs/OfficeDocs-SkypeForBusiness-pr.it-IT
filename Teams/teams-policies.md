---
title: Gestire i criteri dei canali in Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jastark
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
- chat-teams-channels-revamp
description: Informazioni su come usare e gestire i criteri dei canali dei team nell'organizzazione per controllare le operazioni che gli utenti possono eseguire in team e canali.
ms.openlocfilehash: 1223f191550675d5edd7b99a1cf9820fa14c9992
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198558"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Gestire i criteri dei canali in Microsoft Teams

Gli amministratori possono usare i criteri in Microsoft Teams per controllare cosa possono fare gli utenti dell'organizzazione in team e canali. Ad esempio, è possibile specificare se gli utenti sono autorizzati a creare canali privati o condivisi.

È possibile gestire i criteri dei team passando ai **criteri di Teams**  >  nell'interfaccia di amministrazione di Microsoft Teams. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.

È possibile modificare il criterio globale o creare e assegnare criteri personalizzati. Dopo aver modificato il criterio globale o assegnato un criterio, potrebbero essere necessarie 24 ore prima che le modifiche vengano applicate.

## <a name="channel-policies"></a>Criteri per i canali

Per i canali dei team sono disponibili i criteri seguenti:

|Criterio|Descrizione|
|:-----|:----------|
|**Creare canali privati**|Quando **attivato**, i proprietari e i membri del team possono creare canali privati. I proprietari del team possono controllare se i membri possono creare canali privati in ogni team.|
|**Creare canali condivisi**|Quando **attivato**, i proprietari del team possono creare canali condivisi. Le app di Teams disponibili per l'organizzazione sono disponibili anche nei canali condivisi.|
|**Invitare utenti esterni a canali condivisi**|Quando **attivato**, i proprietari e i membri dei canali condivisi possono invitare partecipanti esterni da organizzazioni in cui è stata configurata un'attendibilità tra organizzazioni. I criteri di Teams per l'organizzazione si applicano a questi canali.|
|**Partecipare a canali condivisi esterni**|Quando **attivato**, gli utenti possono partecipare ai canali condivisi creati da altre organizzazioni in cui è stata configurata un'attendibilità tra organizzazioni. I criteri di Teams per l'altra organizzazione si applicano a questi canali.|

## <a name="create-a-custom-teams-policy"></a>Creare criteri personalizzati per i team

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare a **Criteri di Teams** > .
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.

    ![Screenshot delle impostazioni dei criteri dei team.](media/teams-policies.png)
4. Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva**.

5. Fare clic su **Salva**.

## <a name="edit-a-teams-policy"></a>Modificare i criteri di un team

È possibile modificare i criteri globali o i criteri personalizzati creati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare a **Criteri di Teams** > .
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Assegnare criteri di team personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Argomenti correlati

[Gestire i siti e i siti dei canali connessi a Teams](/SharePoint/teams-connected-sites)

[Canali privati in Teams](private-channels.md)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
