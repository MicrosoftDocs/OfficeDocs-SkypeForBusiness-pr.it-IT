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
f1keywords: None
ms.custom:
- SMB
description: Prima che gli utenti dell'organizzazione possano usare Skype meeting broadcast, è necessario abilitarlo. A questo scopo, devi sapere come usare Windows PowerShell. Se non si conosce Windows PowerShell, è consigliabile assumere un partner Microsoft per eseguire questo passaggio.
ms.openlocfilehash: edf9c372a98da9e09d7e9040c6d035e389c8b1ec
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989141"
---
# <a name="enable-skype-meeting-broadcast"></a>Abilitare Skype Meeting Broadcast

Prima che gli utenti dell'organizzazione possano usare Skype meeting broadcast, è necessario abilitarlo. A questo scopo, devi sapere come usare Windows PowerShell. Se non si conosce Windows PowerShell, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Abilitare Skype meeting broadcast con l'interfaccia di amministrazione di Skype for business

![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**

1. Accedere con l'account di amministratore globale di Office 365 o con l'account di [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)amministratore di Skype for business.
    
2. Nell'interfaccia di amministrazione accedere a**Teams**di interfaccia di **Amministrazione** > .
    
3. Nell'interfaccia di **amministrazione di teams**, passa a**riunioni broadcast** **legacy Portal** > **online** > e quindi seleziona **Abilita Skype meeting broadcast**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Abilitare Skype meeting broadcast tramite PowerShell

1. Verificare che sia in esecuzione la versione 3,0 o successiva di Windows PowerShell.
    
2. A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.
    
3. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
4. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0. Quando richiesto, riavviare il computer.
    
5. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
6. Scegliere **Windows PowerShell**dal **menu Start**.
    
7. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. Conferma la configurazione corrente di Skype meeting broadcast eseguendo:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Verificare che il parametro _EnableBroadcastMeeting_ sia impostato su `False`.
    
     ![Cmdlet per l'organizzazione di Skype meeting broadcast.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Abilitare Skype meeting broadcast per l'organizzazione eseguendo:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    È possibile verificare che l'impostazione sia abilitata eseguendo `Get-CsBroadcastMeetingConfiguration` di nuovo.
    
     ![Cmdlet per l'organizzazione di Skype meeting broadcast.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Dopo aver apportato la modifica, il portale di Skype meeting broadcast può richiedere fino a un'ora. 
  
10. Gli utenti possono ora tenere riunioni broadcast con altri utenti nella tua azienda. Per iniziare, posizionare il puntatore su [Skype meeting broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurare la rete per la trasmissione di riunioni con partecipanti esterni

Se si dispone di un firewall e si vogliono tenere le trasmissioni broadcast con persone esterne all'azienda (che non sono una società federata), è necessario configurare la rete usando queste istruzioni: configurare [la rete per Skype meeting broadcast](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Se non si ha esperienza con la configurazione del firewall, prendere in considerazione l'assunzione di un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.
  
Per ignorare questo passaggio e aggiungere un altro business alla Federazione, vedere [consentire agli utenti di contattare utenti Skype for business esterni](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Argomenti correlati

[Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
