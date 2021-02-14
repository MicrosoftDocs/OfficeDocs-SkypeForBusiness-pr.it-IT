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
description: "Informazioni su come abilitare o disabilitare l'accesso dei chiamanti anonimi a una riunione dall'interfaccia di amministrazione di Teams. "
ms.openlocfilehash: 6d5dd7c08d37993c541a0a4f670fd240057bfb3a
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691502"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Avviare un'audioconferenza tramite telefono senza un PIN in Microsoft Teams

Può essere frustrante per gli utenti che a una riunione a conferenze si svolgono nella sala di attesa della riunione ad ascoltare musica perché l'organizzatore della riunione di Microsoft Teams non ha avviato la riunione. 
  
Se l'organizzatore della riunione chiama la riunione, per impostazione predefinita è necessario un PIN per avviare la riunione. È possibile configurarla in modo che chiunque possa accedere a una riunione senza che venga richiesto un PIN per avviare la riunione. È possibile usare l'interfaccia di amministrazione per abilitare o disabilitare questa impostazione per un singolo utente.
  
Se qualcuno ha avviato la riunione dall'app Microsoft Teams, non è necessario un PIN per l'organizzatore della riunione. Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono. Il PIN per le riunioni viene inviato all'utente audio quando gli viene assegnata la licenza **di Audioconferenza** e viene abilitato per i servizi di audioconferenza. Vedi [Invia un messaggio e-mail con](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) le informazioni e le e-mail per i servizi di audioconferenza che vengono inviate automaticamente agli utenti in caso di modifica delle [impostazioni.](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti.** 

2. Selezionare un utente nell'elenco e quindi fare clic **su Modifica** nella parte superiore della pagina. 

3. Accanto a **Audioconferenza,** fai clic **su Modifica.**

4. Nel riquadro **Audioconferenza,** i chiamanti con accesso esterno possono essere la **prima persona in una riunione.**
    
4. Fare clic **su Applica.** 

**Uso Windows PowerShell**
  
Per altre informazioni, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)

## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

- Se desideri reimpostare il PIN, consulta Reimpostare [il PIN di audioconferenza.](reset-the-audio-conferencing-pin-in-teams.md)
    
- Se l'accesso anonimo, o senza la necessità di un PIN per avviare una riunione, è disabilitato:
    
  - Se la riunione non è ancora iniziata (non c'è ancora nessuno): se è l'organizzatore, al chiamante verrà chiesto di specificare se è l'organizzatore; se dice sì, gli verrà richiesto il PIN e, dopo aver immesso il PIN, la riunione verrà avviata e l'utente dovrà partecipare alla riunione.
    
  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.
    
- Se l'accesso anonimo, o senza la necessità di un PIN per avviare una riunione, è abilitato:
    
  - Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN. Poiché l'impostazione dell'organizzatore è disattivata, la riunione verrà avviata e i chiamanti anonimi potranno partecipare alla riunione.
    
  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni sulle Windows PowerShell, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
