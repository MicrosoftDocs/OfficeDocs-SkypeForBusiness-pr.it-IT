---
title: Impostazione dei criteri di conferenza per la propria organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
- Setup
description: 'Le conferenze sono una parte importante di Skype for Business online: le conferenze consentono a gruppi di utenti di incontrarsi online per visualizzare diapositive e video, condividere applicazioni, scambiare file e comunicare e collaborare in altro modo.'
ms.openlocfilehash: 35cbafdbd69f3241cc1634e4edff455b4c35926d
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561657"
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
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
    Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Avviare una sessione di Windows PowerShell**
    
1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
    > [!NOTE]
    > Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [impostare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloccare i trasferimenti di file e la condivisione del desktop durante le riunioni

- Per creare un nuovo criterio per queste impostazioni, eseguire:
  > 
  > ```
  > New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  > ```
  > Vedere ulteriori informazioni sui cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
  > 
  > ```
  > Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  > ```
  > Vedere ulteriori informazioni sui cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .
    
  Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) per apportare modifiche al criterio esistente, quindi utilizzare il cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) per applicare le impostazioni ai propri utenti.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloccare la registrazione di conferenze e impedire che utenti anonimi partecipino alle riunioni

- Per creare un nuovo criterio per queste impostazioni, eseguire: 
  > 
  > ```
  > New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  > ```
  > Vedere ulteriori informazioni sui cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .
    
- Per assegnare il criterio creato ad Amos Marble, eseguire:
  > 
  > ```
  >  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  > ```
  > Vedere ulteriori informazioni sui cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .
    
Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) per applicare le impostazioni per gli utenti.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Impedire ai partecipanti anonimi di registrare le riunioni e agli utenti esterni di salvare il contenuto delle riunioni

- Per creare un nuovo criterio per queste impostazioni, eseguire:  
  > 
  > ```
  > New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  > ```
  > Vedere ulteriori informazioni sui cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
    
> 
>   ```
>   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
>   ```

Vedere ulteriori informazioni sui cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .
    
Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) per apportare modifiche al criterio esistente, quindi utilizzare il cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) per applicare le impostazioni ai propri utenti.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Trasferimenti di file bloccati punto-punto](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

  
 