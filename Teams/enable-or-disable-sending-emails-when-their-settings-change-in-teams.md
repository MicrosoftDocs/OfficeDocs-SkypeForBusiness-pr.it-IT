---
title: opzioni di Email quando cambiano le impostazioni dei servizi di audioconferenza
ms.author: heidip
author: MicrosoftHeidi
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
description: "Informazioni su come abilitare o disabilitare Microsoft Teams per l'invio di messaggi di posta elettronica agli utenti quando vengono modificate impostazioni come il pin o il numero di conferenza predefinito in Teams. "
ms.openlocfilehash: a5119d6f612ed083ac4e72ab52f6bb189af4c9d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642107"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Abilitare o disabilitare l'invio di messaggi di posta elettronica quando le impostazioni delle audioconferenze vengono modificate in Microsoft Teams

Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per l'Audioconferenza. A volte, tuttavia, può essere necessario ridurre il numero di messaggi di posta elettronica inviati agli utenti di Microsoft Teams. In tal caso, puoi disabilitare l'invio dei messaggi posta elettronica.
  
Se disabiliti l'invio di e-mail, i messaggi e-mail di audioconferenza non verranno inviati agli utenti, inclusi i messaggi e-mail relativi a quando gli utenti sono abilitati o disabilitati per le audioconferenze, quando il PIN viene reimpostato e quando l'ID conferenza e il numero di telefono predefinito per le conferenze cambiano.
  
Ecco un esempio di messaggio di posta elettronica inviato agli utenti quando sono abilitati per le audioconferenze:
  
![Esempio di messaggio di posta elettronica per i servizi di audioconferenza.](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>I messaggi di posta elettronica quando vengono inviati agli utenti?

- Dopo l'abilitazione per i servizi di audioconferenza, agli utenti dell'organizzazione vengono inviati diversi messaggi di posta elettronica:

  - Quando una licenza di **Audioconferenza** viene loro assegnata.

  - Quando reimporti manualmente il PIN di audioconferenza dell'utente.

  - Quando reimposti manualmente l'ID conferenza dell'utente.

  - Quando la licenza di **Audioconferenza** viene loro rimossa.

  - Quando il provider di servizi di audioconferenza di un utente viene modificato da Microsoft a un altro provider o **Nessuno**.

  - Quando il provider di servizi di audioconferenza di un utente diventa Microsoft.

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Abilitare o disabilitare l'invio di posta elettronica agli utenti

È possibile usare Microsoft Teams o Windows PowerShell per abilitare o disabilitare la posta elettronica inviata agli utenti.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

2. Nella parte superiore della pagina **Conference Bridge** fare clic su **Impostazioni bridge**.

3. Nel riquadro **Impostazioni bridge** abilitare o disabilitare **l'opzione Invia automaticamente messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni di accesso**.

4. Fare clic su **Salva**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Uso di Windows PowerShell

È anche possibile usare il modulo PowerShell di Microsoft Teams ed eseguire:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Puoi utilizzare [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.

Per altre informazioni, vedere le [informazioni di riferimento su PowerShell di Microsoft Teams](/powershell/module/teams/?view=teams-ps) .

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Modi migliori per gestire Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Argomenti correlati

[Messaggi di posta elettronica inviati agli utenti quando le impostazioni dei servizi di audioconferenza cambiano](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
