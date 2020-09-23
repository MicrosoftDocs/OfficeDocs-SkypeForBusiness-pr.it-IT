---
title: Gestire i criteri di routing vocale in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come creare e gestire i criteri di routing vocale in Microsoft teams.
ms.openlocfilehash: 2bef422f22dc212b2c615e2ca2ab98806b396e9f
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217657"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Gestire i criteri di routing vocale in Microsoft Teams

Se si è distribuito il [routing diretto del sistema telefonico](direct-routing-landing-page.md) nell'organizzazione, è possibile usare i criteri di routing vocale per consentire agli utenti di Skype for business online di ricevere e effettuare chiamate telefoniche alla rete PSTN (Public Switched Telephone Network) usando l'infrastruttura di telefonia locale.

Un criterio di routing vocale è un contenitore per i record di utilizzo PSTN. Per creare e gestire i criteri di routing vocale, è possibile **passare a**criteri di routing Voice Voice nell'interfaccia di amministrazione di  >  **Voice routing policies** Microsoft teams o tramite Windows PowerShell.

Puoi usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati. Gli utenti otterranno automaticamente il criterio globale a meno che non si creino e si assegnano criteri personalizzati. Tieni presente che puoi modificare le impostazioni nel criterio globale, ma non puoi rinominarle o eliminarle.

È importante sapere che l'assegnazione di criteri di routing vocale a un utente non consente loro di effettuare chiamate PSTN in teams. Dovrai anche abilitare l'instradamento diretto dell'utente per il sistema telefonico e completare altri passaggi di configurazione. Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md).

## <a name="create-a-custom-voice-routing-policy"></a>Creare un criterio di routing vocale personalizzato

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **passa a**  >  **criteri di routing**vocale e quindi fai clic su **Aggiungi**.<br>
    ![Screenshot della pagina Aggiungi criteri di routing vocale nell'interfaccia di amministrazione di Microsoft Teams ](media/manage-voice-routing-policies.png) 
2. Immettere un nome e una descrizione per il criterio.
3. In **record utilizzo PSTN**fare clic su **Aggiungi utilizzo PSTN**e quindi selezionare i record che si desidera aggiungere. Se è necessario creare un nuovo record di utilizzo PSTN, fare clic su **Aggiungi**.
4. Se sono stati aggiunti più record di utilizzo PSTN, disponili nell'ordine desiderato.
5. Al termine, fare clic su **applica**.
6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-voice-routing-policy"></a>Modificare un criterio di routing vocale

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare il criterio globale o i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **accedere ai**  >  **criteri di routing**vocale.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Fare clic su **Aggiungi/Rimuovi record di utilizzo PSTN**, apportare le modifiche desiderate e quindi fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Assegnare criteri di routing vocale personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Argomenti correlati

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Configurare il routing vocale per il routing diretto](direct-routing-voice-routing.md)

[Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)

[Assegnare criteri agli utenti in teams](assign-policies.md)
