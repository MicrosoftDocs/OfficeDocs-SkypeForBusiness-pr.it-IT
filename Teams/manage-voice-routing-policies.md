---
title: Gestire i criteri di routing vocale in Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Informazioni su come creare e gestire i criteri di routing vocale in Microsoft Teams.
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802556"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Gestire i criteri di routing vocale in Microsoft Teams

Se hai distribuito [](direct-routing-landing-page.md) il routing diretto del sistema telefonico nella tua organizzazione, utilizzi i criteri di routing vocale per consentire agli utenti di Teams e Skype for Business online di ricevere ed effettuare chiamate alla rete PSTN (Public Switched Telephone Network) utilizzando l'infrastruttura di telefonia locale.

Un criterio di routing vocale è un contenitore per i record di utilizzo PSTN. Per creare e gestire i criteri di routing vocale, è possibile accedere ai criteri di routing vocale nell'interfaccia di amministrazione di Microsoft Teams o tramite  >   Windows PowerShell.

È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti riceveranno automaticamente i criteri globali, a meno che non vengano creati e assegnati criteri personalizzati. Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non rinominarlo o eliminarlo.

È importante sapere che l'assegnazione di criteri di routing vocale a un utente non gli consente di effettuare chiamate PSTN in Teams. Dovrai anche abilitare l'utente per l'instradamento diretto del sistema telefonico ed eseguire altri passaggi di configurazione. Per altre informazioni, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md)

## <a name="create-a-custom-voice-routing-policy"></a>Creare criteri di routing vocale personalizzati

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a** Criteri  >  **di instradamento vocale,** quindi fai clic su **Aggiungi.**<br>
    ![Screenshot della pagina Aggiungi criteri di routing vocale nell'interfaccia di amministrazione di Microsoft Teams ](media/manage-voice-routing-policies.png) 
2. Immettere un nome e una descrizione per il criterio.
3. In **Record di utilizzo PSTN** fare clic su Aggiungi utilizzo **PSTN** e quindi selezionare i record da aggiungere. Se è necessario creare un nuovo record di utilizzo PSTN, fare clic su **Aggiungi.**
4. Se sono stati aggiunti più record di utilizzo PSTN, disporli nell'ordine desiderato.
5. Al termine, fare clic su **Applica.**
6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [New-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-voice-routing-policy"></a>Modificare un criterio di routing vocale

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Criteri**  >  **di instradamento vocale.**
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Fare **clic su Aggiungi/rimuovi record** di utilizzo PSTN, apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Set-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Assegnare un criterio di routing vocale personalizzato agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>Argomenti correlati

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Configurare il routing vocale per l'instradamento diretto](direct-routing-voice-routing.md)

[Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)
