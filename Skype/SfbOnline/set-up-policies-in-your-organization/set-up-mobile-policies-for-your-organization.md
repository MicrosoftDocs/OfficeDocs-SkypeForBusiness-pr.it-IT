---
title: Impostazione dei criteri per dispositivi mobili per la propria organizzazione
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: È possibile configurare la modalità di connessione degli utenti a Skype for Business online usando l'app Skype for Business su dispositivi mobili, ad esempio una funzionalità che consente agli utenti di effettuare e ricevere chiamate sul proprio cellulare usando il numero di telefono dell'ufficio invece del numero di cellulare. I criteri di mobilità possono essere utilizzati anche per richiedere la presenza di connessioni Wi-Fi quando si effettuano o ricevono chiamate.
ms.openlocfilehash: b0e2f7524f300733840159eacfcf27bb54f5e815
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100492"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Impostazione dei criteri per dispositivi mobili per la propria organizzazione

È possibile configurare la modalità di connessione degli utenti a Skype for Business online usando l'app Skype for Business su dispositivi mobili, ad esempio una funzionalità che consente agli utenti di effettuare e ricevere chiamate sul proprio cellulare usando il numero di telefono dell'ufficio invece del numero di cellulare. I criteri di mobilità possono essere utilizzati anche per richiedere la presenza di connessioni Wi-Fi quando si effettuano o ricevono chiamate.
  
Le impostazioni dei criteri per dispositivi mobili possono essere configurate al momento della creazione di un criterio oppure è possibile usare il cmdlet **Set-CsMobilityPolicy** per modificare le impostazioni di un criterio esistente.
  
## <a name="set-your-mobile-policies"></a>Impostare i criteri di mobilità

> [!NOTE]
> Per tutte le impostazioni dei criteri per dispositivi mobili in Skype for Business online, è necessario usare Windows PowerShell e non è possibile usare **l'interfaccia** di amministrazione **di Skype for Business.** 
  
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
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Richiedere una connessione Wi-Fi per il video per un utente

- Per creare un nuovo criterio per queste impostazioni, eseguire:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
  Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) per applicare l'impostazione agli utenti.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Impedire a un utente di usare l'app di Skype for Business

- Per creare un nuovo criterio per queste impostazioni, eseguire:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Per assegnare il criterio creato ad Amos Marble, eseguire:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
  Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) per applicare l'impostazione agli utenti.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Impedire a un utente di effettuare chiamate voice over IP utilizzando un dispositivo mobile

- Per creare un nuovo criterio per queste impostazioni, eseguire:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) per applicare l'impostazione agli utenti.
  
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

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
