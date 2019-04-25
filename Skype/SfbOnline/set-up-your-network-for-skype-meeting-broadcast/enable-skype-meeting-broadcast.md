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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Le persone all'interno dell'organizzazione possono utilizzare Skype riunione trasmissione, è necessario abilitarla. A tale scopo, è necessario conoscere le modalità di utilizzo di Windows PowerShell. Se non si conosce Windows PowerShell, potrebbe essere necessario rivolgersi a un partner Microsoft per eseguire questo passaggio è.
ms.openlocfilehash: 699b82af07b263331ee5508326bf3e7ed015848e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226820"
---
# <a name="enable-skype-meeting-broadcast"></a>Abilitare Skype Meeting Broadcast

Le persone all'interno dell'organizzazione possono utilizzare Skype riunione trasmissione, è necessario abilitarla. A tale scopo, è necessario conoscere le modalità di utilizzo di Windows PowerShell. Se non si conosce Windows PowerShell, potrebbe essere necessario rivolgersi un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio è.

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Abilitare Skype riunione trasmessi utilizzando il Skype per interfaccia di amministrazione di Business

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

1. Accedere con l'account amministratore globale di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. Nell'interfaccia di amministrazione di Office 365 andare a **Admin Center** > **Skype per le aziende**.
    
3. In **Skype per interfaccia di amministrazione di Business**, accedere alle **riunioni in linea** > **trasmettere le riunioni**e quindi selezionare **Abilita trasmissione riunione Skype**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Abilitare Skype riunione trasmissione tramite PowerShell

1. Verificare che sia in esecuzione versione 3.0 o versione successiva di Windows PowerShell.
    
2. A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.
    
3. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
4. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
5. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
6. Dal **Menu Start**, scegliere **Windows PowerShell**.
    
7. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
   ```
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. Verificare la configurazione corrente Skype trasmissione riunione eseguendo:
    
   ```
   Get-CsBroadcastMeetingConfiguration
   ```

    Verificare che il parametro _EnableBroadcastMeeting_ è impostato su `False`.
    
     ![Cmdlet Skype riunione trasmissione abilitare organizzazione.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Abilitare trasmissione riunione Skype per l'organizzazione mediante l'esecuzione:
    
   ```
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    È possibile verificare che l'impostazione viene abilitata eseguendo `Get-CsBroadcastMeetingConfiguration` nuovamente.
    
     ![Skype riunione trasmissione abilitare Cmdlet dell'organizzazione.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Dopo aver apportato le modifiche, potrebbero richiedere un'ora per rendere effettive nel portale di trasmissione riunione Skype. 
  
10. Gli utenti possono ora riunisce trasmissione con altri utenti nell'azienda. Per ottenere tali introduttiva, puntino al [che cos'è una riunione Skype trasmissione?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurazione della rete per le riunioni con partecipanti esterni di trasmissione

Se è presente un firewall e si desidera mantenere le trasmissioni con utenti esterni all'azienda (che non sono un'azienda federata), è necessario configurare la rete queste istruzioni: [configurazione di rete per la trasmissione riunione Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Se non si è pratici di configurazione del firewall, potrebbe essere necessario rivolgersi un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio è.
  
Per ignorare questo passaggio e invece aggiungere un'altra business per la federazione, vedere [Consenti agli utenti di contatti esterni Skype per gli utenti aziendali](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Argomenti correlati

[Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 