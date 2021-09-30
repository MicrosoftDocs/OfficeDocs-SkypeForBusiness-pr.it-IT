---
title: Avviare un'audioconferenza tramite telefono senza un PIN in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: "Informazioni su come abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione dall'interfaccia di amministrazione di Skype for Business o utilizzando uno script di PowerShell. "
ms.openlocfilehash: d420acff8d5822aa4badd8980481d67bd2eae35b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013370"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Avviare un'audioconferenza tramite telefono senza un PIN in Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Per informazioni sull'avvio di un'audioconferenza senza un PIN in Microsoft Teams, consulta [Avviare un'audioconferenza tramite telefono senza un PIN in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Può essere frustrante per gli utenti che a una riunione a una riunione possono accedere ascoltando musica nella sala d'attesa della riunione, perché l'organizzatore della riunione Skype for Business non ha avviato la riunione. 
  
Se l'organizzatore della riunione chiama per impostazione predefinita, è necessario un PIN per avviare una riunione. È possibile configurarla in modo che chiunque possa accedere a una riunione e non venga richiesto un PIN per avviare la riunione. Puoi usare l'interfaccia di amministrazione di Skype for Business per abilitare o disabilitare questa impostazione per un singolo utente.
  
Non è necessario un PIN per l'organizzatore della riunione se qualcuno ha avviato la riunione dall'app Skype for Business riunione. Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono. Il PIN per le riunioni viene inviato all'utente audio quando gli viene assegnata la licenza **di audioconferenza** e viene abilitato per le audioconferenze. Vedere [Inviare un messaggio di posta](send-an-email-to-a-user-with-their-dial-in-information.md) elettronica a un utente con le informazioni relative alle audioconferenze e i messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando cambiano le [impostazioni di audioconferenza.](emails-sent-to-users-when-their-settings-change.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione
    
1. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a **Utenti di servizi di audioconferenza.**  >   
    
2. Nell'elenco selezionare l'utente e nel riquadro Azioni fare clic su **Modifica.** 
    
3. Nella pagina delle proprietà dell'utente, **in** Opzioni riunione, selezionare o deselezionare Consenti ai chiamanti non autenticati di essere i primi **utenti di una riunione. In caso contrario, attenderà nella sala d'attesa finché un utente autenticato non partecipa**.
    
4. Fare clic su **Salva**. 


    
 **Tramite Windows PowerShell**
  
- Esegui il seguente comando: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

- Se si vuole reimpostare il PIN, vedere Reimpostare [il PIN di audioconferenza.](reset-the-audio-conferencing-pin.md)
    
- Se l'accesso anonimo o la richiesta di un PIN per avviare una riunione è disabilitata:
    
  - Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): a un chiamante verrà chiesto se è l'organizzatore; se dice sì, gli verrà richiesto il PIN e, dopo aver immesso il PIN, la riunione verrà avviata e l'utente si unirà alla riunione.
    
  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.
    
- Se l'accesso anonimo, o non richiede un PIN per avviare una riunione, è abilitato:
    
  - Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN. Poiché l'impostazione dell'organizzatore è disattivata, la riunione verrà avviata e i chiamanti anonimi si uniranno alla riunione.
    
  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche per più di un utente o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft all'indirizzo Scaricare e installare il modulo [Teams PowerShell.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
