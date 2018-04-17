---
title: Change the settings for an Audio Conferencing bridge
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/03/2018
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Get the steps you need to change settings for a conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business or Microsoft Teams apps. "
ms.openlocfilehash: 727392bc81bce2fb3cfd84029e6a275e1eed3e24
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Change the settings for an Audio Conferencing bridge

When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. These phone numbers are used when callers dial in to a meeting. The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.
  
The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings. PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.

  > [!IMPORTANT]
  > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 

> [!CAUTION]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-and-skype-for-business-admin-center"></a>Using the Microsoft Teams and Skype for Business Admin Center

1. In the left navigation, go to **Meetings** > **Conference bridges**. 

2. At the top of the **Conference bridges** page, click **Bridge settings**. 

3. In the **Bridge settings** pane, select: 
  - **Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.
    
    When you turn on **Meeting entry and exit notifications**, you can select these options:
    
  - **Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.
    
  - **Tones** When users dial in to a meeting, an audio tone will be played when they join it.
      
  - **Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.

4. To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.

5. To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.
    See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.
 
6. Click **Apply**. 

## <a name="using-skype-for-business-admin-center"></a>Using Skype for Business admin center

 **Set up the meeting experience when callers join a meeting**
    
1. In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. On the **Microsoft bridge settings** page, under **Meeting join experience**, select:
    
  - **Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.
    
    When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:
    
  - **Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.
    
  - **Tones** When users dial in to a meeting, an audio tone will be played when they join it.
  
  - **Ask callers to record their name before joining the meeting** This is selected by default. If you clear the check box, callers won't be asked to record their name before they join a meeting.
    
3. Vedi **Modificare le impostazioni per un bridge per audioconferenza**.
    
**Set the PIN length for meetings**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.
    
4. On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.
    
    > [!IMPORTANT]
    > The PIN must be between 4 and 12 digits. 
  
**Select whether to send email to your users**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.
    
4. On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.
    
    See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.
    
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Configurare l’audioconferenza](set-up-audio-conferencing.md)
