---
title: Reimpostare il PIN di audioconferenza in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
- seo-marvel-apr2020
description: Informazioni su come reimpostare il PIN di audioconferenza di un utente in Microsoft Teams e informazioni importanti sui PIN.
ms.openlocfilehash: 3f1055551edb45ac422052476196f01ee4d2765d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237466"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Reimpostare il PIN di audioconferenza in Microsoft Teams

Il PIN è un codice costituito da numeri creati per ogni utente di Microsoft Teams abilitato per i servizi di audioconferenza. I PIN per i servizi di audioconferenza vengono utilizzati dagli organizzatori della riunione per identificare che sono l'organizzatore della riunione e consentire loro di avviare una riunione tramite telefono. Se usano l'app Microsoft Teams per avviare la riunione, non è necessario un PIN. Se gli utenti dimenticano il PIN e non possono trovarlo nel messaggio di posta elettronica che gli è stato inviato quando sono stati abilitati per i servizi di audioconferenza, un amministratore può reimpostare il PIN oppure il proprio PIN.
  
Le riunioni possono essere avviate quando un utente autenticato partecipa utilizzando l'app Microsoft Teams o quando l'organizzatore si unisce con il PROPRIO PIN tramite telefono. Se è richiesto un PIN per avviare la riunione tramite telefono, per impostazione predefinita tutti gli utenti che partecipano alla riunione tramite telefono prima dell'inizio della riunione dovranno rimanere nella sala di attesa ascoltando musica fino all'inizio della riunione. Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.

## <a name="reset-a-users-pin"></a>Reimpostare il PIN dell'utente

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi selezionare l'utente nell'elenco di utenti disponibili.

2. Fare **clic su Modifica.**

3. In **Audioconferenza** fare clic **su Reimposta PIN.**

4. Fare clic **su Reimposta.**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>Fare in modo che un utente re reimposta il proprio PIN

1. Fare in modo che l'utente abbia accesso a [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .
2. Fare clic **su Reimposta PIN.** 


## <a name="what-else-should-you-know-about-pins"></a>Quali sono le altre informazioni utili sul PIN?

- Ai fini della sicurezza, il PIN viene visualizzato solo una volta all'amministratore, quando viene reimpostato. Dopo la reimpostazione del PIN da parte di un amministratore, il PIN sarà elencato come ***********.
    
- L'invio automatico dei messaggi di posta elettronica agli utenti è abilitato per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per i servizi di audioconferenza o quando viene reimpostato il PIN. Se invece hai disabilitato l'invio automatico dei messaggi di posta elettronica, all'utente non verrà inviato un messaggio di posta elettronica di reimpostazione del PIN e dovrai inviare manualmente le informazioni sul PIN all'utente.
    
- Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Ad esempio, se due partecipanti tentano di partecipare a una riunione prima che questa inizi, verranno messi nella sala di attesa e ascolteranno musica durante l'attesa e quando l'organizzatore della riunione si unirà usando il PIN tramite telefono, la riunione avrà inizio e i partecipanti nella sala di attesa potranno partecipare alla riunione.
    
- L'impostazione predefinita è non consentire l'avvio di una riunione da parte di chiamanti anonimi.
    
- Quando abiliti un utente per i servizi di audioconferenza, per impostazione predefinita agli utenti vengono inviati messaggi di posta elettronica che includono le informazioni di conferenza e il PIN. L'utente deve avere una cassetta postale di Microsoft 365 o Office 365, perché quando viene reimpostato il PIN, all'utente viene inviato un nuovo PIN tramite posta elettronica all'indirizzo SMTP principale (alias) impostato per l'utente.
    
- Quando si imposta una audioconferenza, impostare le cifre necessari per il PIN nella propria organizzazione. I PIN possono contenere da 4 a 12 cifre. L'impostazione predefinita è 5. Se si modifica l'impostazione della lunghezza del PIN, l'impostazione viene applicata solo sui PIN generati successivamente e non viene applicata per l'impostazione del PIN degli utenti precedetemente abilitati per le audioconferenze. Vedere [impostare la lunghezza del PIN per le riunioni in audioconferenze](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- Per impostazione predefinita, il messaggio di posta elettronica verrà impostato sull'indirizzo SMTP principale di Microsoft 365 o Office 365 dell'utente. È possibile inviare un messaggio di posta elettronica a un indirizzo diverso da Microsoft 365 o non Di Office 365, ad esempio un indirizzo di posta elettronica Hotmail o MSN. È possibile sostituire l'indirizzo di posta elettronica predefinito tramite Windows PowerShell. Questa opzione è utile se gli utenti non hanno una cassetta postale di Exchange in Microsoft 365 o Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni sulle Windows PowerShell, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
  
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user-in-teams.md)
