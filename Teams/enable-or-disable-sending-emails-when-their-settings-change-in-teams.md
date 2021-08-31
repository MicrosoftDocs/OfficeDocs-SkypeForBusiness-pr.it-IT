---
title: Opzioni di posta elettronica quando vengono modificate le impostazioni dei servizi di audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: "Informazioni su come abilitare o disabilitare Skype l'invio di messaggi di posta elettronica agli utenti quando vengono apportate modifiche a impostazioni come il pin o il numero di conferenza predefinito in Microsoft Teams. "
ms.openlocfilehash: f81572feb976ab68a6a65631ec772ec4421f2b1e
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727445"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Abilitare o disabilitare l'invio di messaggi di posta elettronica quando le impostazioni di audioconferenza cambiano Microsoft Teams

Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per l'Audioconferenza. A volte, tuttavia, può essere necessario ridurre il numero di messaggi di posta elettronica inviati Microsoft Teams utenti. In tal caso, puoi disabilitare l'invio dei messaggi posta elettronica.
  
Se si disabilita l'invio di messaggi di posta elettronica, i messaggi di posta elettronica per i servizi di audioconferenza non verranno inviati agli utenti, inclusi i messaggi di posta elettronica per i quali gli utenti sono abilitati o disabilitati per le audioconferenze, quando il PIN viene reimpostato e quando cambia l'ID conferenza e il numero di telefono di conferenza predefinito.
  
Ecco un esempio del messaggio di posta elettronica inviato agli utenti quando sono abilitati per le audioconferenze:
  
![Esempio di messaggio di posta elettronica audioconferenza.](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>I messaggi di posta elettronica quando vengono inviati agli utenti?

- Sono disponibili diversi messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo che sono stati abilitati per le audioconferenze:
    
  - Quando una licenza di **Audioconferenza** viene loro assegnata.
    
  - Quando si reimposta manualmente il PIN di audioconferenza dell'utente.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Quando la licenza di **Audioconferenza** viene loro rimossa.
    
  - Quando il provider di servizi di audioconferenza di un utente viene modificato da Microsoft a un altro provider o **Nessuno**.
    
  - Quando il provider di servizi di audioconferenza di un utente viene modificato in Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Abilitare o disabilitare l'invio di posta elettronica agli utenti

È possibile usare le Microsoft Teams o Windows PowerShell per abilitare o disabilitare la posta elettronica inviata agli utenti.

![Icona che mostra il Microsoft Teams logo.](media/teams-logo-30x30.png) **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**. 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge** abilitare o disabilitare Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di accesso **remoto cambiano.**

4. Fare clic su **Salva**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Uso di Windows PowerShell**
  
È anche possibile usare il modulo Microsoft Teams PowerShell ed eseguire:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

È possibile usare [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) per gestire altre impostazioni per l'organizzazione, tra cui la posta elettronica.

Per altre [informazioni, Microsoft Teams informazioni di riferimento su PowerShell.](/powershell/module/teams/?view=teams-ps)

    
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più sulle Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Argomenti correlati

[Messaggi di posta elettronica inviati agli utenti quando cambiano le impostazioni di audioconferenza](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
