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
description: Prima che le persone dell'organizzazione possano usare Skype Meeting Broadcast, è necessario abilitarlo. A questo scopo, è necessario sapere come usare Windows PowerShell. Se non si conosce il Windows PowerShell, è consigliabile assumere un partner Microsoft per eseguire questo passaggio.
ms.openlocfilehash: ab59348d32ef130df6b0de6e1eb65c92d0222e04
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097112"
---
# <a name="enable-skype-meeting-broadcast"></a>Abilitare Skype Meeting Broadcast

> [!IMPORTANT]
> Skype for Business online è in ritiro il 31 luglio 2021, quando l'accesso al servizio terminerà. Incoraggiamo i clienti a iniziare l'aggiornamento a Microsoft Teams, il client principale per le comunicazioni e il lavoro in team in Microsoft 365.

Prima che le persone dell'organizzazione possano usare Skype Meeting Broadcast, è necessario abilitarlo. A questo scopo, è necessario sapere come usare Windows PowerShell. Se non si conosce Windows PowerShell, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.



> [!NOTE]
> L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for Business (portale legacy). Tutte le impostazioni per la gestione di Skype for Business sono ora disponibili nell'interfaccia di amministrazione di Teams. Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Teams, è necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) dell'amministratore globale o dell'amministratore di Skype for Business. Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Abilitare Skype Meeting Broadcast usando l'interfaccia di amministrazione di Skype for Business

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

1. Accedere con l'account di amministratore globale o l'account di amministratore di Skype for Business all'indirizzo [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. Nell'interfaccia di amministrazione passare a **Interfaccia di amministrazione**  >  **Teams**.
    
3. **Nell'interfaccia di amministrazione di Teams,** vai a Riunioni online legacy **del** portale e quindi  >    >  seleziona **Abilita Skype Meeting Broadcast.**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Abilitare Skype Meeting Broadcast con PowerShell

1. Installare il [modulo di PowerShell di Teams.](/microsoftteams/teams-powershell-install)
    
2. Aprire un Windows PowerShell comando ed eseguire i comandi seguenti: 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. Confermare la configurazione corrente di Skype Meeting Broadcast eseguendo:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Verificare che il parametro  _EnableBroadcastMeeting_ sia impostato su `False` .
    
     ![Cmdlet Di abilitare l'organizzazione di Skype Meeting Broadcast.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Abilita Skype Meeting Broadcast per la tua organizzazione eseguendo:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    È possibile verificare che l'impostazione sia abilitata eseguendo di  `Get-CsBroadcastMeetingConfiguration` nuovo.
    
     ![Cmdlet di abilitazione dell'organizzazione di Skype Meeting Broadcast.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Dopo aver apportato la modifica, potrebbe essere necessario un'ora per rendere effettiva la modifica nel portale Skype Meeting Broadcast. 
  
10. Gli utenti possono ora tenere riunioni in broadcast con altri utenti dell'azienda. Per iniziare, indicarli a [Che cos'è Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurare la rete per la trasmissione di riunioni con partecipanti esterni

Se si ha un firewall e si vogliono tenere trasmissioni con persone esterne all'azienda (che non sono un'azienda federata), è necessario configurare la rete usando queste istruzioni: Configurare la rete per [Skype Meeting Broadcast.](set-up-your-network-for-skype-meeting-broadcast.md) 
  
Se non si ha esperienza nella configurazione del firewall, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.
  
Per ignorare questo passaggio e aggiungere un'altra attività alla federazione, vedere Consentire agli utenti di [contattare utenti skype for Business esterni.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) 
  
## <a name="related-topics"></a>Argomenti correlati

[Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
