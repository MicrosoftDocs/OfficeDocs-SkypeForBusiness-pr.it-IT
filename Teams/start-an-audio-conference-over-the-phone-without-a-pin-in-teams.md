---
title: Avviare l'audioconferenza tramite telefono senza un PIN in Teams
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: "Informazioni su come abilitare o disabilitare la partecipazione di chiamanti anonimi a una riunione dall'Teams di amministrazione. "
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116964"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Avviare un'audioconferenza tramite telefono senza un PIN in Microsoft Teams

Può essere frustrante per gli utenti che a una riunione a una riunione si svolgono nella sala d'attesa della riunione ascoltando musica perché l'organizzatore della riunione di Microsoft Teams non ha avviato la riunione. 
  
Se l'organizzatore della riunione chiama per impostazione predefinita, è necessario un PIN per avviare una riunione. È possibile configurarla in modo che chiunque possa accedere a una riunione e non venga richiesto un PIN per avviare la riunione. È possibile usare l'interfaccia di amministrazione per abilitare o disabilitare questa impostazione per un singolo utente.
  
Non è necessario un PIN per l'organizzatore della riunione se qualcuno ha avviato la riunione dall'app Microsoft Teams riunione. Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono. Il PIN per le riunioni viene inviato all'utente audio quando gli viene assegnata la licenza **di audioconferenza** e viene abilitato per le audioconferenze. Vedere [Inviare un messaggio di posta](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) elettronica a un utente con le informazioni relative alle audioconferenze e i messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando cambiano le [impostazioni di audioconferenza.](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic su **Utenti.** 

2. Selezionare un utente nell'elenco e quindi fare clic **su Modifica** nella parte superiore della pagina. 

3. Accanto a **Audioconferenza** fare clic su **Modifica.**

4. Nel riquadro **Audioconferenza,** abilitare o disabilitare i chiamanti con accesso esterno può essere la prima **persona in una riunione.**
    
4. Fare clic **su Applica**. 

**Uso di Windows PowerShell**
  
Per altre [informazioni, Microsoft Teams informazioni di riferimento su PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

- Per reimpostare il PIN, vedere Reimpostare [il PIN dei servizi di audioconferenza.](reset-the-audio-conferencing-pin-in-teams.md)
    
- Se l'accesso anonimo o la richiesta di un PIN per avviare una riunione è disabilitata:
    
  - Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): un chiamante riceverà una richiesta se è l'organizzatore; se dice sì, gli verrà richiesto il PIN e, dopo aver immesso il PIN, la riunione verrà avviata e l'utente si unirà alla riunione.
    
  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.
    
- Se l'accesso anonimo, o non richiede un PIN per avviare una riunione, è abilitato:
    
  - Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN. Poiché l'impostazione dell'organizzatore è disattivata, la riunione verrà avviata e i chiamanti anonimi si uniranno alla riunione.
    
  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)