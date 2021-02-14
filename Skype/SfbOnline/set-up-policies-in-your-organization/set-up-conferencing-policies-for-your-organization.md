---
title: Impostazione dei criteri di conferenza per la propria organizzazione
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
- Setup
description: 'Le conferenze sono una parte importante di Skype for Business online: le conferenze consentono a gruppi di utenti di incontrarsi online per visualizzare diapositive e video, condividere applicazioni, scambiare file e comunicare e collaborare in altro modo.'
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814755"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Impostazione dei criteri di conferenza per la propria organizzazione

[] Le conferenze sono una parte importante di Skype for Business online: le conferenze consentono a gruppi di utenti di incontrarsi online per visualizzare diapositive e video, condividere applicazioni, scambiare file e comunicare e collaborare in altro modo.
  
È importante mantenere il controllo sulle conferenze e sulle impostazioni di conferenza. In alcuni casi, ci possono essere problemi di sicurezza: per impostazione predefinita chiunque, compresi gli utenti non autenticati, può partecipare alle riunioni e salvare qualsiasi diapositiva o dispensa distribuita durante tali riunioni. Inoltre, ci potrebbero essere preoccupazioni di carattere legale. Per esempio, per impostazione predefinita i partecipanti sono autorizzati a fare annotazioni sui contenuti condivisi; tuttavia, queste annotazioni non vengono salvate quando viene archiviata la riunione. Se è necessario che l'organizzazione tenga un registro di tutte le comunicazioni elettroniche, può essere utile disabilitare le annotazioni. 
  
In Skype for Business online, le conferenze vengono gestite tramite criteri di conferenza. I criteri di conferenza determinano le caratteristiche e le funzionalità che possono essere utilizzate in una conferenza, dalla possibilità di includere audio e video via IP nella conferenza al numero massimo di persone che possono partecipare a una riunione. I criteri di conferenza possono essere configurati in ambito globale o per ciascun utente. Questo dà agli amministratori moltissima flessibilità quando si tratta di decidere quali funzionalità saranno messe a disposizione di quali gli utenti.
  
Le impostazioni dei criteri possono essere configurate al momento della creazione di un criterio; alternativamente, è possibile usare il cmdlet **Set-CsConferencingPolicy** per modificare le impostazioni di un criterio esistente.
  
## <a name="set-your-conferencing-policies"></a>Impostare i criteri di conferenza

> [!NOTE]
> Per tutte le impostazioni dei criteri di conferenza in Skype for Business online è necessario utilizzare Windows PowerShell e **non è possibile** utilizzare l' **interfaccia di amministrazione di Skype for Business**. 
  
### <a name="verify-and-start-windows-powershell"></a>Verificare e avviare Windows PowerShell

- **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
    
    1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
        
    2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
        
    3. Se non si ha la versione 3.0 o successiva, è necessario scaricare e installare gli aggiornamenti per Windows PowerShell. Vedere [Windows Management Framework 4.0 per](https://go.microsoft.com/fwlink/?LinkId=716845) scaricare e aggiornare Windows PowerShell alla versione 4.0. Quando richiesto, riavviare il computer.
        
    4. Dovrai inoltre installare il modulo Windows PowerShell per Teams che ti consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online.
    
    Per altre informazioni, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in un'unica Windows PowerShell singola.](https://technet.microsoft.com/library/dn568015.aspx)
    
- **Avviare una sessione di Windows PowerShell**
    
    1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
        
    2. Nella finestra **Windows PowerShell** connessione a Microsoft 365 o Office 365 eseguendo:
        
     > [!NOTE]
     > Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
     >
     > Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in](https://technet.microsoft.com/library/dn568015.aspx) un'unica finestra di Windows PowerShell oppure Configurare il computer per [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloccare i trasferimenti di file e la condivisione del desktop durante le riunioni

- Per creare un nuovo criterio per queste impostazioni, eseguire:
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   Altre informazioni sul cmdlet [New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   Altre informazioni sul cmdlet [Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)
    
  Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) per apportare modifiche al criterio esistente, quindi utilizzare il cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) per applicare le impostazioni ai propri utenti.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloccare la registrazione di conferenze e impedire che utenti anonimi partecipino alle riunioni

- Per creare un nuovo criterio per queste impostazioni, eseguire: 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   Altre informazioni sul cmdlet [New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)
    
- Per assegnare il criterio creato ad Amos Marble, eseguire:
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   Altre informazioni sul cmdlet [Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)
    
Se hai già creato un criterio, puoi utilizzare il cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) per applicare le impostazioni agli utenti.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Impedire ai partecipanti anonimi di registrare le riunioni e agli utenti esterni di salvare il contenuto delle riunioni

- Per creare un nuovo criterio per queste impostazioni, eseguire:  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   Altre informazioni sul cmdlet [New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

Altre informazioni sul cmdlet [Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)
    
Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) per apportare modifiche al criterio esistente, quindi utilizzare il cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) per applicare le impostazioni ai propri utenti.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell puoi gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che ti semplifica il lavoro quotidiano, quando hai più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Bloccare i trasferimenti di file punto a punto](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

  
 
