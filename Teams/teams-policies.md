---
title: Gestire i criteri dei team in Microsoft Teams
author: cichur
ms.author: v-cichur
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: Informazioni su come usare e gestire i criteri dei team nell'organizzazione per controllare le attività che gli utenti possono eseguire nei team e nei canali.
ms.openlocfilehash: 81541c08ac963f0bcef18ba589b2341915c20d5d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094206"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gestire i criteri dei team in Microsoft Teams

Gli amministratori possono usare i criteri di teams in Microsoft Teams per controllare le attività che gli utenti dell'organizzazione possono eseguire nei team e nei canali. Ad esempio, è possibile impostare se gli utenti sono autorizzati a creare canali privati.

Per gestire i criteri dei team, è **possibile accedere Teams** Teams criteri  >  **nell'Microsoft Teams** di amministrazione. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.

È possibile modificare i criteri globali o creare e assegnare criteri personalizzati. Dopo aver modificato i criteri globali o aver assegnato un criterio, l'applicazione delle modifiche può richiedere alcune ore.

## <a name="create-a-custom-teams-policy"></a>Creare criteri di team personalizzati

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare **a** Teams  >  **Teams criteri.**
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.

    ![Screenshot delle impostazioni dei criteri dei team](media/teams-policies.png)
4. Attivare o disattivare Crea <a name="createchannels"></a> canali **privati,** a seconda che si voglia consentire agli utenti di creare canali privati.

5. Fare clic su **Salva**.

## <a name="edit-a-teams-policy"></a>Modificare un criterio di Teams

È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare **a** Teams  >  **Teams criteri.**
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva.**

## <a name="assign-a-custom-teams-policy-to-users"></a>Assegnare criteri di team personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Argomenti correlati

[Canali privati in Teams](private-channels.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)