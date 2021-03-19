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
ms.openlocfilehash: 1ee3360668084bf6bf99b3ede25584ce9800dd5b
ms.sourcegitcommit: b4b2c7e79679cce6cf5f863ddf708e50164f9a9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50861440"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Reimpostare il PIN di audioconferenza in Microsoft Teams

Un PIN è un codice costituito da numeri creati per ogni utente di Microsoft Teams abilitato per le audioconferenze. I PIN di audioconferenza vengono usati dagli organizzatori della riunione per identificare che sono l'organizzatore della riunione e consentire loro di avviare una riunione tramite telefono. Se usano l'app Microsoft Teams per avviare la riunione, non è necessario un PIN. Se gli utenti dimenticano il PIN e non lo trovano nel messaggio di posta elettronica inviato quando sono stati abilitati per le audioconferenze, un amministratore può reimpostare il PIN oppure reimpostare il PROPRIO PIN.
  
Le riunioni possono essere avviate quando un utente autenticato partecipa usando l'app Microsoft Teams o quando l'organizzatore partecipa con il PIN tramite telefono. Se è richiesto un PIN per avviare la riunione tramite telefono, per impostazione predefinita tutti gli utenti che partecipano alla riunione tramite telefono prima dell'inizio della riunione dovranno rimanere nella sala di attesa ascoltando musica fino all'inizio della riunione. Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.

## <a name="reset-a-users-pin"></a>Reimpostare il PIN dell'utente

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Fare clic **su Modifica**.

3. In **Audioconferenza** fare clic **su Reimposta PIN.**

4. Fare clic **su Reimposta**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>Fare in modo che un utente resetti il proprio PIN

1. Fare in modo che l'utente vada a [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .
2. Fare clic **su Reimposta PIN**. 

> [!NOTE]
> Per GCCH, vai a: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing .

## <a name="what-else-should-you-know-about-pins"></a>Quali sono le altre informazioni utili sul PIN?

- Per motivi di sicurezza, il PIN viene visualizzato una sola volta all'amministratore, quando il PIN viene reimpostato. Dopo la reimpostazione del PIN da parte di un amministratore, il PIN verrà elencato come ***********.
    
- L'invio automatico di messaggi di posta elettronica agli utenti è abilitato per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per le audioconferenze o quando il PIN viene reimpostato. Se tuttavia l'invio automatico dei messaggi di posta elettronica è stato disabilitato, non verrà inviato un messaggio di posta elettronica di reimpostazione del PIN a un utente e sarà necessario inviare manualmente le informazioni sul PIN all'utente.
    
- Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Ad esempio, se due partecipanti provano a partecipare a una riunione prima dell'inizio, verranno messi nella sala d'attesa e ascoltano musica in attesa e quando l'organizzatore della riunione partecipa usando il PIN tramite telefono, la riunione verrà avviata e i partecipanti nella sala d'attesa si uniranno alla riunione.
    
- L'impostazione predefinita è non consentire l'avvio di una riunione da parte di chiamanti anonimi.
    
- Quando si abilita un utente per le audioconferenze, per impostazione predefinita vengono inviati messaggi di posta elettronica che includono le informazioni di conferenza e il PIN. L'utente deve avere una cassetta postale di Microsoft 365 o Office 365, perché quando viene reimpostato un PIN, all'utente verrà inviato un nuovo PIN tramite posta elettronica all'indirizzo SMTP principale (alias) impostato per l'utente.
    
- Quando si imposta una audioconferenza, impostare le cifre necessari per il PIN nella propria organizzazione. I PIN possono essere da 4 a 12 cifre, il valore predefinito è 5. Se si modifica l'impostazione della lunghezza del PIN, l'impostazione viene applicata solo sui PIN generati successivamente e non viene applicata per l'impostazione del PIN degli utenti precedetemente abilitati per le audioconferenze. Vedere [impostare la lunghezza del PIN per le riunioni in audioconferenze](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- Il messaggio di posta elettronica per impostazione predefinita verrà impostato sull'indirizzo SMTP principale di Microsoft 365 o Office 365 dell'utente. È possibile inviare un messaggio di posta elettronica a un indirizzo di posta elettronica non Microsoft 365 o non di Office 365, ad esempio un indirizzo di posta elettronica Hotmail o MSN. È possibile sostituire l'indirizzo di posta elettronica predefinito tramite Windows PowerShell. Questa opzione è utile se gli utenti non hanno una cassetta postale di Exchange in Microsoft 365 o Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più sulle Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user-in-teams.md)
