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
description: È possibile impostare la modalità di connessione degli utenti a Skype for Business online mediante l'app Skype for Business su dispositivi mobili, ad esempio una funzionalità che consente agli utenti di effettuare e ricevere chiamate sul cellulare utilizzando il numero di telefono dell'ufficio invece del numero di cellulare. I criteri dispositivi mobili possono essere utilizzati anche per richiedere Wi-Fi connessioni mobili durante l'esecuzione o la ricezione di chiamate.
ms.openlocfilehash: 5094a536a636300ea70a7d358e24ee5c0f511379
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814745"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Impostazione dei criteri per dispositivi mobili per la propria organizzazione

È possibile impostare la modalità di connessione degli utenti a Skype for Business online mediante l'app Skype for Business su dispositivi mobili, ad esempio una funzionalità che consente agli utenti di effettuare e ricevere chiamate sul cellulare utilizzando il numero di telefono dell'ufficio invece del numero di cellulare. I criteri dispositivi mobili possono essere utilizzati anche per richiedere Wi-Fi connessioni mobili durante l'esecuzione o la ricezione di chiamate.
  
Le impostazioni dei criteri per dispositivi mobili possono essere configurate al momento della creazione di un criterio oppure è possibile usare il cmdlet **Set-CsMobilityPolicy** per modificare le impostazioni di un criterio esistente.
  
## <a name="set-your-mobile-policies"></a>Impostare i criteri di mobilità

> [!NOTE]
> Per tutte le impostazioni dei criteri per dispositivi mobili in Skype for Business online, è necessario utilizzare Windows PowerShell e non è possibile **utilizzare l'interfaccia** di amministrazione **di Skype for Business.** 
  
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

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Richiedere una connessione Wi-Fi per il video per un utente

- Per creare un nuovo criterio per queste impostazioni, eseguire:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Altre informazioni sul cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Altre informazioni sul cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
  Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) per apportare modifiche al criterio esistente e quindi usare il cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) per applicare l'impostazione agli utenti.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Impedire a un utente di usare l'app di Skype for Business

- Per creare un nuovo criterio per queste impostazioni, eseguire:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Altre informazioni sul cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Per assegnare il criterio creato ad Amos Marble, eseguire:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Altre informazioni sul cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
  Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) per apportare modifiche al criterio esistente e quindi usare il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) per applicare l'impostazione agli utenti.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Impedire a un utente di effettuare chiamate voice over IP utilizzando un dispositivo mobile

- Per creare un nuovo criterio per queste impostazioni, eseguire:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Altre informazioni sul cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Altre informazioni sul cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) per apportare modifiche al criterio esistente e quindi usare il cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) per applicare l'impostazione agli utenti.
  
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

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 
