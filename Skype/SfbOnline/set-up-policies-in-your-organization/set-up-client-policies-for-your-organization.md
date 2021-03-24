---
title: Impostazione dei criteri client per la propria organizzazione
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: '[] I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.'
ms.openlocfilehash: 3706e6b4fafe15aa8b799170001af61b837968da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100532"
---
# <a name="set-up-client-policies-for-your-organization"></a>Impostazione dei criteri client per la propria organizzazione

[] I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.
  
Le impostazioni dei criteri client possono essere configurate al momento della creazione di un criterio oppure è possibile usare il cmdlet **Set-CsClientPolicy** per modificare le impostazioni di un criterio esistente.
  
## <a name="set-your-client-policies"></a>Impostare i criteri client

> [!NOTE]
> Per tutte le impostazioni dei criteri client in Skype for Business online, è necessario usare Windows PowerShell e non è possibile usare **l'interfaccia** di amministrazione **di Skype for Business.** 
  
### <a name="start-windows-powershell"></a>Avviare Windows PowerShell

> [!NOTE]
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
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Disabilitare le emoticon e le notifiche sulla presenza e impedire il salvataggio di messaggistica istantanea

- Per creare un nuovo criterio per queste impostazioni, eseguire:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  Per altre informazioni, vedere il cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  Per altre informazioni, vedere il cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) per applicare le impostazioni agli utenti.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Abilitare URL o collegamenti ipertestuali perché siano cliccabili nei messaggi istantanei

- Per creare un nuovo criterio per queste impostazioni, eseguire:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  Per altre informazioni, vedere il cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  Per altre informazioni, vedere il cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) per applicare le impostazioni agli utenti.
  
### <a name="prevent-showing-recent-contacts"></a>Impedire di mostrare i contatti recenti

- Per creare un nuovo criterio per queste impostazioni, eseguire:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  Per altre informazioni, vedere il cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Per assegnare il criterio creato ad Amos Marble, eseguire:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  Per altre informazioni, vedere il cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
  Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) per applicare le impostazioni agli utenti.
  
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

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
