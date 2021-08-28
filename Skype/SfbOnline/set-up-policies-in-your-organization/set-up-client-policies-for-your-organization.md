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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '[] I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.'
ms.openlocfilehash: e5fe976e3adb566c469d2c58a5d2b6a976776ac3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619252"
---
# <a name="set-up-client-policies-for-your-organization"></a>Impostazione dei criteri client per la propria organizzazione

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.
  
Le impostazioni dei criteri client possono essere configurate al momento della creazione di un criterio oppure è possibile usare il cmdlet **Set-CsClientPolicy** per modificare le impostazioni di un criterio esistente.
  
## <a name="set-your-client-policies"></a>Impostare i criteri client

> [!NOTE]
> Per tutte le impostazioni dei criteri client in Skype for Business Online, è necessario usare Windows PowerShell e non è possibile usare **l'interfaccia** di amministrazione Skype for Business **client.** 
  
### <a name="start-windows-powershell"></a>Avviare Windows PowerShell

> [!NOTE]
> Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente. Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online.
1. Installare il [Teams di PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti: 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Per altre informazioni sull'avvio di Windows PowerShell, vedere Connessione a tutti i servizi Microsoft 365 o Office 365 in un'unica finestra [di Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .
 
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

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business Online usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando è necessario eseguire più attività. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Bloccare i trasferimenti di file punto a punto](block-point-to-point-file-transfers.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
