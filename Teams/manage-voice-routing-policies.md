---
title: Gestire i criteri di routing delle chiamate per il routing diretto
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
description: Informazioni su come creare e gestire i criteri di routing delle chiamate in Microsoft Teams.
ms.openlocfilehash: dec6f19dea1f2a44f1c550bf4ae6b9c4f4dedc77
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634935"
---
# <a name="manage-call-routing-policies-for-direct-routing"></a>Gestire i criteri di routing delle chiamate per il routing diretto

Se il routing [](direct-routing-landing-page.md) diretto è stato distribuito nell'organizzazione, si usano i criteri di routing delle chiamate per consentire agli utenti di Teams di ricevere ed effettuare chiamate telefoniche alla rete PSTN (Public Switched Telephone Network) usando l'infrastruttura di telefonia locale.

I criteri di routing delle chiamate (detti anche criteri di routing vocale) sono un contenitore per i record di utilizzo PSTN. Per creare e gestire i criteri di routing vocale, accedere ai criteri di routing vocale nell'interfaccia di amministrazione di Microsoft Teams o usando  >   Windows PowerShell.

È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti riceveranno automaticamente i criteri globali a meno che non si creino e assegnino criteri personalizzati. Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non è possibile rinominarlo o eliminarlo.

È importante sapere che l'assegnazione di un criterio di routing vocale a un utente non gli consente di effettuare chiamate PSTN in Teams. È anche necessario abilitare l'utente per l'Sistema telefonico routing diretto e completare altri passaggi di configurazione. Per altre informazioni, vedere [Configurare il routing diretto.](direct-routing-configure.md)

## <a name="create-a-custom-call-routing-policy"></a>Creare criteri di routing delle chiamate personalizzati

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione, passare **a** Criteri  >  **di routing vocale** e quindi fare clic su **Aggiungi.**<br>
    ![Screenshot della pagina Aggiungi criteri di routing vocale nell'Microsoft Teams di amministrazione.](media/manage-voice-routing-policies.png) 
2. Immettere un nome e una descrizione per il criterio.
3. In **Record di utilizzo PSTN** fare clic su Aggiungi utilizzo **PSTN** e quindi selezionare i record da aggiungere. Se è necessario creare un nuovo record di utilizzo PSTN, fare clic su **Aggiungi**.
4. Se sono stati aggiunti più record di utilizzo PSTN, disporli nell'ordine desiderato.
5. Al termine, fare clic su **Applica.**
6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-call-routing-policy"></a>Modificare un criterio di routing delle chiamate

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione, passare **a** Criteri di  >  **routing vocale.**
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Fare **clic su Aggiungi/rimuovi record di utilizzo PSTN,** apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-call-routing-policy-to-users"></a>Assegnare un criterio di routing delle chiamate personalizzato agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Argomenti correlati

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Configurare il routing delle chiamate per l'instradamento diretto](direct-routing-voice-routing.md)

[Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)