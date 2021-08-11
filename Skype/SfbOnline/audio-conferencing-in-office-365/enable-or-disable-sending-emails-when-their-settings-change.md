---
title: Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: "Informazioni su come abilitare o disabilitare Skype dall'invio di messaggi di posta elettronica agli utenti quando cambiano le impostazioni, quali ad esempio le modifiche del pin o del numero predefinito della conferenza. "
ms.openlocfilehash: f2c0112f3817bfd64184018770348ee50ecb5f31c9b6dd161c90f70bdae97eb5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335736"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Se si desidera abilitare o disabilitare l'invio di messaggi di posta elettronica in Microsoft Teams, consulta [Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per l'Audioconferenza. A volte, tuttavia, si vuole ridurre il numero di messaggi di posta elettronica inviati Skype for Business utenti. In tal caso, puoi disabilitare l'invio dei messaggi posta elettronica.
  
Se si disabilita l'invio di messaggi di posta elettronica, i messaggi di posta elettronica per i servizi di audioconferenza non verranno inviati agli utenti, inclusi i messaggi di posta elettronica per i quali gli utenti sono abilitati o disabilitati per le audioconferenze, quando il PIN viene reimpostato e quando cambia l'ID conferenza e il numero di telefono di conferenza predefinito.
  
Ecco un esempio del messaggio di posta elettronica inviato agli utenti quando sono abilitati per le audioconferenze:
  
![Posta elettronica per Audioconferenza](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>I messaggi di posta elettronica quando vengono inviati agli utenti?

- Sono disponibili diversi messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo che sono stati abilitati per le audioconferenze:
    
  - Quando una licenza di **Audioconferenza** viene loro assegnata.
    
  - Quando si reimposta manualmente il PIN di audioconferenza dell'utente.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Quando la licenza di **Audioconferenza** viene loro rimossa.
    
  - Quando il provider di servizi di audioconferenza di un utente viene modificato da Microsoft a un altro provider o **Nessuno**.
    
  - Quando il provider di servizi di audioconferenza di un utente viene modificato in Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Abilitare o disabilitare l'invio di posta elettronica agli utenti

È possibile usare l'interfaccia Skype for Business di amministrazione o Windows PowerShell per abilitare o disabilitare la posta elettronica inviata agli utenti.

 
![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**
    
1. **Nell'Skype for Business di amministrazione fare** clic su Audioconferenza nel riquadro di spostamento **sinistro.**
    
2. Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.
    
3. Fare clic su **Salva**.
    
    > [!TIP]
    > È inoltre possibile inviare un messaggio di posta elettronica a un utente con le impostazioni di Audioconferenza facendo clic su **Audioconferenza** > **Utenti**, selezionando l'utente e facendo clic su **Invia informazioni conferenza tramite posta elettronica**.  In questo caso, verrà inviato un messaggio di posta elettronica che include solo l'ID conferenza e il numero di telefono della conferenza, ma non il PIN.  Per [altre informazioni, vedere Inviare un messaggio di](send-an-email-to-a-user-with-their-dial-in-information.md) posta elettronica a un utente con le informazioni relative ai servizi di audioconferenza.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Uso di Windows PowerShell**
  
- Esegui il seguente comando per disabilitare l'invio di messaggi di posta elettronica: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Per assistenza su questo cmdlet, vedi [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).
    
## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

- Quando i messaggi di posta elettronica automatici sono disabilitati, è comunque possibile attivare manualmente l'invio di un messaggio di posta elettronica con l'ID conferenza e il numero di telefono usando l'Skype for Business di amministrazione. Tuttavia, in questo caso, il PIN non verrà incluso. Se si vuole reimpostare il PIN di audioconferenza e l'invio di messaggi di posta elettronica è disabilitato, è necessario inviarlo all'utente in un altro modo.
    
- L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- È possibile utilizzare questi cmdlet per risparmiare tempo o automatizzare questa operazione.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Messaggi di posta elettronica inviati agli utenti quando cambiano le impostazioni di audioconferenza](emails-sent-to-users-when-their-settings-change.md)

[Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza](send-an-email-to-a-user-with-their-dial-in-information.md)
