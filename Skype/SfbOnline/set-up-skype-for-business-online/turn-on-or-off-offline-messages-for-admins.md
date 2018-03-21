---
title: Attivare o disattivare i messaggi offline per gli amministratori
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 9aebaf38bf4c936e964696e89a982d822a134507
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2018
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Attivare o disattivare i messaggi offline per gli amministratori

È possibile inviare Skype per messaggi immediati Business ai contatti anche se non sono connessi. Questa funzione consente di far sapere ai contatti che si sta tentando di mettersi in contatto con loro. Non è necessario attendere che gli utenti siano online prima di inviare loro un messaggio. 
  
Per i messaggi offline, è importante sapere:
  
- I messaggi offline non verranno archiviati nella cassetta postale dell'utente.
    
- Cassetta postale dell'utente verranno inviati messaggi non in linea e verrà inviate notifiche all'utente al momento dell'accesso a Skype per le aziende.
    
- Se lo stato del destinatario del messaggio è impostato su **Non disturbare** o **parola presentazione**, ricevono un messaggio senza risposta inviato da Skype del destinatario per il client di Business.
    
Per ulteriori informazioni, vedere [utilizzo offline messaggistica in Skype per le aziende](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).
  
## <a name="to-get-you-started"></a>Per iniziare

### 

 **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
  
1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
### 

 **Avviare una sessione di Windows PowerShell**
  
1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
    > [!NOTE]
    > Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype Business online tramite Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
## <a name="turning-on-or-off-offline-im"></a>Attivazione o disattivazione della messaggistica offline

> [!NOTE]
> Messaggi non in linea sono **solo** disponibili nella versione più recente di Skype a portata di clic per client di Business e non sono disponibili quando viene utilizzato un precedenti Skype Click-to-Run for Business o un file MSI utilizzato per installare Skype per client di Business.
  
Per abilitare o disabilitare messaggi non in linea inviare messaggi non in linea per gli utenti dell'organizzazione, impostare _EnableIMAutoArchiving_ su `True` o `False`. Per impostazione predefinita, questo è impostato su `True`.
  
Per disattivarli, utilizzare il cmdlet **Set-CsClientPolicy** ed eseguire:
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Per abilitare o disabilitare l'invio di messaggi non in linea messaggi non in linea per un utente, impostare _EnableIMAutoArchiving_ su `True` o `False`. Per impostazione predefinita, è impostato su  `True`. È possibile utilizzare un criterio esistente o crearne uno simile all'esempio seguente.
  
> 
  ```
  New-CsClientPolicy -Identity OfflineIM
  ```

> 
  ```
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  ```

> 
  ```
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a>Commenti e suggerimenti?
Per inviare commenti e suggerimenti prodotto o per consentire us sapere come ci si limita, vedere [Skype per commenti e suggerimenti Business](https://www.skypefeedback.com).