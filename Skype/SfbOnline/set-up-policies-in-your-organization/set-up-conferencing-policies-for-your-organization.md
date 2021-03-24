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
ms.openlocfilehash: f4c8831408ed5c17073456306c0f48add73161ff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100522"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Impostazione dei criteri di conferenza per la propria organizzazione

[] Le conferenze sono una parte importante di Skype for Business online: le conferenze consentono a gruppi di utenti di incontrarsi online per visualizzare diapositive e video, condividere applicazioni, scambiare file e comunicare e collaborare in altro modo.
  
È importante mantenere il controllo sulle conferenze e sulle impostazioni di conferenza. In alcuni casi, ci possono essere problemi di sicurezza: per impostazione predefinita chiunque, compresi gli utenti non autenticati, può partecipare alle riunioni e salvare qualsiasi diapositiva o dispensa distribuita durante tali riunioni. Inoltre, ci potrebbero essere preoccupazioni di carattere legale. Per esempio, per impostazione predefinita i partecipanti sono autorizzati a fare annotazioni sui contenuti condivisi; tuttavia, queste annotazioni non vengono salvate quando viene archiviata la riunione. Se è necessario che l'organizzazione tenga un registro di tutte le comunicazioni elettroniche, può essere utile disabilitare le annotazioni. 
  
In Skype for Business online, le conferenze vengono gestite tramite criteri di conferenza. I criteri di conferenza determinano le caratteristiche e le funzionalità che possono essere utilizzate in una conferenza, dalla possibilità di includere audio e video via IP nella conferenza al numero massimo di persone che possono partecipare a una riunione. I criteri di conferenza possono essere configurati in ambito globale o per ciascun utente. Questo dà agli amministratori moltissima flessibilità quando si tratta di decidere quali funzionalità saranno messe a disposizione di quali gli utenti.
  
Le impostazioni dei criteri possono essere configurate al momento della creazione di un criterio; alternativamente, è possibile usare il cmdlet **Set-CsConferencingPolicy** per modificare le impostazioni di un criterio esistente.
  
## <a name="set-your-conferencing-policies"></a>Impostare i criteri di conferenza

> [!NOTE]
> Per tutte le impostazioni dei criteri di conferenza in Skype for Business online è necessario utilizzare Windows PowerShell e **non è possibile** utilizzare l' **interfaccia di amministrazione di Skype for Business**. 

### <a name="start-windows-powershell"></a>Avviare Windows PowerShell

 > [!Note]
> Skype for Business Online Connector fa attualmente parte dell'ultimo modulo di PowerShell di Teams. Se si usa l'ultima versione pubblica di Teams PowerShell, non è necessario installare Skype for Business Online Connector.
1. Installare il [modulo di PowerShell di Teams.](/microsoftteams/teams-powershell-install)
    
2. Aprire un Windows PowerShell comando ed eseguire i comandi seguenti: 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi [di Microsoft 365 o Office 365 in](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) un'unica finestra di Windows PowerShell o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloccare i trasferimenti di file e la condivisione del desktop durante le riunioni

- Per creare un nuovo criterio per queste impostazioni, eseguire:
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   Per altre informazioni, vedere il cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   Per altre informazioni, vedere il cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
  Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) per apportare modifiche al criterio esistente, quindi utilizzare il cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) per applicare le impostazioni ai propri utenti.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloccare la registrazione di conferenze e impedire che utenti anonimi partecipino alle riunioni

- Per creare un nuovo criterio per queste impostazioni, eseguire: 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   Per altre informazioni, vedere il cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Per assegnare il criterio creato ad Amos Marble, eseguire:
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   Per altre informazioni, vedere il cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) per applicare le impostazioni agli utenti.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Impedire ai partecipanti anonimi di registrare le riunioni e agli utenti esterni di salvare il contenuto delle riunioni

- Per creare un nuovo criterio per queste impostazioni, eseguire:  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   Per altre informazioni, vedere il cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

Per altre informazioni, vedere il cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) per apportare modifiche al criterio esistente, quindi utilizzare il cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) per applicare le impostazioni ai propri utenti.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più sulle Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che può semplificare il lavoro quotidiano, quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Bloccare i trasferimenti di file punto a punto](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

  
