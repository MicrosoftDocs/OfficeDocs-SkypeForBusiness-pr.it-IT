---
title: Abilitare Skype Meeting Broadcast
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Prima che le persone dell'organizzazione possano usare Riunione Skype Broadcast, è necessario abilitarlo. A questo scopo, è necessario sapere come usare Windows PowerShell. Se non si conosce il Windows PowerShell, è consigliabile assumere un partner Microsoft per eseguire questo passaggio.
ms.openlocfilehash: 99e5464ac092f30edf2667dbfd772b11c41ca4a795893e1e3415a54cf566ee44
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339264"
---
# <a name="enable-skype-meeting-broadcast"></a>Abilitare Skype Meeting Broadcast

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Skype for Business Online è in ritiro il 31 luglio 2021, quando l'accesso al servizio terminerà. Incoraggiamo i clienti a iniziare l'aggiornamento a Microsoft Teams, il client principale per le comunicazioni e il lavoro in team in Microsoft 365.

Prima che le persone dell'organizzazione possano usare Riunione Skype Broadcast, è necessario abilitarlo. A questo scopo, è necessario sapere come usare Windows PowerShell. Se non si conosce il Windows PowerShell, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.



> [!NOTE]
> L Microsoft Teams di amministrazione ha sostituito l'Skype for Business di amministrazione (portale legacy). Tutte le impostazioni per la Skype for Business sono ora disponibili nell'Teams di amministrazione. È necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) di Amministratore globale o amministratore Skype for Business per gestire Skype for Business funzionalità di Teams di amministrazione. Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Abilitare Riunione Skype Broadcast tramite l'interfaccia Skype for Business di amministrazione

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

1. Accedere con l'account di amministratore globale o Skype for Business di amministrazione su [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. Nell'interfaccia di amministrazione passare a **Interfaccia di amministrazione**  >  **Teams**.
    
3. **Nell'Teams di amministrazione** passare **a** Riunioni online legacy del portale e quindi selezionare Abilita Riunione Skype  >    >   **Broadcast.**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Abilitare Riunione Skype broadcast tramite PowerShell

1. Installare il [modulo Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti: 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. Confermare la configurazione Riunione Skype broadcast eseguendo:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Verificare che il parametro  _EnableBroadcastMeeting_ sia impostato su `False` .
    
     ![Riunione Skype Cmdlet Per abilitare la trasmissione dell'organizzazione.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Abilitare Riunione Skype broadcast per l'organizzazione eseguendo:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    È possibile verificare che l'impostazione sia abilitata eseguendo di  `Get-CsBroadcastMeetingConfiguration` nuovo.
    
     ![Riunione Skype Cmdlet per abilitare la trasmissione dell'organizzazione.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Dopo aver apportato la modifica, l'applicazione della modifica nel portale di Riunione Skype Broadcast potrebbe richiedere fino a un'ora. 
  
10. Gli utenti possono ora tenere riunioni in broadcast con altri utenti dell'azienda. Per iniziare, scegliere Che [cos'è](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) un Riunione Skype Broadcast?
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurare la rete per la trasmissione di riunioni con partecipanti esterni

Se si ha un firewall e si vogliono tenere trasmissioni con persone esterne all'azienda (che non sono un'azienda federata), è necessario configurare la rete usando queste istruzioni: Configurare la rete [per Riunione Skype Broadcast](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Se non si ha esperienza nella configurazione del firewall, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.
  
Per ignorare questo passaggio e aggiungere un'altra azienda alla federazione, vedere Consentire agli utenti di contattare utenti Skype for Business [esterni](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Argomenti correlati

[Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
