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
ms.openlocfilehash: b6ff40e34c6459a75d0b79a8d750902a3457e00d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239109"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Attivare o disattivare il precaricamento dei contenuti delle riunioni tramite Outlook

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Gli utenti possono precaricare contenuto, file o allegati Outlook una convocazione di riunione a una riunione di Skype for Business Online, ma è possibile attivarla o disattivarla. È attivata per impostazione predefinita per tutte le organizzazioni che usano Skype for Business Online. Vedere come [Precaricare gli allegati per una riunione Skype for Business](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).
  
> [!NOTE]
> Attualmente non sono disponibili cmdlet in Skype for Business Online per l'impostazione o la visualizzazione dei valori online per _MaxContentStorageMB_ _e MaxUploadFileMB._ Sono disponibili solo per le distribuzioni locali. È importante sapere che il contenuto non verrà caricato in una riunione se il contenuto allegato supera _maxUploadFileSizeMB_ o se viene raggiunto il limite _MaxContentStorageMB._
  
## <a name="to-get-you-started"></a>Per iniziare

## <a name="start-windows-powershell"></a>Avviare Windows PowerShell

> [!NOTE]
> Skype for Business Online Connector fa attualmente parte dell'Teams di PowerShell più recente. Se si usa la versione pubblica più recente Teams PowerShell, non è necessario installare Skype for Business Online Connector.
1. Installare il [modulo Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

Per altre informazioni sull'avvio di Windows PowerShell, vedere Connessione a tutti i servizi Microsoft 365 o Office 365 in un'unica finestra [di Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .
  
## <a name="turning-it-on-or-off"></a>Attivazione o disattivazione del precaricamento

La possibilità di precaricare il contenuto allegato Outlook una convocazione riunione Skype for Business riunioni online è attivata per impostazione predefinita, ma potrebbe essere necessario impedire agli utenti dell'organizzazione di precaricare il contenuto nelle riunioni.
  
> [!IMPORTANT]
> Questa impostazione può essere attivata o disattivata solo per l'intera organizzazione. non è possibile attivarla o disattivarla per un singolo utente. 
  
 **Per disattivarla, aprire Windows PowerShell e procedere come segue:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Se si desidera riattivarla, aprire Windows PowerShell e procedere come segue:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business Online usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando è necessario eseguire più attività. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
