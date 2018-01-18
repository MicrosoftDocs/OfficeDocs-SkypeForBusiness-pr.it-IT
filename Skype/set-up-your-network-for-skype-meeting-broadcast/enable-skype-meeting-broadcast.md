---
title: Abilitare la trasmissione riunione Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Le persone all'interno dell'organizzazione possono utilizzare Skype riunione trasmissione, è necessario abilitarla. A tale scopo, è necessario conoscere le modalità di utilizzo di Windows PowerShell. Se non si conosce Windows PowerShell, potrebbe essere necessario rivolgersi a un partner Microsoft per eseguire questo passaggio è."
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a>Abilitare la trasmissione riunione Skype

Le persone all'interno dell'organizzazione possono utilizzare Skype riunione trasmissione, è necessario abilitarla. A tale scopo, è necessario conoscere le modalità di utilizzo di Windows PowerShell. Se non si conosce Windows PowerShell, potrebbe essere necessario rivolgersi un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio è.
  
> [!CAUTION]
> Skype riunione trasmissione è disattivata per impostazione predefinita in quanto la distribuzione dei contenuti multimediali di una riunione di trasmissione utilizza contenuto di rete (CDN del Microsoft Azure) per garantire la scalabilità molto alta per supportare migliaia di persone che seguono una trasmissione. Il contenuto multimediale in blocchi passare attraverso la rete CDN è crittografato e la cache CDN con una durata limitata. Inoltre, il componente di Azure CDN potrebbe non ancora soddisfare tutti gli elementi delle clausole modello UE derivanti dalla direttiva sulla protezione dei dati dell'Unione europea. Se si attiva questa caratteristica, l'utente riconosce questo avviso. 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Abilitare Skype riunione trasmessi utilizzando il Skype per interfaccia di amministrazione di Business

1. Accedere con l'account amministratore globale di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. Nell'interfaccia di amministrazione di Office 365 andare a **Admin Center** > **Skype per le aziende**.
    
3. In **Skype per interfaccia di amministrazione di Business**, accedere alle **riunioni in linea** > **trasmettere le riunioni**e quindi selezionare **Abilita trasmissione riunione Skype**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Abilitare Skype riunione trasmissione tramite PowerShell

1. Verificare che sia in esecuzione versione 3.0 o versione successiva di Windows PowerShell.
    
1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
2. Dal **Menu Start**, scegliere **Windows PowerShell**.
    
3. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. Verificare la configurazione corrente Skype trasmissione riunione eseguendo:
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Verificare che il parametro _EnableBroadcastMeeting_ è impostato su `False`.
    
     ![Cmdlet Skype riunione trasmissione abilitare organizzazione.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Abilitare trasmissione riunione Skype per l'organizzazione mediante l'esecuzione:
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    È possibile verificare che l'impostazione viene abilitata eseguendo `Get-CsBroadcastMeetingConfiguration` nuovamente.
    
     ![Skype riunione trasmissione abilitare Cmdlet dell'organizzazione.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Dopo aver apportato le modifiche, potrebbero richiedere un'ora per rendere effettive nel portale di trasmissione riunione Skype. 
  
6. Gli utenti possono ora riunisce trasmissione con altri utenti nell'azienda. Per ottenere tali introduttiva, puntino al [che cos'è una riunione Skype trasmissione?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurazione della rete per le riunioni con partecipanti esterni di trasmissione

Se è presente un firewall e si desidera mantenere le trasmissioni con utenti esterni all'azienda (che non sono un'azienda federata), è necessario configurare la rete queste istruzioni: [configurazione di rete per la trasmissione riunione Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Se non si è pratici di configurazione del firewall, potrebbe essere necessario rivolgersi un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio è.
  
Per ignorare questo passaggio e invece aggiungere un'altra business per la federazione, vedere [Consenti agli utenti di contatti esterni Skype per gli utenti aziendali](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Argomenti correlati

[Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

