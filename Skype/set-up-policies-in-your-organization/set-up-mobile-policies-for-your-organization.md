---
title: Impostare i criteri per dispositivi mobili per l'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "È possibile impostare come cui gli utenti possono connettersi Skype, Business online utilizzando il Skype per app Business nei dispositivi mobili, ad esempio una caratteristica che consente agli utenti di effettuare e ricevere chiamate telefoniche sul telefono cellulare utilizzando il numero di telefono dell'ufficio anziché il numero di cellulare numero. Criteri per dispositivi mobili anche utilizzabile per richiedere connessioni Wi-Fi quando effettuare o ricevere chiamate."
ms.openlocfilehash: 0772091e33043ed9ce5019b5c26ec8857d158260
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Impostare i criteri per dispositivi mobili per l'organizzazione

È possibile impostare come cui gli utenti possono connettersi Skype, Business online utilizzando il Skype per app Business nei dispositivi mobili, ad esempio una caratteristica che consente agli utenti di effettuare e ricevere chiamate telefoniche sul telefono cellulare utilizzando il numero di telefono dell'ufficio anziché il numero di cellulare numero. Criteri per dispositivi mobili anche utilizzabile per richiedere connessioni Wi-Fi quando effettuare o ricevere chiamate.
  
Impostazioni di criteri per dispositivi mobili possono essere configurate durante la creazione di un criterio oppure è possibile utilizzare il cmdlet **Set-CsMobilityPolicy** per modificare le impostazioni di un criterio esistente.
  
## <a name="set-your-mobile-policies"></a>Impostare i criteri di mobilità

> [!NOTE]
> Per tutte le impostazioni dei criteri per dispositivi mobili in Skype Business online, è necessario utilizzare Windows PowerShell e non è **possibile utilizzare** **Skype per interfaccia di amministrazione di Business**. 
  
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

  Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype Business online tramite Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Richiedere una connessione Wi-Fi per il video per un utente

- Per creare un nuovo criterio per queste impostazioni, eseguire:
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  Vedere ulteriori informazioni sui cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  Vedere ulteriori informazioni sui cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .
    
  Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) per applicare l'impostazione per gli utenti.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Impedire a un utente di usare l'app di Skype for Business

- Per creare un nuovo criterio per queste impostazioni, eseguire:
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  Vedere ulteriori informazioni sui cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .
    
- Per assegnare il criterio creato ad Amos Marble, eseguire:  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  Vedere ulteriori informazioni sui cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .
    
  Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) per applicare l'impostazione per gli utenti.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Impedire a un utente di effettuare chiamate voice over IP utilizzando un dispositivo mobile

- Per creare un nuovo criterio per queste impostazioni, eseguire:
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  Vedere ulteriori informazioni sui cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  Vedere ulteriori informazioni sui cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .
    
Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) per applicare l'impostazione per gli utenti.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzati](create-custom-external-access-policies.md)

[Trasferimenti di file bloccati punto-punto](block-point-to-point-file-transfers.md)

[Impostare i criteri client per l'organizzazione](set-up-client-policies-for-your-organization.md)

[Impostare i criteri relativi alle conferenze nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

