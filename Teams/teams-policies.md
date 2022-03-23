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
description: Informazioni su come usare e gestire i criteri dei canali di Teams nell'organizzazione per controllare le attività che gli utenti possono eseguire in team e canali.
ms.openlocfilehash: 5acac362485b1004e1db61229c437810fdbcbc6d
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711780"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Gestire i criteri dei canali in Microsoft Teams

Gli amministratori possono usare i criteri in Microsoft Teams controllare le attività che gli utenti dell'organizzazione possono eseguire in team e canali. Ad esempio, è possibile impostare se gli utenti sono autorizzati a creare canali privati o condivisi.

Per gestire i criteri dei team, accedere **Teams** >  **Teams criteri nell'Microsoft Teams** di amministrazione. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.

È possibile modificare i criteri globali o creare e assegnare criteri personalizzati. Dopo aver modificato i criteri globali o aver assegnato un criterio, l'applicazione delle modifiche potrebbe richiedere 24 ore.

## <a name="channel-policies"></a>Criteri per i canali

Per i canali dei team sono disponibili i criteri seguenti:

|Criterio|Descrizione|
|:-----|:----------|
|**Creare canali privati**|Se **l'è**, i proprietari e i membri del team possono creare canali privati. I proprietari del team possono controllare se i membri possono creare canali privati in ogni team.|
|**Creare canali condivisi**|Quando **è on**, i proprietari del team possono creare canali condivisi. Teams le app disponibili per l'organizzazione sono disponibili anche nei canali condivisi.|
|**Invitare utenti esterni a canali condivisi**|Quando **è questa** impostazione, i proprietari e i membri dei canali condivisi possono invitare partecipanti esterni da organizzazioni in cui è stato configurato un trust tra organizzazioni. Teams criteri per l'organizzazione si applicano a questi canali.|
|**Partecipare a canali condivisi esterni**|Quando **è on**, gli utenti possono partecipare a canali condivisi creati da altre organizzazioni in cui è stato configurato un trust tra organizzazioni. Teams criteri per l'altra organizzazione si applicano a questi canali.|

## <a name="create-a-custom-teams-policy"></a>Creare criteri di team personalizzati

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione **passare a** >  Teams **Teams criteri**.
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.

    ![Screenshot delle impostazioni dei criteri dei team.](media/teams-policies.png)
4. Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva**.

5. Fare clic su **Salva**.

## <a name="edit-a-teams-policy"></a>Modificare un criterio di Teams

È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione **passare a** >  Teams **Teams criteri**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Assegnare criteri di team personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Argomenti correlati

[Gestire Teams siti connessi e siti di canale](/SharePoint/teams-connected-sites)

[Canali privati in Teams](private-channels.md)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
