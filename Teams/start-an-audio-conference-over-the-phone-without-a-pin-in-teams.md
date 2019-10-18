---
title: Avviare una conferenza audio tramite telefono senza PIN in Microsoft Teams
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come abilitare o disabilitare i chiamanti anonimi che partecipano a una riunione dall'interfaccia di amministrazione di teams. "
ms.openlocfilehash: 78b35b65c1bb27d366e8e9fa27c49ef32864081f
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570007"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Avviare una conferenza audio tramite telefono senza PIN in Microsoft Teams

Potrebbe essere frustrante per gli utenti che accedono a una riunione che si terrà nella sala di attesa della riunione che ascolta la musica perché l'organizzatore della riunione Microsoft teams non ha avviato la riunione. 
  
Se un organizzatore della riunione chiama alla riunione, per impostazione predefinita è necessario un PIN per avviare una riunione. È possibile configurarlo in modo che chiunque possa effettuare la chiamata a una riunione e non venga richiesto un PIN per avviare la riunione. È possibile usare l'interfaccia di amministrazione per abilitare o disabilitare questa impostazione per un singolo utente.
  
Un PIN non è necessario per l'organizzatore della riunione se qualcuno ha avviato la riunione dall'app Microsoft teams. Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono. Il PIN per le riunioni viene inviato all'utente audio quando viene assegnata la **licenza di audioconferenza e** abilitata per l'audioconferenza. Vedere [inviare un messaggio di posta elettronica a un utente con le informazioni di audioconferenza e i](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) [messaggi di posta elettronica inviati automaticamente agli utenti quando cambiano le impostazioni dei](emails-sent-to-users-when-their-settings-change-in-teams.md)servizi di audioconferenza.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra fare clic su **utenti**. 

2. Selezionare un utente nell'elenco e quindi fare clic su **modifica** nella parte superiore della pagina. 

3. Accanto a servizi di **audioconferenza**fare clic su **modifica**.

4. Nel riquadro **audioconferenza** abilitare o disabilitare **i chiamanti non autenticati può essere la prima persona di una riunione**.
    
4. Fai clic su **Salva**. 

**Tramite Windows PowerShell**
  
Per altre informazioni, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .

## <a name="what-else-should-you-know"></a>Quali altre informazioni devi conoscere?

- Se si vuole reimpostare il PIN, vedere [reimpostare il pin per la conferenza audio](reset-the-audio-conferencing-pin-in-teams.md).
    
- Se l'accesso anonimo o non richiede un PIN per avviare una riunione, è disabilitato:
    
  - Se la riunione non è ancora iniziata (non c'è nessuno nella riunione): A un chiamante verrà richiesto se è l'organizzatore; Se dice sì, verrà richiesto il PIN e, dopo aver inserito il PIN, verrà avviata la riunione e l'utente parteciperà alla riunione.
    
  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.
    
- Se l'accesso anonimo o non richiede un PIN per avviare una riunione, è abilitato:
    
  - Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN. Dato che l'impostazione dell'organizzatore è impostata su disattivato, la riunione verrà avviata e i chiamanti anonimi si uniranno alla riunione.
    
  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
