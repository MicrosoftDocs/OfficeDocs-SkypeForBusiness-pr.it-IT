---
title: Gestire i criteri di routing vocale per il routing diretto
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come creare e gestire i criteri di routing vocale in Microsoft Teams.
ms.openlocfilehash: 15e0d14310865244570dee677ac19238e9510628
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598460"
---
# <a name="manage-voice-routing-policies-for-direct-routing"></a>Gestire i criteri di routing vocale per il routing diretto

Se è stato distribuito [Sistema telefonico Routing](direct-routing-landing-page.md) diretto nell'organizzazione, si usano i criteri di routing vocale per consentire agli utenti di Teams e Skype for Business Online di ricevere ed effettuare chiamate telefoniche alla rete PSTN (Public Switched Telephone Network) usando l'infrastruttura di telefonia locale.

Un criterio di routing vocale è un contenitore per i record di utilizzo PSTN. Per creare e gestire i criteri di routing vocale, accedere ai criteri di routing vocale nell'interfaccia di amministrazione di Microsoft Teams o usando  >   Windows PowerShell.

È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti riceveranno automaticamente i criteri globali a meno che non si creino e assegnino criteri personalizzati. Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non è possibile rinominarlo o eliminarlo.

È importante sapere che l'assegnazione di un criterio di routing vocale a un utente non gli consente di effettuare chiamate PSTN in Teams. È anche necessario abilitare l'utente per l'Sistema telefonico routing diretto e completare altri passaggi di configurazione. Per altre informazioni, vedere [Configurare il routing diretto.](direct-routing-configure.md)

## <a name="create-a-custom-voice-routing-policy"></a>Creare un criterio di routing vocale personalizzato

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione, passare **a** Criteri  >  **di routing vocale** e quindi fare clic su **Aggiungi.**<br>
    ![Screenshot della pagina Aggiungi criteri di routing vocale nell'interfaccia Microsoft Teams di amministrazione](media/manage-voice-routing-policies.png) 
2. Immettere un nome e una descrizione per il criterio.
3. In **Record di utilizzo PSTN** fare clic su Aggiungi utilizzo **PSTN** e quindi selezionare i record da aggiungere. Se è necessario creare un nuovo record di utilizzo PSTN, fare clic su **Aggiungi**.
4. Se sono stati aggiunti più record di utilizzo PSTN, disporli nell'ordine desiderato.
5. Al termine, fare clic su **Applica.**
6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-voice-routing-policy"></a>Modificare un criterio di routing vocale

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare **a** Criteri di  >  **routing vocale.**
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Fare **clic su Aggiungi/rimuovi record di utilizzo PSTN,** apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Assegnare un criterio di routing vocale personalizzato agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Argomenti correlati

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Configurare il routing vocale per il routing diretto](direct-routing-voice-routing.md)

[Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)