---
title: Gestire i criteri dei team in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri per i team dell'organizzazione per controllare gli utenti che possono eseguire in team e canali.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 9ed0bd3aadcde76835bb3d435429785ceaf562a2
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938145"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gestire i criteri dei team in Microsoft Teams

Come amministratore, puoi usare i criteri di teams in Microsoft teams per controllare gli utenti che possono eseguire in team e canali. Ad esempio, puoi impostare se gli utenti possono scoprire team privati nei risultati della ricerca e nella raccolta team e se gli utenti possono creare canali privati.

Per gestire i criteri dei team, è possibile **passare a**criteri teams teams nell'interfaccia di amministrazione di  >  **Teams policies** Microsoft teams. Puoi usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.

È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati. Dopo aver modificato il criterio globale o assegnato un criterio, è possibile che le modifiche abbiano effetto.

## <a name="create-a-custom-teams-policy"></a>Creare un criterio teams personalizzato

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a**  >  **criteri**teams teams.
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.

    ![Screenshot delle impostazioni dei criteri di Teams](media/teams-policies.png)
4. Scegliere le impostazioni desiderate:

- **Individuazione di team privati** (in anteprima privata)<a name="discoverteams"> </a> : attivare questa impostazione per consentire agli utenti di individuare team privati nei risultati della ricerca e nella raccolta team.
- **Creare canali privati**: <a name="createchannels"> </a>attivare questa impostazione per consentire agli utenti di creare canali privati.

5. Fare clic su **Salva**.

## <a name="edit-a-teams-policy"></a>Modificare un criterio Teams

È possibile modificare il criterio globale o i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a**  >  **criteri**teams teams.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Assegnare un criterio team personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Argomenti correlati

[Gestire l'individuazione di team privati in Teams](manage-discovery-of-private-teams.md)

[Canali privati in teams](private-channels.md)

[Assegnare criteri agli utenti in teams](assign-policies.md)
