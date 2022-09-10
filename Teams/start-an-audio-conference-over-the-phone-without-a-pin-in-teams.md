---
title: Avviare l'audioconferenza tramite telefono senza un PIN in Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: "Informazioni su come abilitare o disabilitare la partecipazione di chiamanti anonimi a una riunione dall'interfaccia di amministrazione di Teams. "
ms.openlocfilehash: a858c95527d09e24004d025787bee52c0de84705
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641947"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Avviare un'audioconferenza tramite telefono senza un PIN in Microsoft Teams

Può essere frustrante per gli utenti che accedono a una riunione nella sala di attesa della riunione ascoltando musica perché l'organizzatore della riunione di Microsoft Teams non ha avviato la riunione.
  
Se un organizzatore della riunione chiama la riunione, per impostazione predefinita è necessario un PIN per avviare una riunione. È possibile configurarla in modo che chiunque possa accedere a una riunione e non venga richiesto un PIN per avviare la riunione. È possibile usare l'interfaccia di amministrazione per abilitare o disabilitare questa impostazione per un singolo utente.
  
Non è necessario un PIN per l'organizzatore della riunione se qualcuno ha avviato la riunione dall'app Microsoft Teams. Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono. Il PIN per le riunioni viene inviato all'utente audio quando gli viene assegnata la licenza per i **servizi di audioconferenza** e viene abilitato per le audioconferenze. Vedi [Inviare un messaggio di posta elettronica a un utente con le informazioni sui servizi di audioconferenza](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) e [Messaggi di posta elettronica inviati automaticamente agli utenti in caso di modifica delle impostazioni di audioconferenza](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro fare clic su **Utenti**.

2. Selezionare un utente nell'elenco e quindi fare clic su **Modifica** nella parte superiore della pagina.

3. Accanto a **Audioconferenza**, fai clic su **Modifica**.

4. Nel riquadro **Audioconferenza** , abilita o disabilita **i chiamanti con accesso esterno può essere la prima persona in una riunione**.

5. Fare clic su **Applica**.

### <a name="using-windows-powershell"></a>Uso di Windows PowerShell

Per altre informazioni, vedere le [informazioni di riferimento su PowerShell di Microsoft Teams](/powershell/module/teams/?view=teams-ps) .

## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

- Se vuoi reimpostare il PIN, vedi [Reimpostare il PIN dei servizi di audioconferenza](reset-the-audio-conferencing-pin-in-teams.md).

- Se l'accesso anonimo, o se non è necessario un PIN per avviare una riunione, viene disabilitato:

  - Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): al chiamante verrà chiesto se è l'organizzatore; in caso affermativo, gli verrà richiesto il PIN e, dopo aver immesso il PIN, la riunione verrà avviata e l'utente accederà alla riunione.

  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.

- Se l'accesso anonimo, o se non è necessario un PIN per avviare una riunione, è abilitato:

  - Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN. Poiché l'impostazione dell'organizzatore è disattivata, la riunione verrà avviata e i chiamanti anonimi parteciperanno alla riunione.

  - Se la riunione è già iniziata (qualcun altro è già in riunione): al chiamante non verrà chiesto se è l'organizzatore e non le verrà mai richiesto il PIN. la riunione è già iniziata e il chiamante vi parteciperà.

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che semplifica il lavoro quotidiano quando si hanno più attività da svolgere. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare i servizi di audioconferenza in Microsoft 365 per Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
