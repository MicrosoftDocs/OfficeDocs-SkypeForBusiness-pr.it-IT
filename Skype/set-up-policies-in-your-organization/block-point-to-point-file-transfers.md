---
title: "Block Point-to-Point file transfers"
ms.author: tonysmit
author: tonysmit
ms.date: 11/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
description: "In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings. However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization. Following the steps below, you can block P2P file transfers with federated organizations or partners."
---

# Block Point-to-Point file transfers

In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings. However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization. Following the steps below, you can block P2P file transfers with federated organizations or partners.
  
 A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners. For this scenario, you would need to do:
  
- Assign a conferencing policy with P2P file transfer enabled ( _EnableP2PFileTransfer_ set to _True_) to users in your organization.
    
- Create aglobal external user communication policy set to block external P2P file transfers ( _EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization. 
    
You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error. And if a user tries to send a file, they will receive a **File transfer is turned off** error.
  
To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it. The following minimum version of Skype for Business 2016 Click-to-Run client is required:
  
|**Type**|**Release date**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release for Current Channel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571.2006)  <br/> |
|Current Channel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571.2072)  <br/> |
|Deferred Channel  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files. 
  
## Verify and start Windows PowerShell

- **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
    
1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
    Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Avviare una sessione di Windows PowerShell**
    
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

    Per altre informazioni sull'avvio di Windows PowerShell, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o[Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
    
## Disable P2P file transfers for your organization

By default,  _EnableP2PFileTransfer_ is enabled on the organization's global policy. When it was created, your users were assigned the _BposSAllModality_ policy.
  
> To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level. To do that, run:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## Disable P2P file transfers for a user

- You can apply this to a user by creating a new policy and granting it to that user. To do that, run: 
    
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```

> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## Want to know more about Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    

