---
title: Attivare o disattivare il precaricamento dei contenuti delle riunioni tramite Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 079d0642158aa6d28b3c92a63e77afa0a0024d94
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814585"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Attivare o disattivare il precaricamento dei contenuti delle riunioni tramite Outlook

Gli utenti possono precaricare contenuti, file o allegati allegati a una convocazione di riunione di Outlook per una riunione Skype for Business online, ma è possibile attivarla o disattivarla. È attivata per impostazione predefinita per tutte le organizzazioni che usano Skype for Business online. Vedere come [Precaricare gli allegati per una riunione Skype for Business](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).
  
> [!NOTE]
> Attualmente, non sono disponibili cmdlet in Skype for Business online per l'impostazione o la visualizzazione di valori online per _MaxContentStorageMB_ e _MaxUploadFileMB._ Sono disponibili solo per le distribuzioni locali. È importante sapere che il contenuto non verrà caricato in una riunione se il contenuto allegato supera il _valore MaxUploadFileSizeMB_ o se viene raggiunto il limite _MaxContentStorageMB._
  
## <a name="to-get-you-started"></a>Per iniziare

### 

 **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
  
1. A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Vedere [Windows Management Framework 4.0 per](https://go.microsoft.com/fwlink/?LinkId=716845) scaricare e aggiornare Windows PowerShell alla versione 4.0. Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
Per altre informazioni, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in un'unica Windows PowerShell singola.](https://technet.microsoft.com/library/dn568015.aspx)
  
### 

 **Avviare una sessione di Windows PowerShell**
  
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
  
## <a name="turning-it-on-or-off"></a>Attivazione o disattivazione del precaricamento

La possibilità di precaricare il contenuto allegato a una convocazione di riunione di Outlook per le riunioni Skype for Business Online è attivata per impostazione predefinita, ma potrebbe essere necessario impedire agli utenti dell'organizzazione di precaricare il contenuto delle riunioni.
  
> [!IMPORTANT]
> Questa impostazione può essere attivata o disattivata solo per l'intera organizzazione; non è possibile attivarla o disattivarla per un singolo utente. 
  
 **Per disattivarla, aprire Windows PowerShell e procedere come segue:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Se si desidera riattivarla, aprire Windows PowerShell e procedere come segue:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell puoi gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che ti semplifica il lavoro quotidiano, quando hai più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
