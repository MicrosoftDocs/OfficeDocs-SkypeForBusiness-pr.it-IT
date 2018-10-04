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
description: Prima che le persone nella tua organizzazione possano usare Skype Meeting Broadcast, devi abilitarlo. Per eseguire questo passaggio devi sapere come usare Windows PowerShell. Se non conosci Windows PowerShell, può essere utile assumere un partner Microsoft che se ne occupi al posto tuo.
ms.openlocfilehash: 699b82af07b263331ee5508326bf3e7ed015848e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370864"
---
# <a name="enable-skype-meeting-broadcast"></a>Abilitare Skype Meeting Broadcast

[] Prima che le persone nella tua organizzazione possano usare Skype Meeting Broadcast, devi abilitarlo. Per eseguire questo passaggio devi sapere come usare Windows PowerShell. Se non conosci Windows PowerShell, può essere utile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) che se ne occupi al posto tuo.

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Abilitare Skype Meeting Broadcast con l'interfaccia di amministrazione di Skype for Business

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

1. Accedere con l'account amministratore globale di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. Nell'interfaccia di amministrazione di Office 365, passare a **Interfacce di amministrazione** > **Skype for Business**.
    
3. In **Skype per interfaccia di amministrazione di Business**, accedere alle **riunioni in linea** > **trasmettere le riunioni**e quindi selezionare **Abilita trasmissione riunione Skype**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Abilitare Skype Meeting Broadcast con PowerShell

1. Verifica che sia in esecuzione Windows PowerShell versione 3.0 o successiva.
    
2. Per verificare che sia in esecuzione la versione 3.0 o successive: **Menu Start** > **Windows PowerShell**.
    
3. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
4. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
5. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
6. Dal **Menu Start**, scegliere **Windows PowerShell**.
    
7. Nella finestra **Windows PowerShell**, stabilisci la connessione alla tua organizzazione Office 365 eseguendo:
    
   ```
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. Conferma la configurazione corrente di Skype Meeting Broadcast eseguendo:
    
   ```
   Get-CsBroadcastMeetingConfiguration
   ```

    Verifica che il parametro  _EnableBroadcastMeeting_ sia impostato su `False`.
    
     ![Cmdlet per abilitare Skype Meeting Broadcast nell'organizzazione.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Abilita Skype Meeting Broadcast per la tua organizzazione eseguendo:
    
   ```
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Puoi confermare che l'impostazione sia abilitata eseguendo di nuovo  `Get-CsBroadcastMeetingConfiguration`.
    
     ![Cmdlet per abilitare Skype Meeting Broadcast nell'organizzazione.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Dopo aver apportato la modifica, potrebbe essere necessario attendere fino a un'ora perché questa diventi effettiva nel portale Skype Meeting Broadcast. 
  
10. Ora i tuoi utenti possono tenere riunioni in broadcast con altri utenti nell'azienda. Come prime indicazioni, fai riferimento a [Informazioni su Skype Meeting Broadcast](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d).
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurare la rete per le riunioni in broadcast con partecipanti esterni

Se hai un firewall e vuoi trasmettere webinar o altre riunioni a partecipanti all'esterno dell'azienda (che non siano aziende federate), devi configurare la rete secondo queste istruzioni: [Configurare la rete per Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Se non hai dimestichezza con la configurazione del firewall, può essere utile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) che se ne occupi al posto tuo.
  
Per tralasciare questo passaggio e aggiungere un'altra azienda alla federazione, consulta [Consentire agli utenti di contattare utenti Skype for Business esterni](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>See also

[Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 