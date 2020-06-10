---
title: Reimpostare il PIN di conferenza audio in Microsoft Teams
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
description: Informazioni su come reimpostare il PIN per le conferenze audio di un utente in Microsoft teams e scoprire informazioni importanti sui pin.
ms.openlocfilehash: 8926218c72c888edb00480ff8382672a3730cf15
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666188"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Reimpostare il PIN di conferenza audio in Microsoft Teams

Un PIN è un codice composto da numeri creati per ogni utente di Microsoft teams abilitato per i servizi di audioconferenza. I pin di conferenza audio vengono usati dagli organizzatori della riunione per identificare che sono l'organizzatore della riunione e consentire loro di avviare una riunione tramite telefono. Se usano l'app Microsoft teams per avviare la riunione, non è necessario un PIN. Se gli utenti dimenticano il PIN e non riescono a trovarlo nel messaggio di posta elettronica inviato loro quando sono stati abilitati per i servizi di audioconferenza, un amministratore può reimpostare il PIN oppure può reimpostare il proprio PIN.
  
Le riunioni possono essere avviate quando un utente autenticato entra in contatto con l'app Microsoft teams o quando l'organizzatore si unisce al proprio PIN tramite telefono. Se è richiesto un PIN per avviare la riunione tramite telefono, per impostazione predefinita tutti gli utenti che partecipano alla riunione tramite telefono prima dell'inizio della riunione dovranno rimanere nella sala di attesa ascoltando musica fino all'inizio della riunione. Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.

## <a name="reset-a-users-pin"></a>Reimpostare il PIN dell'utente

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Fare clic su **modifica**.

3. In **audioconferenza**fare clic su **Reimposta PIN**.

4. Fare clic su **Reimposta**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Reimpostazione del PIN da parte dell'utente

1. Far accedere l'utente [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .
2. Fare clic su **Reimposta PIN**. 


## <a name="what-else-should-you-know-about-pins"></a>Quali sono le altre informazioni utili sul PIN?

- Ai fini della sicurezza, il PIN viene visualizzato solo una volta dall'amministratore, alla reimpostazione del PIN. Dopo la reimpostazione del PIN da parte di un amministratore, il PIN verrà elencato come * * * * * * * * * * *.
    
- L'invio automatico di messaggi di posta elettronica agli utenti è abilitato per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per i servizi di audioconferenza o quando il PIN viene reimpostato. Ma se si è disabilitato l'invio automatico di messaggi di posta elettronica, un messaggio di reimpostazione del PIN non verrà inviato a un utente e sarà necessario inviare manualmente le informazioni sul PIN all'utente.
    
- Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Se ad esempio due partecipanti tentano di partecipare a una riunione prima che questa inizi, dovranno rimanere nella sala di attesa ascoltando musica e quando l'organizzatore della riunione si unirà usando il proprio PIN tramite telefono, la riunione avrà inizio e i partecipanti nella sala di attesa potranno partecipare alla riunione.
    
- L'impostazione predefinita consiste nel non consentire l'avvio di una riunione da parte di chiamanti anonimi.
    
- Quando si Abilita un utente per i servizi di audioconferenza, per impostazione predefinita vengono inviati messaggi di posta elettronica che includono informazioni per i servizi di conferenza e il PIN. L'utente deve avere una cassetta postale di Microsoft 365 o Office 365, poiché quando viene reimpostato un PIN, un nuovo PIN verrà inviato all'utente tramite posta elettronica all'indirizzo SMTP principale (alias) impostato per l'utente.
    
- Quando si imposta una audioconferenza, impostare le cifre necessari per il PIN nella propria organizzazione. I pin possono essere da 4 a 12 cifre: l'impostazione predefinita è 5. Se si modifica l'impostazione della lunghezza del PIN, l'impostazione viene applicata solo sui PIN generati successivamente e non viene applicata per l'impostazione del PIN degli utenti precedetemente abilitati per le audioconferenze. Vedere [impostare la lunghezza del PIN per le riunioni in audioconferenze](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- Per impostazione predefinita, il messaggio di posta elettronica verrà impostato sull'indirizzo SMTP principale di Microsoft 365 o Office 365 dell'utente. È possibile inviare un messaggio di posta elettronica a un indirizzo non Microsoft 365 o non Office 365, ad esempio un indirizzo di posta elettronica Hotmail o MSN. È possibile sostituire l'indirizzo di posta elettronica predefinito tramite Windows PowerShell. Questa operazione è utile se gli utenti non hanno una cassetta postale di Exchange in Microsoft 365 o Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione in grado di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.
  
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user-in-teams.md)
