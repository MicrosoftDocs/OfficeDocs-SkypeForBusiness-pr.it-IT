---
title: Inviare un messaggio di posta elettronica a un utente con Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Inviare agli utenti un messaggio di posta elettronica con le loro informazioni di audioconferenza su Skype for Business online.
ms.openlocfilehash: 428ff78fe501200ef9607a03d76c034007517cf0
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727675"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Inviare un messaggio di posta elettronica a un utente con le informazioni relative ai servizi di audioconferenza in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Per informazioni sull'invio di informazioni di Audioconferenza agli utenti su Microsoft Teams, consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza su Microsoft Teams](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

In alcuni casi, potrebbe essere necessario inviare agli utenti di Skype for Business le informazioni di Audioconferenza. A questo scopo, usare l'interfaccia di  amministrazione **Skype for Business** e fare clic su Invia informazioni conferenza tramite posta elettronica sotto le proprietà di un utente. Quando invii questo messaggio di posta elettronica, conterrà tutte le informazioni relative ai servizi di audioconferenza, tra cui:
  
- Il numero di telefono per le conferenze o per l'accesso esterno dell'utente.
    
- L'ID conferenza dell'utente.
    
   
Ecco un esempio del messaggio di posta elettronica inviato:
  
![Posta elettronica per i servizi di conferenza telefonica con accesso esterno.](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fai clic su **Modifica**.

3. Su **Audioconferenza**, fai clic su **Invia informazioni sulla conferenza nel messaggio di posta elettronica**.

1. Accedere con l'account aziendale o dell'istituto di istruzione.
    
2. Passare all'interfaccia di amministrazione > **Skype for Business** e nel riquadro di spostamento sinistro fare clic su **Audioconferenza.**
    
3. Fare **clic su** Utenti e quindi selezionare l'utente.
    
4. In the Action pane, click **Send conference info via email**.
    
> [!TIP]
> È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza modificando le proprietà dell'utente e quindi facendo clic su **Invia** informazioni conferenza tramite  >  **posta elettronica.** 

## <a name="what-else-should-you-know-about-this-email"></a>Cos'altro occorre sapere su questo messaggio di posta elettronica?

- Sono disponibili diversi messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo che sono stati abilitati per le audioconferenze:
    
  - Quando una licenza di **Audioconferenza** viene loro assegnata.
    
  - Quando si reimposta manualmente il PIN di audioconferenza dell'utente.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Quando una licenza di **Audioconferenza** è rimossa a loro.
    
  - Quando il provider di servizi di audioconferenza per un utente viene modificato da Microsoft a un altro provider o **Nessuno**.
    
  - Quando il provider di servizi di audioconferenza per un utente viene modificato in Microsoft.
    
- Per impostazione predefinita, il mittente dei messaggi di posta elettronica viene inviato da Microsoft 365 o Office 365, ma è possibile modificare l'indirizzo di posta elettronica e il nome visualizzato usando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Per apportare modifiche all'indirizzo di posta elettronica che invia il messaggio agli utenti, è necessario:
    
  - Immettere l'indirizzo di posta elettronica nel parametro SendEmailFromAddress.
    
  - Imposta il parametro SendEmailOverride su True.
    
  - Immettere il nome visualizzato del messaggio di posta elettronica nel parametro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
    Per inviare un messaggio di posta elettronica all'utente con le informazioni relative ai servizi di audioconferenza, eseguire le operazioni seguenti:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
