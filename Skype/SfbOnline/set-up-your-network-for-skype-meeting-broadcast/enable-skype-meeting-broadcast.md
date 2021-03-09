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
description: Prima che le persone nella tua organizzazione possano utilizzare Skype Meeting Broadcast, devi attivarlo. A questo scopo, è necessario sapere come usare Windows PowerShell. Se non si conosce il Windows PowerShell, è consigliabile assumere un partner Microsoft per eseguire questo passaggio.
ms.openlocfilehash: fed56c850d1d909bdd72bda0eb8c1dcd24df0f10
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568892"
---
# <a name="enable-skype-meeting-broadcast"></a>Abilitare Skype Meeting Broadcast

> [!IMPORTANT]
> Skype for Business online verrà ritirato il 31 luglio 2021, data in cui l'accesso al servizio terminerà. Consigliamo ai clienti di iniziare l'aggiornamento a Microsoft Teams, il client di base per le comunicazioni e il lavoro in team in Microsoft 365.

Prima che le persone nella tua organizzazione possano utilizzare Skype Meeting Broadcast, devi attivarlo. A questo scopo, è necessario sapere come usare Windows PowerShell. Se non si conosce il Windows PowerShell, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.



> [!NOTE]
> L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for Business (portale legacy). Tutte le impostazioni per la gestione di Skype for Business sono ora disponibili nell'interfaccia di amministrazione di Teams. Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Teams, è necessario disporre del ruolo di amministratore di [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) come amministratore globale o amministratore di Skype for Business. Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Abilitare Skype Meeting Broadcast con l'interfaccia di amministrazione di Skype for Business

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

1. Accedi con il tuo account di amministratore globale o con l'account amministratore di Skype for Business all'indirizzo [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. Nell'interfaccia di amministrazione passare a **Team delle interfaccia di**  >  **amministrazione.**
    
3. **Nell'interfaccia di amministrazione di Teams,** vai a Riunioni broadcast del **portale** legacy e  >  **riunioni online,** quindi  >  seleziona Abilita Skype **Meeting Broadcast.**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Abilitare Skype Meeting Broadcast con PowerShell

1. Installare il [modulo Teams di PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Aprire un Windows PowerShell comando ed eseguire i comandi seguenti: 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. Conferma la configurazione corrente di Skype Meeting Broadcast eseguendo:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Verificare che il  _parametro EnableBroadcastMeeting_ sia impostato su `False` .
    
     ![Cmdlet per abilitare Skype Meeting Broadcast nell'organizzazione.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Abilitare Skype Meeting Broadcast per l'organizzazione eseguendo:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Per verificare che l'impostazione sia abilitata, eseguire di  `Get-CsBroadcastMeetingConfiguration` nuovo l'applicazione.
    
     ![Cmdlet per abilitare Skype Meeting Broadcast nell'organizzazione.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Dopo aver apportato la modifica, l'applicazione nel portale di Skype Meeting Broadcast può richiedere fino a un'ora. 
  
10. Gli utenti possono ora tenere riunioni in broadcast con altri utenti della tua azienda. Per iniziare, indicargli che [cos'è Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurare la rete per la trasmissione delle riunioni con partecipanti esterni

Se hai un firewall e vuoi tenere trasmissioni con persone esterne all'azienda (che non sono aziende federate), devi configurare la rete nel modo seguente: Configurare la rete per [Skype Meeting Broadcast.](set-up-your-network-for-skype-meeting-broadcast.md) 
  
Se non hai esperienza nella configurazione del firewall, può essere utile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per fare questo passaggio.
  
Per ignorare questo passaggio e aggiungere un'altra azienda alla federazione, vedere Consentire agli utenti di [contattare utenti Skype for Business esterni.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) 
  
## <a name="related-topics"></a>Argomenti correlati

[Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
