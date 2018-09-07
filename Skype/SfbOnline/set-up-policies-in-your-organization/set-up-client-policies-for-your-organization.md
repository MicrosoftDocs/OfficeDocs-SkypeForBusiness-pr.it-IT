---
title: Impostazione dei criteri client per la propria organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.
ms.openlocfilehash: 791d54dd12e5f222958fd4513abdeca2433cbf16
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857862"
---
# <a name="set-up-client-policies-for-your-organization"></a>Impostazione dei criteri client per la propria organizzazione

[] I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.
  
Impostazioni dei criteri client possono essere configurate durante la creazione di un criterio oppure è possibile utilizzare il cmdlet **Set-CsClientPolicy** per modificare le impostazioni di un criterio esistente.
  
## <a name="set-your-client-policies"></a>Impostare i criteri client

> [!NOTE]
> Per tutte le impostazioni dei criteri client in Skype Business online, è necessario utilizzare Windows PowerShell e non è **possibile utilizzare** **Skype per interfaccia di amministrazione di Business**. 
  
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
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Disattivare le notifiche di presenza e le emoticon e impedire il salvataggio dei messaggi immediati

- Per creare un nuovo criterio per queste impostazioni, eseguire:
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  Vedere ulteriori informazioni sui cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  Vedere ulteriori informazioni sui cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) per applicare le impostazioni per gli utenti.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Abilitare URL o collegamenti ipertestuali perché siano cliccabili nei messaggi istantanei

- Per creare un nuovo criterio per queste impostazioni, eseguire:
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  Vedere ulteriori informazioni sui cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  Vedere ulteriori informazioni sui cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) per applicare le impostazioni per gli utenti.
  
### <a name="prevent-showing-recent-contacts"></a>Impedire di mostrare i contatti recenti

- Per creare un nuovo criterio per queste impostazioni, eseguire:
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  Vedere ulteriori informazioni sui cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Per assegnare il criterio creato ad Amos Marble, eseguire:
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  Vedere ulteriori informazioni sui cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
  Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) per applicare le impostazioni per gli utenti.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Trasferimenti di file bloccati punto-punto](block-point-to-point-file-transfers.md)

[Impostare i criteri relativi alle conferenze nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 