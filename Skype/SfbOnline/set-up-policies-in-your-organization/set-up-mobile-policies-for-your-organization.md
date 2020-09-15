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
description: Puoi configurare il modo in cui gli utenti si connettono a Skype for business online usando l'app Skype for business su dispositivi mobili, ad esempio una funzionalità che consente agli utenti di effettuare e ricevere chiamate telefoniche sul proprio telefono cellulare usando il proprio numero di telefono aziendale anziché il numero di cellulare. I criteri di mobilità possono essere usati anche per richiedere connessioni Wi-Fi durante la creazione o la ricezione di chiamate.
ms.openlocfilehash: 5094a536a636300ea70a7d358e24ee5c0f511379
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814745"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Impostazione dei criteri per dispositivi mobili per la propria organizzazione

Puoi configurare il modo in cui gli utenti si connettono a Skype for business online usando l'app Skype for business su dispositivi mobili, ad esempio una funzionalità che consente agli utenti di effettuare e ricevere chiamate telefoniche sul proprio telefono cellulare usando il proprio numero di telefono aziendale anziché il numero di cellulare. I criteri di mobilità possono essere usati anche per richiedere connessioni Wi-Fi durante la creazione o la ricezione di chiamate.
  
Le impostazioni dei criteri per dispositivi mobili possono essere configurate al momento della creazione di un criterio oppure puoi usare il cmdlet **Set-CsMobilityPolicy** per modificare le impostazioni di un criterio esistente.
  
## <a name="set-your-mobile-policies"></a>Impostare i criteri di mobilità

> [!NOTE]
> Per tutte le impostazioni dei criteri per dispositivi mobili in Skype for business online, è necessario utilizzare Windows PowerShell e non è possibile **usare** l'interfaccia di **amministrazione di Skype for business**. 
  
### <a name="verify-and-start-windows-powershell"></a>Verificare e avviare Windows PowerShell

- **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
    
    1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
        
    2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
        
    3. Se non si ha la versione 3,0 o successiva, è necessario scaricare e installare gli aggiornamenti in Windows PowerShell. Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0. Riavviare il computer quando viene richiesto.
        
    4. Sarà inoltre necessario installare il modulo di Windows PowerShell per Teams che consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online.
    
    Per saperne di più, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Avviare una sessione di Windows PowerShell**
    
    1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
        
    2. Nella finestra di **Windows PowerShell** connettersi a Microsoft 365 o Office 365 eseguendo:
        
       > [!NOTE]
       > Skype for Business Online Connector fa attualmente parte del modulo di PowerShell più recente di teams.
       >
       > Se si usa l'ultima [versione pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare il connettore Skype for business online.

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Richiedere una connessione Wi-Fi per il video per un utente

- Per creare un nuovo criterio per queste impostazioni, eseguire:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
  Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) per applicare l'impostazione agli utenti.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Impedire a un utente di usare l'app di Skype for Business

- Per creare un nuovo criterio per queste impostazioni, eseguire:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Per assegnare il criterio creato ad Amos Marble, eseguire:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
  Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) per applicare l'impostazione agli utenti.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Impedire a un utente di effettuare chiamate voice over IP utilizzando un dispositivo mobile

- Per creare un nuovo criterio per queste impostazioni, eseguire:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) per applicare l'impostazione agli utenti.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui potresti voler usare Windows PowerShell per gestire Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Bloccare i trasferimenti di file Point-to-Point](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 
